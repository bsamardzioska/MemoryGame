Memory Game - Семинарска работа по Визуелно програмирање
==========

1. Опис на проблемот:
==========
<p>
Се работи за игра која им овозможува на лицата да си ги тестираат своите способности за меморирање. Целта на играта е да се погодат две исти квадратчиња т.е. при кликање на нив тие да имаат иста боја. За да биде играта успешно завршена треба да се погодат сите квадратчиња да бидат во иста боја.
<br/>
Опис на играта: <a>http://en.wikipedia.org/wiki/Concentration_(game)</a>
</p>

2. Интерфејс, функционалности и правила:
==========
<p>
При стартување на апликацијата се појавуваат три менија. Менито File е поставено прво и ви овозможува два избори. Со избирање на New Game се стартува играта со 2 редици и 3 колони. Во второто мени Options можете да изберете Board Size за да се појават квадратчиња според ваш избор. При кликање на втората опција Exit од менито File апликацијата се затвара, додека при избирање на опциите од менито Help се наоѓаат About this Game(link до интернет страна за играта) и Instructions(помош како треба да играте).
</p>

<img src="http://s17.postimg.org/lxdgnqyqn/image.png" />
<img src="http://s22.postimg.org/xu8hluk29/image.png" />
<img src="http://s11.postimg.org/hrs7xu5hv/image.png" />

3. Програмско решение:
==========
<b>Решението ги содржи следниве функции кои се дел од Form1:</b><br/>
// Funkcija koja se koristi za odbiranje na pozadinska boja za <br/>
// kvadratite. Funkcijata koristi generator na slucajni broevi <br/>
// za da opredeli indeks za bojata. Indeksot sluzi za pristap do <br/>
// poleto colorsList i zemanje na soodvetnata boja od tamu. <br/>
// Poleto colorsUsed gi sodrzi site boi za inicijalizacija. <br/>
// Nizata colorUsed sluzi za oznacuvanje koja od boite vo colorsList <br/>
// e zafatena. Sekoja od boite vo colorsList moze da se javi najmnogu <br/>
// dvapati na nacrtanite kvadrati.<br/>
<b>private Color colorFunc()</b>

//Funkcija koja sluzi za iscrtuvanje na kvadratite. <br/>
//Sekoj kvadrat e objekt od klasata Button. Prvo se <br/>
//kreira matrica od kopcinja so odbranite dimenzii (x i y). <br/>
//Potoa poedinecno se kreira sekoe kopce, se postavuvaat <br/>
//negovite dimenzii, pocetna pozicija, ime, se dodava <br/>
//nastan za klikanje na istoto i se postavuvaat vrednostite za progress-bar. <br/>
//Istovremeno, se odbira bojata koja ke bide povrzana so soodvetniot <br/>
//kvadrat (kopce), potoa istiot se dodava na panel.<br/>
<b>private void CreateTable()</b>

//Funkcija koja sluzi za prikazuvanje na labela so <br/>
//soodvetniot broj na izbrani kvadrati na formata <br/>
//Za najmala, sredna i golema tabla soodvetno se <br/>
//postaveni vrednostite 0, 1 i 2.<br/>
<b>private Label GetBoardSizeLabel()</b>

//Funkcija koja se koristi za postavuvanje na labela nad <br/>
//preostanatoto vreme za igranje, na soodvetna pozicija.<br/>
<b>private Label GetTimeLabel()</b>

<br/>
<img src="http://s9.postimg.org/8afavp6bj/image.png" />
<br/><b><i>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Приказ при избор на 6x6 квадрати од менито Options</i></b>
