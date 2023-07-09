# Begreber

| **Begreb**              | **Evt. mit ord**     | **Betydning**                                                                                                                                                                                                    |
| ----------------------- | -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Class/Klasse            | Class                | En klasse der definerer noget der kan have flere forskellige variable eller metoder. Eksempel: [[#Class]]                                                                                                        |
| Object/Objekt           | Object               | En instans af en klasse, denne har allerede fået tildelt eventuelle variable (værdier)                                                                                                                           |
| Method/metode           | Function             | En metode er tildelt en klasse, metoden definerer hvad man kan gøre med en instans af den klasse.                                                                                                                |
| Parameter               | Variable             | En parameter skal tildeles hvis en metode har brug for mere info, sættes ind i parantes når man kalder en metode.                                                                                                |
| State                   | Values               | De værdier et object har fået tildelt.                                                                                                                                                                           |
| Compiler                | Compiler             | En compiler laver source coden om til kode computeren kan forstå. Eksempelvis: Java bliver compilet til C++, som kan forstås af styresystemet, som compiler sin kode til Assembly, som kan forstås af hardwaren. |
| Result                  | Return result        | En metode kan returnere et resultat af en datatype, eksempelvis en String, hvis ikke den returnerer et resultat, er metoden en "void".                                                                           |
| Feltvariabler/fields    | Variable             | Variabler der tilhører en klasse.                                                                                                                                                                                |
| Konstruktør/Constructor | Constructor          | Den metode der bliver udført, når man laver en klasse første gang.                                                                                                                                               |
| Access modifyer         | null                 | Public/private.                                                                                                                                                                                                  |
| Getter/Access metode    | Getter               | En metode i en klasse, der bruges til at tilgå variable i en klasse.                                                                                                                                             |
| Mutator metode          | Mutator              | En metode i en klasse, der bruges til at ændre variable i en klasse.                                                                                                                                             |
| Signatur                | null                 | Signatur er metodens navn + type.                                                                                                                                                                                |
| Primitiv type           | int, double, boolean | Typer der starter med lille bogstav. Disse typer bliver lagret direkte i obejktet.                                                                                                                               |
| Klasse type             | String, klasser      | Typer der starter med stort bogstav. Disse typer er objekter for sig selv, som man peger på.                                                                                                                     |
| Konkatenering           | null                 | Sætte tekststringe sammen, fx. når man laver println.                                                                                                                                                            |
| Parameterliste          | Variables            | Listen af parametre der skal bruge til at udføre en metode.                                                                                                                                                      |
| Garbage collection      | Garbage collection   | Når objekter ikke bruges mere slettes de fra hukommelsen, dette kaldes garbage collection.                                                                                                                       |
| Keywords                | null                 | Ord der er reserveret til en specifik ting, fx. "for".                                                                                                                                                           |
| Overloaded              | null                 | Hvis en operator kan bruges til flere forskellige ting, er den overloaded. Eks. + er overloaded, da den kan lægge tal sammen og strings sammen.                                                                  |
| Stærkt type check       | Strongly typed       | Hvis der bliver checket for typefejl før koden bliver kørt.                                                                                                                                                      |
| Klasse variabler        | Global variable      | Variabler der har den samme værdi, på tværs af alle objekter af samme klasse.                                                                                                                                    |
| Klasse metoder          | Global function      | Metoder der kan bruges på tværs af alle objekter af samme klasse.                                                                                                                                                |
| Modularization          | Modularization       | At dele store komplekse problemer op i små mindre komplekse problemer.                                                                                                                                           |
| Abstraction             | Abstraction          | At ignorere detaljerne for at fokusere på det større billede.                                                                                                                                                    |
| ArrayList               | Array/List           | En liste/samling af objekter. [[#ArrayList]].                                                                                                                                                                    |
| Forfremmelse            | Convertion           | Bruge variabler på tværs af typer. Forfremmelse gør typens bitstørrelse større.                                                                                                                                  |
| Begrænsning             | Convertion           | Bruge variabler på tværs af typer. Begrænsning gør typens bitstørrelse mindre.                                                                                                                                   |
| Immutable               | Immutable            | Optimering af gentagelser i variable, to variable af samme værdi vil få samme plads i RAM.                                                                                                                       |
|                         |                      |                                                                                                                                                                                                                  |


# Datatyper

| Type    | Betydning                        | Primitiv/klasse |
| ------- | -------------------------------- | --------------- |
| int     | Integer/tæller, hele tal.        | Primitiv        |
| String  | Tekststring, indkapsuleret i "". | Klasse          |
| boolean | True/false.                      | Primitiv        |
| double  | Reelle tal, kommatal.            | Primitiv        |
|         |                                  |                 |


# Udtryk og operatorer
| **Udrtyk/operator**           | **Brug**                                 | **Betydning**                                                                                                     |
| ----------------------------- | ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Assignment                    | `v = exp;`                               | Man tildeler/ændrer en variabels værdi.                                                                           |
| Return                        | `return exp;`                            | Man returnerer en værdi, bruges ofte i metoder.                                                                   |
| Metodekald (internt)          | `method(...);`                           | Man kalder en metode i samme objekt.                                                                              |
| Metodekald (eksternt)         | `object-reference.method(...);`          | Man kalder en metod i et andet objekt.                                                                            |
| Blok                          | `{s1;}`                                  | En kodeblok.                                                                                                      |
| Selektion (if)                | `if (amount > 0) {} else {}`             | En blok der kun udføres hvis udtrykket i parantes er true.                                                        |
| Indlejret selektion           | `if (day > 30) {if (month > 12) {}}`     | En selektionsblok der sidder i en anden selektionsblok.                                                           |
| Selektion mellem mange        | `switch(day) {case 1: return "monday";}` | En switch sætning giver muligheden for at have mange cases.                                                       |
| Selektion i udtryk            | `exp ? exp1 : exp2;`                     | Hvis man giver et udtryk som er true vil den vælge den første, hvis ikke den anden.                               |
| Negerings operator            | `if (!isFemale)`                         | Tjekker om noget er false.                                                                                        |
| Iteration - [[#for loop]]     | `for (declare; test; update) {}`         | Kører koden i blokken så længe test er true.                                                                      |
| While løkke - [[#while loop]] | `while (test) {}`                        | Kører koden i blokken så længe test er true, men ændrer ikke nogen værdier automatisk.                            |
| Do-while løkke                | `do {} while(test);`                     | Kører koden i blokken så længe test er true, men kører koden før den tester.                                      |
| Konstant                      | `69`                                     | En konstant er noget der ikke ændrer sig efter den er assignet.                                                   |
| Aritmetiske op                | `+, -, *, /, %`                          | Ligger to udtryk sammen.                                                                                          |
| Logiske op                    | `&&, !`                                  | Udvider udtryk.                                                                                                   |
| Relationelle op               | `==, !=, <, >, <=, >=`                   | Sammenligner udtryk.                                                                                              |
| New                           | `new Class(...);`                        | New er også en operator.                                                                                          |
| Keywords                      | `class, new, public, if, for, while...`  | Ord som er reserverede.                                                                                           |
| Navne (identifiers)           | `int, boolean, double...`                | Ord som definerer en type.                                                                                        |
| Konstanter (literals)         | `"Aarhus Universitet", 69, 4.20`         | Værdier som ikke kan ændre sig.                                                                                   |
| Specialtegn                   | `;, (), [], {}...`                       | Tegn der bruges i koden.                                                                                          |
| Stort CamelCase               | `CamelCase`                              | Bruges til klasser.                                                                                               |
| Lille camelCase               | `camelCase`                              | Bruges til variabler og metodenavne.                                                                              |
| Static                        | `public static void...`                  | Bruges til at lave klassevariable og klassemetoder (gøre så det kan bruges på tværs af objekter af samme klasse). |
| Type cast (begrænsning)                     | `(type)`                                 | Bruges til at lave en type om til en anden, eksempelvis double til int.                                           |
|                    |                                          |                                                                                                                   |


# Kode eksempler

## Class
```java
public class Person {
	//Feltvariable/fields
	private String name;
	private int age;

	//Constructor/konstruktør
	public Person(String n, int a) { //Parameterlisten er defineret i parantes.
		name = n;
		age = a;
	}

	//Getter/Access metode.
	public getName() {
		return name;
	}

	//Mutator metode.
	public changeName(String newName) {
		name = newName;
	}
}
```

## For loop
```java
for (int i = 0; /*Erklæring/declaration*/ i < 10; /*Test*/ i++ /*Opdatering/upadte*/) {
	doSomething(); //Body
}
```

## While loop
```java
while (isTrue /*Test*/) {
	doSomething(); //Body
}
```

## Turtle class
```java
public class Turtle {
	public Turtle() {}

	public void polygon(double size, int n) {
		if (n !> 2) System.out.println("n must be >= 3"); return;
		for (int i = 0; i < n; i++) {
			move(size);
			turn(360.0 / n);
		}
	}

	public void square(double size) {
		polygon(4, size);
	}

	public void circle(double radius) {
		polygon(100, 2 * radius * Math.PI / 100);
	}
}
```

## ArrayList
```java
import java.util.ArrayList;
public class AddressBook {
	private ArrayList<Person> persons;
	...
	public AdressBook(...) {
		persons = new ArrayList<>();
		...
	}

	public void addPerson(Person p) {
		persons.add(p);
	}
}
```

## For each
```java
for (String track : tracks) {
	...
}
```

## Sorting

### Comparable
```java
public class Sorting implements Comparable<Sorting> {
	String string;
	int number;
	...

	public int compareTo(Sorting s) {
		if (this.number != s.number) {
			return this.number - s.number;
		}
		return this.string.compareTo(s.string);
	}
}
```

### Comparator
```java
public class ByString implements Comparator<Sorting> {
	public int compare(Sorting s1, Sorting s2) {
		return s1.getString().compareTo(s2.getString());
	}
}

...
//Using comparator
public sortByString() {
	return sortings.sort(new ByString());
}
```
