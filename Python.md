# Python
## Proměnné
- Hodnoty se do proměnných přiřazují pomocí rovnítka `=`.

- Hodnoty se zobrazují pomocí `print()`. Print takto bez argumentu vypíše prázdný řádek.

  Při výpisu odděluje jednotlivé argumenty mezerou což mění argumetn `sep` (např.`print(1,2,3,4, sep=", ")` oddělí čárkou).

  Na konci výpisu přejde na nový řádek což mění argumetn `end` (např.`print("1 + 2", end=" ")` místo přechodu na nový řádek napíše mezeru).

- Hodnoty od uživatele se zadávají pomocí `input()`.
- Názvy proměnných jsou `case sensitive`, nesmí začínat číslem, nesmí obsahovat mezeru (místo mezery se používá podtržítko `_`).
- Opětovné přiřazení hodnoty do proměnné přepíše její původní hodnotu.

## Datové typy
String se používá pro texty a Integer a Float pro čísla.

Dělení dvou celých čísel (např. 9/3) vždy vrací typ Float (3.0).

Zobrazení dvou stringů pomocí `print("Iron" + Man")` provede sloučení řetězců a vypíše "IronMan".

Kontrolu datového typu v proměnné provedeme pomocí `type()`.

### String
Datový typ pro text.

Datový typ String musí být uveden mezi uvozovkami `"` nebo `'` (je jedno které, ale musí se shodovat).

Když chceš načíst datový typ String zadej `promenna = input("Zadej text:")`

### Integer
Datový typ pro celá čísla bez desetinné čárky. Číslo může být pozitivní, negativní nebo nula.

Datový typ Integer nesmí být uveden mezi uvozovkami.

Když chceš načíst datový typ Integer zadej `promenna = int(input("Zadej číslo:"))`.

### Float
Datový typ pro čísla s desetinnou čárkou. Číslo může být pozitivní, negativní.

Datový typ Float nesmí být uveden mezi uvozovkami.

Když chceš načíst datový typ Float zadej `promenna = float(input("Zadej číslo:"))`.

### Komentář
Komentáře jsou uvedeny za hash symbolem `#`, víceřádkové pak mezi dvojicí hash symbolů `"""` (nebo `'''`).

## Operátory
### Základní aritmetické operátory
Základní aritmetika `+`, `-`, `*`, `/` (např. `1 + 1`)

Negace `-` (např. `-5`)

Dělení se zbytkem (celočíselné dělení) `//` (např.`7 // 2`)

Zbytek po dělení `%` (např.`7 % 2`)

Umocnění (3 na druhou) `**` (např. `3 ** 2`)

:=

|

^

&

<<

>>

@

[]

()

{}

### Porovnávací operátory
Hodnoty jsou vždy jen True nebo False (pozor na velikost písmen).

Je rovno, není rovno `==`, `!=` (např. `1 == 1`, `1 != 1`)
Menší než, větší než `<`, `>` (např. `3 < 5`, `3 > 5`)
Menší nebo rovno, větší nebo rovno `<=`, `>=` (např. `3 <= 5`, `3 >= 5`)
"A zároveň" `and` (např. `True and False`, `2 < 3 and 5 < 3`)
"A nebo" `or` (např. `True or False`, `2 < 3 or 5 < 3`)
"Ne" `not` (např. `not False`, `not 5 < 3`)

## Podmínky
### Podmínka if
```
if promenna:  # Za if je podmínka která musí být True.
    print("něco")
elif promenna >= číslo:  # Když je podmínka False tak se provede následující.
    print("něco jiného")
elif promenna >= jiné_číslo:  # Podmínek elif může být několik.
    print("něco ještě jiného")
else:  # Když nenastala shoda předchozích podmínek tak se provede následující.
    print("něco nakonec")
```

## Funkce
### Zjištění délky řetězce
`len(argument)`
__Příklad:__
```
slovo = "Ahoj"
delka = len(slovo)
print(delka)
```

### Převádění typů
`str(123)` Převede jakoukoli hodnotu na řetězec

`int("123")` Převádí na celé číslo, `int(124.4)` odstřihne z desetinných čísel necelou část

`float("123.4")` Převádí na reálné číslo

`bool(1)` Převede prázdný řetězec a 0 na False, jiné řetězce nebo čísla na True.

### Náhoda
`from random import randrange, uniform`
`randrange(0, 10)` náhodné celé číslo od 0 do 9
`uniform(0, 10)` náhodné reálné číslo 0 <= x < 10

### Informace o programu
`help(x)` Nápověda k objektu x.
`dir()` Přehled jmen promnných, `dir(x)` přehled atributů objektu x.
`type(x)` Typ objektu x.

### Matematika
`from math import sin, cos, tan, sqrt, pi`

`round(x)` zaokrouhlení

`floor(x)` zaokrouhlení dolů

`ceil(x)` zaokrouhlení nahoru

`sin(u)`, `cos(u)`, `tan(u)` goniometrické funkce v radiánech

`degrees(r)` radiány na stupně, `radians(d)` stupně na radiány

`sqrt(x)` druhá odmocnina

`abs(x)` absolutní hodnota

## Cykly
### Cyklus for
Jako proměnná pouze pro potřeby cyklu se často používá "i", "j" nebo prázdná proměnná "_".

__Příklad:__
```
for pozdrav in "Ahoj", "Hello", "Hola", "Hey":
    print(pozdra + "!")
```

__Příklad:__
```
for i in range(5):
    print(i)
```

### Cyklus while
Ukončení cyklu provede příkaz `break`.

```
while podmínka:
    print("něco")
```
