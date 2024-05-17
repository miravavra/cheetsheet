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

Datový typ String musí být uveden mezi uvozovkami `"` nebo `'` (je jedno které, ale musí se shodovat). Pro zápis uvozovek v řetězci lze zapsat se zpětným lomítkem `\"` nebo `\'`.

Když chceš načíst datový typ String zadej `promenna = input("Zadej text:")`

#### Speciální znaky
`\n` znak pro nový řádek (několik nových řádků lze také ohraničit trojitými uvozovkami - způsobuje odsazení textu pokud je v odsazeném kódu)
`\t` vypíše tabulátor
`\\` vypíše zpětné lomítko

Se zpětným lomítkem se dá zadat jakýkoliv znak (včetně emoji).

Zápis podle jména standardu Unicode:

`\N{název}`

Zápis podle identifikačního čísla standardu Unicode:

`\x{název}`, `\u{název}`, `\U{název}`

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
### Zjištění jestli řetězec obsahuje/neobsahuje podřetězec
Vrací hodnotu `True` pokud je/není podřetězec obsažen v řetězci.

`podřetězec` in `řetězec`

__Příklad:__
```
"oko" in "čokoláda"
```

`podřetězec` not in `řetězec`

__Příklad:__
```
"dub" not in "čokoláda"
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

### Definice vlastních funkcí
Ukončení funkce provede příkaz `return`.
Když funkce neskončí příkazem `return`, automaticky vrátí hodnotu `None`.
Vstupy (jako `input`) a výstupy (jako `print`) přímo ve funkci omezují možnost s výsledkem dále pracovat = je lepší zpracování výsledku nechat mimo funkci.

__Příklad:__
```
from math import pi

def obsah_elipsy(a, b):
    '''Vrátí obsah elipsy s poloosami daných délek.'''
    return pi * a * b # Jen samotný výpočet.

# Print a input jsou vně funkce.
x = float(input('Zadej délku poloosy 1: '))
y = float(input('Zadej délku poloosy 2: '))
print('Obsah je', obsah_elipsy(x, y))

```


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

## Metody
Jsou svázané s objektem a volají se tak, že se za objekt napíše tečka, za ní jméno metody a to celé se připojí závorky s případnými argumenty.

- promenna.upper() Převod na velká písmena
- promenna.lower() Převod na malá písmena
- retezec.count(podretezec) Počet výskytů podřetězce v řetězci
- retezec.index(podretezec) Pozice 1. výskytu podřetězce v řetězci
- retezec.index(podretezec, pozice) Jako index, ale hledá od pozice
- retezec.lstrip() Odstraní bílé znaky* ze začátku
- retezec.rstrip() Odstraní bílé znaky* z konce
- retezec.strip() Odstraní bílé znaky z obou stran
- retezec.replace(a, b) Nahradí podřetězce a za b
- retezec.startswith(s) Začíná řetězec podřetězcem s?
- retezec.endswith(s) Končí řetězec podřetězcem s?
- retezec.format() Formátování

## Moduly
Jsou to vlastně takové knihovny z kterých můžeš importovat např. jednotlivé proměnné nebo můžeš importovat celý modul.
Vlastní modul vytvoříš tak, že uděláš pythoní soubor.

## Seznamy
Seznamy jsou měnitelné.

### Měnění seznamů
- append Přidá prvek na konec seznamu
- extend() Přidá více prvků najednou
- pop() Odebere daný prvek (defaultně poslední) a také je to jeho návratová hodnota
- insert() Přidá prvek na danou pozici
- remove() Odstraní první výskyt daného prvku
- clear() odstraní všechny prvky
- sort() seřadí seznam "podle abecedy", čísla vzestupně
- reverse() obrátí pořadí prvků

__Příklad:__
`seznam.sort(reverse=True)`

### Vybírání ze seznamu
Výběr prvnku na určité pozici.
```
zviratka=['pes', 'kočka', 'králík']
print(zviratka[2])
```

Výběr podseznamu.
```
zviratka=['pes', 'kočka', 'králík', 'had', 'andulka']
print(zviratka[1:-2])
```

### Měnění prvků
```
zviratka=['pes', 'kočka', 'králík', 'had', 'andulka']
print(zviratka[1:-2])
zviratka[1:-2]=['koťátko', 'králíček']
print(zviratka)
```

### Mazání prvků
- přiřazením prázdné hodnoty `[]` Tato metoda není moc přehledná
- pop() Smaže daný (defaultně poslední) prvek

__Příklad:__
`liznuta_karta = balicek.pop()`

- remove() Smaže první výskyt
- clear Smaže celý seznam

### Tvoření seznamů
- `list` Funkce list převádí na seznam. Z řetězce udělá seznam znaků, z range udělá seznam čísel.
```
abeceda = list('abcdefghijklmnopqrstuvwxyz')
cisla = list(range(100))
```
- metoda `split`  Když chceme dostat seznam slov
```
slova = 'Tato věta je složitá, rozdělme ji na slova!'.split()
```
Když máš nějaká data oddělená čárkami, použij split s čárkou.
```
zaznamy = '3A,8B,2E,9D'.split(',')
```
- metoda `join`  Když chceme spojit seznam řetězců zase dohromady do jediného řetězce.
```
veta = ' '.join(slova)
```
