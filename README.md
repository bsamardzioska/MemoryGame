Memory Game - Семинарска работа по Визуелно програмирање
==========

Опис на проблемот:
==========
<p>
Се работи за игра која им овозможува на лицата да си ги тестираат своите способности за меморирање. Целта на играта е да се погодат две исти квадратчиња т.е. при кликање на нив тие да имаат иста боја. За да биде играта успешно завршена треба да се погодат сите квадратчиња да бидат во иста боја.
<br/>
Опис на играта: <a>http://en.wikipedia.org/wiki/Concentration_(game)</a>
</p>

Интерфејс, функционалности и правила:
==========
<p>
При стартување на апликацијата се појавуваат три менија. Менито File е поставено прво и ви овозможува два избори. Со избирање на New Game се стартува играта со 2 редици и 3 колони. Во второто мени Options можете да изберете Board Size за да се појават квадратчиња според ваш избор. При кликање на втората опција Exit од менито File апликацијата се затвара, додека при избирање на опциите од менито Help се наоѓаат About this Game(link до интернет страна за играта) и Instructions(помош како треба да играте).
</p>

<img src="http://s17.postimg.org/lxdgnqyqn/image.png" />
<img src="http://s22.postimg.org/xu8hluk29/image.png" />
<img src="http://s11.postimg.org/hrs7xu5hv/image.png" />

Програмско решение:
==========
<b>Решението ги содржи следниве функции кои се дел од Form1:</b>

// Funkcija koja se koristi za odbiranje na pozadinska boja za // kvadratite. Funkcijata koristi generator na slucajni broevi // za da opredeli indeks za bojata. Indeksot sluzi za pristap do // poleto colorsList i zemanje na soodvetnata boja od tamu. // Poleto colorsUsed gi sodrzi site boi za inicijalizacija. // Nizata colorUsed sluzi za oznacuvanje koja od boite vo colorsList // e zafatena. Sekoja od boite vo colorsList moze da se javi najmnogu // dvapati na nacrtanite kvadrati.
private Color colorFunc() { int index=0; index=ran.Next(0,x*y/2); while (colorUsed[index] == true) { if (colorUsed[index + (x * y / 2)] == true) index = ran.Next(0, x * y / 2); else { colorUsed[index + (x * y / 2)] = true; return colorsList[index]; } } colorUsed[index] = true; return colorsList[index]; }
//Funkcija koja sluzi za iscrtuvanje na kvadratite. //Sekoj kvadrat e objekt od klasata Button. Prvo se //kreira matrica od kopcinja so odbranite dimenzii (x i y). //Potoa poedinecno se kreira sekoe kopce, se postavuvaat //negovite dimenzii, pocetna pozicija, ime, se dodava //nastan za klikanje na istoto i se postavuvaat vrednostite za progress-bar. //Istovremeno, se odbira bojata koja ke bide povrzana so soodvetniot //kvadrat (kopce), potoa istiot se dodava na panel.
private void CreateTable() { buttons = new Button[x, y]; a = (this.Width / 2) - (x / 2) * 60; b = (this.Height / 2) - (y / 2) * 60;
for (int i = 0; i < x; i++) { for (int j = 0; j < y; j++) { buttons[i, j] = new Button { Height = 50, Width = 50, }; Point p = new Point(a + i * 60, b + j * 60); buttons[i, j].Width = 50; buttons[i, j].Height = 50; buttons[i, j].Location = p; buttons[i, j].Name = "btn" + i.ToString() + j.ToString(); buttons[i, j].Click += Form1_Click;
colors.Add(colorFunc()); panel1.Controls.Add(buttons[i, j]); } } panel1.Controls.Add(GetTimeLabel()); pbTime = new ProgressBar { Height = 30, Width = 50*x + 10*(x-1), }; pbTime.Location = new Point(a, b + y * 60 + 18); pbTime.Minimum = 0; if(boardSize == 0) pbTime.Maximum = 60; else if (boardSize == 1) pbTime.Maximum = 120; else pbTime.Maximum = 300; pbTime.Value = 0; panel1.Controls.Add(pbTime); timer.Stop(); timer.Start(); }
//Funkcija koja sluzi za prikazuvanje na labela so //soodvetniot broj na izbrani kvadrati na formata //Za najmala, sredna i golema tabla soodvetno se //postaveni vrednostite 0, 1 i 2.
private Label GetBoardSizeLabel() { Label lblBoardSize = new Label(); lblBoardSize.Location = new Point(a - 4, b - 25); lblBoardSize.Width = 200; string boardSizeStr = string.Empty; if (boardSize == 0) boardSizeStr += "2 x 3"; else if (boardSize == 1) boardSizeStr += "6 x 6"; else boardSizeStr += "8 x 9"; lblBoardSize.Text = "Големина на табла: " + boardSizeStr; lblBoardSize.Font = new Font("Calibri", 12); return lblBoardSize; }
//Funkcija koja se koristi za postavuvanje na labela nad //preostanatoto vreme za igranje, na soodvetna pozicija.
private Label GetTimeLabel() { Label timeLabel = new Label(); timeLabel.Text = "Преостанато време:"; timeLabel.Width = 200; timeLabel.Location = new Point(a - 2, b + y * 60 - 5); timeLabel.Font = new Font("Calibri", 9); return timeLabel; }

