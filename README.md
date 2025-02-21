Teorija:
**Osnovni tipi:**

- **integer** (cela števila)
- **boolean** (logični tip, true/false)
- **string** (nizi)
- **decimal** (double ali float, števila z decimalno vejico)

**Sestavljeni tipi:**

- **array** (polja)
- **object** (objekti)

**Poseben tip:**

- **NULL** (spremenljivke brez vrednosti)

---

### GET in POST metode
![[Pasted image 20250221152857.png]]
Metodi za branje podatkov, ki so posredovani preko obrazca (`<form>`).

- **GET**: Podatki se prenesejo preko URL-ja in so dostopni v globalni spremenljivki `$_GET`.
- **POST**: Podatki se prenesejo preko telesa HTTP zahteve in so dostopni v globalni spremenljivki `$_POST`.

Oba metoda omogočata dostop do podatkov, poslanih z obrazca.

---

### Polja (arrays) v PHP

Polja v PHP omogočajo, da v eni spremenljivki hranimo več vrednosti različnih tipov.

PHP pozna tri vrste polj:

1. **Numerična polja**: Indeksirana z zaporednimi številkami.
    
    php
    
    KopirajUredi
    
    `$arr = [5, 10, 15];`
    
2. **Asociativna polja**: Ključi so lahko nizi ali druge vrste podatkov.
    
    php
    
    KopirajUredi
    
    `$arr = ["ime" => "Janez", "starost" => 30];`
    
3. **Večdimenzijska polja**: Polje, ki vsebuje druge polja.
    
    php
    
    KopirajUredi
    
    `$arr = [     1 => [4.1, 4.2, 4.3],     2 => [5.1, 5.2, 5.3] ];`
    

**Primer izpisa večdimenzijskega polja**:

php

KopirajUredi

`print_r($arr[1]); // Izpiše Array ( [0] => 4.1 [1] => 4.2 [2] => 4.3 )`

**Primer napake**:

php

KopirajUredi

`echo $arr[3]; // Izpiše "nič" (ker ključ 3 ne obstaja)`

### Delo s tabelami

Polja v PHP uporabljajo **array pointer**, ki omogoča "sprehod" po tabeli. To pomeni, da lahko dostopamo do elementov tabele enega za drugim, pri čemer se kazalec premika od začetka proti koncu.

Nekateri uporabni funkcionalnosti za polja:

- `count($array)` – šteje elemente v polju
- `shuffle($array)` – premeša elemente v polju
- `sort($array)` – uredi elemente po vrednosti
- `ksort($array)` – uredi elemente po ključu
- `range(0, 12)` – ustvari polje s številkami od 0 do 12

---

### Preverjanje stanja spremenljivk

- `empty($var)` – preveri, ali je spremenljivka prazna (lahko je `NULL`, `0`, prazen niz, itd.)
- `isset($var)` – preveri, ali je spremenljivka nastavljena (ni `NULL`)
- `var_dump($var)` – izpiše podrobnosti o spremenljivki
- `unset($var)` – uniči spremenljivko (odstrani jo iz pomnilnika)

---

### Piškotki

Za dodajanje piškotkov v PHP uporabljaš funkcijo `setcookie()`.

Primer:

php

KopirajUredi

`setcookie("user", "John Doe", time() + 3600, "/"); // Piškotek bo veljal eno uro`
![[Pasted image 20250221152931.png]]




###Praksa

 Vsak php dokument se začne
 ```php
 <?php
 ?>
```
Izpis nečesa:
```php
echo "<p> zdravo </p>" 
// -> tole je komentar;
ispis spremenljivke v besedilu
$starost = 45;
echo "Janez je star $starost let.";
```
Računanje v  php-ju:
```php
echo 2+2; // izpiše 4 
echo 3*9; // izpiše 27 
echo 42-10; // izpiše 32 
echo 14/3; // izpiše 4.6666666666667
echo 14%3; // izpiše 2 
//PHP ne pozna celoštevilskega deljenja. Lahko ga vsilimo tako: 
echo (int)(14/3); // izpiše 4
// Seštevanhje je izključno matematična operacija 
```
Združevanje nizov:
```php
echo "Hello " . "Janez"; // izpiše Hello Janez 
echo 2 . 3; // izpiše 23 
echo 2.3; // izpiše 2.3
```
Deklaracija Spremenljivk:

```php
$a = 3; // tule bo $a integer  
$a = "Janez"; // tule $a postane string  
$a = 'Janez'; // enako kot zgoraj  
$a = true; // tule boolean  
$a = 5.3504; // in tule decimal  
$a = NULL; // tule pa se $a izprazni
```
Primer vnašanja podatkov 
```php
<form action="prijava.php" method="get tu je lahko namesto geta post">
<input type="text" name="uname"><br />
<input type="password" name="pass"><br />
<input type="submit" value="Prijava"><br />
</form>
```
Primer  branja podatkov:
```php
echo $_GET['uname']; // če je metoda get in imamo v formu input z imenom uname 
echo $_GET['pass'];
echo $_POST['uname']; // če je metoda post in imamo v formu input z imenom uname 
echo $_POST['pass'];
echo $_REQUEST['uname'];//Univerzalna opcija in v  formu input z imenom uname 
echo $_REQUEST['pass'];
+ppt php 2 strani 9-14 so primerti
```


Operatorji:
```php
<?php
// Dodelitev vrednosti
$a = 5; // Dodeli 5 spremenljivki $a

// Aritmetični operatorji
$a += 5; // Dodaj 5 k $a. $a => 10
$a -= 5; // Odštej 5 od $a. $a => 5
$a *= 5; // Pomnoži $a s 5. $a => 25
$a /= 5; // Deli $a s 5. $a => 5
$a %= 5; // Izračunaj ostanek. $a => 0

// Aritmetični operatorji
$result = -$a;  // Negacija
$result = $a + $b; // Seštevanje
$result = $a - $b; // Odštevanje
$result = $a * $b; // Množenje
$result = $a / $b; // Deljenje
$result = $a % $b; // Modulus (ostanek pri deljenju)

// Inkrement / Dekrement
++$a; // Pre-increment: poveča $a za 1, nato vrne $a
$a++; // Post-increment: vrne $a, nato poveča $a za 1
--$a; // Pre-decrement: zmanjša $a za 1, nato vrne $a
$a--; // Post-decrement: vrne $a, nato zmanjša $a za 1

// Primerjalni operatorji
$result = ($a == $b);  // Enako (vrednosti enake, tip se lahko pretvori)
$result = ($a === $b); // Identicno (vrednosti in tipi enaki)
$result = ($a != $b);  // Ni enako
$result = ($a <> $b);  // Ni enako (alternativna sintaksa)
$result = ($a !== $b); // Ni identicno (razlicne vrednosti ali tipi)
$result = ($a < $b);   // Manjše kot
$result = ($a > $b);   // Večje kot
$result = ($a <= $b);  // Manjše ali enako
$result = ($a >= $b);  // Večje ali enako

// Logični operatorji
$result = ($a and $b); // In (obe vrednosti morata biti TRUE)
$result = ($a or $b);  // Ali (vsaj ena vrednost je TRUE)
$result = ($a xor $b); // Ekskluzivni ALI (ena vrednost TRUE, ne obe)
$result = (!$a);       // Negacija (TRUE, če je $a FALSE)
$result = ($a && $b);  // In (enako kot 'and', a z višjo prioriteto)
$result = ($a || $b);  // Ali (enako kot 'or', a z višjo prioriteto)
?>

```
if stavki : 
```php
if ($pogoj) {
    echo "pogoj je true";
}

if ($pogoj) {
    echo "pogoj je true";
} else {
    echo "pogoj je false";
}

// If-else if-else stavek
if ($pogoj1) {
    echo "pogoj1 je true";
} else if ($pogoj2) {
    echo "pogoj2 je true";
} else {
    echo "noben izmed prejšnjih pogojev ni true";
}

PRIMER::
// Pogoj je lahko sestavljen
if ($a > $b && $a > $c) {
    echo "$a je največje";
}

if ($a > $b and $a > $c) {
    echo "$a je največje";
}

if ($a == 5) { // Pravilno! Primerjava vrednosti
    echo "a je enako 5";
}



```
swich case:
```php
switch ($izraz) {
    case "vrednost1":
        echo "ukaz1";
        break;
    case "vrednost2":
        echo "ukaz2";
        break;
    case "vrednost3":
        echo "ukaz3";
        break;
    default:
        echo "ukazDefault";
        break;
}
```

For:
```php
for($i=0; $i<10; $i++) 
{ echo $i; } 

for(;;) { // telo neskončne zanke }
```
While:
```php
$i=0; while ($i<10) 
{ echo $i; $i++; }
while(true) { // telo neskončne while zanke }
```
do While:
```php
$i=0; do 
{ echo $i; $i++; }while($i<10);
do { // telo neskončne do-while zanke
}while(true);
```

Numerična tabela 
```php
Izdelava tabele: $a = array(43,64,38,93,1,57,59,38); 
ali 
$a = array();
$a[0] = 43; 
$a[1] = 64; 
... 
$a[7] = 38;
```
Asociativna tabele:

```php
$dneviVMesecu = array ( "Januar"=>31,
"Februar"=>28, 
"Marec"=>31, 
"April"=>30, 
"Maj"=>31, ...);

echo $dneviVMesecu['Januar']; // izpiše 31
```

Foreach:
```php
	foreach ($tabela as $value)
	 { stavki } 
	 foreach ($tabela as $key => $value)
	  { stavki }
	$petstevil = array(1,2,3,4,5);
	 foreach($petstevil as $stevilo){ 
	 echo "$stevilo  "; 
	 }
	foreach($petstevil as $kljuc=>$stevilo) {
	 echo "$kljuc - $stevilo  ";
	  } 
	  foreach($_GET as $k=>$v) {
	   echo $k . " " . $v; 
	   }
	  
```

Count
```php
$a[0] = 1;
$a[1] = 3;
$a[2] = 5; 
$result = count($a); // $result == 3
```
shuffle:
```php
$tabela = array(1,2,3,4,5);
shuffle($tabela); 
```
sort:
```php
$tabela = array(4,3,1,5,2); 
sort($tabela);
rsort($array) - uredi tabelo v obratnem vrstnem redu 
ksort($array) - uredi asociativno tabelo po ključu
```
range(min, max);
Vrne tabelo s števili med min in max (vključno):
```php
$tabela = range(1, 5); print_r($tabela);
```

```php

// Preveri ali je spremenljivka prazna
// Spodnje vrednosti se smatrajo kot prazne:
// ● "" (an empty string) … empty(“”) vrne true
// ● 0 (0 as an integer) … empty(0) vrne true
// ● 0.0 (0 as a float) … empty(0.0) vrne true
// ● "0" (0 as a string) … empty(“0”) vrne true
// ● NULL
// ● FALSE
// ● array() (an empty array) … empty(array()) … vrne true
// ● $var; (a variable declared, but without a value) …. empty($var) … vrne true

$var = ""; 
if(empty($var)) { 
    echo "Spremenljivka je prazna"; // Izpis: Spremenljivka je prazna
}

// Preveri ali je spremenljivka nastavljena oz. ni NULL
// Spodnje spremenljivke NISO nastavljene:
// $a; … isset($a) … vrne false
// $b = NULL; … isset($b) … vrne false
$a;
if(empty($a)) { 
    echo "Spremenljivka je prazna"; // Izpis: Spremenljivka je prazna
}
if(isset($a)) {
    echo "Spremenljivka je nastavljena"; // Ne bo se izpisalo
}

$b = NULL;
if(empty($b)) {
    echo "Spremenljivka je prazna"; // Izpis: Spremenljivka je prazna
}
if(isset($b)) {
    echo "Spremenljivka je nastavljena"; // Ne bo se izpisalo
}

// empty vs isset primeri
$a = 0;
if(empty($a)) { 
    echo "Spremenljivka je prazna"; // Izpis: Spremenljivka je prazna
}
if(isset($a)) {
    echo "Spremenljivka je nastavljena"; // Izpis: Spremenljivka je nastavljena
}

$a = NULL;
if(empty($a)) { 
    echo "Spremenljivka je prazna"; // Izpis: Spremenljivka je prazna
}
if(isset($a)) {
    echo "Spremenljivka je nastavljena"; // Ne bo se izpisalo
}

$a = "";
if(empty($a)) { 
    echo "Spremenljivka je prazna"; // Izpis: Spremenljivka je prazna
}
if(isset($a)) {
    echo "Spremenljivka je nastavljena"; // Izpis: Spremenljivka je nastavljena
}

$a = array();
if(empty($a)) { 
    echo "Spremenljivka je prazna"; // Izpis: Spremenljivka je prazna
}
if(isset($a)) {
    echo "Spremenljivka je nastavljena"; // Izpis: Spremenljivka je nastavljena
}

$a = false;
if(empty($a)) { 
    echo "Spremenljivka je prazna"; // Izpis: Spremenljivka je prazna
}
if(isset($a)) {
    echo "Spremenljivka je nastavljena"; // Izpis: Spremenljivka je nastavljena
}

// Var_dump - Vrne podatke o spremenljivki
$a = 5;
var_dump($a); // Izpiše: int(5)

$a = "Hello";
var_dump($a); // Izpiše: string(5) "Hello"

$a = true;
var_dump($a); // Izpiše: bool(true)

$a = array(1.3, 2, "3");
var_dump($a); // Izpiše: array(3) { [0]=> float(1.3) [1]=> int(2) [2]=> string(1) "3" }

// Uniči spremenljivko
$a = 5;
unset($a);
if(isset($a)) { 
    echo "Spremenljivka je nastavljena"; // Ne bo se izpisalo
}
if(empty($a)) { 
    echo "Spremenljivka je prazna"; // Izpis: Spremenljivka je prazna
}
var_dump($a); // Izpiše: NULL

// Preverjanje tipa spremenljivke
$isInt = is_int(4); // true
$isIntString = is_int('4'); // false
$isIntFloat = is_int(3.5); // false
$isIntBool = is_int(true); // false

$isNull = is_null($var); // true ali false, odvisno od vrednosti $var

$isDouble = is_double(3); // false
$isDoubleFloat = is_double(3.0); // true
$isDoubleExp = is_double(1e7); // true

$isBool = is_bool(true); // true
$isBoolNum = is_bool(1); // false

$isArray = is_array(array(1, 2)); // true
$isArrayRange = is_array(range(1, 9)); // true

$isNumeric = is_numeric(4); // true
$isNumericString = is_numeric("4"); // true
$isNumericFloat = is_numeric(4.4); // true
$isNumericStr = is_numeric("3.5"); // true
$isNotNumeric = is_numeric("5a"); // false

```


```php
<?php
session_start();
$_SESSION["uporabnik"] = "Marko";
echo $_SESSION["uporabnik"];
?>

<?php
setcookie("uporabnik", "Marko", time() + 3600); // 1 ura
echo $_COOKIE["uporabnik"];
?>

```

```php
<?php
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "moja_baza";

$conn = new mysqli($servername, $username, $password, $dbname);

if ($conn->connect_error) {
    die("Povezava ni uspela: " . $conn->connect_error);
}
?>

```

```php
<?php
$sql = "SELECT * FROM uporabniki";
$result = $conn->query($sql);

if ($result->num_rows > 0) {
    while($row = $result->fetch_assoc()) {
        echo "Ime: " . $row["ime"] . "<br>";
    }
} else {
    echo "Ni rezultatov.";
}
$conn->close();
?>

```
