﻿<h1>2048 - 3 in 1</h1>
<p></p>


<h2>Опис на проблемот</h2>

<p>Нашата апликација е познатата игра 2048. Притоа покрај нејзината веќе позната варијанта, во нашата апликација ги вклучивме игрите Фибоначи, каде што броевите се генерираат според низата на Фибоначи, почнувајќи од бројот еден и Troll 2048, којашто насоката на придвижување на броевите ја бира по случаен избор.</p>
<p>Апликацијата е наменета да служи како забава на корисникот.</p>




<h2>Упатство за користење</h2>

<p>При стартување на апликацијата, ни се отвара почетниот прозорец.  Во textbox компонентата покрај лабелата Name, можете да го внесете вашето име, доколку сакате истото да се зачува во листата со најдобри резултати, во спротивно играта ве регистрира како User. Понатаму можете да си изберете игра од понудените три која сакате да ја играте. Во зависност од тоа која игра сакате да ја играте кликнувате на соодветното копче. Co кликнување на копчето High Scores ни се отвара нова форма која ни ги прикажува десетте најдобри резултати кои биле зачувани.</p>




<h2>Правила на играње</h2>

<p>Сите три игри се играат на исти начин со користење на стрелките на тастатурата. Во зависност од која стрелка е притисната на тој начин се придвижуваат генерираните бројки до последното слободно поле во таа насока.</p>

<h3>Game 2048</h3>
<p>Целта на оваа игра е во едно од полињата да се добие бројот 2048. Најпрво во две полиња, избрани по случаен избор ни се генерираат два од броевите два и четири, притоа двојка се генерира со веројатност 90%, а четворката со 10% веројатност. Понатаму со секое притискање на стрелките од тастатурата, играта ни генерира уште една двојка во празните полиња. Доколку во насоката во која сме притиснале да се движиме има соседни полиња со исти броеви, истите се спојуваат во едно со вредност двојно поголема. Играта завршува кога во едно поле ќе се добие бројот 2048 или кога ќе ги исполните сите полиња со броеви така што во ниедна насока нема соседни полиња со иста вредност. Кога завршува играта се појавува МеssageBox со соодветната порака во зависност од начинот на кој ви завршува играта. Доколку притиснете ОК, ве враќа на почетниот прозорец, со притискање на Cancel останувате на истата игра. Со враќање на почетниот прозероц, вашите најдобри резултати се зачувуваат во датотеката high.bin. Во полето score ви се пресметуваат постигнатите поени од играта што моментално ја играте, а во Best Score, најдобрите поени што сте ги постигнале од било која игра од моментот од кога сте го отвориле овој прозорец. Со притискање на New game, започнувате нова игра од овој тип.</p>

<h3>Troll 2048</h3>
<p>Оваа игра, е иста како претходната, играта 2048, со таа разлика што без разлика која стрелка да ја претиснеш, играта сама ти генерира насока по случаен избор и според истата ги придвижува соодветните полиња.</p>

<h3>Fibonacci</h3>
<p>Во оваа игра најпрво се генерираат две единици и спојувањето на броевите се одвива според низата на Фибоначи, т.е. кога во избраната насока ќе се појават соседни полиња коишто претставуваат два последователни члена од низата на Фибоначи, истите се спојуваат во едно и неговата вредност е членот од низата што следи после тие два члена. Овде играта завршува кога во некое поле ќе се појави бројот 6765 или кога ќе нема повеќе потези.</p>



<h2>Решението на проблемот</h2>

<h3>Number</h3>
<p>Во оваа класа се чуваат статички променливи од тип Color, коишто ја чуваат бојата за секој број. Во промеливата Color се зачувува една од претходните дефинирани бои, во зависност од тоа кој број е генериран. Во оваа класа се чуваат и променливите index (индексот на бројот во низата броеви од играта) , Value (кој број е генериран) и Fresh – дали да има посебен ефект.</p>

<h3>Game</h3>
<p>Податоците за играта ги чуваме во апстрактната класата Game. Притоа ја чуваме низата (sequence) од која ги влечеме потребните броеви како низа од броеви, чуваме матрица со димензии 4х4 (board) со податоци од класата Number и во променливата score го чуваме потребниот резултат. Методите во оваа класа CanShift и Shift се апстрактни и се имплементираат во класите Game2048 и GameFibonacci, кои ја наследуваат оваа класа и ги претставуваат веќе спомнатите игри. Методот CanShift, проверува дали играта има уште потези. Додека пак методот Shift(direction) ги поместува броевите во дефинираната насока (direction).  Покрај овие методи постојат и методите isFull(), кој проверува дали цела матрица ни е исполнета со броеви, методот makeStale(), која што го иницијализира полето Fresh на false, за секое непразно поле од матрицата, методот generateNumber(), којшто го генерира бројот два со веројатност од 90% или бројот 4, во поле по случаен избор.</p>

<h3>Game2048 и GameFibonacci</h3>
<p>Овие две класи наследуваат од класата Game и ги имплементираат апстрактните методи CanShift и Shift, според тоа каква игра претставуваат и на кој начин се одвива спојувањето на броевите. Во Shift методот исто така се пресметува и резултатот на играчот.</p>

<h3>HighScores</h3>
<p>Во оваа класа се чува името на играчот (Name), неговиот најдобар резултат (Score) и од која игра е добиен тој резултат (Game). Податоците од оваа класа се сериализабилни, т.е. и по исклучување на апликацијата, тие продолжуваат да се чуваат во датотеката high.bin.</p>
<p>Кога се вклучува играта прв пат на некој компјутер се креира оваа датотека, потоа со секое играње на играта и ново вклучување, резултатите се чуваат во неа, а во копчето High Scores на почетниот прозорец се печатат само десетте најдобри, сортирани по опаѓачки редослед според постигнатиот резултат.</p>

<p>Покрај набројаните, во нашата апликација користиме и два тајмери. Со помош на тајмерот timer го извршуваме движењето на броевите во саканата насока, а со помош на тајмерот popOutTimer го постигнуваме дополнителниот ефект при генерирање ново поле или при спојување на две полиња во едно.</p>


<p></p>
<h3>Изработиле</h3>
<p>Ивона Лазаровска 116017
<p>Благоја Евкоски 111070
<p>Ана Атанасова 116001
