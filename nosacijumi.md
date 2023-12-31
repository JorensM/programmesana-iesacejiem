# Nosacījumi

Iepriekšējā nodaļā iemācijāmies par programmēšanas pamatvienību - mainīgajiem.

Līdz šim esam mācijušies tikai kā rakstīt deterministiskas programmas - jeb programmas kuras nemainās, un katru reizi veic tās pašas darbības, tik ilgi kamēr kods nav mainījies. Bet parasti programmas nav tik vienkāršas - tās mainās atkarībā no apstākļiem un lietotāja ievadi (par ievadi mācīsimies nākošajā nodaļā).

Šajā nodaļā mēs mācīsimies par nosacījumiem, jeb conditionals. **Nosacījumi** tas ir veids kā var ļaut programmas darbībai mainīties atkarībā no kāda apstākļa, piemēram mainīgā vērtības

Nosacījumi seko šādai sintaksei:

```
if (expression) {
    //Darbība ja 'expression' vērtība ir patiesa
} else {
    //Darbība ja 'expression' vērtība nav patiesa
}
```

> 'expression' no angļu valodas nozīmē 'izteiksme'

> Drošivien ievērojāt divas jaunas zīmes `{` un `}` - **figūriekavas** jeb **curly braces**. Tās izmanto lai apzīmētu kādu nodalītu kodu daļu jeb koda bloku. Bez izmantošanas nosacījumos, tās vēl izmanto funkciju, klašu, objektu un ciklu definēšanā (par šiem jēdzieneim turpmākajās nodaļās)

Piemēram, varam izvedot mainīgo, un pārbaudīt vai tā vērtība atbilst kādai vērtībai

```
let mainigais = 10;

if (mainigais == 5) {
    console.log('Mainīgais ir vienāds ar 5')
} else {
    console.log('Mainīgais nav vienāds ar 5') //Izvada tikai šo tekstu
}
```

Izanalizēsim šo kodu.

Vispirms mēs definējam mainīgo `mainigais` ar vērtību 10. 

```
let mainigais = 10
```

Tālāk mēs pārbaudām vai tā vērtība ir vienāda ar 5.Ja nosacījums ir patiess(jeb mainigā vērtība ir 5), tad viss kas ir starp `{` un `}` zīmēm tiek palaists kā parasts kods. Takā mūsu gadījumā nosacījums ir nepatiess, tad šis kods tiek izlaists un nākošais tiek lasīsts.

```
if (mainigais == 5) {
    console.log('Mainīgais ir vienāds ar 5') // Kods netiek palaists
}
```

Tālāk mēs nosakām kam būtu jānotiek, ja nosacījums nebija patiess. Takā mūsu nosacījums nebija patiess, tad šis kods tiek palaists

```
else {
    console.log('Mainīgais nav vienāds ar 5') // Kods tiek palaists
}
```

Varat izmainīt mainīgā vērtību no 10 un 5, un redzēsiet ka tiek palaists `if` koda bloks, nevis `else` bloks.

'If' ir angļu vārds kurš nozīmē 'ja', un 'else' nozīmē 'citādāk'. Tādad šajā kodā mēs esam uzrakstījuši 'Ja mainigā vērtība ir 5, tad izvadīt šadu tekstu. Citādāk izvadīt citu tekstu'

Var arī rakstīt nosacījumu bez `else`, bet tikai ar `if` - tad kods tiks palaists ja `if` nosacījums bija patiess, bet nekas konkrēts netiks izdarīts ja tas nebija patiess, un programma turpinās savu darbību.

Ievērojiet, ka mēs uzrakstījām `==` nevis `=`. `=` nozīmē ka mēs pievienojam vērtību, bet `==` nozīmē ka mēs pārbaudam vērtību. Ir svarīgi šo iegaumēt, citādāk mums bieži sanāks nejauši uzrakstīt `=` kas novedīs pie 'bagiem'

Bez `==` simbola, pastāv vēl vairāki citi simboli lai pārbaudītu vērtību. 

 * `==` - Vienāds ar
 * `!=` - Nav vienāds ar
 * `>`  - Ir augstāks par
 * `<`  - Ir zemāks par
 * `>=` - Ir augstāks par vai vienāds ar
 * `<=` - Ir zemāks par vai vienāds ar

Piemēram, mēs varam pārbaudīt vai skaitļa vērtība ir augstāka par 10:

```
let skaitlis1 = 5
let skaitlis2 = 20

if (skaitlis1 > 10) {
    console.log('skaitlis1 ir augstāks par 10')
}

if (skaitlis2 > 10) {
    console.log('skaitlis2 ir augstāks par 10')
}
```

Šajā gadījuma pirmais koda bloks netiks palaists, jo tā nosacījums ir nepatiess, bet otrais - tiks, jo tā nosacījums ir patiess

Varat nomainīt `skaitlis1` vērtību uz kādu skaitli kas ir augstāks par 10, un tad redzēsiet ka attiecīgais koda bloks tiek palaists.

## Else if

Bez `if` un `else` pastāv vēl `else if`. Ar `else if` var izveidot vēlvienu vai vairākus nosacījumus kuri seko iepriekšējam nosacījumam

```
let skaitlis = 20

if (skaitlis == 10) {
    console.log('Skaitlis ir vienāds ar 10')
} else if (skaitlis == 20) {
    console.log('Skaitlis ir vienāds ar 20') // Tikai šis kods tiks palaists
} else {
    console.log('Skaitlis nav vienāds ne ar 10 ne ar 20')
}
```

Šajā kodā mēs vispirs ar `if` pārbaudam vai skaitlis ir vienāds ar 10. Takā skailtis nav vienāds ar 10, programma izlaiž šo koda bloku un lasa nākošo, jeb `else if`. Programma pārbauda vai `else if` nosacījums ir patiess, un takā tas ir, tad palaiž šo koda bloku. Takā iepriekšējais nosacījums bija patiess, tad nākošais (`else`) tiek izlaists.

Ja pirmais nosacījums (`if`) būtu bijis patiess, tad gan `else if` gan `else` tiktu izlaisti. Ja pirmie divi nosacījumi būtu bijuši nepatiesi, tad `else` tiktu palaists

`else if` var arī ķēdēt, jeb rakstīt vairākus `else if`, vienu pēc otra, piemēram

let skailtis = 20

if (skaitlis == 15) {
    console.log('Skaitlis ir vienāds ar 15')
} else if (skaitlis > 50) {
    console.log('Skaitlis ir augstāks par 50')
} else if (skaitlis > 10) {
    console.log('Skaitlis ir augstāks par 10, be ne augstāks par 50, un nav vienāds ar 15') // Šis bloks tiks palaists
} else {
    console.log('Skaitlis nav augstāks par 50')
}

Šajā gadījumā pirmie divi nosacījumi tiks izlaisti jo nav patiesi, bet trešais tiks palaists jo ir patiess, un pēdējais tiks izlaists jo tas tiek palaists tikai ja visi iepriekšējie nav patiesi.

Pamēģiniet nomainīt `skaitlis` uz 15 un palaist kodu. Tad tikai pirmais bloks tiks palaists, jo tā nosacījums būs patiess. Respektīvi, visi pārējie bloki tiks izlaisti.

## Citi vērtību tipi


Nosacījumos var lietot ne tikai skaitļus, bet arī tekstu un `patiess`/`nepatiess`. Bet ar šiem vērtību tipiem var lietot tikai `==` (vienāds ar) un `!=` (nav vienāds ar) salīdzinājuma zīmēm

### Teksts

```
let mainigais = "Teksts"

if(mainigais != "Teksts") {
    console.log("Mainīgais nav vienāds ar 'teksts'")
} else {
    console.log("Mainīgais ir vienāds ar 'teksts'") // Šis kods tiks palaists
}
```

### `patiess`/`nepatiess`

Iespējams no iepriekšējās nodaļas par mainīgajiem, atceraties ka runājām nedaudz par vērtību tipu `boolean` jeb `patiess`/`nepatiess`. `boolean` tas ir vērtību tips, kurš var pastāvēt kā viena no divām vērtībām - vai nu `true`, jeb `patiess`, vai nu `false`, jeb nepatiess.

```
let mainigais = true
let cits_mainigais = false
```

Šādu vērtību tipu arī var lietot nosacījumos.

```
if (mainigais == true) {
    console.log('Mainīgais ir patiess')
} else {
    console.log('Mainīgais ir nepatiess')
}
```

## Aritmētika

tāpat kā mainīgo definīcijā, arī nosacījumos drīkst lietot aritmētiku.

```
let skaitlis1 = 2
let skaitlis2 = 2

if(skaitlis1 + skaitlis2 == 4) {
    console.log('Skaitļu summa ir 4') // Šis bloks tiks palaists
} else {
    console.log('Skaitļu summa nav 4')
}
```

## &&

Vienā nosacījumā ir iespējams iekļaut vairākas izteiksmes ar `&&` jeb AND (un) simbolu. Nosacījums būs patiess ja visas izteiksmes kuras lieto `&&` ir patiesas

```
let skaitlis = 10
if (skaitlis > 5 && skaitlis < 15) {
    console.log('Skaitlis ir augstāks par 5 un zemāks par 15') // Šhis bloks tiks palaists
} else {
    console.log('Skaitlis nav augstāks par 5 un nav zemāks par 15')
}
```

Ja viena no izteiksmēm kura lieto `&&` ir nepatiesa, tad nosacījums ir nepatiess un tiek izlaists. Piemēram

```
let skaitlis = 10
if (skaitlis > 5 && skaitlis == 15) {
    console.log('Skaitlis ir augstāks par 5 un vienāds ar 15') // Netiks palaists
} else {
    console.log('Skaitlis nav augstāks par 5 vai nav vienāds 15') //Tiks palaists
}
```

Šajā gadījumā nosacījums ir nepatiess, jo viena no `&&` izteiksmēm ir bijusi nepatiesa. Ir iespējams arī ķēdēt šīs izteiksmes ar vairāk nekā vienu `&&`, piemēram:

```
if ( n > 5 && n < 50 && n != 15)
```

Šajā gadījumā nosacījums ir patiess ja `n` ir augstāks par 5 UN ir zemāks par 50 un nav vienāds ar 15

> Līdz šim nebijām lietojuši mainīgo kura nosaukums ir tikai viens burts. Šāds nosaukums ir pilnīgi derīgs un to drīkst lietot kā mainīgā nosakumumu. Bet ir rekomendēts mainīgo nosaukumos lietot pilnus vārdus kuri konkrēti raksturo šī mainīgā nozīmi un pielietojumu.

`&&` simbolu var lasīt kā "un", 

```
if (skaitlis > 5 un skaitlis < 15)
```

## ||

Pastāv vēlviens simbols `||` jeb OR (vai)

Kad lieto `||` simbolu tad tikai tai izteiksmei kura lieto šo simbolu ir jābūt patiesai, un visas pārējās var būt nepatiesas. Piemēram

```
let skailtis = 40

if (skaitlis < 20 || skaitlis == 40) {
    console.log('Skaitlis ir vai nu zemāks par 20 un augstāks par 10, vai nu tas ir vienāds ar 40') // Tiks palaists
}
```

Ja mēs izmainītu `skaitlis` vērtību uz 10, tad nosacījums arī būtu patiess, bet ja izmainītu uz vērtību kā piemēram 25 vai 50, tad nosacījums nebūtu patiess

`||` var lasīt kā "vai":

```
if (skaitlis < 20 un skaitlis > 10 vai skaitlis == 40)
```

Var lietot gan `&&` gan `||` kopā, piemēram

```
let skailtis = 40

if (skaitlis < 20 && skaitlis > 10 || skaitlis == 40) {
    console.log('Skaitlis ir vai nu zemāks par 20 un augstāks par 10, vai nu tas ir vienāds ar 40') // Tiks palaists
}
```

## Iestaprināšana

Nosacījumus var ievietot vienu otrā. To sauc par **nesting** jeb **iestaprināšanu**

```
let skaitlis = 10;

if(skailtis > 0) {
    console.log('skaitlis ir pozitīvs un')
    if(skaitlis > 50) {
        console.log('tas ir lielāks par 50')
    } else {
        console.log('tas ir mazāks par 50')
    }
} else {
    console.log('skaitlis ir negatīvs')
}
```

Šajā kodā, mēs vispirms pārbaudam vai skaitlis ir lielāks par 0. Takā tas ir, tad mēs vēl pārbaudam vai tas ir lielāks par 50. Ja skaitlis būtu bijis mazāks par 0, tad šis nosacījums:

```
if(skaitlis > 50) {
    //...
} else {
    //...
}
```

Netiktu pat pārbaudīts.

## Noslēgums

Šajā nodaļā iemācijāmies par vēlvienu svarīgu programmēšanas aspektu - nosacījumiem un salīdzināšanu. Nosacījumi, tāpat kā mainīgie, ir ļoti svarīgs programmēšanas pamataspekts un tiek bieži ļoti bieži lietots kad raksta kodu.

Nākošajā nodaļā mācīsimies par ievadi - varēsim uzrakstīt programmu kura veic noteiktas darbības atkarībā no lietotāja ievades


## Jautājumi

3.1: Vienkāršos vārdos, kas ir nosacījumi?

A: Nosacījumi ir koda bloki, kuri tiek palaists atkarībā no tā vai kāda izteiksme ir patiesa vai nepatiesa

3.2: Kāds teksts tiks izvadīts konsolē palaižot doto kodu?
```
let skaitlis = 10

if(skaitlis == 15) {
    console.log('1')
} else {
    console.log('2')
}
```

A: 2

3.3: Kāds teksts tiks izvadīts konsolē palaižot doto kodu?
```
let skaitlis = 16

if(skaitlis > 20 && skaitlis < 15) {
    console.log('1')
} else {
    console.log('2')
}
```

A: 1

3.4: Kāds teksts tiks izvadīts konsolē palaižot doto kodu?
```
let skaitlis = 20

if(skaitlis == 15 || skailtis == 20) {
    console.log('1')
} else {
    console.log('2')
}
```

A: 1

3.4: Kāds teksts tiks izvadīts konsolē palaižot doto kodu?
```
let skaitlis = 20

if(skaitlis == 15) {
    console.log('1')
} else if (skaitlis == 20) {
    console.log('2')
} else {
    console.log('3')
}
```

A: 1

3.5: Kāds teksts tiks izvadīts konsolē palaižot doto kodu?
```
let skaitlis = false

if(skaitlis == true) {
    console.log('1')
} else {
    console.log('2')
}
```

A: 2

## Uzdevumi

3.1: Uzrakstiet programmu, kura definē mainīgo `abc` ar vērtību "Teksts", un tad ar nosacījumu pārbauda, vai mainīgā vērtība ir vienāda ar "Teksts", un izvada konsolē tekstu "1", ja nosacījumus ir patiess, un "2", ja nosacījums nav patiess.

```
let abc = "Teksts"

if(abc == "Teksts") {
    console.log('1')
} else {
    console.log('2')
}
```

3.2: Uzrakstiet programmu, kura definē mainīgo ar jebkādu skaitlisko vērtību, un tad izvada tekstu atkarībā no šādiem nosacījumiem(kur X ir mainīgā vērtība):
    1. Ja skaitlis ir lielāks par 20, izvada "Skaitlis X ir lielāks par 20"
    2. Ja skaitlis ir mazāks par 20, izvada "Skaitlis X ir mazāks par 20"
    3. Citādāk izvada "Skaitlis X ir vienāds ar 20"
```
let skaitlis = 15

if (skaitlis > 20) {
    console.log("Skaitlis " + skaitlis + " ir lielāks par 20")
} else if (skaitlis < 20) {
    console.log("Skaitlis " + skaitlis + " ir mazāks par 20")
} else {
    console.log("Skaitlis " + skaitlis + " ir vienāds ar 20")
}
```