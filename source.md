<section id="themes">
	<h2>Themes</h2>
		<p>
			Set your presentation theme: <br>
			<!-- Hacks to swap themes after the page has loaded. Not flexible and only intended for the reveal.js demo deck. -->
                        <a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/black.css'); return false;">Black (default)</a> -
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/white.css'); return false;">White</a> -
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/league.css'); return false;">League</a> -
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/sky.css'); return false;">Sky</a> -
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/beige.css'); return false;">Beige</a> -
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/simple.css'); return false;">Simple</a> <br>
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/serif.css'); return false;">Serif</a> -
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/blood.css'); return false;">Blood</a> -
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/night.css'); return false;">Night</a> -
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/moon.css'); return false;">Moon</a> -
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/solarized.css'); return false;">Solarized</a>
		</p>
</section>

H:

# DATA

by Jean Pierre Charalambos  
[Universidad Nacional de Colombia](https://unal.edu.co/)

H:

# Index

1. Tabular data
 
H:

## Tabular data methods
### [LoadTable](https://processing.org/reference/loadTable_.html)

```java
Table table = loadTable("data.csv");
```

V:

## Tabular data methods
### [Reading data](https://processing.github.io/processing-javadocs/core/processing/data/Table.html)

| x   | y   | diameter  | name       |
|-----|-----|-----------|------------|
| 160 | 103 | 43.19838  | Happy      |
| 372 | 137 | 52.42526  | Sad        |
| 273 | 235 | 61.14072  | Joyous     |
| 121 | 179 | 44.758068 | Melancholy |


```java
int val1 = table.getInt(2, 1);      // val now has the value 235
float val2 = table.getFloat(3, 2);  // val2 now has the value 44.758068
String s = table.getString(0, 3);   // s now has the value “Happy”
```

V:

## Tabular data methods
### [TableRaw object](https://processing.github.io/processing-javadocs/core/processing/data/TableRow.html)

| x   | y   | diameter  | name       |
|-----|-----|-----------|------------|
| 160 | 103 | 43.19838  | Happy      |
| 372 | 137 | 52.42526  | Sad        |
| 273 | 235 | 61.14072  | Joyous     |
| 121 | 179 | 44.758068 | Melancholy |


```java
TableRow row = table.getRow(2); // Gets the third row (index 2)
int x = row.getInt("x"); // 	    // x has the value 273
int y = row.getInt("y");            // y has the value 235
float d = row.getFloat("diameter"); // d has the value 61.14072
String s = row.getString("name");   // s has the value “Joyous”
```

V:

## Tabular data methods
### [getRowCount()](https://processing.github.io/processing-javadocs/core/processing/data/Table.html)

```java
for (int i = 0; i<table.getRowCount(); i++) {
  // Access each row of the table one at a time, in a loop.
  TableRow row = table.getRow(i);
  float x = row.getFloat("x");
  float y = row.getFloat("y");
  float d = row.getFloat("diameter");
  String n = row.getString("name");
  // Do something with the data of each row
}
```

V:

## Tabular data methods
### [Write data](https://processing.github.io/processing-javadocs/core/processing/data/Table.html)

```java
//Create a new row.
TableRow row = table.addRow();
//Set the values of all columns in that row.
row.setFloat("x", mouseX);
row.setFloat("y", mouseY);
row.setFloat("diameter", random(40, 80));
row.setString("name", "new label");
saveTable(table, "data/data.csv");
```

Refer to [save table](https://processing.org/reference/saveTable_.html)

V:

## Tabular data methods
### [Other useful commands](https://processing.github.io/processing-javadocs/core/processing/data/Table.html)

```java
Table table = loadTable("data.csv", "header"); //see https://processing.org/reference/loadTable_.html)
removeRaw()
findRows()
matchRows()
```

H:

## References

* [Data](https://processing.org/tutorials/data/)
