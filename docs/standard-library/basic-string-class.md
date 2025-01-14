---
title: basic_string-Klasse
ms.date: 11/04/2016
f1_keywords:
- xstring/std::basic_string
- xstring/std::basic_string::allocator_type
- xstring/std::basic_string::const_iterator
- xstring/std::basic_string::const_pointer
- xstring/std::basic_string::const_reference
- xstring/std::basic_string::const_reverse_iterator
- xstring/std::basic_string::difference_type
- xstring/std::basic_string::iterator
- xstring/std::basic_string::npos
- xstring/std::basic_string::pointer
- xstring/std::basic_string::reference
- xstring/std::basic_string::reverse_iterator
- xstring/std::basic_string::size_type
- xstring/std::basic_string::traits_type
- xstring/std::basic_string::value_type
- xstring/std::basic_string::append
- xstring/std::basic_string::assign
- xstring/std::basic_string::at
- xstring/std::basic_string::back
- xstring/std::basic_string::begin
- xstring/std::basic_string::c_str
- xstring/std::basic_string::capacity
- xstring/std::basic_string::cbegin
- xstring/std::basic_string::cend
- xstring/std::basic_string::clear
- xstring/std::basic_string::compare
- xstring/std::basic_string::copy
- xstring/std::basic_string::crbegin
- xstring/std::basic_string::crend
- xstring/std::basic_string::_Copy_s
- xstring/std::basic_string::data
- xstring/std::basic_string::empty
- xstring/std::basic_string::end
- xstring/std::basic_string::erase
- xstring/std::basic_string::find
- xstring/std::basic_string::find_first_not_of
- xstring/std::basic_string::find_first_of
- xstring/std::basic_string::find_last_not_of
- xstring/std::basic_string::find_last_of
- xstring/std::basic_string::front
- xstring/std::basic_string::get_allocator
- xstring/std::basic_string::insert
- xstring/std::basic_string::length
- xstring/std::basic_string::max_size
- xstring/std::basic_string::pop_back
- xstring/std::basic_string::push_back
- xstring/std::basic_string::rbegin
- xstring/std::basic_string::rend
- xstring/std::basic_string::replace
- xstring/std::basic_string::reserve
- xstring/std::basic_string::resize
- xstring/std::basic_string::rfind
- xstring/std::basic_string::shrink_to_fit
- xstring/std::basic_string::size
- xstring/std::basic_string::substr
- xstring/std::basic_string::swap
helpviewer_keywords:
- std::basic_string [C++]
- std::basic_string [C++], allocator_type
- std::basic_string [C++], const_iterator
- std::basic_string [C++], const_pointer
- std::basic_string [C++], const_reference
- std::basic_string [C++], const_reverse_iterator
- std::basic_string [C++], difference_type
- std::basic_string [C++], iterator
- std::basic_string [C++], npos
- std::basic_string [C++], pointer
- std::basic_string [C++], reference
- std::basic_string [C++], reverse_iterator
- std::basic_string [C++], size_type
- std::basic_string [C++], traits_type
- std::basic_string [C++], value_type
- std::basic_string [C++], append
- std::basic_string [C++], assign
- std::basic_string [C++], at
- std::basic_string [C++], back
- std::basic_string [C++], begin
- std::basic_string [C++], c_str
- std::basic_string [C++], capacity
- std::basic_string [C++], cbegin
- std::basic_string [C++], cend
- std::basic_string [C++], clear
- std::basic_string [C++], compare
- std::basic_string [C++], copy
- std::basic_string [C++], crbegin
- std::basic_string [C++], crend
- std::basic_string [C++], _Copy_s
- std::basic_string [C++], data
- std::basic_string [C++], empty
- std::basic_string [C++], end
- std::basic_string [C++], erase
- std::basic_string [C++], find
- std::basic_string [C++], find_first_not_of
- std::basic_string [C++], find_first_of
- std::basic_string [C++], find_last_not_of
- std::basic_string [C++], find_last_of
- std::basic_string [C++], front
- std::basic_string [C++], get_allocator
- std::basic_string [C++], insert
- std::basic_string [C++], length
- std::basic_string [C++], max_size
- std::basic_string [C++], pop_back
- std::basic_string [C++], push_back
- std::basic_string [C++], rbegin
- std::basic_string [C++], rend
- std::basic_string [C++], replace
- std::basic_string [C++], reserve
- std::basic_string [C++], resize
- std::basic_string [C++], rfind
- std::basic_string [C++], shrink_to_fit
- std::basic_string [C++], size
- std::basic_string [C++], substr
- std::basic_string [C++], swap
ms.assetid: a9c3e0a2-39bf-4c8a-b093-9abe30839591
ms.openlocfilehash: ab93f8b225e27c0cf4d294d176c566bd6f2b5d02
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409784"
---
# <a name="basicstring-class"></a>basic_string-Klasse

Bei den von einem Objekt der `basic_string`-Vorlagenklasse gesteuerten Sequenzen handelt es sich um die Standard-C++-Zeichenfolgenklasse, und sie werden normalerweise als Zeichenfolgen bezeichnet. Allerdings sollten diese nicht mit den in der C++-Standardbibliothek verwendeten auf NULL endenden Zeichenfolgen im C-Stil verwechselt werden. Die C++-Standardzeichenfolge ist ein Container, der die Verwendung von Zeichenfolgen als Normaltypen, wie das Verwenden von Vergleichs- und Verkettungsvorgängen, Iteratoren, STL-Algorithmen sowie das Kopieren und Zuweisen mit von Klassenzuweisung verwaltetem Arbeitsspeicher, ermöglicht. Falls eine C++-Standardzeichenfolge in eine auf NULL endende Zeichenfolge im C-Stil konvertiert werden muss, verwenden Sie den Member [basic_string::c_str](#c_str).

## <a name="syntax"></a>Syntax

```cpp
template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_string;
```

### <a name="parameters"></a>Parameter

*CharType*<br/>
Der Datentyp eines einzelnen in der Zeichenfolge zu speichernden Zeichens. Die C++ Standardbibliothek bietet spezialisierungen dieser Vorlagenklasse mit den Typdefinitionen [Zeichenfolge](../standard-library/string-typedefs.md#string) für Elemente des Typs **Char**, [Wstring](../standard-library/string-typedefs.md#wstring), für die **"wchar_t"**, [u16string](../standard-library/string-typedefs.md#u16string) für `char16_t`, und [u32string](../standard-library/string-typedefs.md#u32string) für `char32_t`.

*Merkmale*<br/>
Verschiedene wichtige Eigenschaften der der `CharType` Elemente in einer Basic_string-Spezialisierung werden von der Klasse beschrieben `Traits`. Der Standardwert ist `char_traits`< `CharType`>.

*Allocator*<br/>
Der Typ, mit dem das gespeicherte Zuordnungsobjekt darstellt wird, mit dem Details zum Belegen und Freigeben des Arbeitsspeichers der Zeichenfolge gekapselt werden. Der Standardwert lautet **allocator**< `CharType`>.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[basic_string](#basic_string)|Erstellt eine Zeichenfolge, die leer ist, oder von bestimmten Zeichen initialisiert wird, oder eine vollständige oder teilweise Kopie eines anderen Zeichenfolgenobjekts oder einer C-Zeichenfolge ist.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[allocator_type](#allocator_type)|Ein Typ, mit dem die `allocator`-Klasse für ein Zeichenfolgenobjekt dargestellt wird.|
|[const_iterator](#const_iterator)|Ein Typ, der einen Iterator mit wahlfreiem Zugriff bereitstellt, mit dem auf ein **const**-Element zugegriffen wird, und mit dem dieses Element gelesen werden kann.|
|[const_pointer](#const_pointer)|Ein Typ, der einen Zeiger auf ein **const**-Element in einer Zeichenfolge bereitstellt.|
|[const_reference](#const_reference)|Ein Typ, der einen Verweis auf ein **const**-Element bereitstellt, das in einer Liste zum Lesen und Ausführen von **const**-Vorgängen gespeichert ist.|
|[const_reverse_iterator](#const_reverse_iterator)|Ein Typ, der einen Iterator mit wahlfreiem Zugriff bereitstellt, mit dem jedes **const**-Element in der Zeichenfolge gelesen werden kann.|
|[difference_type](#difference_type)|Ein Typ, der den Unterschied zwischen zwei Iteratoren, die auf Elemente innerhalb derselben Zeichenfolge verweisen, bereitstellt.|
|[Iterator](#iterator)|Ein Typ, der einen Iterator mit zufälligem Zugriff bereitstellt, mit dem jedes Element in einer Zeichenfolge gelesen oder geändert werden kann.|
|[npos](#npos)|Ein initialisierter Integralwert ohne Vorzeichen-1 an, der angibt "nicht gefunden" oder "alle verbleibenden Zeichen" Wenn eine Funktion für die Suche ein Fehler auftritt.|
|[Zeiger](#pointer)|Ein Typ, der einen Zeiger auf ein Zeichenelement in einer Zeichenfolge oder einem Zeichenarray bereitstellt.|
|[Verweis](#reference)|Ein Typ, der einen Verweis auf ein in einer Zeichenfolge gespeichertes Element bereitstellt.|
|[reverse_iterator](#reverse_iterator)|Ein Typ, der einen Iterator mit zufälligem Zugriff bereitstellt, mit dem ein Element in einer umgekehrten Zeichenfolge gelesen oder geändert werden kann.|
|[size_type](#size_type)|Ein Integraltyp ohne Vorzeichen für die Anzahl von Elementen in einer Zeichenfolge.|
|[traits_type](#traits_type)|Ein Typ für die Zeichenmerkmale der in einer Zeichenfolge gespeicherten Elemente.|
|[value_type](#value_type)|Ein Typ, der die Art der in einer Zeichenfolge gespeicherten Zeichen darstellt.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[append](#append)|Fügt am Ende einer Zeichenfolge Zeichen hinzu.|
|[assign](#assign)|Weist dem Inhalt einer Zeichenfolge neue Zeichenwerte zu.|
|[at](#at)|Gibt einen Verweis auf das Element an einer angegebenen Position in der Zeichenfolge zurück.|
|[Rückseite](#back)||
|[begin](#begin)|Gibt ein Iterator zurück, der das erste Element in der Zeichenfolge adressiert.|
|[c_str](#c_str)|Konvertiert den Inhalt einer Zeichenfolge als eine auf NULL endende Zeichenfolge im C-Format zurück.|
|[capacity](#capacity)|Gibt die höchste Anzahl von Elementen zurück, die ohne Erhöhung der Speicherbelegung der Zeichenfolge in einer Zeichenfolge gespeichert werden können.|
|[cbegin](#cbegin)|Gibt einen const-Iterator zurück, der das erste Element in der Zeichenfolge adressiert.|
|[cend](#cend)|Gibt einen const-Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer Zeichenfolge nachfolgt.|
|[clear](#clear)|Löscht alle Elemente einer Zeichenfolge.|
|[compare](#compare)|Vergleicht eine Zeichenfolge mit einer angegebenen Zeichenfolge, um zu bestimmen, ob die beiden Zeichenfolgen gleich sind, oder ob eine lexikografisch kleiner als die andere ist.|
|[copy](#copy)|Kopiert höchstens eine angegebene Anzahl von Zeichen aus einer indizierten Position in einer Quellzeichenfolge in ein Zielzeichenarray. Veraltet. Verwenden Sie stattdessen [basic_string::_Copy_s](#copy_s).|
|[crbegin](#crbegin)|Gibt einen const-Iterator zurück, der das erste Element in einer umgekehrter Zeichenfolge adressiert.|
|[crend](#crend)|Gibt einen const-Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer umgekehrten Zeichenfolge nachfolgt.|
|[_Copy_s](#copy_s)|Kopiert höchstens eine angegebene Anzahl von Zeichen aus einer indizierten Position in einer Quellzeichenfolge in ein Zielzeichenarray.|
|[data](#data)|Konvertiert den Inhalt einer Zeichenfolge in ein Zeichenarray.|
|[empty](#empty)|Testet, ob in der Zeichenfolge Zeichen enthalten sind.|
|[end](#end)|Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer Zeichenfolge nachfolgt.|
|[erase](#erase)|Entfernt ein Element oder einen Reihe von Elementen einer Zeichenfolge von einer angegebenen Position.|
|[find](#find)|Sucht eine Zeichenfolge vorwärts nach dem ersten Vorkommen einer Teilzeichenfolge ab, die mit einer bestimmten Zeichensequenz übereinstimmt.|
|[find_first_not_of](#find_first_not_of)|Durchsucht eine Zeichenfolge nach dem ersten Zeichen, das kein Element der angegebenen Zeichenfolge ist.|
|[find_first_of](#find_first_of)|Durchsucht eine Zeichenfolge nach dem ersten Zeichen, das einem Element der angegebenen Zeichenfolge entspricht.|
|[find_last_not_of](#find_last_not_of)|Durchsucht eine Zeichenfolge nach dem letzten Zeichen, das kein Element der angegebenen Zeichenfolge ist.|
|[find_last_of](#find_last_of)|Durchsucht eine Zeichenfolge nach dem letzten Zeichen, das ein Element der angegebenen Zeichenfolge ist.|
|[Vorderseite](#front)|Gibt einen Verweis auf das erste Element in einer Zeichenfolge zurück.|
|[get_allocator](#get_allocator)|Gibt eine Kopie des zum Erstellen der Zeichenfolge verwendeten `allocator`-Objekts zurück.|
|[insert](#insert)|Fügt ein Element oder mehrere Elemente oder ein Reihe von Elementen an einer bestimmten Position in die Zeichenfolge ein.|
|[length](#length)|Gibt die aktuelle Anzahl von Elementen in einer Zeichenfolge zurück.|
|[max_size](#max_size)|Gibt die Höchstanzahl von Zeichen, die eine Zeichenfolge enthalten könnte zurück.|
|[pop_back](#pop_back)|Löscht das letzte Element der Zeichenfolge.|
|[push_back](#push_back)|Fügt ein Element am Ende der Zeichenfolge hinzu.|
|[rbegin](#rbegin)|Gibt einen Iterator an das erste Element in einer umgekehrten Zeichenfolge zurück.|
|[rend](#rend)|Gibt einen Iterator zurück, der auf die Position direkt hinter dem letzten Element in einer umgekehrten Zeichenfolge zeigt.|
|[replace](#replace)|Ersetzt Elemente an einer bestimmten Position in einer Zeichenfolge durch angegebene Zeichen oder Zeichen, die aus anderen Bereichen oder Zeichenfolgen oder C-Zeichenfolgen kopiert werden.|
|[reserve](#reserve)|Legt die Kapazität der Zeichenfolge auf eine Zahl fest, die mindestens so groß ist, wie eine angegebene Anzahl.|
|[resize](#resize)|Gibt eine neue Größe für eine Zeichenfolge an und fügt Elemente an bzw. löscht sie bei Bedarf.|
|[rfind](#rfind)|Sucht eine Zeichenfolge rückwärts nach dem ersten Vorkommen einer Teilzeichenfolge ab, die mit einer bestimmten Zeichensequenz übereinstimmt.|
|[shrink_to_fit](#shrink_to_fit)|Verwirft die Überkapazität der Zeichenfolge.|
|[size](#size)|Gibt die aktuelle Anzahl von Elementen in einer Zeichenfolge zurück.|
|[substr](#substr)|Kopiert eine Teilzeichenfolge höchstens einer beliebigen Anzahl von Zeichen aus einer Zeichenfolge, beginnend an einer angegebenen Position.|
|[swap](#swap)|Tauschen Sie den Inhalt von zwei Zeichenfolgen aus.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator+=](#op_add_eq)|Fügt einer Zeichenfolge Zeichen an.|
|[operator=](#op_eq)|Weist dem Inhalt einer Zeichenfolge neue Zeichenwerte zu.|
|[operator&#91;&#93;](#op_at)|Stellt mit einem angegebenen Index in einer Zeichenfolge einen Verweis auf das Zeichen.|

## <a name="remarks"></a>Hinweise

Wenn eine Funktion aufgefordert wird, eine Sequenz zu generieren, die länger als [max_size](#max_size)-Elemente ist, wird von der Funktion ein Längenfehler gemeldet, indem ein Objekt des Typs [length_error](../standard-library/length-error-class.md) ausgelöst wird.

Verweise, Zeiger und Iteratoren, mit denen Elemente der gesteuerten Sequenz festgelegt werden, können nach jedem Aufruf einer Funktion, mit der die gesteuerte Sequenz geändert wird, oder nach dem ersten Aufruf einer anderen als einer **const**-Memberfunktion ungültig werden.

## <a name="requirements"></a>Anforderungen

**Header:** \<string>

**Namespace:** std

## <a name="allocator_type"></a> basic_string::allocator_type

Ein Typ, mit dem die Zuweisungsklasse für ein Zeichenfolgenobjekt dargestellt wird.

```cpp
typedef Allocator allocator_type;
```

### <a name="remarks"></a>Hinweise

Der Type stellt ein Synonym für den Vorlagenparameter `Allocator` dar.

### <a name="example"></a>Beispiel

```cpp
// basic_string_allocator_type.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // The following lines declare objects
   // that use the default allocator.
   string s1;
   basic_string <char>::allocator_type xchar = s1.get_allocator( );
   // You can now call functions on the allocator class xchar used by s1
}
```

## <a name="append"></a> basic_string::append

Fügt am Ende einer Zeichenfolge Zeichen hinzu.

```cpp
basic_string<CharType, Traits, Allocator>& append(
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& append(
    const value_type* ptr,
    size_type count);

basic_string<CharType, Traits, Allocator>& append(
    const basic_string<CharType, Traits, Allocator>& str,
    size_type _Off,
    size_type count);

basic_string<CharType, Traits, Allocator>& append(
    const basic_string<CharType, Traits, Allocator>& str);

basic_string<CharType, Traits, Allocator>& append(
    size_type count,
    value_type _Ch);

template <class InputIterator>
basic_string<CharType, Traits, Allocator>& append(
    InputIterator first,
    InputIterator last);

basic_string<CharType, Traits, Allocator>& append(
    const_pointer first,
    const_pointer last);

basic_string<CharType, Traits, Allocator>& append(
    const_iterator first,
    const_iterator last);
```

### <a name="parameters"></a>Parameter

*ptr*<br/>
Die C-Zeichenfolge, die angefügt werden soll.

*str*<br/>
Die Zeichenfolge, deren Zeichen angefügt werden sollen.

*_Off*<br/>
Der Index des Teils der Quellzeichenfolge, der die anzufügenden Zeichen bereitstellt.

*count*<br/>
Die Anzahl der Zeichen, die höchstens aus der Quellzeichenfolge angefügt werden darf.

*_Ch*<br/>
Der Zeichenwert, der angefügt werden soll.

*first*<br/>
Ein Eingabeiterator, der das erste Element im Bereich adressiert, der angefügt werden soll.

*last*<br/>
Ein Eingabeiterator, const_pointer oder const_iterator, der die Position eines der letzten Elemente im anzufügenden Bereich adressiert.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Zeichenfolgenobjekt, an das die Zeichen angefügt werden, die von der Memberfunktion übergeben werden.

### <a name="remarks"></a>Hinweise

Zeichen angefügt werden können, in eine Zeichenfolge mit der [Operator +=](#op_add_eq) oder den Memberfunktionen `append` oder [Push_back](#push_back). `operator+=` Fügt einfache Argumentwerte an während der mehreren Argumenten `append` Member-Funktion ermöglicht es einen bestimmten Teil einer Zeichenfolge für das Hinzufügen angegeben werden.

### <a name="example"></a>Beispiel

```cpp
// basic_string_append.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function
   // appending a C-string to a string
   string str1a ( "Hello " );
   cout << "The original string str1 is: " << str1a << endl;
   const char *cstr1a = "Out There ";
   cout << "The C-string cstr1a is: " << cstr1a << endl;
   str1a.append ( cstr1a );
   cout << "Appending the C-string cstr1a to string str1 gives: "
        << str1a << "." << endl << endl;

   // The second member function
   // appending part of a C-string to a string
   string str1b ( "Hello " );
   cout << "The string str1b is: " << str1b << endl;
   const char *cstr1b = "Out There ";
   cout << "The C-string cstr1b is: " << cstr1b << endl;
   str1b.append ( cstr1b , 3 );
   cout << "Appending the 1st part of the C-string cstr1b "
        << "to string str1 gives: " << str1b << "."
        << endl << endl;

   // The third member function
   // appending part of one string to another
   string str1c ( "Hello " ), str2c ( "Wide World " );
   cout << "The string str2c is: " << str2c << endl;
   str1c.append ( str2c , 5 , 5 );
   cout << "The appended string str1 is: "
        << str1c << "." << endl << endl;

   // The fourth member function
   // appending one string to another in two ways,
   // comparing append and operator [ ]
   string str1d ( "Hello " ), str2d ( "Wide " ), str3d ( "World " );
   cout << "The  string str2d is: " << str2d << endl;
   str1d.append ( str2d );
   cout << "The appended string str1d is: "
        << str1d << "." << endl;
   str1d += str3d;
   cout << "The doubly appended strig str1 is: "
        << str1d << "." << endl << endl;

   // The fifth member function
   // appending characters to a string
   string str1e ( "Hello " );
   str1e.append ( 4 , '!' );
   cout << "The string str1 appended with exclamations is: "
        << str1e << endl << endl;

   // The sixth member function
   // appending a range of one string to another
   string str1f ( "Hello " ), str2f ( "Wide World " );
   cout << "The string str2f is: " << str2f << endl;
   str1f.append ( str2f.begin ( ) + 5 , str2f.end ( ) - 1 );
   cout << "The appended string str1 is: "
        << str1f << "." << endl << endl;
}
```

```Output
The original string str1 is: Hello
The C-string cstr1a is: Out There
Appending the C-string cstr1a to string str1 gives: Hello Out There .

The string str1b is: Hello
The C-string cstr1b is: Out There
Appending the 1st part of the C-string cstr1b to string str1 gives: Hello Out.

The string str2c is: Wide World
The appended string str1 is: Hello World.

The  string str2d is: Wide
The appended string str1d is: Hello Wide .
The doubly appended strig str1 is: Hello Wide World .

The string str1 appended with exclamations is: Hello !!!!

The string str2f is: Wide World
The appended string str1 is: Hello World.
```

## <a name="assign"></a> basic_string::assign

Weist dem Inhalt einer Zeichenfolge neue Zeichenwerte zu.

```cpp
basic_string<CharType, Traits, Allocator>& assign(
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& assign(
    const value_type* ptr,
    size_type count);

basic_string<CharType, Traits, Allocator>& assign(
    const basic_string<CharType, Traits, Allocator>& str,
    size_type off,
    size_type count);

basic_string<CharType, Traits, Allocator>& assign(
    const basic_string<CharType, Traits, Allocator>& str);

basic_string<CharType, Traits, Allocator>& assign(
    size_type count,
    value_type _Ch);

template <class InIt>
basic_string<CharType, Traits, Allocator>& assign(
    InputIterator first,
    InputIterator last);

basic_string<CharType, Traits, Allocator>& assign(
    const_pointer first,
    const_pointer last);

basic_string<CharType, Traits, Allocator>& assign(
    const_iterator first,
    const_iterator last);
```

### <a name="parameters"></a>Parameter

*ptr*<br/>
Ein Zeiger auf die Zeichen einer C-Zeichenfolge, die der Zielzeichenfolge zugewiesen werden sollen.

*count*<br/>
Die Anzahl der Zeichen, die aus der Quellzeichenfolge zugewiesen werden soll.

*str*<br/>
Die Quellzeichenfolge, deren Zeichen der Zielzeichenfolge zugewiesen werden sollen.

*_Ch*<br/>
Der Zeichenwert, der zugewiesen werden soll.

*first*<br/>
Ein Eingabeiterator, const_pointer oder const_iterator, der das erste Zeichen im Bereich der Quellzeichenfolge adressiert, die dem Zielbereich zugewiesen werden soll.

*last*<br/>
Ein Eingabeiterator, const_pointer oder const_iterator, der das Zeichen nach dem letzten Zeichen im Bereich der Quellzeichenfolge adressiert, die dem Zielbereich zugewiesen werden soll.

*off*<br/>
Die Position, ab der neue Zeichen zugewiesen werden.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Zeichenfolgenobjekt, dem durch die Memberfunktion neue Zeichen zugewiesen werden sollen.

### <a name="remarks"></a>Hinweise

Den Zeichenfolgen können neue Zeichenwerte zugewiesen werden. Der neue Wert kann entweder eine Zeichenfolge und C-Zeichenfolge oder ein einzelnes Zeichen sein. Die [Operator =](#op_eq) kann verwendet werden, wenn der neue Wert andernfalls durch einen einzelnen Parameter beschrieben werden kann die Memberfunktion `assign`, die über mehrere Parameter verfügt kann verwendet werden, um anzugeben, welcher Teil der Zeichenfolge, ein Ziel zugewiesen werden soll Zeichenfolge.

### <a name="example"></a>Beispiel

```cpp
// basic_string_assign.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function assigning the
   // characters of a C-string to a string
   string str1a;
   const char *cstr1a = "Out There";
   cout << "The C-string cstr1a is: " << cstr1a <<  "." << endl;
   str1a.assign ( cstr1a );
   cout << "Assigning the C-string cstr1a to string str1 gives: "
        << str1a << "." << endl << endl;

   // The second member function assigning a specific
   // number of the of characters a C-string to a string
   string  str1b;
   const char *cstr1b = "Out There";
   cout << "The C-string cstr1b is: " << cstr1b << endl;
   str1b.assign ( cstr1b , 3 );
   cout << "Assigning the 1st part of the C-string cstr1b "
        << "to string str1 gives: " << str1b << "."
        << endl << endl;

   // The third member function assigning a specific number
   // of the characters from one string to another string
   string str1c ( "Hello " ), str2c ( "Wide World " );
   cout << "The string str2c is: " << str2c << endl;
   str1c.assign ( str2c , 5 , 5 );
   cout << "The newly assigned string str1 is: "
        << str1c << "." << endl << endl;

   // The fourth member function assigning the characters
   // from one string to another string in two equivalent
   // ways, comparing the assign and operator =
   string str1d ( "Hello" ), str2d ( "Wide" ), str3d ( "World" );
   cout << "The original string str1 is: " << str1d << "." << endl;
   cout << "The string str2d is: " << str2d << endl;
   str1d.assign ( str2d );
   cout << "The string str1 newly assigned with string str2d is: "
        << str1d << "." << endl;
   cout << "The string str3d is: " << str3d << "." << endl;
   str1d = str3d;
   cout << "The string str1 reassigned with string str3d is: "
        << str1d << "." << endl << endl;

   // The fifth member function assigning a specific
   // number of characters of a certain value to a string
   string str1e ( "Hello " );
   str1e.assign ( 4 , '!' );
   cout << "The string str1 assigned with eclamations is: "
        << str1e << endl << endl;

   // The sixth member function assigning the value from
   // the range of one string to another string
   string str1f ( "Hello " ), str2f ( "Wide World " );
   cout << "The string str2f is: " << str2f << endl;
   str1f.assign ( str2f.begin ( ) + 5 , str2f.end ( ) - 1 );
   cout << "The string str1 assigned a range of string str2f is: "
        << str1f << "." << endl << endl;
}
```

```Output
The C-string cstr1a is: Out There.
Assigning the C-string cstr1a to string str1 gives: Out There.

The C-string cstr1b is: Out There
Assigning the 1st part of the C-string cstr1b to string str1 gives: Out.

The string str2c is: Wide World
The newly assigned string str1 is: World.

The original string str1 is: Hello.
The string str2d is: Wide
The string str1 newly assigned with string str2d is: Wide.
The string str3d is: World.
The string str1 reassigned with string str3d is: World.

The string str1 assigned with eclamations is: !!!!

The string str2f is: Wide World
The string str1 assigned a range of string str2f is: World.
```

## <a name="at"></a> basic_string::at

Stellt mit einem angegebenen Index in einer Zeichenfolge einen Verweis auf das Zeichen.

```cpp
const_reference at(size_type _Off) const;

reference at(size_type _Off);
```

### <a name="parameters"></a>Parameter

*_Off*<br/>
Der Index des Elements, auf das verwiesen werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Zeichen der Zeichenfolge an der Position, die durch den Parameterindex angegeben wird.

### <a name="remarks"></a>Hinweise

Das erste Element der Zeichenfolge hat einen Index von 0 (null) und die folgenden Elemente werden nacheinander durch positiven ganze Zahlen indiziert, damit eine Zeichenfolge der Länge *n* verfügt über eine *n*th-Element ab, das durch die Anzahl *n -* 1.

Das Element [Operator&#91; &#93; ](#op_at) ist schneller als die Memberfunktion `at` für die Bereitstellung von Lese- und Schreibzugriff auf die Elemente einer Zeichenfolge.

Das Element `operator[]` überprüft nicht, ob der Index als Parameter übergebenen gültig ist, aber die Memberfunktion `at` unterstützt und daher sollte verwendet werden, wenn die Gültigkeit nicht sicher ist. Ein ungültiger Index, d.h. ein Index weniger, die 0 (null) oder größer als oder gleich der Größe der Zeichenfolge, mit der Memberfunktion übergeben `at` löst eine [Out_of_range-Klasse](../standard-library/out-of-range-class.md) Ausnahme. Ein ungültiger Index, der an `operator[]` übergeben wird, führt zu nicht definiertem Verhalten. Der Index, der gleich der Länge der Zeichenfolge ist, ist allerdings ein gültiger Index für const-Zeichenfolgen. Der Operator gibt das NULL-Zeichen zurück, wenn dieser Index übergeben wurde.

Der zurückgegebene Verweis wird möglicherweise durch Neuzuordnungen oder Änderungen für nicht **konstante**  Zeichenfolgen ungültig.

### <a name="example"></a>Beispiel

```cpp
// basic_string_at.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ( "Hello world" ), str2 ( "Goodbye world" );
   const string  cstr1 ( "Hello there" ), cstr2 ( "Goodbye now" );
   cout << "The original string str1 is: " << str1 << endl;
   cout << "The original string str2 is: " << str2 << endl;

   // Element access to the non const strings
   basic_string <char>::reference refStr1 = str1 [6];
   basic_string <char>::reference refStr2 = str2.at ( 3 );

   cout << "The character with an index of 6 in string str1 is: "
        << refStr1 << "." << endl;
   cout << "The character with an index of 3 in string str2 is: "
        << refStr2 << "." << endl;

   // Element access to the const strings
   basic_string <char>::const_reference crefStr1 = cstr1 [ cstr1.length ( ) ];
   basic_string <char>::const_reference crefStr2 = cstr2.at ( 8 );

   if ( crefStr1 == '\0' )
      cout << "The null character is returned as a valid reference."
           << endl;
   else
      cout << "The null character is not returned." << endl;
   cout << "The character with index 8 in the const string cstr2 is: "
        << crefStr2 << "." << endl;
}
```

## <a name="back"></a> basic_string::back

Gibt einen Verweis auf das letzte Element der Zeichenfolge zurück.

```cpp
const_reference back() const;

reference back();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das letzte Element der Zeichenfolge, die nicht leer sein darf.

### <a name="remarks"></a>Hinweise

## <a name="basic_string"></a> basic_string::basic_string

Erstellt eine Zeichenfolge, die leer ist, oder von bestimmten Zeichen initialisiert wird, oder eine vollständige oder teilweise Kopie eines anderen Zeichenfolgenobjekts oder einer C-Zeichenfolge (null-terminiert) ist.

```cpp
basic_string();

explicit basic_string(
    const allocator_type& _Al);

basic_string(
    const basic_string& right);

basic_string(
    basic_string&& right);

basic_string(
    const basic_string& right,
    size_type _Roff,
    size_type count = npos);

basic_string(
    const basic_string& right,
    size_type _Roff,
    size_type count,
    const allocator_type& _Al);

basic_string(
    const value_type* ptr,
    size_type count);

basic_string(
    const value_type* ptr,
    size_type count,
    const allocator_type& _Al);

basic_string(
    const value_type* ptr);

basic_string(
    const value_type* ptr,
    const allocator_type& _Al);

basic_string(
    size_type count,
    value_type _Ch);

basic_string(
    size_type count,
    value_type _Ch,
    const allocator_type& _Al);

template <class InputIterator>
basic_string(
    InputIterator first,
    InputIterator last);

template <class InputIterator>
basic_string(
    InputIterator first,
    InputIterator last,
    const allocator_type& _Al);

basic_string(
    const_pointer first,
    const_pointer last);

basic_string(
    const_iterator first,
    const_iterator last);
```

### <a name="parameters"></a>Parameter

*ptr*<br/>
Die C-Zeichenfolge, deren Zeichen verwendet werden, um die erstellte `string` zu initialisieren. Dieser Wert darf kein Nullzeiger sein.

*_Al*<br/>
Der Speicherzuordnerklasse für das Zeichenfolgenobjekt, das erstellt wird.

*count*<br/>
Die Anzahl der zu initialisierenden Zeichen.

*right*<br/>
Die Zeichenfolge zum Initialisieren der zu erstellenden Zeichenfolge.

*_Roff*<br/>
Der Index eines Zeichens in einer Zeichenfolge, die als erste verwendet wird, um Zeichenwerte für die zu erstellende Zeichenfolge zu initialisieren.

*_Ch*<br/>
Der Zeichenwert, der in die zu erstellende Zeichenfolge kopiert werden soll.

*first*<br/>
Ein Eingabeiterator, const_pointer oder const_iterator, der das erste Element im einzufügenden Quellbereich adressiert.

*last*<br/>
Ein Eingabeiterator, const_pointer oder const_iterator, der die Position eines der letzten Elemente im einzufügenden Quellbereich adressiert.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Zeichenfolgenobjekt, das von den Konstruktoren erstellt wird.

### <a name="remarks"></a>Hinweise

Von allen Konstruktoren wird ein [basic_string::allocator_type](#allocator_type) gespeichert, und die gesteuerte Sequenz wird initialisiert. Das Zuweisungsobjekt ist das Argument `al`, sofern es vorhanden ist. Für den Kopierkonstruktor ist es `right.`[basic_string::get_allocator](#get_allocator)`()`. Andernfalls ist der Wert `Alloc()`.

Die gesteuerte Sequenz wird in eine Kopie der Operandensequenz initialisiert, die von den verbleibenden Operanden angegeben werden. Ein Konstruktor ohne Operandensequenz gibt eine leere gesteuerte Sequenz an. Wenn `InputIterator` ein ganzzahliger Typ in einem Vorlagenkonstruktor ist, verhält sich die Operandensequenz _F `irst,  last` wie `(size_type) first, (value_type) last`.

### <a name="example"></a>Beispiel

```cpp
// basic_string_ctor.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function initializing with a C-string
   const char *cstr1a = "Hello Out There.";
   basic_string <char> str1a ( cstr1a , 5);
   cout << "The string initialized by C-string cstr1a is: "
        << str1a << "." << endl;

   // The second member function initializing with a string
   string  str2a ( "How Do You Do" );
   basic_string <char> str2b ( str2a , 7 , 7 );
   cout << "The string initialized by part of the string cstr2a is: "
        << str2b << "." << endl;

   // The third member function initializing a string
   // with a number of characters of a specific value
   basic_string <char> str3a ( 5, '9' );
   cout << "The string initialized by five number 9s is: "
        << str3a << endl;

   // The fourth member function creates an empty string
   // and string with a specified allocator
   basic_string <char> str4a;
   string str4b;
   basic_string <char> str4c ( str4b.get_allocator( ) );
   if (str4c.empty ( ) )
      cout << "The string str4c is empty." << endl;
   else
      cout << "The string str4c is not empty." << endl;

   // The fifth member function initializes a string from
   // another range of characters
   string str5a ( "Hello World" );
   basic_string <char> str5b ( str5a.begin ( ) + 5 , str5a.end ( ) );
   cout << "The string initialized by another range is: "
        << str5b << "." << endl;
}
```

## <a name="begin"></a> basic_string::begin

Gibt ein Iterator zurück, der das erste Element in der Zeichenfolge adressiert.

```cpp
const_iterator begin() const;

iterator begin();
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator mit wahlfreiem Zugriff, der das erste Element der Sequenz oder den Punkt unmittelbar nach dem Ende einer leeren Sequenz adressiert.

### <a name="example"></a>Beispiel

```cpp
// basic_string_begin.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( ) {
   using namespace std;
   string str1 ( "No way out." ), str2;
   basic_string <char>::iterator strp_Iter, str1_Iter, str2_Iter;
   basic_string <char>::const_iterator str1_cIter;

   str1_Iter = str1.begin ( );
   cout << "The first character of the string str1 is: "
        << *str1_Iter << endl;
   cout << "The full original string str1 is: " << str1 << endl;

   // The dereferenced iterator can be used to modify a character
*str1_Iter = 'G';
   cout << "The first character of the modified str1 is now: "
        << *str1_Iter << endl;
   cout << "The full modified string str1 is now: " << str1 << endl;

   // The following line would be an error because iterator is const
   // *str1_cIter = 'g';

   // For an empty string, begin is equivalent to end
   if (  str2.begin ( ) == str2.end ( ) )
      cout << "The string str2 is empty." << endl;
   else
      cout << "The string str2 is not empty." << endl;
}
```

## <a name="c_str"></a> basic_string::c_str

Konvertiert den Inhalt einer Zeichenfolge in einen NULL-terminierten C-String.

```cpp
const value_type *c_str() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die im C-Stil angegebene Version der aufrufenden Zeichenfolge.  Der Zeigerwert ist nach Aufrufen einer nicht-konstanten Funktion nicht gültig. Dies betrifft auch den Destruktor in der Klasse „basic_string“ im Objekt.

### <a name="remarks"></a>Hinweise

Objekte des Typs „String“, die zur C++-Vorlagenklasse „basic_string\<char>“ gehören, enden nicht unbedingt auf NULL. Das NULL-Zeichen „\0„ wird als Sonderzeichen in einer C-Zeichenfolge verwendet, um das Ende einer Zeichenfolge zu markieren. Es hat allerdings keine besondere Bedeutung in einem Objekt des Typs „string“ und kann genau wie jedes andere Zeichen ein Teil der Zeichenfolge sein. Es wird eine automatische Konvertierung von **const Char** <strong>\*</strong> in Zeichenfolgen, sondern die Zeichenfolge-Klasse bietet keine automatische Konvertierung von Zeichenfolgen im C-Format in Objekte des Typs **"basic_string"\<Char >**.

Die zurückgegebene Zeichenfolge im C-Format darf nicht geändert werden, weil dadurch der Zeiger auf die Zeichenfolge ungültig oder gelöscht werden könnte. Das liegt daran, dass die Lebensdauer des Zeigers eingeschränkt und sein Besitzer die Klasse „string“ ist.

### <a name="example"></a>Beispiel

```cpp
// basic_string_c_str.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   string  str1 ( "Hello world" );
   cout << "The original string object str1 is: "
        << str1 << endl;
   cout << "The length of the string object str1 = "
        << str1.length ( ) << endl << endl;

   // Converting a string to an array of characters
   const char *ptr1 = 0;
   ptr1= str1.data ( );
   cout << "The modified string object ptr1 is: " << ptr1
        << endl;
   cout << "The length of character array str1 = "
        << strlen ( ptr1) << endl << endl;

   // Converting a string to a C-style string
   const char *c_str1 = str1.c_str ( );
   cout << "The C-style string c_str1 is: " << c_str1
        << endl;
   cout << "The length of C-style string str1 = "
        << strlen ( c_str1) << endl << endl;
}
```

```Output
The original string object str1 is: Hello world
The length of the string object str1 = 11

The modified string object ptr1 is: Hello world
The length of character array str1 = 11

The C-style string c_str1 is: Hello world
The length of C-style string str1 = 11
```

## <a name="capacity"></a> basic_string::capacity

Gibt die höchste Anzahl von Elementen zurück, die ohne Erhöhung der Speicherbelegung der Zeichenfolge in einer Zeichenfolge gespeichert werden können.

```cpp
size_type capacity() const;
```

### <a name="return-value"></a>Rückgabewert

Die Größe des Speicherplatzes, der im Arbeitsspeicher zugewiesen ist, um die Zeichenfolge einzuschließen.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt den Speicherplatz zurück, der aktuell zugewiesen ist, um die kontrollierte Sequenz zu enthalten. Der Wert muss mindestens so groß sein wie [size](#size).

### <a name="example"></a>Beispiel

```cpp
// basic_string_capacity.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string  str1 ("Hello world");
   cout << "The original string str1 is: " << str1 << endl;

   // The size and length member functions differ in name only
   basic_string <char>::size_type sizeStr1, lenStr1;
   sizeStr1 = str1.size ( );
   lenStr1 = str1.length ( );

   basic_string <char>::size_type capStr1, max_sizeStr1;
   capStr1 = str1.capacity ( );
   max_sizeStr1 = str1.max_size ( );

   // Compare size, length, capacity & max_size of a string
   cout << "The current size of original string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The current length of original string str1 is: "
        << lenStr1 << "." << endl;
   cout << "The capacity of original string str1 is: "
        << capStr1 << "." << endl;
   cout << "The max_size of original string str1 is: "
        << max_sizeStr1 << "." << endl << endl;

   str1.erase ( 6, 5 );
   cout << "The modified string str1 is: " << str1 << endl;

   sizeStr1 = str1.size (  );
   lenStr1 = str1.length (  );
   capStr1 = str1.capacity (  );
   max_sizeStr1 = str1.max_size (  );

   // Compare size, length, capacity & max_size of a string
   // after erasing part of the original string
   cout << "The current size of modified string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The current length of modified string str1 is: "
        << lenStr1 << "." << endl;
   cout << "The capacity of modified string str1 is: "
        << capStr1 << "." << endl;
   cout << "The max_size of modified string str1 is: "
        << max_sizeStr1 << "." << endl;
}
```

## <a name="cbegin"></a> basic_string::cbegin

Gibt eine **const** -Iterator, der das erste Element im Bereich adressiert.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Rückgabewert

Ein **const** Iterator mit wahlfreiem Zugriff, der verweist auf das erste Element des Bereichs, oder die Position direkt hinter das Ende eines leeren Bereichs (für einen leeren Bereich gilt `cbegin() == cend()`).

### <a name="remarks"></a>Hinweise

Bei dem Rückgabewert `cbegin` können die Elemente im Bereich nicht geändert werden.

Sie können diese Memberfunktion anstelle der `begin()`-Memberfunktion verwenden, um sicherzustellen, dass der Rückgabewert `const_iterator` ist. Normalerweise wird sie zusammen mit dem [auto](../cpp/auto-cpp.md)-Typableitungs-Schlüsselwort verwendet, wie im folgenden Beispiel gezeigt. In diesem Beispiel können Sie auch `Container` ein beliebiger änderbarer (nicht- **const**) Container jeder Art, die unterstützt `begin()` und `cbegin()`.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a> basic_string::cend

Gibt eine **const** Iterator, der die Position direkt hinter dem letzten Element in einem Bereich.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Rückgabewert

Ein **const** Iterator mit wahlfreiem Zugriff, der direkt hinter das Ende des Bereichs verweist.

### <a name="remarks"></a>Hinweise

`cend` wird verwendet, um zu testen, ob ein Iterator das Ende seines Bereichs übergeben hat.

Sie können diese Memberfunktion anstelle der `end()`-Memberfunktion verwenden, um sicherzustellen, dass der Rückgabewert `const_iterator` ist. Normalerweise wird sie zusammen mit dem [auto](../cpp/auto-cpp.md)-Typableitungs-Schlüsselwort verwendet, wie im folgenden Beispiel gezeigt. In diesem Beispiel können Sie auch `Container` ein beliebiger änderbarer (nicht- **const**) Container jeder Art, die unterstützt `end()` und `cend()`.

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

Der von `cend` zurückgegebene Wert darf nicht dereferenziert werden.

## <a name="clear"></a> basic_string::clear

Löscht alle Elemente einer Zeichenfolge.

```cpp
void clear();
```

### <a name="remarks"></a>Hinweise

Die Zeichenfolge, für die die Memberfunktion aufgerufen wird, ist leer.

### <a name="example"></a>Beispiel

```cpp
// basic_string_clear.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string  str1 ("Hello world"), str2;
   basic_string <char>::iterator str_Iter;
   cout << "The original string str1 is: ";
   for ( str_Iter = str1.begin( ); str_Iter != str1.end( ); str_Iter++ )
      cout << *str_Iter;
   cout << endl;

   str1.clear ( );
   cout << "The modified string str1 is: ";
   for ( str_Iter = str1.begin( ); str_Iter != str1.end( ); str_Iter++ )
      cout << *str_Iter;
   cout << endl;

   //For an empty string, begin is equivalent to end
   if ( str1.begin ( ) == str1.end ( ) )
      cout << "Nothing printed above because "
           << "the string str1 is empty." << endl;
   else
      cout << "The string str1 is not empty." << endl;
}
```

```Output
The original string str1 is: Hello world
The modified string str1 is:
Nothing printed above because the string str1 is empty.
```

## <a name="compare"></a> basic_string::compare

Führt einen Vergleich unter Berücksichtigung der Groß-/Kleinschreibung mit einer angegebenen Zeichenfolge aus, um zu bestimmen, ob die beiden Zeichenfolgen gleich sind, oder ob eine lexikografisch kleiner als die andere ist.

```cpp
int compare(
    const basic_string<CharType, Traits, Allocator>& str) const;

int compare(
    size_type _Pos1,
    size_type _Num1,
    const basic_string<CharType, Traits, Allocator>& str) const;

int compare(
    size_type _Pos1,
    size_type _Num1,
    const basic_string<CharType, Traits, Allocator>& str,
    size_type _Off,
    size_type count) const;

int compare(
    const value_type* ptr) const;

int compare(
    size_type _Pos1,
    size_type _Num1,
    const value_type* ptr) const;

int compare(
    size_type _Pos1,
    size_type _Num1,
    const value_type* ptr
    size_type _Num2) const;
```

### <a name="parameters"></a>Parameter

*str*<br/>
Die Zeichenfolge, die mit der Operandenzeichenfolge verglichen werden soll.

*_Pos1*<br/>
Der Index der Operandenzeichenfolge, an dem der Vergleich beginnt.

*_Num1*<br/>
Die maximale Anzahl von Zeichen aus der Operandenzeichenfolge, die verglichen werden soll.

*_Num2*<br/>
Die maximale Anzahl von Zeichen aus der Parameterzeichenfolge, die verglichen werden soll.

*_Off*<br/>
Der Index der Parameterzeichenfolge, an dem der Vergleich beginnt.

*count*<br/>
Die maximale Anzahl von Zeichen aus der Parameterzeichenfolge, die verglichen werden soll.

*ptr*<br/>
Die C-Zeichenfolge, die mit der Operandenzeichenfolge verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

Ein negativer Wert, wenn die Operandenzeichenfolge kleiner ist als die Parameterzeichenfolge; 0, wenn die beiden Zeichenfolgen gleich sind; ein positiver Wert, wenn die Operandenzeichenfolge größer ist als die Parameterzeichenfolge.

### <a name="remarks"></a>Hinweise

Die `compare` Memberfunktionen verglichen werden soll, entweder vollständig oder teilweise der Parameter- und operandenzeichenfolgen Zeichenfolgen je nachdem, welche verwendet.

Beim Vergleich wird die Groß-/Kleinschreibung berücksichtigt.

### <a name="example"></a>Beispiel

```cpp
// basic_string_compare.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function compares
   // an operand string to a parameter string
   int comp1;
   string s1o ( "CAB" );
   string s1p ( "CAB" );
   cout << "The operand string is: " << s1o << endl;
   cout << "The parameter string is: " << s1p << endl;
   comp1 = s1o.compare ( s1p );
   if ( comp1 < 0 )
      cout << "The operand string is less than "
           << "the parameter string." << endl;
   else if ( comp1 == 0 )
      cout << "The operand string is equal to "
           << "the parameter string." << endl;
   else
      cout << "The operand string is greater than "
           << "the parameter string." << endl;
   cout << endl;

   // The second member function compares part of
   // an operand string to a parameter string
   int comp2a, comp2b;
   string s2o ( "AACAB" );
   string s2p ( "CAB" );
   cout << "The operand string is: " << s2o << endl;
   cout << "The parameter string is: " << s2p << endl;
   comp2a = s2o.compare (  2 , 3 , s2p );
   if ( comp2a < 0 )
      cout << "The last three characters of "
           << "the operand string\n are less than "
           << "the parameter string." << endl;
   else if ( comp2a == 0 )
      cout << "The last three characters of "
           << "the operand string\n are equal to "
           << "the parameter string." << endl;
   else
      cout << "The last three characters of "
           << "the operand string\n is greater than "
           << "the parameter string." << endl;

   comp2b = s2o.compare (  0 , 3 , s2p );
   if ( comp2b < 0 )
      cout << "The first three characters of "
           << "the operand string\n are less than "
           << "the parameter string." << endl;
   else if ( comp2b == 0 )
      cout << "The first three characters of "
           << "the operand string\n are equal to "
           << "the parameter string." << endl;
   else
      cout << "The first three characters of "
           << "the operand string\n is greater than "
           << "the parameter string." << endl;
   cout << endl;

   // The third member function compares part of
   // an operand string to part of a parameter string
   int comp3a;
   string s3o ( "AACAB" );
   string s3p ( "DCABD" );
   cout << "The operand string is: " << s3o << endl;
   cout << "The parameter string is: " << s3p << endl;
   comp3a = s3o.compare (  2 , 3 , s3p , 1 , 3 );
   if ( comp3a < 0 )
      cout << "The three characters from position 2 of "
           << "the operand string are less than\n "
           << "the 3 characters parameter string "
           << "from position 1." << endl;
   else if ( comp3a == 0 )
      cout << "The three characters from position 2 of "
           << "the operand string are equal to\n "
           << "the 3 characters parameter string "
           << "from position 1." << endl;
   else
      cout << "The three characters from position 2 of "
           << "the operand string is greater than\n "
           << "the 3 characters parameter string "
           << "from position 1." << endl;
   cout << endl;

   // The fourth member function compares
   // an operand string to a parameter C-string
   int comp4a;
   string s4o ( "ABC" );
   const char* cs4p = "DEF";
   cout << "The operand string is: " << s4o << endl;
   cout << "The parameter C-string is: " << cs4p << endl;
   comp4a = s4o.compare ( cs4p );
   if ( comp4a < 0 )
      cout << "The operand string is less than "
           << "the parameter C-string." << endl;
   else if ( comp4a == 0 )
      cout << "The operand string is equal to "
           << "the parameter C-string." << endl;
   else
      cout << "The operand string is greater than "
           << "the parameter C-string." << endl;
   cout << endl;

   // The fifth member function compares part of
   // an operand string to a parameter C-string
   int comp5a;
   string s5o ( "AACAB" );
   const char* cs5p = "CAB";
   cout << "The operand string is: " << s5o << endl;
   cout << "The parameter string is: " << cs5p << endl;
   comp5a = s5o.compare (  2 , 3 , s2p );
   if ( comp5a < 0 )
      cout << "The last three characters of "
           << "the operand string\n are less than "
           << "the parameter C-string." << endl;
   else if ( comp5a == 0 )
      cout << "The last three characters of "
           << "the operand string\n are equal to "
           << "the parameter C-string." << endl;
   else
      cout << "The last three characters of "
           << "the operand string\n is greater than "
           << "the parameter C-string." << endl;
   cout << endl;

   // The sixth member function compares part of
   // an operand string to part of an equal length of
   // a parameter C-string
   int comp6a;
   string s6o ( "AACAB" );
   const char* cs6p = "ACAB";
   cout << "The operand string is: " << s6o << endl;
   cout << "The parameter C-string is: " << cs6p << endl;
   comp6a = s6o.compare (  1 , 3 , cs6p , 3 );
   if ( comp6a < 0 )
      cout << "The 3 characters from position 1 of "
           << "the operand string are less than\n "
           << "the first 3 characters of the parameter C-string."
           << endl;
   else if ( comp6a == 0 )
      cout << "The 3 characters from position 2 of "
           << "the operand string are equal to\n "
           << "the first 3 characters of the parameter C-string."
           <<  endl;
   else
      cout << "The 3 characters from position 2 of "
           << "the operand string is greater than\n "
           << "the first 3 characters of the parameter C-string."
           << endl;
   cout << endl;
}
```

```Output
The operand string is: CAB
The parameter string is: CAB
The operand string is equal to the parameter string.

The operand string is: AACAB
The parameter string is: CAB
The last three characters of the operand string
are equal to the parameter string.
The first three characters of the operand string
are less than the parameter string.

The operand string is: AACAB
The parameter string is: DCABD
The three characters from position 2 of the operand string are equal to
the 3 characters parameter string from position 1.

The operand string is: ABC
The parameter C-string is: DEF
The operand string is less than the parameter C-string.

The operand string is: AACAB
The parameter string is: CAB
The last three characters of the operand string
are equal to the parameter C-string.

The operand string is: AACAB
The parameter C-string is: ACAB
The 3 characters from position 2 of the operand string are equal to
the first 3 characters of the parameter C-string.
```

## <a name="const_iterator"></a> basic_string::const_iterator

Ein Typ, der einen Iterator mit wahlfreiem Zugriff bereitstellt, mit dem auf ein **const**-Element zugegriffen wird, und mit dem dieses Element gelesen werden kann.

```cpp
typedef implementation-defined const_iterator;
```

### <a name="remarks"></a>Hinweise

Ein Typ `const_iterator` kann nicht zum Ändern des Werts eines Zeichens verwendet werden und wird verwendet, um eine Zeichenfolge vorwärts zu durchlaufen.

### <a name="example"></a>Beispiel

Im Beispiel für [begin](#begin) wird verdeutlicht, wie ein `const_iterator` deklariert und verwendet wird.

## <a name="const_pointer"></a> basic_string::const_pointer

Ein Typ, der einen Zeiger auf ein **const**-Element in einer Zeichenfolge bereitstellt.

```cpp
typedef typename allocator_type::const_pointer const_pointer;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `allocator_type::const_pointer`.

Für den Typ `string`, dies ist äquivalent zum `char*`.

Zeiger, die als „const“ deklariert werden, müssen beim Deklarieren initialisiert werden. Const-Zeiger zeigen immer auf den gleichen Speicherbereich und können auf konstante oder nicht konstante Daten zeigen.

### <a name="example"></a>Beispiel

```cpp
// basic_string_const_ptr.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   basic_string<char>::const_pointer pstr1a = "In Here";
   const char *cstr1c = "Out There";

   cout << "The string pstr1a is: " << pstr1a <<  "." << endl;
   cout << "The C-string cstr1c is: " << cstr1c << "." << endl;
}
```

```Output
The string pstr1a is: In Here.
The C-string cstr1c is: Out There.
```

## <a name="const_reference"></a> basic_string::const_reference

Ein Typ, der einen Verweis auf ein **const**-Element bereitstellt, das in einer Liste zum Lesen und Ausführen von **const**-Vorgängen gespeichert ist.

```cpp
typedef typename allocator_type::const_reference const_reference;
```

### <a name="remarks"></a>Hinweise

Ein `const_reference`-Typ kann nicht zum Ändern des Werts eines Elements verwendet werden.

Der Typ ist ein Synonym für `allocator_type::const_reference`. Für die Zeichenfolge `type`, dies ist äquivalent zu "const" `char&`.

### <a name="example"></a>Beispiel

Im Beispiel für [t](#at) wird verdeutlicht, wie ein `const_reference` deklariert und verwendet wird.

## <a name="const_reverse_iterator"></a> basic_string::const_reverse_iterator

Ein Typ, der einen Iterator mit wahlfreiem Zugriff bereitstellt, mit dem jedes **const**-Element in der Zeichenfolge gelesen werden kann.

```cpp
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;
```

### <a name="remarks"></a>Hinweise

Ein Typ `const_reverse_iterator` kann den Wert eines Zeichens nicht ändern und wird verwendet, um die Zeichenfolge in umgekehrter Reihenfolge zu durchlaufen.

### <a name="example"></a>Beispiel

Im Beispiel für [rbegin](#rbegin) wird verdeutlicht, wie ein `const_reverse_iterator` deklariert und verwendet wird.

## <a name="copy"></a> basic_string::copy

Kopiert höchstens eine angegebene Anzahl von Zeichen aus einer indizierten Position in einer Quellzeichenfolge in ein Zielzeichenarray.

Diese Methode ist potenziell unsicher, da sie darauf basiert, dass der Aufrufer überprüft, ob die übergebenen Werte korrekt sind. Verwenden Sie stattdessen [basic_string::_Copy_s](#copy_s).

```cpp
size_type copy(
    value_type* ptr,
    size_type count,
    size_type _Off = 0) const;
```

### <a name="parameters"></a>Parameter

*ptr*<br/>
Das Zielzeichenarray, in das die Elemente kopiert werden sollen.

_ *Anzahl* die Anzahl der Zeichen, höchstens aus der Quellzeichenfolge kopiert werden.

*_Off*<br/>
Die Anfangsposition in der Quellzeichenfolge, ab der Kopien erstellt werden dürfen.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der tatsächlich kopierten Zeichen.

### <a name="remarks"></a>Hinweise

Es wird kein NULL-Zeichen ans Ende der Kopie angefügt.

### <a name="example"></a>Beispiel

```cpp
// basic_string_copy.cpp
// compile with: /EHsc /W3
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ( "Hello World" );
   basic_string <char>::iterator str_Iter;
   char array1 [ 20 ] = { 0 };
   char array2 [ 10 ] = { 0 };
   basic_string <char>:: pointer array1Ptr = array1;
   basic_string <char>:: value_type *array2Ptr = array2;

   cout << "The original string str1 is: ";
   for ( str_Iter = str1.begin( ); str_Iter != str1.end( ); str_Iter++ )
      cout << *str_Iter;
   cout << endl;

   basic_string <char>:: size_type nArray1;
   // Note: string::copy is potentially unsafe, consider
   // using string::_Copy_s instead.
   nArray1 = str1.copy ( array1Ptr , 12 );  // C4996
   cout << "The number of copied characters in array1 is: "
        << nArray1 << endl;
   cout << "The copied characters array1 is: " << array1 << endl;

   basic_string <char>:: size_type nArray2;
   // Note: string::copy is potentially unsafe, consider
   // using string::_Copy_s instead.
   nArray2 = str1.copy ( array2Ptr , 5 , 6  );  // C4996
   cout << "The number of copied characters in array2 is: "
           << nArray2 << endl;
   cout << "The copied characters array2 is: " << array2Ptr << endl;
}
```

```Output
The original string str1 is: Hello World
The number of copied characters in array1 is: 11
The copied characters array1 is: Hello World
The number of copied characters in array2 is: 5
The copied characters array2 is: World
```

## <a name="crbegin"></a> basic_string::crbegin

Gibt einen const-Iterator zurück, der das erste Element in einer umgekehrter Zeichenfolge adressiert.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Rückgabewert

Ein reverse-Iterator, der auf die Position unmittelbar hinter dem Ende der Zeichenfolge verweist. Die Position kennzeichnet den Anfang der umgekehrten Zeichenfolge.

## <a name="crend"></a> basic_string::crend

Gibt einen const-Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer umgekehrten Zeichenfolge nachfolgt.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Rückgabewert

Ein const_reverse-Iterator, der auf den Speicherort verweist, der dem letzten Element in einer umgekehrten Zeichenfolge nachfolgt (der Speicherort, der dem ersten Element in der nicht umgekehrten Zeichenfolge vorangegangen war).

### <a name="remarks"></a>Hinweise

## <a name="copy_s"></a> basic_string::_Copy_s

Kopiert höchstens eine angegebene Anzahl von Zeichen aus einer indizierten Position in einer Quellzeichenfolge in ein Zielzeichenarray.

```cpp
size_type _Copy_s(
    value_type* dest,
    size_type dest_size,
    size_type count,
    size_type _Off = 0) const;
```

### <a name="parameters"></a>Parameter

*dest*<br/>
Das Zielzeichenarray, in das die Elemente kopiert werden sollen.

*dest_size*<br/>
Die Größe des *Dest*.

_ *Anzahl* die Anzahl der Zeichen, höchstens aus der Quellzeichenfolge kopiert werden.

*_Off*<br/>
Die Anfangsposition in der Quellzeichenfolge, ab der Kopien erstellt werden dürfen.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der tatsächlich kopierten Zeichen.

### <a name="remarks"></a>Hinweise

Es wird kein NULL-Zeichen ans Ende der Kopie angefügt.

### <a name="example"></a>Beispiel

```cpp
// basic_string__Copy_s.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
    using namespace std;
    string str1("Hello World");
    basic_string<char>::iterator str_Iter;
    const int array1_size = 20;
    char array1[array1_size] = { 0 };
    const int array2_size = 10;
    char array2[array2_size] = { 0 };
    basic_string<char>:: pointer array1Ptr = array1;
    basic_string<char>:: value_type *array2Ptr = array2;

    cout << "The original string str1 is: ";
    for (str_Iter = str1.begin(); str_Iter != str1.end(); str_Iter++)
        cout << *str_Iter;
    cout << endl;

    basic_string<char>::size_type nArray1;
    nArray1 = str1._Copy_s(array1Ptr, array1_size, 12);
    cout << "The number of copied characters in array1 is: "
         << nArray1 << endl;
    cout << "The copied characters array1 is: " << array1 << endl;

    basic_string<char>:: size_type nArray2;
    nArray2 = str1._Copy_s(array2Ptr, array2_size, 5, 6);
    cout << "The number of copied characters in array2 is: "
         << nArray2 << endl;
    cout << "The copied characters array2 is: " << array2Ptr << endl;
}
```

```Output
The original string str1 is: Hello World
The number of copied characters in array1 is: 11
The copied characters array1 is: Hello World
The number of copied characters in array2 is: 5
The copied characters array2 is: World
```

## <a name="data"></a> basic_string::data

Konvertiert den Inhalt einer Zeichenfolge in ein Zeichenarray.

```cpp
const value_type *data() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das erste Element des Arrays, das die Inhalte der Zeichenfolge enthält. Bei einem leeren Array ein Nicht-NULL-Zeiger, der nicht dereferenziert werden kann.

### <a name="remarks"></a>Hinweise

Objekte des Typs „String“, die zur C++-Vorlagenklasse „basic_string \<char>“ gehören, enden nicht unbedingt auf NULL. Der Rückgabetyp für `data` ist nicht gültige C-Zeichenfolge ist, da kein Null-Zeichen angehängt wird. Das NULL-Zeichen „\0“ wird als Sonderzeichen in einer C-Zeichenfolge verwendet, um das Ende einer Zeichenfolge zu markieren. Es hat allerdings keine besondere Bedeutung in einem Objekt des Typs „string“ und kann genau wie jedes andere Zeichen ein Teil des Zeichenfolgenobjekts sein.

Es wird eine automatische Konvertierung von **const Char** <strong>\*</strong> in Zeichenfolgen, sondern die Zeichenfolge-Klasse bietet keine automatische Konvertierung von Zeichenfolgen im C-Format in Objekte des Typs **"basic_string" \<Char >**.

Die zurückgegebene Zeichenfolge sollte nicht geändert werden, da dadurch der Zeiger auf die Zeichenfolge für ungültig erklärt oder gelöscht werden könnte, da die Lebensdauer des Zeigers eingeschränkt ist, und er im Besitz der Klasse „string“ ist.

### <a name="example"></a>Beispiel

```cpp
// basic_string_data.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   string str1 ( "Hello world" );
   cout << "The original string object str1 is: "
        << str1 << endl;
   cout << "The length of the string object str1 = "
        << str1.length ( ) << endl << endl;

   // Converting a string to an array of characters
   const char *ptr1 = 0;
   ptr1= str1.data ( );
   cout << "The modified string object ptr1 is: " << ptr1
        << endl;
   cout << "The length of character array str1 = "
        << strlen ( ptr1) << endl << endl;

   // Converting a string to a C-style string
   const char *c_str1 = str1.c_str ( );
   cout << "The C-style string c_str1 is: " << c_str1
        << endl;
   cout << "The length of C-style string str1 = "
        << strlen ( c_str1) << endl << endl;
}
```

```Output
The original string object str1 is: Hello world
The length of the string object str1 = 11

The modified string object ptr1 is: Hello world
The length of character array str1 = 11

The C-style string c_str1 is: Hello world
The length of C-style string str1 = 11
```

## <a name="difference_type"></a> basic_string::difference_type

Ein Typ, der den Unterschied zwischen zwei Iteratoren, die auf Elemente innerhalb derselben Zeichenfolge verweisen, bereitstellt.

```cpp
typedef typename allocator_type::difference_type difference_type;
```

### <a name="remarks"></a>Hinweise

Der Ganzzahltyp mit Vorzeichen beschreibt ein Objekt, das die Differenz zwischen den Adressen von zwei beliebigen Elementen in der gesteuerten Sequenz darstellen kann.

Für den Typ `string`, dies ist äquivalent zum `ptrdiff_t`.

### <a name="example"></a>Beispiel

```cpp
// basic_string_diff_type.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ( "quintillion" );
   cout << "The original string str1 is: " << str1 << endl;
   basic_string <char>::size_type indexChFi, indexChLi;

   indexChFi = str1.find_first_of ( "i" );
   indexChLi = str1.find_last_of ( "i" );
   basic_string<char>::difference_type diffi = indexChLi - indexChFi;

   cout << "The first character i is at position: "
        << indexChFi << "." << endl;
   cout << "The last character i is at position: "
        << indexChLi << "." << endl;
   cout << "The difference is: " << diffi << "." << endl;
}
```

```Output
The original string str1 is: quintillion
The first character i is at position: 2.
The last character i is at position: 8.
The difference is: 6.
```

## <a name="empty"></a> basic_string::empty

Testet, ob in der Zeichenfolge Zeichen enthalten sind oder nicht.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn das Zeichenfolgenobjekt keine Zeichen enthält; **FALSE**, wenn es mindestens ein Zeichen enthält.

### <a name="remarks"></a>Hinweise

Die Memberfunktion entspricht [size](#size) == 0.

### <a name="example"></a>Beispiel

```cpp
// basic_string_empty.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main() {
   using namespace std;

   bool b1, b2;

   string str1 ("Hello world");
   cout << "The original string object str1 is: " << str1 << endl;
   b1 = str1.empty();
   if (b1)
      cout << "The string object str1 is empty." << endl;
   else
      cout << "The string object str1 is not empty." << endl;
   cout << endl;

   // An example of an empty string object
   string str2;
   b2 = str2.empty();
   if (b2)
      cout << "The string object str2 is empty." << endl;
   else
      cout << "The string object str2 is not empty." << endl;
}
```

## <a name="end"></a> basic_string::end

Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer Zeichenfolge nachfolgt.

```cpp
const_iterator end() const;

iterator end();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Iterator mit wahlfreiem Zugriff zurück, der den Speicherort adressiert, der dem letzten Element in einer Zeichenfolge nachfolgt.

### <a name="remarks"></a>Hinweise

`end` wird häufig verwendet, um zu testen, ob ein Iterator das Ende seiner Zeichenfolge erreicht hat. Der von `end` zurückgegebene Wert darf nicht dereferenziert werden.

Wenn der Rückgabewert von `end` zu `const_iterator` zugewiesen wird, kann das Zeichenfolgenobjekt nicht geändert werden. Wenn der Rückgabewert von `end` zugewiesen ist ein `iterator`, kann das Zeichenfolgenobjekt geändert werden.

### <a name="example"></a>Beispiel

```cpp
// basic_string_end.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ( "No way out." ), str2;
   basic_string <char>::iterator str_Iter, str1_Iter, str2_Iter;
   basic_string <char>::const_iterator str1_cIter;

   str1_Iter = str1.end ( );
   str1_Iter--;
   str1_Iter--;
   cout << "The last character-letter of the string str1 is: " << *str1_Iter << endl;
   cout << "The full orginal string str1 is: " << str1 << endl;

   // end used to test when an iterator has reached the end of its string
   cout << "The string is now: ";
   for ( str_Iter = str1.begin( ); str_Iter != str1.end( ); str_Iter++ )
      cout << *str_Iter;
   cout << endl;

   // The dereferenced iterator can be used to modify a character
*str1_Iter = 'T';
   cout << "The last character-letter of the modified str1 is now: "
        << *str1_Iter << endl;
   cout << "The modified string str1 is now: " << str1 << endl;

   // The following line would be an error because iterator is const
   // *str1_cIter = 'T';

   // For an empty string, end is equivalent to begin
   if ( str2.begin( ) == str2.end ( ) )
      cout << "The string str2 is empty." << endl;
   else
      cout << "The stringstr2  is not empty." << endl;
}
```

```Output
The last character-letter of the string str1 is: t
The full orginal string str1 is: No way out.
The string is now: No way out.
The last character-letter of the modified str1 is now: T
The modified string str1 is now: No way ouT.
The string str2 is empty.
```

## <a name="erase"></a> basic_string::erase

Entfernt ein Element oder einen Reihe von Elementen einer Zeichenfolge von einer angegebenen Position.

```cpp
iterator erase(
    iterator first,
    iterator last);

iterator erase(
    iterator _It);

basic_string<CharType, Traits, Allocator>& erase(
    size_type _Pos = 0,
    size_type count = npos);
```

### <a name="parameters"></a>Parameter

*first*<br/>
Ein Iterator, der die Position des ersten Elements im zu löschenden Bereich adressiert.

*last*<br/>
Ein Iterator, der die Position adressiert, die um 1 höher ist als die Position des letzten Elements im zu löschenden Bereich.

*_It*<br/>
Ein Iterator, der die Position des Elements in der zu löschenden Zeichenfolge adressiert.

*_Pos*<br/>
Der Index des ersten Zeichens in der zu löschenden Zeichenfolge.

*count*<br/>
Die Anzahl der Elemente, die gelöscht werden, sofern im Bereich der mit *_Pos* beginnenden Zeichenfolge entsprechend viele Elemente vorhanden sind.

### <a name="return-value"></a>Rückgabewert

Bei den ersten beiden Memberfunktionen adressiert ein Iterator das erste Zeichen nach dem letzten Zeichen, das von der Memberfunktion entfernt wurde. Bei der dritten Memberfunktion ein Verweis auf das Zeichenfolgenobjekt, aus dem die Elemente gelöscht wurden.

### <a name="remarks"></a>Hinweise

Die dritte Memberfunktion gibt **\*this** zurück.

### <a name="example"></a>Beispiel

```cpp
// basic_string_erase.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The 1st member function using a range demarcated
   // by iterators
   string str1 ( "Hello world" );
   basic_string <char>::iterator str1_Iter;
   cout << "The original string object str1 is: "
        << str1 << "." << endl;
   str1_Iter = str1.erase ( str1.begin ( ) + 3 , str1.end ( ) - 1 );
   cout << "The first element after those removed is: "
        << *str1_Iter << "." << endl;
   cout << "The modified string object str1 is: " << str1
           << "." << endl << endl;

   // The 2nd member function erasing a char pointed to
   // by an iterator
   string str2 ( "Hello World" );
   basic_string <char>::iterator str2_Iter;
   cout << "The original string object str2 is: " << str2
        << "." << endl;
   str2_Iter = str2.erase ( str2.begin ( ) + 5 );
   cout << "The first element after those removed is: "
        << *str2_Iter << "." << endl;
   cout << "The modified string object str2 is: " << str2
        << "." << endl << endl;

   // The 3rd member function erasing a number of chars
   // after a char
   string str3 ( "Hello computer" ), str3m;
   basic_string <char>::iterator str3_Iter;
   cout << "The original string object str3 is: "
        << str3 << "." << endl;
   str3m = str3.erase ( 6 , 8 );
   cout << "The modified string object str3m is: "
        << str3m << "." << endl;
}
```

```Output
The original string object str1 is: Hello world.
The first element after those removed is: d.
The modified string object str1 is: Held.

The original string object str2 is: Hello World.
The first element after those removed is: W.
The modified string object str2 is: HelloWorld.

The original string object str3 is: Hello computer.
The modified string object str3m is: Hello .
```

## <a name="find"></a> basic_string::find

Sucht eine Zeichenfolge vorwärts nach dem ersten Vorkommen einer Teilzeichenfolge ab, die mit einer bestimmten Zeichensequenz übereinstimmt.

```cpp
size_type find(
    value_type _Ch,
    size_type _Off = 0) const;

size_type find(
    const value_type* ptr,
    size_type _Off = 0) const;

size_type find(
    const value_type* ptr,
    size_type _Off,
    size_type count) const;

size_type find(
    const basic_string<CharType, Traits, Allocator>& str,
    size_type _Off = 0) const;
```

### <a name="parameters"></a>Parameter

*_Ch*<br/>
Der Zeichenwert, nach dem die Memberfunktion suchen soll.

*_Off*<br/>
Index der Position, an der die Suche beginnen soll.

*ptr*<br/>
Die C-Zeichenfolge, nach der die Memberfunktion suchen soll.

*count*<br/>
Die Anzahl von Zeichen, vom ersten Zeichen vorwärts, in der C-Zeichenfolge nach der die Memberfunktion suchen soll.

*str*<br/>
Die Zeichenfolge, nach der die Memberfunktion suchen soll.

### <a name="return-value"></a>Rückgabewert

Der Index des ersten Zeichens der Teilzeichenfolge, nach der bei Erfolg gesucht wird; andernfalls `npos`.

### <a name="example"></a>Beispiel

```cpp
// basic_string_find.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function
   // searches for a single character in a string
   string str1 ( "Hello Everyone" );
   cout << "The original string str1 is: " << str1 << endl;
   basic_string <char>::size_type indexCh1a, indexCh1b;

   indexCh1a = str1.find ( "e" , 3 );
   if (indexCh1a != string::npos )
      cout << "The index of the 1st 'e' found after the 3rd"
           << " position in str1 is: " << indexCh1a << endl;
   else
      cout << "The character 'e' was not found in str1 ." << endl;

   indexCh1b = str1.find ( "x" );
   if (indexCh1b != string::npos )
      cout << "The index of the 'x' found in str1 is: "
           << indexCh1b << endl << endl;
   else
      cout << "The Character 'x' was not found in str1."
           << endl << endl;

   // The second member function searches a string
   // for a substring as specified by a C-string
   string str2 ( "Let me make this perfectly clear." );
   cout << "The original string str2 is: " << str2 << endl;
   basic_string <char>::size_type indexCh2a, indexCh2b;

   const char *cstr2 = "perfect";
   indexCh2a = str2.find ( cstr2 , 5 );
   if ( indexCh2a != string::npos )
      cout << "The index of the 1st element of 'perfect' "
           << "after\n the 5th position in str2 is: "
           << indexCh2a << endl;
   else
      cout << "The substring 'perfect' was not found in str2 ."
           << endl;

   const char *cstr2b = "imperfectly";
   indexCh2b = str2.find ( cstr2b , 0 );
   if (indexCh2b != string::npos )
      cout << "The index of the 1st element of 'imperfect' "
           << "after\n the 5th position in str3 is: "
           << indexCh2b << endl;
   else
      cout << "The substring 'imperfect' was not found in str2 ."
           << endl << endl;

   // The third member function searches a string
   // for a substring as specified by a C-string
   string str3 ( "This is a sample string for this program" );
   cout << "The original string str3 is: " << str3 << endl;
   basic_string <char>::size_type indexCh3a, indexCh3b;

   const char *cstr3a = "sample";
   indexCh3a = str3.find ( cstr3a );
   if ( indexCh3a != string::npos )
      cout << "The index of the 1st element of sample "
           << "in str3 is: " << indexCh3a << endl;
   else
      cout << "The substring 'perfect' was not found in str3 ."
           << endl;

   const char *cstr3b = "for";
   indexCh3b = str3.find ( cstr3b , indexCh3a + 1 , 2 );
   if (indexCh3b != string::npos )
      cout << "The index of the next occurrence of 'for' is in "
           << "str3 begins at: " << indexCh3b << endl << endl;
   else
      cout << "There is no next occurrence of 'for' in str3 ."
           << endl << endl;

   // The fourth member function searches a string
   // for a substring as specified by a string
   string str4 ( "clearly this perfectly unclear." );
   cout << "The original string str4 is: " << str4 << endl;
   basic_string <char>::size_type indexCh4a, indexCh4b;

   string str4a ( "clear" );
   indexCh4a = str4.find ( str4a , 5 );
   if ( indexCh4a != string::npos )
      cout << "The index of the 1st element of 'clear' "
           << "after\n the 5th position in str4 is: "
           << indexCh4a << endl;
   else
      cout << "The substring 'clear' was not found in str4 ."
           << endl;

   string str4b ( "clear" );
   indexCh4b = str4.find ( str4b );
   if (indexCh4b != string::npos )
      cout << "The index of the 1st element of 'clear' "
           << "in str4 is: "
           << indexCh4b << endl;
   else
      cout << "The substring 'clear' was not found in str4 ."
           << endl << endl;
}
```

```Output
The original string str1 is: Hello Everyone
The index of the 1st 'e' found after the 3rd position in str1 is: 8
The Character 'x' was not found in str1.

The original string str2 is: Let me make this perfectly clear.
The index of the 1st element of 'perfect' after
the 5th position in str2 is: 17
The substring 'imperfect' was not found in str2 .

The original string str3 is: This is a sample string for this program
The index of the 1st element of sample in str3 is: 10
The index of the next occurrence of 'for' is in str3 begins at: 24

The original string str4 is: clearly this perfectly unclear.
The index of the 1st element of 'clear' after
the 5th position in str4 is: 25
The index of the 1st element of 'clear' in str4 is: 0
```

## <a name="find_first_not_of"></a> basic_string::find_first_not_of

Durchsucht eine Zeichenfolge nach dem ersten Zeichen, das kein Element der angegebenen Zeichenfolge ist.

```cpp
size_type find_first_not_of(
    value_type _Ch,
    size_type _Off = 0) const;

size_type find_first_not_of(
    const value_type* ptr,
    size_type _Off = 0) const;

size_type find_first_not_of(
    const value_type* ptr,
    size_type _Off,
    size_type count) const;

size_type find_first_not_of(
    const basic_string<CharType, Traits, Allocator>& str,
    size_type _Off = 0) const;
```

### <a name="parameters"></a>Parameter

*_Ch*<br/>
Der Zeichenwert, nach dem die Memberfunktion suchen soll.

*_Off*<br/>
Index der Position, an der die Suche beginnen soll.

*ptr*<br/>
Die C-Zeichenfolge, nach der die Memberfunktion suchen soll.

*count*<br/>
Die Anzahl von Zeichen, vom ersten Zeichen vorwärts, in der C-Zeichenfolge nach der die Memberfunktion suchen soll.

*str*<br/>
Die Zeichenfolge, nach der die Memberfunktion suchen soll.

### <a name="return-value"></a>Rückgabewert

Der Index des ersten Zeichens der Teilzeichenfolge, nach der bei Erfolg gesucht wird; andernfalls `npos`.

### <a name="example"></a>Beispiel

```cpp
// basic_string_find_first_not_of.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function
   // searches for a single character in a string
   string str1 ( "xddd-1234-abcd" );
   cout << "The original string str1 is: " << str1 << endl;
   basic_string <char>::size_type indexCh1a, indexCh1b;
   static const basic_string <char>::size_type npos = -1;

   indexCh1a = str1.find_first_not_of ( "d" , 2 );
   if ( indexCh1a != npos )
      cout << "The index of the 1st 'd' found after the 3rd"
           << " position in str1 is: " << indexCh1a << endl;
   else
      cout << "The character 'd' was not found in str1 ." << endl;

   indexCh1b = str1.find_first_not_of  ( "x" );
   if (indexCh1b != npos )
      cout << "The index of the 'non x' found in str1 is: "
           << indexCh1b << endl << endl;
   else
      cout << "The character 'non x' was not found in str1."
           << endl << endl;

   // The second member function searches a string
   // for a substring as specified by a C-string
   string str2 ( "BBB-1111" );
   cout << "The original string str2 is: " << str2 << endl;
   basic_string <char>::size_type indexCh2a, indexCh2b;

   const char *cstr2 = "B1";
   indexCh2a = str2.find_first_not_of ( cstr2 , 6 );
   if ( indexCh2a != npos )
      cout << "The index of the 1st occurrence of an "
           << "element of 'B1' in str2 after\n the 6th "
           << "position is: " << indexCh2a << endl;
   else
      cout << "Elements of the substring 'B1' were not"
           << "\n found in str2 after the 6th position."
           << endl;

   const char *cstr2b = "B2";
   indexCh2b = str2.find_first_not_of ( cstr2b );
   if ( indexCh2b != npos )
      cout << "The index of the 1st element of 'B2' "
           << "after\n the 0th position in str2 is: "
           << indexCh2b << endl << endl;
   else
      cout << "The substring 'B2' was not found in str2 ."
           << endl << endl << endl;

   // The third member function searches a string
   // for a substring as specified by a C-string
   string str3 ( "444-555-GGG" );
   cout << "The original string str3 is: " << str3 << endl;
   basic_string <char>::size_type indexCh3a, indexCh3b;

   const char *cstr3a = "45G";
   indexCh3a = str3.find_first_not_of ( cstr3a );
   if ( indexCh3a != npos )
      cout << "The index of the 1st occurrence of an "
           << "element in str3\n other than one of the "
           << "characters in '45G' is: " << indexCh3a
           << endl;
   else
      cout << "Elements in str3 contain only characters "
           << " in the string '45G'. "
           << endl;

   const char *cstr3b = "45G";
   indexCh3b = str3.find_first_not_of ( cstr3b , indexCh3a + 1 , 2 );
   if ( indexCh3b != npos )
      cout << "The index of the second occurrence of an "
           << "element of '45G' in str3\n after the 0th "
           << "position is: " << indexCh3b << endl << endl;
   else
      cout << "Elements in str3 contain only characters "
           << " in the string  '45G'. "
           << endl  << endl;

   // The fourth member function searches a string
   // for a substring as specified by a string
   string str4 ( "12-ab-12-ab" );
   cout << "The original string str4 is: " << str4 << endl;
   basic_string <char>::size_type indexCh4a, indexCh4b;

   string str4a ( "ba3" );
   indexCh4a = str4.find_first_not_of ( str4a , 5 );
   if (indexCh4a != npos )
      cout << "The index of the 1st non occurrence of an "
           << "element of 'ba3' in str4 after\n the 5th "
           << "position is: " << indexCh4a << endl;
   else
      cout << "Elements other than those in the substring"
           << " 'ba3' were not found in the string str4."
           << endl;

   string str4b ( "12" );
   indexCh4b = str4.find_first_not_of ( str4b  );
   if (indexCh4b != npos )
      cout << "The index of the 1st non occurrence of an "
           << "element of '12' in str4 after\n the 0th "
           << "position is: " << indexCh4b << endl;
   else
      cout << "Elements other than those in the substring"
           << " '12' were not found in the string str4."
           << endl;
}
```

```Output
The original string str1 is: xddd-1234-abcd
The index of the 1st 'd' found after the 3rd position in str1 is: 4
The index of the 'non x' found in str1 is: 1

The original string str2 is: BBB-1111
Elements of the substring 'B1' were not
found in str2 after the 6th position.
The index of the 1st element of 'B2' after
the 0th position in str2 is: 3

The original string str3 is: 444-555-GGG
The index of the 1st occurrence of an element in str3
other than one of the characters in '45G' is: 3
The index of the second occurrence of an element of '45G' in str3
after the 0th position is: 7

The original string str4 is: 12-ab-12-ab
The index of the 1st non occurrence of an element of 'ba3' in str4 after
the 5th position is: 5
The index of the 1st non occurrence of an element of '12' in str4 after
the 0th position is: 2
```

## <a name="find_first_of"></a> basic_string::find_first_of

Durchsucht eine Zeichenfolge nach dem ersten Zeichen, das einem Element der angegebenen Zeichenfolge entspricht.

```cpp
size_type find_first_of(
    value_type _Ch,
    size_type _Off = 0) const;

size_type find_first_of(
    const value_type* ptr,
    size_type _Off = 0) const;

size_type find_first_of(
    const value_type* ptr,
    size_type _Off,
    size_type count) const;

size_type find_first_of(
    const basic_string<CharType, Traits, Allocator>& str,
    size_type _Off = 0) const;
```

### <a name="parameters"></a>Parameter

*_Ch*<br/>
Der Zeichenwert, nach dem die Memberfunktion suchen soll.

*_Off*<br/>
Index der Position, an der die Suche beginnen soll.

*ptr*<br/>
Die C-Zeichenfolge, nach der die Memberfunktion suchen soll.

*count*<br/>
Die Anzahl von Zeichen, vom ersten Zeichen vorwärts, in der C-Zeichenfolge nach der die Memberfunktion suchen soll.

*str*<br/>
Die Zeichenfolge, nach der die Memberfunktion suchen soll.

### <a name="return-value"></a>Rückgabewert

Der Index des ersten Zeichens der Teilzeichenfolge, nach der bei Erfolg gesucht wird; andernfalls `npos`.

### <a name="example"></a>Beispiel

```cpp
// basic_string_find_first_of.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function
   // searches for a single character in a string
   string str1 ( "abcd-1234-abcd-1234" );
   cout << "The original string str1 is: " << str1 << endl;
   basic_string <char>::size_type indexCh1a, indexCh1b;
   static const basic_string <char>::size_type npos = -1;

   indexCh1a = str1.find_first_of ( "d" , 5 );
   if ( indexCh1a != npos )
      cout << "The index of the 1st 'd' found after the 5th"
           << " position in str1 is: " << indexCh1a << endl;
   else
      cout << "The character 'd' was not found in str1 ." << endl;

   indexCh1b = str1.find_first_of ( "x" );
   if ( indexCh1b != npos )
      cout << "The index of the 'x' found in str1 is: "
           << indexCh1b << endl << endl;
   else
      cout << "The character 'x' was not found in str1."
           << endl << endl;

   // The second member function searches a string
   // for any element of a substring as specified by a C-string
   string str2 ( "ABCD-1234-ABCD-1234" );
   cout << "The original string str2 is: " << str2 << endl;
   basic_string <char>::size_type indexCh2a, indexCh2b;

   const char *cstr2 = "B1";
   indexCh2a = str2.find_first_of ( cstr2 , 6 );
   if ( indexCh2a != npos )
      cout << "The index of the 1st occurrence of an "
           << "element of 'B1' in str2 after\n the 6th "
           << "position is: " << indexCh2a << endl;
   else
      cout << "Elements of the substring 'B1' were not "
           << "found in str2 after the 10th position."
           << endl;

   const char *cstr2b = "D2";
   indexCh2b = str2.find_first_of ( cstr2b );
   if ( indexCh2b != npos )
      cout << "The index of the 1st element of 'D2' "
           << "after\n the 0th position in str2 is: "
           << indexCh2b << endl << endl;
   else
      cout << "The substring 'D2' was not found in str2 ."
           << endl << endl << endl;

   // The third member function searches a string
   // for any element of a substring as specified by a C-string
   string str3 ( "123-abc-123-abc-456-EFG-456-EFG" );
   cout << "The original string str3 is: " << str3 << endl;
   basic_string <char>::size_type indexCh3a, indexCh3b;

   const char *cstr3a = "5G";
   indexCh3a = str3.find_first_of ( cstr3a );
   if ( indexCh3a != npos )
      cout << "The index of the 1st occurrence of an "
           << "element of '5G' in str3 after\n the 0th "
           << "position is: " << indexCh3a << endl;
   else
      cout << "Elements of the substring '5G' were not "
           << "found in str3\n after the 0th position."
           << endl;

   const char *cstr3b = "5GF";
   indexCh3b = str3.find_first_of  ( cstr3b , indexCh3a + 1 , 2 );
   if (indexCh3b != npos )
      cout << "The index of the second occurrence of an "
           << "element of '5G' in str3\n after the 0th "
           << "position is: " << indexCh3b << endl << endl;
   else
      cout << "Elements of the substring '5G' were not "
           << "found in str3\n after the first occurrrence."
           << endl << endl;

   // The fourth member function searches a string
   // for any element of a substring as specified by a string
   string str4 ( "12-ab-12-ab" );
   cout << "The original string str4 is: " << str4 << endl;
   basic_string <char>::size_type indexCh4a, indexCh4b;

   string str4a ( "ba3" );
   indexCh4a = str4.find_first_of ( str4a , 5 );
   if ( indexCh4a != npos )
      cout << "The index of the 1st occurrence of an "
           << "element of 'ba3' in str4 after\n the 5th "
           << "position is: " << indexCh4a << endl;
   else
      cout << "Elements of the substring 'ba3' were not "
           << "found in str4\n after the 0th position."
           << endl;

   string str4b ( "a2" );
   indexCh4b = str4.find_first_of ( str4b );
   if ( indexCh4b != npos )
      cout << "The index of the 1st occurrence of an "
           << "element of 'a2' in str4 after\n the 0th "
           << "position is: " << indexCh4b << endl;
   else
      cout << "Elements of the substring 'a2' were not "
           << "found in str4\n after the 0th position."
           << endl;
}
```

```Output
The original string str1 is: abcd-1234-abcd-1234
The index of the 1st 'd' found after the 5th position in str1 is: 13
The character 'x' was not found in str1.

The original string str2 is: ABCD-1234-ABCD-1234
The index of the 1st occurrence of an element of 'B1' in str2 after
the 6th position is: 11
The index of the 1st element of 'D2' after
the 0th position in str2 is: 3

The original string str3 is: 123-abc-123-abc-456-EFG-456-EFG
The index of the 1st occurrence of an element of '5G' in str3 after
the 0th position is: 17
The index of the second occurrence of an element of '5G' in str3
after the 0th position is: 22

The original string str4 is: 12-ab-12-ab
The index of the 1st occurrence of an element of 'ba3' in str4 after
the 5th position is: 9
The index of the 1st occurrence of an element of 'a2' in str4 after
the 0th position is: 1
```

## <a name="find_last_not_of"></a> basic_string::find_last_not_of

Durchsucht eine Zeichenfolge nach dem letzten Zeichen, das kein Element der angegebenen Zeichenfolge ist.

```cpp
size_type find_last_not_of(
    value_type _Ch,
    size_type _Off = npos) const;

size_type find_last_not_of(
    const value_type* ptr,
    size_type _Off = npos) const;

size_type find_last_not_of(
    const value_type* ptr,
    size_type _Off,
    size_type count) const;

size_type find_last_not_of(
    const basic_string<CharType, Traits, Allocator>& str,
    size_type _Off = npos) const;
```

### <a name="parameters"></a>Parameter

*_Ch*<br/>
Der Zeichenwert, nach dem die Memberfunktion suchen soll.

*_Off*<br/>
Index der Position, an der die Suche enden soll.

*ptr*<br/>
Die C-Zeichenfolge, nach der die Memberfunktion suchen soll.

*count*<br/>
Die Anzahl von Zeichen, vom ersten Zeichen vorwärts, in der C-Zeichenfolge nach der die Memberfunktion suchen soll.

*str*<br/>
Die Zeichenfolge, nach der die Memberfunktion suchen soll.

### <a name="return-value"></a>Rückgabewert

Der Index des ersten Zeichens der Teilzeichenfolge, nach der bei Erfolg gesucht wird; andernfalls `npos`.

### <a name="example"></a>Beispiel

```cpp
// basic_string_find_last_not_of.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function
   // searches for a single character in a string
   string str1 ( "dddd-1dd4-abdd" );
   cout << "The original string str1 is: " << str1 << endl;
   basic_string <char>::size_type indexCh1a, indexCh1b;
   static const basic_string <char>::size_type npos = -1;

   indexCh1a = str1.find_last_not_of ( "d" , 7 );
   if ( indexCh1a != npos )
      cout << "The index of the last non 'd'\n found before the "
           << "7th position in str1 is: " << indexCh1a << endl;
   else
      cout << "The non 'd' character was not found ." << endl;

   indexCh1b = str1.find_last_not_of  ( "d" );
   if ( indexCh1b != npos )
      cout << "The index of the non 'd' found in str1 is: "
           << indexCh1b << endl << endl;
   else
      cout << "The Character 'non x' was not found in str1."
           << endl << endl;

   // The second member function searches a string
   // for a substring as specified by a C-string
   string str2 ( "BBB-1111" );
   cout << "The original string str2 is: " << str2 << endl;
   basic_string <char>::size_type indexCh2a, indexCh2b;

   const char *cstr2 = "B1";
   indexCh2a = str2.find_last_not_of  ( cstr2 , 6 );
   if ( indexCh2a != npos )
      cout << "The index of the last occurrence of a "
           << "element\n not of 'B1' in str2 before the 6th "
           << "position is: " << indexCh2a << endl;
   else
      cout << "Elements not of the substring 'B1' were not "
           << "\n found in str2 before the 6th position."
           << endl;

   const char *cstr2b = "B-1";
   indexCh2b = str2.find_last_not_of  ( cstr2b );
   if ( indexCh2b != npos )
      cout << "The index of the last element not "
           << "in 'B-1'\n is: "
           << indexCh2b << endl << endl;
   else
      cout << "The elements of the substring 'B-1' were "
           << "not found in str2 ."
           << endl << endl;

   // The third member function searches a string
   // for a substring as specified by a C-string
   string str3 ( "444-555-GGG" );
   cout << "The original string str3 is: " << str3 << endl;
   basic_string <char>::size_type indexCh3a, indexCh3b;

   const char *cstr3a = "45G";
   indexCh3a = str3.find_last_not_of ( cstr3a );
   if ( indexCh3a != npos )
      cout << "The index of the last occurrence of an "
           << "element in str3\n other than one of the "
           << "characters in '45G' is: " << indexCh3a
           << endl;
   else
      cout << "Elements in str3 contain only characters "
           << " in the string  '45G'. "
           << endl;

   const char *cstr3b = "45G";
   indexCh3b = str3.find_last_not_of ( cstr3b , 6 , indexCh3a - 1 );
   if (indexCh3b != npos )
      cout << "The index of the penultimate occurrence of an "
           << "element\n not in '45G' in str3 is: "
           << indexCh3b << endl << endl;
   else
      cout << "Elements in str3 contain only characters "
           << " in the string '45G'. "
           << endl  << endl;

   // The fourth member function searches a string
   // for a substring as specified by a string
   string str4 ( "12-ab-12-ab" );
   cout << "The original string str4 is: " << str4 << endl;
   basic_string <char>::size_type indexCh4a, indexCh4b;

   string str4a ( "b-a" );
   indexCh4a = str4.find_last_not_of  ( str4a , 5 );
   if ( indexCh4a != npos )
      cout << "The index of the last occurrence of an "
           << "element not\n in 'b-a' in str4 before the 5th "
           << "position is: " << indexCh4a << endl;
   else
      cout << "Elements other than those in the substring"
           << " 'b-a' were not found in the string str4."
           << endl;

   string str4b ( "12" );
   indexCh4b = str4.find_last_not_of ( str4b  );
   if ( indexCh4b != npos )
      cout << "The index of the last occurrence of an "
           << "element not in '12'\n in str4 before the end "
           << "position is: " << indexCh4b << endl;
   else
      cout << "Elements other than those in the substring"
           << " '12'\n were not found in the string str4."
           << endl;
}
```

```Output
The original string str1 is: dddd-1dd4-abdd
The index of the last non 'd'
found before the 7th position in str1 is: 5
The index of the non 'd' found in str1 is: 11

The original string str2 is: BBB-1111
The index of the last occurrence of a element
not of 'B1' in str2 before the 6th position is: 3
The elements of the substring 'B-1' were not found in str2 .

The original string str3 is: 444-555-GGG
The index of the last occurrence of an element in str3
other than one of the characters in '45G' is: 7
The index of the penultimate occurrence of an element
not in '45G' in str3 is: 3

The original string str4 is: 12-ab-12-ab
The index of the last occurrence of an element not
in 'b-a' in str4 before the 5th position is: 1
The index of the last occurrence of an element not in '12'
in str4 before the end position is: 10
```

## <a name="find_last_of"></a> basic_string::find_last_of

Durchsucht eine Zeichenfolge nach dem letzten Zeichen, das einem Element der angegebenen Zeichenfolge entspricht.

```cpp
size_type find_last_of(
    value_type _Ch,
    size_type _Off = npos) const;

size_type find_last_of(
    const value_type* ptr,
    size_type _Off = npos) const;

size_type find_last_of(
    const value_type* ptr,
    size_type _Off,
    size_type count) const;

size_type find_last_of(
    const basic_string<CharType, Traits, Allocator>& str,
    size_type _Off = npos) const;
```

### <a name="parameters"></a>Parameter

*_Ch*<br/>
Der Zeichenwert, nach dem die Memberfunktion suchen soll.

*_Off*<br/>
Index der Position, an der die Suche enden soll.

*ptr*<br/>
Die C-Zeichenfolge, nach der die Memberfunktion suchen soll.

*count*<br/>
Die Anzahl von Zeichen, vom ersten Zeichen vorwärts, in der C-Zeichenfolge nach der die Memberfunktion suchen soll.

*str*<br/>
Die Zeichenfolge, nach der die Memberfunktion suchen soll.

### <a name="return-value"></a>Rückgabewert

Falls erfolgreich, der Index des letzten Zeichens der gesuchten Teilzeichenfolge, andernfalls `npos`.

### <a name="example"></a>Beispiel

```cpp
// basic_string_find_last_of.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function
   // searches for a single character in a string
   string str1 ( "abcd-1234-abcd-1234" );
   cout << "The original string str1 is: " << str1 << endl;
   basic_string <char>::size_type indexCh1a, indexCh1b;
   static const basic_string <char>::size_type npos = -1;

   indexCh1a = str1.find_last_of ( "d" , 14 );
   if ( indexCh1a != npos )
      cout << "The index of the last 'd' found before the 14th"
           << " position in str1 is: " << indexCh1a << endl;
   else
      cout << "The character 'd' was not found in str1 ." << endl;

   indexCh1b = str1.find_first_of ( "x" );
   if ( indexCh1b != npos )
      cout << "The index of the 'x' found in str1 is: "
           << indexCh1b << endl << endl;
   else
      cout << "The character 'x' was not found in str1."
           << endl << endl;

   // The second member function searches a string
   // for a substring as specified by a C-string
   string str2 ( "ABCD-1234-ABCD-1234" );
   cout << "The original string str2 is: " << str2 << endl;
   basic_string <char>::size_type indexCh2a, indexCh2b;

   const char *cstr2 = "B1";
   indexCh2a = str2.find_last_of  ( cstr2 , 12 );
   if (indexCh2a != npos )
      cout << "The index of the last occurrence of an "
           << "element of 'B1' in str2 before\n the 12th "
           << "position is: " << indexCh2a << endl;
   else
      cout << "Elements of the substring 'B1' were not "
           << "found in str2 before the 12th position."
           << endl;

   const char *cstr2b = "D2";
   indexCh2b = str2.find_last_of  ( cstr2b );
   if ( indexCh2b != npos )
      cout << "The index of the last element of 'D2' "
           << "after\n the 0th position in str2 is: "
           << indexCh2b << endl << endl;
   else
      cout << "The substring 'D2' was not found in str2 ."
           << endl << endl << endl;

   // The third member function searches a string
   // for a substring as specified by a C-string
   string str3 ( "456-EFG-456-EFG" );
   cout << "The original string str3 is: " << str3 << endl;
   basic_string <char>::size_type indexCh3a;

   const char *cstr3a = "5E";
   indexCh3a = str3.find_last_of ( cstr3a , 8 , 8 );
   if ( indexCh3a != npos )
      cout << "The index of the last occurrence of an "
           << "element of '5E' in str3 before\n the 8th "
           << "position is: " << indexCh3a << endl << endl;
   else
      cout << "Elements of the substring '5G' were not "
           << "found in str3\n before the 8th position."
           << endl << endl;

   // The fourth member function searches a string
   // for a substring as specified by a string
   string str4 ( "12-ab-12-ab" );
   cout << "The original string str4 is: " << str4 << endl;
   basic_string <char>::size_type indexCh4a, indexCh4b;

   string str4a ( "ba3" );
   indexCh4a = str4.find_last_of  ( str4a , 8 );
   if ( indexCh4a != npos )
      cout << "The index of the last occurrence of an "
           << "element of 'ba3' in str4 before\n the 8th "
           << "position is: " << indexCh4a << endl;
   else
      cout << "Elements of the substring 'ba3' were not "
           << "found in str4\n after the 0th position."
           << endl;

   string str4b ( "a2" );
   indexCh4b = str4.find_last_of ( str4b  );
   if ( indexCh4b != npos )
      cout << "The index of the last occurrence of an "
           << "element of 'a2' in str4 before\n the 0th "
           << "position is: " << indexCh4b << endl;
   else
      cout << "Elements of the substring 'a2' were not "
           << "found in str4\n after the 0th position."
           << endl;
}
```

```Output
The original string str1 is: abcd-1234-abcd-1234
The index of the last 'd' found before the 14th position in str1 is: 13
The character 'x' was not found in str1.

The original string str2 is: ABCD-1234-ABCD-1234
The index of the last occurrence of an element of 'B1' in str2 before
the 12th position is: 11
The index of the last element of 'D2' after
the 0th position in str2 is: 16

The original string str3 is: 456-EFG-456-EFG
The index of the last occurrence of an element of '5E' in str3 before
the 8th position is: 4

The original string str4 is: 12-ab-12-ab
The index of the last occurrence of an element of 'ba3' in str4 before
the 8th position is: 4
The index of the last occurrence of an element of 'a2' in str4 before
the 0th position is: 9
```

## <a name="front"></a> basic_string::front

Gibt einen Verweis auf das erste Element in einer Zeichenfolge zurück.

```cpp
const_reference front() const;

reference front();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das erste Element der Zeichenfolge, die nicht leer sein darf.

### <a name="remarks"></a>Hinweise

## <a name="get_allocator"></a> basic_string::get_allocator

Gibt eine Kopie des Zuweisungsobjekts zurück, das zum Erstellen einer Zeichenfolge verwendet wird.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Rückgabewert

Die von der Zeichenfolge verwendete Zuweisung.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt das gespeicherte Zuweisungsobjekt zurück.

Zuordnungsfunktionen für die Zeichenfolgenklasse geben an, wie die Klasse Speicher verwaltet. Für die meisten Programmieranforderungen reichen die Standardzuordnungsfunktionen mit Containerklassen aus. Schreiben und Verwenden Ihrer eigener Zuweisungsklasse ist ein C++ -Thema für Fortgeschrittene.

### <a name="example"></a>Beispiel

```cpp
// basic_string_get_allocator.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // The following lines declare objects
   // that use the default allocator.
   string s1;
   basic_string <char> s2;
   basic_string <char, char_traits< char >, allocator< char > > s3;

   // s4 will use the same allocator class as s1
   basic_string <char> s4( s1.get_allocator ( ) );

   basic_string <char>::allocator_type xchar = s1.get_allocator( );
   // You can now call functions on the allocator class xchar used by s1
}
```

## <a name="insert"></a> basic_string::insert

Fügt ein Element oder mehrere Elemente oder ein Reihe von Elementen an einer bestimmten Position in die Zeichenfolge ein.

```cpp
basic_string<CharType, Traits, Allocator>& insert(
    size_type _P0,
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& insert(
    size_type _P0,
    const value_type* ptr,
    size_type count);

basic_string<CharType, Traits, Allocator>& insert(
    size_type _P0,
    const basic_string<CharType, Traits, Allocator>& str);

basic_string<CharType, Traits, Allocator>& insert(
    size_type _P0,
    const basic_string<CharType, Traits, Allocator>& str,
    size_type _Off,
    size_type count);

basic_string<CharType, Traits, Allocator>& insert(
    size_type _P0,
    size_type count,
    value_type _Ch);

iterator insert(
    iterator _It);

iterator insert(
    iterator _It,
    value_type _Ch)l
template <class InputIterator>
void insert(
    iterator _It,
    InputIterator first,
    InputIterator last);

void insert(
    iterator _It,
    size_type count,
    value_type _Ch);

void insert(
    iterator _It,
    const_pointer first,
    const_pointer last);

void insert(
    iterator _It,
    const_iterator first,
    const_iterator last);
```

### <a name="parameters"></a>Parameter

*_P0*<br/>
Der Index der Position hinter der Einfügemarke für die neuen Zeichen.

*ptr*<br/>
Die C-Zeichenfolge, die ganz oder teilweise in die Zeichenfolge eingefügt werden soll.

*count*<br/>
Die Anzahl der einzufügenden Zeichen.

*str*<br/>
Die Zeichenfolge, die ganz oder teilweise in die Zielzeichenfolge eingefügt werden soll.

*_Off*<br/>
Der Index des Teils der Quellzeichenfolge, der die anzufügenden Zeichen bereitstellt.

*_Ch*<br/>
Der Zeichenwert der einzufügenden Elemente.

*_It*<br/>
Ein Iterator, der die Position adressiert, hinter der ein Zeichen eingefügt werden soll.

*first*<br/>
Ein Eingabeiterator, const_pointer oder const_iterator, der das erste Element im einzufügenden Quellbereich adressiert.

*last*<br/>
Ein Eingabeiterator, const_pointer oder const_iterator, der die Position eines der letzten Elemente im einzufügenden Quellbereich adressiert.

### <a name="return-value"></a>Rückgabewert

Entweder ein Verweis auf das Zeichenfolgenobjekt, dem von der Memberfunktion neue Zeichen zugewiesen werden, oder, im Fall der Einfügung von Einzelzeichen, ein Iterator, der die Position des eingefügten Zeichens adressiert, oder nichts, abhängig von der betreffenden Memberfunktion.

### <a name="example"></a>Beispiel

```cpp
// basic_string_insert.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function inserting a C-string
   // at a given position
   basic_string <char> str1a ( "way" );
   const char *cstr1a = "a";
   str1a.insert ( 0, cstr1a );
   cout << "The string with a C-string inserted at position 0 is: "
        << str1a << "." << endl;

   // The second member function inserting a C-string
   // at a given position for a specified number of elements
   basic_string <char> str2a ( "Good" );
   const char *cstr2a = "Bye Bye Baby";
   str2a.insert ( 4, cstr2a ,3 );
   cout << "The string with a C-string inserted at the end is: "
        << str2a << "." << endl;

   // The third member function inserting a string
   // at a given position
   basic_string <char> str3a ( "Bye" );
   string str3b ( "Good" );
   str3a.insert ( 0, str3b );
   cout << "The string with a string inserted at position 0 is: "
        << str3a << "." << endl;

   // The fourth member function inserting part of
   // a string at a given position
   basic_string <char> str4a ( "Good " );
   string str4b ( "Bye Bye Baby" );
   str4a.insert ( 5, str4b , 8 , 4 );
   cout << "The string with part of a string inserted at position 4 is: "
        << str4a << "." << endl;

   // The fifth member function inserts a number of characters
   // at a specified position in the string
   string str5 ( "The number is: ." );
   str5.insert ( 15 , 3 , '3' );
   cout << "The string with characters inserted is: "
        << str5 << endl;

   // The sixth member function inserts a character
   // at a specified position in the string
   string str6 ( "ABCDFG" );
   basic_string <char>::iterator str6_Iter = ( str6.begin ( ) + 4 );
   str6.insert ( str6_Iter , 'e' );
   cout << "The string with a character inserted is: "
        << str6 << endl;

   // The seventh member function inserts a range
   // at a specified position in the string
   string str7a ( "ABCDHIJ" );
   string str7b ( "abcdefgh" );
   basic_string <char>::iterator str7a_Iter = (str7a.begin ( ) + 4 );
   str7a.insert ( str7a_Iter , str7b.begin ( ) + 4 , str7b.end ( ) -1 );
   cout << "The string with a character inserted from a range is: "
        << str7a << endl;

   // The eigth member function inserts a number of
   // characters at a specified position in the string
   string str8 ( "ABCDHIJ" );
   basic_string <char>::iterator str8_Iter = ( str8.begin ( ) + 4 );
   str8.insert ( str8_Iter , 3 , 'e' );
   cout << "The string with a character inserted from a range is: "
        << str8 << endl;
}
```

```Output
The string with a C-string inserted at position 0 is: away.
The string with a C-string inserted at the end is: GoodBye.
The string with a string inserted at position 0 is: GoodBye.
The string with part of a string inserted at position 4 is: Good Baby.
The string with characters inserted is: The number is: 333.
The string with a character inserted is: ABCDeFG
The string with a character inserted from a range is: ABCDefgHIJ
The string with a character inserted from a range is: ABCDeeeHIJ
```

## <a name="iterator"></a> basic_string::iterator

Ein Typ, der einen Iterator mit wahlfreiem Zugriff bereitstellt, mit dem auf ein **const**-Element zugegriffen wird, und mit dem dieses Element gelesen werden kann.

```cpp
typedef implementation-defined iterator;
```

### <a name="remarks"></a>Hinweise

Ein Typ `iterator` kann zum Ändern des Werts eines Zeichens verwendet werden und wird verwendet, um eine Zeichenfolge vorwärts zu durchlaufen.

### <a name="example"></a>Beispiel

Im Beispiel für [begin](#begin) wird verdeutlicht, wie ein `iterator` deklariert und verwendet wird.

## <a name="length"></a> basic_string::length

Gibt die aktuelle Anzahl von Elementen in einer Zeichenfolge zurück.

```cpp
size_type length() const;
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion ist identisch mit [size](#size).

### <a name="example"></a>Beispiel

```cpp
// basic_string_length.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ("Hello world");
   cout << "The original string str1 is: " << str1 << endl;

   // The size and length member functions differ in name only
   basic_string <char>::size_type sizeStr1, lenStr1;
   sizeStr1 = str1.size ( );
   lenStr1 = str1.length ( );

   basic_string <char>::size_type capStr1, max_sizeStr1;
   capStr1 = str1.capacity ( );
   max_sizeStr1 = str1.max_size ( );

   // Compare size, length, capacity & max_size of a string
   cout << "The current size of original string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The current length of original string str1 is: "
        << lenStr1 << "." << endl;
   cout << "The capacity of original string str1 is: "
        << capStr1 << "." << endl;
   cout << "The max_size of original string str1 is: "
        << max_sizeStr1 << "." << endl << endl;

   str1.erase ( 6, 5 );
   cout << "The modified string str1 is: " << str1 << endl;

   sizeStr1 = str1.size ( );
   lenStr1 = str1.length ( );
   capStr1 = str1.capacity ( );
   max_sizeStr1 = str1.max_size ( );

   // Compare size, length, capacity & max_size of a string
   // after erasing part of the original string
   cout << "The current size of modified string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The current length of modified string str1 is: "
        << lenStr1 << "." << endl;
   cout << "The capacity of modified string str1 is: "
        << capStr1 << "." << endl;
   cout << "The max_size of modified string str1 is: "
        << max_sizeStr1 << "." << endl;
}
```

## <a name="max_size"></a> basic_string::max_size

Gibt die Höchstanzahl von Zeichen, die eine Zeichenfolge enthalten könnte zurück.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Rückgabewert

Die Höchstanzahl von Zeichen, die eine Zeichenfolge enthalten könnte.

### <a name="remarks"></a>Hinweise

Eine Ausnahme vom Typ [Length_error-Klasse](../standard-library/length-error-class.md) wird ausgelöst, wenn ein Vorgang eine Zeichenfolge erstellt, bei der die Länge größer ist als die Maximalgröße.

### <a name="example"></a>Beispiel

```cpp
// basic_string_max_size.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ("Hello world");
   cout << "The original string str1 is: " << str1 << endl;

   // The size and length member functions differ in name only
   basic_string <char>::size_type sizeStr1, lenStr1;
   sizeStr1 = str1.size ( );
   lenStr1 = str1.length ( );

   basic_string <char>::size_type capStr1, max_sizeStr1;
   capStr1 = str1.capacity ( );
   max_sizeStr1 = str1.max_size ( );

   // Compare size, length, capacity & max_size of a string
   cout << "The current size of original string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The current length of original string str1 is: "
        << lenStr1 << "." << endl;
   cout << "The capacity of original string str1 is: "
        << capStr1 << "." << endl;
   cout << "The max_size of original string str1 is: "
        << max_sizeStr1 << "." << endl << endl;

   str1.erase ( 6, 5 );
   cout << "The modified string str1 is: " << str1 << endl;

   sizeStr1 = str1.size ( );
   lenStr1 = str1.length ( );
   capStr1 = str1.capacity ( );
   max_sizeStr1 = str1.max_size ( );

   // Compare size, length, capacity & max_size of a string
   // after erasing part of the original string
   cout << "The current size of modified string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The current length of modified string str1 is: "
        << lenStr1 << "." << endl;
   cout << "The capacity of modified string str1 is: "
        << capStr1 << "." << endl;
   cout << "The max_size of modified string str1 is: "
        << max_sizeStr1 << "." << endl;
}
```

## <a name="npos"></a> basic_string::npos

Ein initialisierter Integralwert ohne Vorzeichen-1 an, der angibt "nicht gefunden" oder "alle verbleibenden Zeichen" Wenn eine Funktion für die Suche ein Fehler auftritt.

```cpp
static const size_type npos = -1;
```

### <a name="remarks"></a>Hinweise

Wenn der Rückgabewert ist auf überprüft werden soll die `npos` Wert, es funktioniert nicht, wenn der Rückgabewert des Typs ist [Size_type](#size_type) und nicht entweder **Int** oder **ohne Vorzeichen**.

### <a name="example"></a>Beispiel

Im Beispiel für [find](#find) wird verdeutlicht, wie `npos` deklariert und verwendet wird.

## <a name="op_add_eq"></a> basic_string::operator+=

Fügt einer Zeichenfolge Zeichen an.

```cpp
basic_string<CharType, Traits, Allocator>& operator+=(
    value_type _Ch);

basic_string<CharType, Traits, Allocator>& operator+=(
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& operator+=(
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*_Ch*<br/>
Das Zeichen, das angefügt werden soll.

*ptr*<br/>
Die Zeichen der C-Zeichenfolge, die angefügt werden sollen.

*right*<br/>
Die Zeichen der Zeichenfolge, die angefügt werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Zeichenfolgenobjekt, an das die Zeichen angefügt werden, die von der Memberfunktion übergeben werden.

### <a name="remarks"></a>Hinweise

Zeichen können mithilfe von `operator+=` oder den Memberfunktionen [append](#append) oder [push_back](#push_back) an eine Zeichenfolge angefügt werden. `operator+=` fügt einfache Argumentwerte an, während die Memberfunktion „append“ mit mehreren Argumenten zulässt, dass ein bestimmter Teil einer Zeichenfolge für das Hinzufügen angegeben wird.

### <a name="example"></a>Beispiel

```cpp
// basic_string_op_app.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function
   // appending a single character to a string
   string str1a ( "Hello" );
   cout << "The original string str1 is: " << str1a << endl;
   str1a +=  '!' ;
   cout << "The string str1 appended with an exclamation is: "
        << str1a << endl << endl;

   // The second member function
   // appending a C-string to a string
   string  str1b ( "Hello " );
   const char *cstr1b = "Out There";
   cout << "The C-string cstr1b is: " << cstr1b << endl;
   str1b +=  cstr1b;
   cout << "Appending the C-string cstr1b to string str1 gives: "
        << str1b << "." << endl << endl;

   // The third member function
   // appending one string to another in two ways,
   // comparing append and operator [ ]
   string str1d ( "Hello " ), str2d ( "Wide " ), str3d ( "World" );
   cout << "The string str2d is: " << str2d << endl;
   str1d.append ( str2d );
   cout << "The appended string str1d is: "
        << str1d << "." << endl;
   str1d += str3d;
   cout << "The doubly appended strig str1 is: "
        << str1d << "." << endl << endl;
}
```

```Output
The original string str1 is: Hello
The string str1 appended with an exclamation is: Hello!

The C-string cstr1b is: Out There
Appending the C-string cstr1b to string str1 gives: Hello Out There.

The string str2d is: Wide
The appended string str1d is: Hello Wide .
The doubly appended strig str1 is: Hello Wide World.
```

## <a name="op_eq"></a> basic_string::operator=

Weist dem Inhalt einer Zeichenfolge neue Zeichenwerte zu.

```cpp
basic_string<CharType, Traits, Allocator>& operator=(
    value_type _Ch);

basic_string<CharType, Traits, Allocator>& operator=(
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& operator=(
    const basic_string<CharType, Traits, Allocator>& right);

basic_string<CharType, Traits, Allocator>& operator=(
    const basic_string<CharType, Traits, Allocator>&& right);
```

### <a name="parameters"></a>Parameter

*_Ch*<br/>
Der Zeichenwert, der zugewiesen werden soll.

*ptr*<br/>
Ein Zeiger auf die Zeichen einer C-Zeichenfolge, die der Zielzeichenfolge zugewiesen werden sollen.

*right*<br/>
Die Quellzeichenfolge, deren Zeichen der Zielzeichenfolge zugewiesen werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Zeichenfolgenobjekt, dem durch die Memberfunktion neue Zeichen zugewiesen werden sollen.

### <a name="remarks"></a>Hinweise

Den Zeichenfolgen können neue Zeichenwerte zugewiesen werden. Der neue Wert kann entweder eine Zeichenfolge und C-Zeichenfolge oder ein einzelnes Zeichen sein. `operator=` kann verwendet werden, wenn ein neuer Wert durch einen einzelnen Parameter beschrieben werden kann. Andernfalls kann die Memberfunktion [assign](#assign), die über mehrere Parameter verfügt, verwendet werden, um anzugeben, welcher Teil der Zeichenfolge einer Zielzeichenfolge zugewiesen werden soll.

### <a name="example"></a>Beispiel

```cpp
// basic_string_op_assign.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function assigning a
   // character of a certain value to a string
   string str1a ( "Hello " );
   str1a = '0';
   cout << "The string str1 assigned with the zero character is: "
        << str1a << endl << endl;

   // The second member function assigning the
   // characters of a C-string to a string
   string  str1b;
   const char *cstr1b = "Out There";
   cout << "The C-string cstr1b is: " << cstr1b <<  "." << endl;
   str1b = cstr1b;
   cout << "Assigning the C-string cstr1a to string str1 gives: "
        << str1b << "." << endl << endl;

   // The third member function assigning the characters
   // from one string to another string in two equivalent
   // ways, comparing the assign and operator =
   string str1c ( "Hello" ), str2c ( "Wide" ), str3c ( "World" );
   cout << "The original string str1 is: " << str1c << "." << endl;
   cout << "The string str2c is: " << str2c << "." << endl;
   str1c.assign ( str2c );
   cout << "The string str1 newly assigned with string str2c is: "
        << str1c << "." << endl;
   cout << "The string str3c is: " << str3c << "." << endl;
   str1c = str3c;
   cout << "The string str1 reassigned with string str3c is: "
        << str1c << "." << endl << endl;
}
```

```Output
The string str1 assigned with the zero character is: 0

The C-string cstr1b is: Out There.
Assigning the C-string cstr1a to string str1 gives: Out There.

The original string str1 is: Hello.
The string str2c is: Wide.
The string str1 newly assigned with string str2c is: Wide.
The string str3c is: World.
The string str1 reassigned with string str3c is: World.
```

## <a name="op_at"></a> basic_string::operator[]

Stellt mit einem angegebenen Index in einer Zeichenfolge einen Verweis auf das Zeichen.

```cpp
const_reference operator[](size_type _Off) const;
reference operator[](size_type _Off);
```

### <a name="parameters"></a>Parameter

*_Off*<br/>
Der Index des Elements, auf das verwiesen werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Zeichen der Zeichenfolge an der Position, die durch den Parameterindex angegeben wird.

### <a name="remarks"></a>Hinweise

Das erste Element der Zeichenfolge hat einen Index von 0, und die folgenden Elemente werden nacheinander durch positive ganze Zahlen indiziert, sodass eine Zeichenfolge der Länge *n* über ein *n*-te Element verfügt, das durch die Zahl *n* - 1 indiziert wird.

`operator[]` ist schneller als die Memberfunktion [at](#at) beim Bereitstellen von Lese- und Schreibzugriff auf die Elemente einer Zeichenfolge.

`operator[]` wird nicht überprüft, ob der Index als Parameter übergebenen gültig ist, aber die Memberfunktion `at` ist und daher in die Gültigkeit verwendet werden soll nicht bestimmte. Ein ungültiger Index (ein Index, der kleiner, die 0 (null) oder größer als oder gleich der Größe der Zeichenfolge), die an die Memberfunktion `at` löst eine [Out_of_range-Klasse](../standard-library/out-of-range-class.md) Ausnahme. Ein ungültiger Index, der an `operator[]` übergeben wird, führt zu nicht definiertem Verhalten. Der Index, der gleich der Länge der Zeichenfolge ist, ist allerdings ein gültiger Index für const-Zeichenfolgen. Der Operator gibt das NULL-Zeichen zurück, wenn dieser Index übergeben wurde.

Der zurückgegebene Verweis wird möglicherweise durch Neuzuordnungen oder Änderungen für nicht **konstante**  Zeichenfolgen ungültig.

Beim Kompilieren mit [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md) mit Einstellung auf 1 oder 2 tritt ein Laufzeitfehler auf, wenn Sie versuchen, auf ein Element außerhalb der Grenzen der Zeichenfolge zuzugreifen. Weitere Informationen finden Sie unter [Checked Iterators](../standard-library/checked-iterators.md).

### <a name="example"></a>Beispiel

```cpp
// basic_string_op_ref.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ( "Hello world" ), str2 ( "Goodbye world" );
   const string cstr1 ( "Hello there" ), cstr2 ( "Goodbye now" );
   cout << "The original string str1 is: " << str1 << endl;
   cout << "The original string str2 is: " << str2 << endl;

   // Element access to the non-const strings
   basic_string <char>::reference refStr1 = str1 [6];
   basic_string <char>::reference refStr2 = str2.at ( 3 );

   cout << "The character with an index of 6 in string str1 is: "
        << refStr1 << "." << endl;
   cout << "The character with an index of 3 in string str2 is: "
        << refStr2 << "." << endl;

   // Element access to the const strings
   basic_string <char>::const_reference crefStr1 = cstr1 [ cstr1.length ( ) ];
   basic_string <char>::const_reference crefStr2 = cstr2.at ( 8 );

   if ( crefStr1 == '\0' )
      cout << "The null character is returned as a valid reference."
           << endl;
   else
      cout << "The null character is not returned." << endl;
   cout << "The character with index of 8 in the const string cstr2 is: "
        << crefStr2 << "." << endl;
}
```

## <a name="pointer"></a> basic_string::pointer

Ein Typ, der einen Zeiger auf ein Zeichenelement in einer Zeichenfolge oder einem Zeichenarray bereitstellt.

```cpp
typedef typename allocator_type::pointer pointer;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `allocator_type::pointer`.

Für den Typ `string`, dies ist äquivalent zum **Char**<strong>\*</strong>.

### <a name="example"></a>Beispiel

```cpp
// basic_string_pointer.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   basic_string<char>::pointer pstr1a = "In Here";
   char *cstr1b = "Out There";
   cout << "The string pstr1a is: " << pstr1a <<  "." << endl;
   cout << "The C-string cstr1b is: " << cstr1b << "." << endl;
}
```

```Output
The string pstr1a is: In Here.
The C-string cstr1b is: Out There.
```

## <a name="pop_back"></a> basic_string::pop_back

Löscht das letzte Element der Zeichenfolge.

```cpp
void pop_back();
```

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ruft tatsächlich `erase(size() - 1)` auf, um das letzte Element der Sequenz zu löschen, das nicht leer sein darf.

## <a name="push_back"></a> basic_string::push_back

Fügt ein Element am Ende der Zeichenfolge hinzu.

```cpp
void push_back(value_type _Ch);
```

### <a name="parameters"></a>Parameter

*_Ch*<br/>
Das Zeichen am Ende der Zeichenfolge hinzugefügt werden soll.

### <a name="remarks"></a>Hinweise

Die Memberfunktion ruft effektiv [insert](#insert)([end](#end), _ *Ch* ) auf.

### <a name="example"></a>Beispiel

```cpp
// basic_string_push_back.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ( "abc" );
   basic_string <char>::iterator str_Iter, str1_Iter;

   cout << "The original string str1 is: ";
   for ( str_Iter = str1.begin( ); str_Iter != str1.end( ); str_Iter++ )
      cout << *str_Iter;
   cout << endl;

   // str1.push_back ( 'd' );
   str1_Iter = str1.end ( );
   str1_Iter--;
   cout << "The last character-letter of the modified str1 is now: "
        << *str1_Iter << endl;

   cout << "The modified string str1 is: ";
   for ( str_Iter = str1.begin( ); str_Iter != str1.end( ); str_Iter++ )
      cout << *str_Iter;
   cout << endl;
}
```

```Output
The original string str1 is: abc
The last character-letter of the modified str1 is now: c
The modified string str1 is: abc
```

## <a name="rbegin"></a> basic_string::rbegin

Gibt einen Iterator an das erste Element in einer umgekehrten Zeichenfolge zurück.

```cpp
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Iterator mit wahlfreiem Zugriff auf das erste Element in einer umgekehrten Zeichenfolge zurück und adressiert das potentiell letzte Element in der entsprechenden nicht umgekehrten Zeichenfolge.

### <a name="remarks"></a>Hinweise

`rbegin` wird bei einer umgekehrten Zeichenfolge auf die gleiche Weise verwendet, wie [begin](#begin) bei einer Zeichenfolge verwendet wird.

Wenn der Rückgabewert von `rbegin` zu `const_reverse_iterator` zugewiesen wird, kann das Zeichenfolgenobjekt nicht geändert werden. Wenn der Rückgabewert von `rbegin` zu `reverse_iterator` zugewiesen wird, kann das Zeichenfolgenobjekt geändert werden.

`rbegin` kann verwendet werden, um eine Iteration rückwärts durch eine Zeichenfolge zu initialisieren.

### <a name="example"></a>Beispiel

```cpp
// basic_string_rbegin.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ( "Able was I ere I saw Elba" ), str2;
   basic_string <char>::reverse_iterator str_rIter, str1_rIter, str2_rIter;
   basic_string <char>::const_reverse_iterator str1_rcIter;

   str1_rIter = str1.rbegin ( );
   // str1_rIter--;
   cout << "The first character-letter of the reversed string str1 is: "
        << *str1_rIter << endl;
   cout << "The full reversed string str1 is:\n ";
   for ( str_rIter = str1.rbegin( ); str_rIter != str1.rend( ); str_rIter++ )
      cout << *str_rIter;
   cout << endl;

   // The dereferenced iterator can be used to modify a character
*str1_rIter = 'A';
   cout << "The first character-letter of the modified str1 is now: "
        << *str1_rIter << endl;
   cout << "The full modified reversed string str1 is now:\n ";
   for ( str_rIter = str1.rbegin( ); str_rIter != str1.rend( ); str_rIter++ )
      cout << *str_rIter;
   cout << endl;

   // The following line would be an error because iterator is const
   // *str1_rcIter = 'A';

   // For an empty string, begin is equivalent to end
   if ( str2.rbegin( ) == str2.rend ( ) )
      cout << "The string str2 is empty." << endl;
   else
      cout << "The stringstr2  is not empty." << endl;
}
```

```Output
The first character-letter of the reversed string str1 is: a
The full reversed string str1 is:
ablE was I ere I saw elbA
The first character-letter of the modified str1 is now: A
The full modified reversed string str1 is now:
AblE was I ere I saw elbA
The string str2 is empty.
```

## <a name="reference"></a> basic_string::reference

Ein Typ, der einen Verweis auf ein in einer Zeichenfolge gespeichertes Element bereitstellt.

```cpp
typedef typename allocator_type::reference reference;
```

### <a name="remarks"></a>Hinweise

Ein Typ `reference` kann zum Ändern des Werts eines Elements verwendet werden.

Der Typ ist ein Synonym für `allocator_type::reference`.

Für den Typ `string`, dies ist äquivalent zum `chr&`.

### <a name="example"></a>Beispiel

Im Beispiel für [t](#at) wird verdeutlicht, wie ein `reference` deklariert und verwendet wird.

## <a name="rend"></a> basic_string::rend

Gibt einen Iterator zurück, der den Speicherort adressiert, der dem letzten Element einer umgekehrten Zeichenfolge nachfolgt.

```cpp
const_reverse_iterator rend() const;

reverse_iterator rend();
```

### <a name="return-value"></a>Rückgabewert

Ein umgekehrter Iterator mit wahlfreiem Zugriff, der den Speicherort adressiert, der dem letzten Element einer umgekehrten Zeichenfolge nachfolgt.

### <a name="remarks"></a>Hinweise

`rend` wird bei einer umgekehrten Zeichenfolge auf die gleiche Weise verwendet, wie [end](#end) bei einer Zeichenfolge verwendet wird.

Wenn der Rückgabewert von `rend` zu `const_reverse_iterator` zugewiesen wird, kann das Zeichenfolgenobjekt nicht geändert werden. Wenn der Rückgabewert von `rend` zu `reverse_iterator` zugewiesen wird, kann das Zeichenfolgenobjekt geändert werden.

`rend` kann verwendet werden, um zu testen, ob das Ende der Zeichenfolge von einem umgekehrten Iterator erreicht wurde.

Der von `rend` zurückgegebene Wert darf nicht dereferenziert werden.

### <a name="example"></a>Beispiel

```cpp
// basic_string_rend.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ("Able was I ere I saw Elba"), str2;
   basic_string <char>::reverse_iterator str_rIter, str1_rIter, str2_rIter;
   basic_string <char>::const_reverse_iterator str1_rcIter;

   str1_rIter = str1.rend ( );
   str1_rIter--;
   cout << "The last character-letter of the reversed string str1 is: "
        << *str1_rIter << endl;
   cout << "The full reversed string str1 is:\n ";
   for ( str_rIter = str1.rbegin( ); str_rIter != str1.rend( ); str_rIter++ )
      cout << *str_rIter;
   cout << endl;

   // The dereferenced iterator can be used to modify a character
*str1_rIter = 'o';
   cout << "The last character-letter of the modified str1 is now: "
        << *str1_rIter << endl;
   cout << "The full modified reversed string str1 is now:\n ";
   for ( str_rIter = str1.rbegin( ); str_rIter != str1.rend( ); str_rIter++ )
      cout << *str_rIter;
   cout << endl;

   // The following line would be an error because iterator is const
   // *str1_rcIter = 'T';

   // For an empty string, end is equivalent to begin
   if ( str2.rbegin( ) == str2.rend ( ) )
      cout << "The string str2 is empty." << endl;
   else
      cout << "The stringstr2  is not empty." << endl;
}
```

```Output
The last character-letter of the reversed string str1 is: A
The full reversed string str1 is:
ablE was I ere I saw elbA
The last character-letter of the modified str1 is now: o
The full modified reversed string str1 is now:
ablE was I ere I saw elbo
The string str2 is empty.
```

## <a name="replace"></a> basic_string::replace

Ersetzt Elemente an einer bestimmten Position in einer Zeichenfolge durch angegebene Zeichen oder Zeichen, die aus anderen Bereichen oder Zeichenfolgen oder C-Zeichenfolgen kopiert werden.

```cpp
basic_string<CharType, Traits, Allocator>& replace(
    size_type _Pos1,
    size_type _Num1,
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& replace(
    size_type _Pos1,
    size_type _Num1,
    const basic_string<CharType, Traits, Allocator>& str);

basic_string<CharType, Traits, Allocator>& replace(
    size_type _Pos1,
    size_type _Num1,
    const value_type* ptr,
    size_type _Num2);

basic_string<CharType, Traits, Allocator>& replace(
    size_type _Pos1,
    size_type _Num1,
    const basic_string<CharType, Traits, Allocator>& str,
    size_type _Pos2,
    size_type _Num2);

basic_string<CharType, Traits, Allocator>& replace(
    size_type _Pos1,
    size_type _Num1,
    size_type count,
    value_type _Ch);

basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,
    iterator last0,
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,
    iterator last0,
    const basic_string<CharType, Traits, Allocator>& str);

basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,
    iterator last0,
    const value_type* ptr,
    size_type _Num2);

basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,
    iterator last0,
    size_type _Num2,
    value_type _Ch);

template <class InputIterator>
basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,
    iterator last0,
    InputIterator first,
    InputIterator last);

basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,
    iterator last0,
    const_pointer first,
    const_pointer last);

basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,
    iterator last0,
    const_iterator first,
    const_iterator last);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Die Zeichenfolge, die als Quelle für die Zeichen für die Operandenzeichenfolge verwendet werden soll.

*_Pos1*<br/>
Der Index der Operandenzeichenfolge, an dem die Ersetzung beginnt.

*_Num1*<br/>
Die maximale Anzahl von Zeichen, die in der Operandenzeichenfolge ersetzt werden sollen.

*_Pos2*<br/>
Der Index der Parameterzeichenfolge, an dem der Kopiervorgang beginnt.

*_Num2*<br/>
Die maximale Anzahl von Zeichen aus der C-Parameterzeichenfolge.

*ptr*<br/>
Die C-Zeichenfolge, die als Quelle für die Zeichen für die Operandenzeichenfolge verwendet werden soll.

*_Ch*<br/>
Das Zeichen, das in die Operandenzeichenfolge kopiert werden soll.

*first0*<br/>
Ein Iterator, der das erste Zeichen adressiert, das in der Operandenzeichenfolge entfernt werden soll.

*last0*<br/>
Ein Iterator, der das letzte Zeichen adressiert, das in der Operandenzeichenfolge entfernt werden soll.

*first*<br/>
Ein Iterator, const_pointer oder const_iterator, der das erste Zeichen adressiert, das in die Parameterzeichenfolge eingefügt werden soll.

*last*<br/>
Ein Iterator, const_pointer oder const_iterator, der das letzte Zeichen adressiert, das in die Parameterzeichenfolge eingefügt werden soll.

*count*<br/>
Die Anzahl der *_Ch* in die Operandenzeichenfolge kopiert wird.

### <a name="return-value"></a>Rückgabewert

Die Operandenzeichenfolge, bei der die Ersetzung vorgenommen wurde.

### <a name="example"></a>Beispiel

```cpp
// basic_string_replace.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first two member functions replace
   // part of the operand string with
   // characters from a parameter string or C-string
   string result1a, result1b;
   string s1o ( "AAAAAAAA" );
   string s1p ( "BBB" );
   const char* cs1p = "CCC";
   cout << "The operand string s1o is: " << s1o << endl;
   cout << "The parameter string s1p is: " << s1p << endl;
   cout << "The parameter C-string cs1p is: " << cs1p << endl;
   result1a = s1o.replace ( 1 , 3 , s1p );
   cout << "The result of s1o.replace ( 1 , 3 , s1p )\n is "
        << "the string: " << result1a << "." << endl;
   result1b = s1o.replace ( 5 , 3 , cs1p );
   cout << "The result of s1o.replace ( 5 , 3 , cs1p )\n is "
        << "the string: " << result1b << "." << endl;
   cout << endl;

   // The third & fourth member function replace
   // part of the operand string with characters
   // form part of a parameter string or C-string
   string result2a, result2b;
   string s2o ( "AAAAAAAA" );
   string s2p ( "BBB" );
   const char* cs2p = "CCC";
   cout << "The operand string s2o is: " << s2o << endl;
   cout << "The parameter string s1p is: " << s2p << endl;
   cout << "The parameter C-string cs2p is: " << cs2p << endl;
   result2a = s2o.replace ( 1 , 3 , s2p , 1 , 2 );
   cout << "The result of s2o.replace (1, 3, s2p, 1, 2)\n is "
        << "the string: " << result2a << "." << endl;
   result2b = s2o.replace ( 4 , 3 , cs2p , 1 );
   cout << "The result of s2o.replace (4 ,3 ,cs2p)\n is "
        << "the string: " << result2b << "." << endl;
   cout << endl;

   // The fifth member function replaces
   // part of the operand string with characters
   string result3a;
   string s3o ( "AAAAAAAA" );
   char ch3p = 'C';
   cout << "The operand string s3o is: " << s3o << endl;
   cout << "The parameter character c1p is: " << ch3p << endl;
   result3a = s3o.replace ( 1 , 3 , 4 , ch3p );
   cout << "The result of s3o.replace(1, 3, 4, ch3p)\n is "
        << "the string: " << result3a << "." << endl;
   cout << endl;

   // The sixth & seventh member functions replace
   // part of the operand string, delineated with iterators,
   // with a parameter string or C-string
   string s4o ( "AAAAAAAA" );
   string s4p ( "BBB" );
   const char* cs4p = "CCC";
   cout << "The operand string s4o is: " << s4o << endl;
   cout << "The parameter string s4p is: " << s4p << endl;
   cout << "The parameter C-string cs4p is: " << cs4p << endl;
   basic_string<char>::iterator IterF0, IterL0;
   IterF0 = s4o.begin ( );
   IterL0 = s4o.begin ( ) + 3;
   string result4a, result4b;
   result4a = s4o.replace ( IterF0 , IterL0 , s4p );
   cout << "The result of s1o.replace (IterF0, IterL0, s4p)\n is "
        << "the string: " << result4a << "." << endl;
   result4b = s4o.replace ( IterF0 , IterL0 , cs4p );
   cout << "The result of s4o.replace (IterF0, IterL0, cs4p)\n is "
        << "the string: " << result4b << "." << endl;
   cout << endl;

   // The 8th member function replaces
   // part of the operand string delineated with iterators
   // with a number of characters from a parameter C-string
   string s5o ( "AAAAAAAF" );
   const char* cs5p = "CCCBB";
   cout << "The operand string s5o is: " << s5o << endl;
   cout << "The parameter C-string cs5p is: " << cs5p << endl;
   basic_string<char>::iterator IterF1, IterL1;
   IterF1 = s5o.begin ( );
   IterL1 = s5o.begin ( ) + 4;
   string result5a;
   result5a = s5o.replace ( IterF1 , IterL1 , cs5p , 4 );
   cout << "The result of s5o.replace (IterF1, IterL1, cs4p ,4)\n is "
        << "the string: " << result5a << "." << endl;
   cout << endl;

   // The 9th member function replaces
   // part of the operand string delineated with iterators
   // with specified characters
   string s6o ( "AAAAAAAG" );
   char ch6p = 'q';
   cout << "The operand string s6o is: " << s6o << endl;
   cout << "The parameter character ch6p is: " << ch6p << endl;
   basic_string<char>::iterator IterF2, IterL2;
   IterF2 = s6o.begin ( );
   IterL2 = s6o.begin ( ) + 3;
   string result6a;
   result6a = s6o.replace ( IterF2 , IterL2 , 4 , ch6p );
   cout << "The result of s6o.replace (IterF1, IterL1, 4, ch6p)\n is "
        << "the string: " << result6a << "." << endl;
   cout << endl;

   // The 10th member function replaces
   // part of the operand string delineated with iterators
   // with part of a parameter string delineated with iterators
   string s7o ( "OOOOOOO" );
   string s7p ( "PPPP" );
   cout << "The operand string s7o is: " << s7o << endl;
   cout << "The parameter string s7p is: " << s7p << endl;
   basic_string<char>::iterator IterF3, IterL3, IterF4, IterL4;
   IterF3 = s7o.begin ( ) + 1;
   IterL3 = s7o.begin ( ) + 3;
   IterF4 = s7p.begin ( );
   IterL4 = s7p.begin ( ) + 2;
   string result7a;
   result7a = s7o.replace ( IterF3 , IterL3 , IterF4 , IterL4 );
   cout << "The result of s7o.replace (IterF3 ,IterL3 ,IterF4 ,IterL4)\n is "
        << "the string: " << result7a << "." << endl;
   cout << endl;
}
```

```Output
The operand string s1o is: AAAAAAAA
The parameter string s1p is: BBB
The parameter C-string cs1p is: CCC
The result of s1o.replace ( 1 , 3 , s1p )
is the string: ABBBAAAA.
The result of s1o.replace ( 5 , 3 , cs1p )
is the string: ABBBACCC.

The operand string s2o is: AAAAAAAA
The parameter string s1p is: BBB
The parameter C-string cs2p is: CCC
The result of s2o.replace (1, 3, s2p, 1, 2)
is the string: ABBAAAA.
The result of s2o.replace (4 ,3 ,cs2p)
is the string: ABBAC.

The operand string s3o is: AAAAAAAA
The parameter character c1p is: C
The result of s3o.replace(1, 3, 4, ch3p)
is the string: ACCCCAAAA.

The operand string s4o is: AAAAAAAA
The parameter string s4p is: BBB
The parameter C-string cs4p is: CCC
The result of s1o.replace (IterF0, IterL0, s4p)
is the string: BBBAAAAA.
The result of s4o.replace (IterF0, IterL0, cs4p)
is the string: CCCAAAAA.

The operand string s5o is: AAAAAAAF
The parameter C-string cs5p is: CCCBB
The result of s5o.replace (IterF1, IterL1, cs4p ,4)
is the string: CCCBAAAF.

The operand string s6o is: AAAAAAAG
The parameter character ch6p is: q
The result of s6o.replace (IterF1, IterL1, 4, ch6p)
is the string: qqqqAAAAG.

The operand string s7o is: OOOOOOO
The parameter string s7p is: PPPP
The result of s7o.replace (IterF3 ,IterL3 ,IterF4 ,IterL4)
is the string: OPPOOOO.
```

## <a name="reserve"></a> basic_string::reserve

Legt die Kapazität der Zeichenfolge auf eine Zahl fest, die mindestens so groß ist, wie eine angegebene Anzahl.

```cpp
void reserve(size_type count = 0);
```

### <a name="parameters"></a>Parameter

*count*<br/>
Die Anzahl der Zeichen, für die Speicher reserviert wird.

### <a name="remarks"></a>Hinweise

Es ist wichtig, über ausreichende Kapazität zu verfügen, da Neuzuordnungen ein zeitaufwendiger Prozess sind, bei dem alle Verweise, Zeiger und Iteratoren für ungültig erklärt werden, die auf Zeichen in einer Zeichenfolge verweisen.

Das Konzept der Kapazität für Objekte des Typs „string“ ist das gleiche Konzept wie für Objekte des Typs „vector“. Im Gegensatz zu Vektor, der die Memberfunktion `reserve` aufgerufen werden, um die Kapazität eines Objekts zu verringern. Die Anforderung ist nicht bindend und kann erfolgen oder nicht. Als Standard Wert für den Parameter NULL ist, einen Aufruf der `reserve` ist eine nicht-bindende Anfrage zum Verkleinern der Kapazität der Zeichenfolge, um die Anzahl von Zeichen derzeit in der Zeichenfolge zu passen. Die Kapazität wird nie unter die aktuelle Anzahl der Zeichen reduziert.

Das Aufrufen von `reserve` ist die einzige Möglichkeit, die Kapazität einer Zeichenfolge zu verringern. Wie oben erwähnt, ist diese Anforderung nicht bindend und könnte nicht ausgeführt werden.

### <a name="example"></a>Beispiel

```cpp
// basic_string_reserve.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ("Hello world");
   cout << "The original string str1 is: " << str1 << endl;

   basic_string <char>::size_type sizeStr1, sizerStr1;
   sizeStr1 = str1.size ( );
   basic_string <char>::size_type capStr1, caprStr1;
   capStr1 = str1.capacity ( );

   // Compare size & capacity of the original string
   cout << "The current size of original string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The capacity of original string str1 is: "
        << capStr1 << "." << endl << endl;

   // Compare size & capacity of the string
   // with added capacity
   str1.reserve ( 40 );
   sizerStr1 = str1.size ( );
   caprStr1 = str1.capacity ( );

   cout << "The string str1with augmented capacity is: "
        << str1 << endl;
   cout << "The current size of string str1 is: "
        << sizerStr1 << "." << endl;
   cout << "The new capacity of string str1 is: "
        << caprStr1 << "." << endl << endl;

   // Compare size & capacity of the string
   // with downsized capacity
   str1.reserve ( );
   basic_string <char>::size_type sizedStr1;
   basic_string <char>::size_type capdStr1;
   sizedStr1 = str1.size ( );
   capdStr1 = str1.capacity ( );

   cout << "The string str1 with downsized capacity is: "
        << str1 << endl;
   cout << "The current size of string str1 is: "
        << sizedStr1 << "." << endl;
   cout << "The reduced capacity of string str1 is: "
        << capdStr1 << "." << endl << endl;
}
```

```Output
The original string str1 is: Hello world
The current size of original string str1 is: 11.
The capacity of original string str1 is: 15.

The string str1with augmented capacity is: Hello world
The current size of string str1 is: 11.
The new capacity of string str1 is: 47.

The string str1 with downsized capacity is: Hello world
The current size of string str1 is: 11.
The reduced capacity of string str1 is: 47.
```

## <a name="resize"></a> basic_string::resize

Gibt eine neue Größe für eine Zeichenfolge an und fügt Elemente an bzw. löscht sie bei Bedarf.

```cpp
void resize(
    size_type count,);

void resize(
    size_type count,
    _Elem _Ch);
```

### <a name="parameters"></a>Parameter

*count*<br/>
Die neue Größe der Zeichenfolge.

*_Ch*<br/>
Der Wert, mit dem angefügte Zeichen initialisiert werden, wenn zusätzliche Elemente erforderlich sind.

### <a name="remarks"></a>Hinweise

Wenn die resultierende Größe die maximale Anzahl an Zeichen übersteigt, löst das Formular `length_error` aus.

### <a name="example"></a>Beispiel

```cpp
// basic_string_resize.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string  str1 ( "Hello world" );
   cout << "The original string str1 is: " << str1 << endl;

   basic_string <char>::size_type sizeStr1;
   sizeStr1 = str1.size ( );
   basic_string <char>::size_type capStr1;
   capStr1 = str1.capacity ( );

   // Compare size & capacity of the original string
   cout << "The current size of original string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The capacity of original string str1 is: "
        << capStr1 << "." << endl << endl;

   // Use resize to increase size by 2 elements: exclamations
   str1.resize ( str1.size ( ) + 2 , '!' );
   cout << "The resized string str1 is: " << str1 << endl;

   sizeStr1 = str1.size ( );
   capStr1 = str1.capacity ( );

   // Compare size & capacity of a string after resizing
   cout << "The current size of resized string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The capacity of resized string str1 is: "
        << capStr1 << "." << endl << endl;

   // Use resize to increase size by 20 elements:
   str1.resize ( str1.size ( ) + 20 );
   cout << "The resized string str1 is: " << str1 << endl;

   sizeStr1 = str1.size ( );
   capStr1 = str1.capacity ( );

   // Compare size & capacity of a string after resizing
   // note capacity increases automatically as required
   cout << "The current size of modified string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The capacity of modified string str1 is: "
        << capStr1 << "." << endl << endl;

   // Use resize to downsize by 28 elements:
   str1.resize ( str1.size ( ) - 28 );
   cout << "The downsized string str1 is: " << str1 << endl;

   sizeStr1 = str1.size (  );
   capStr1 = str1.capacity (  );

   // Compare size & capacity of a string after downsizing
   cout << "The current size of downsized string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The capacity of downsized string str1 is: "
        << capStr1 << "." << endl;
}
```

```Output
The original string str1 is: Hello world
The current size of original string str1 is: 11.
The capacity of original string str1 is: 15.

The resized string str1 is: Hello world!!
The current size of resized string str1 is: 13.
The capacity of resized string str1 is: 15.

The resized string str1 is: Hello world!!
The current size of modified string str1 is: 33.
The capacity of modified string str1 is: 47.

The downsized string str1 is: Hello
The current size of downsized string str1 is: 5.
The capacity of downsized string str1 is: 47.
```

## <a name="reverse_iterator"></a> basic_string::reverse_iterator

Ein Typ, der einen Verweis auf ein in einer Zeichenfolge gespeichertes Element bereitstellt.

```cpp
typedef std::reverse_iterator<iterator> reverse_iterator;
```

### <a name="remarks"></a>Hinweise

Ein Typ `reverse_iterator` kann verwendet werden, um den Wert eines Zeichens zu ändern und wird verwendet, um die Zeichenfolge in umgekehrter Reihenfolge zu durchlaufen.

### <a name="example"></a>Beispiel

Im Beispiel für [rbegin](#rbegin) wird verdeutlicht, wie `reverse_iterator` deklariert und verwendet wird.

## <a name="rfind"></a> basic_string::rfind

Sucht eine Zeichenfolge rückwärts nach dem ersten Vorkommen einer Teilzeichenfolge ab, die mit einer bestimmten Zeichensequenz übereinstimmt.

```cpp
size_type rfind(
    value_type _Ch,
    size_type _Off = npos) const;

size_type rfind(
    const value_type* ptr,
    size_type _Off = npos) const;

size_type rfind(
    const value_type* ptr,
    size_type _Off,
    size_type count) const;

size_type rfind(
    const basic_string<CharType, Traits, Allocator>& str,
    size_type _Off = npos) const;
```

### <a name="parameters"></a>Parameter

*_Ch*<br/>
Der Zeichenwert, nach dem die Memberfunktion suchen soll.

*_Off*<br/>
Index der Position, an der die Suche beginnen soll.

*ptr*<br/>
Die C-Zeichenfolge, nach der die Memberfunktion suchen soll.

*count*<br/>
Die Anzahl von Zeichen, vom ersten Zeichen vorwärts, in der C-Zeichenfolge nach der die Memberfunktion suchen soll.

*str*<br/>
Die Zeichenfolge, nach der die Memberfunktion suchen soll.

### <a name="return-value"></a>Rückgabewert

Der Index des letzten Vorkommens des ersten Zeichens der Teilzeichenfolge, nach der bei Erfolg rückwärts gesucht wird; andernfalls `npos`.

### <a name="example"></a>Beispiel

```cpp
// basic_string_rfind.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function
   // searches for a single character in a string
   string str1 ( "Hello Everyone" );
   cout << "The original string str1 is: " << str1 << endl;
   basic_string <char>::size_type indexCh1a, indexCh1b;
   static const basic_string <char>::size_type npos = -1;

   indexCh1a = str1.rfind ( "e" , 9 );
   if ( indexCh1a != npos )
      cout << "The index of the 1st 'e' found before the 9th"
           << " position in str1 is: " << indexCh1a << endl;
   else
      cout << "The character 'e' was not found in str1 ." << endl;

   indexCh1b = str1.rfind ( "x" );
   if ( indexCh1b != npos )
      cout << "The index of the 'x' found in str1 is: "
           << indexCh1b << endl << endl;
   else
      cout << "The character 'x' was not found in str1."
           << endl << endl;

   // The second member function searches a string
   // for a substring as specified by a C-string
   string str2 ( "Let me make this perfectly clear." );
   cout << "The original string str2 is: " << str2 << endl;
   basic_string <char>::size_type indexCh2a, indexCh2b;

   const char *cstr2 = "perfect";
   indexCh2a = str2.rfind ( cstr2 , 30 );
   if ( indexCh2a != npos )
      cout << "The index of the 1st element of 'perfect' "
           << "before\n the 30th position in str2 is: "
           << indexCh2a << endl;
   else
      cout << "The substring 'perfect' was not found in str2 ."
           << endl;

   const char *cstr2b = "imperfectly";
   indexCh2b = str2.rfind ( cstr2b , 30 );
   if ( indexCh2b != npos )
      cout << "The index of the 1st element of 'imperfect' "
           << "before\n the 5th position in str3 is: "
           << indexCh2b << endl;
   else
      cout << "The substring 'imperfect' was not found in str2 ."
           << endl << endl;

   // The third member function searches a string
   // for a substring as specified by a C-string
   string str3 ( "It is a nice day. I am happy." );
   cout << "The original string str3 is: " << str3 << endl;
   basic_string <char>::size_type indexCh3a, indexCh3b;

   const char *cstr3a = "nice";
   indexCh3a = str3.rfind ( cstr3a );
   if ( indexCh3a != npos )
      cout << "The index of the 1st element of 'nice' "
           << "in str3 is: " << indexCh3a << endl;
   else
      cout << "The substring 'nice' was not found in str3 ."
           << endl;

   const char *cstr3b = "am";
   indexCh3b = str3.rfind ( cstr3b , indexCh3a + 25 , 2 );
   if ( indexCh3b != npos )
      cout << "The index of the next occurrance of 'am' in "
           << "str3 begins at: " << indexCh3b << endl << endl;
   else
      cout << "There is no next occurrence of 'am' in str3 ."
           << endl << endl;

   // The fourth member function searches a string
   // for a substring as specified by a string
   string str4 ( "This perfectly unclear." );
   cout << "The original string str4 is: " << str4 << endl;
   basic_string <char>::size_type indexCh4a, indexCh4b;

   string str4a ( "clear" );
   indexCh4a = str4.rfind ( str4a , 15 );
   if (indexCh4a != npos )
      cout << "The index of the 1st element of 'clear' "
           << "before\n the 15th position in str4 is: "
           << indexCh4a << endl;
   else
      cout << "The substring 'clear' was not found in str4 "
           << "before the 15th position." << endl;

   string str4b ( "clear" );
   indexCh4b = str4.rfind ( str4b );
   if ( indexCh4b != npos )
      cout << "The index of the 1st element of 'clear' "
           << "in str4 is: "
           << indexCh4b << endl;
   else
      cout << "The substring 'clear' was not found in str4 ."
           << endl << endl;
}
```

```Output
The original string str1 is: Hello Everyone
The index of the 1st 'e' found before the 9th position in str1 is: 8
The character 'x' was not found in str1.

The original string str2 is: Let me make this perfectly clear.
The index of the 1st element of 'perfect' before
the 30th position in str2 is: 17
The substring 'imperfect' was not found in str2 .

The original string str3 is: It is a nice day. I am happy.
The index of the 1st element of 'nice' in str3 is: 8
The index of the next occurrance of 'am' in str3 begins at: 20

The original string str4 is: This perfectly unclear.
The substring 'clear' was not found in str4 before the 15th position.
The index of the 1st element of 'clear' in str4 is: 17
```

## <a name="shrink_to_fit"></a> basic_string::shrink_to_fit

Verwirft die Überkapazität der Zeichenfolge.

```cpp
void shrink_to_fit();
```

### <a name="remarks"></a>Hinweise

Diese Memberfunktion löscht nicht mehr benötigten Speicherplatz im Container.

## <a name="size"></a> basic_string::size

Gibt die aktuelle Anzahl von Elementen in einer Zeichenfolge zurück.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Rückgabewert

Die Länge der Zeichenfolge.

### <a name="example"></a>Beispiel

```cpp
// basic_string_size.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ("Hello world");
   cout << "The original string str1 is: " << str1 << endl;

   // The size and length member functions differ in name only
   basic_string <char>::size_type sizeStr1, lenStr1;
   sizeStr1 = str1.size (  );
   lenStr1 = str1.length (  );

   basic_string <char>::size_type capStr1, max_sizeStr1;
   capStr1 = str1.capacity (  );
   max_sizeStr1 = str1.max_size (  );

   // Compare size, length, capacity & max_size of a string
   cout << "The current size of original string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The current length of original string str1 is: "
        << lenStr1 << "." << endl;
   cout << "The capacity of original string str1 is: "
        << capStr1 << "." << endl;
   cout << "The max_size of original string str1 is: "
        << max_sizeStr1 << "." << endl << endl;

   str1.erase ( 6, 5 );
   cout << "The modified string str1 is: " << str1 << endl;

   sizeStr1 = str1.size ( );
   lenStr1 = str1.length ( );
   capStr1 = str1.capacity ( );
   max_sizeStr1 = str1.max_size ( );

   // Compare size, length, capacity & max_size of a string
   // after erasing part of the original string
   cout << "The current size of modified string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The current length of modified string str1 is: "
        << lenStr1 << "." << endl;
   cout << "The capacity of modified string str1 is: "
        << capStr1 << "." << endl;
   cout << "The max_size of modified string str1 is: "
        << max_sizeStr1 << "." << endl;
}
```

## <a name="size_type"></a> basic_string::size_type

Ein Ganzzahltyp ohne Vorzeichen, der die Anzahl von Elementen und Indizes in einer Zeichenfolge darstellen kann.

```cpp
typedef typename allocator_type::size_type size_type;
```

### <a name="remarks"></a>Hinweise

Er entspricht `allocator_type::size_type`.

Für den Typ `string`, dies ist äquivalent zum `size_t`.

### <a name="example"></a>Beispiel

```cpp
// basic_string_size_type.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   string str1 ( "Hello world" );

   basic_string <char>::size_type sizeStr1, capStr1;
   sizeStr1 = str1.size (  );
   capStr1 = str1.capacity (  );

   cout << "The current size of string str1 is: "
        << sizeStr1 << "." << endl;
   cout << "The capacity of string str1 is: " << capStr1
         << "." << endl;
}
```

```Output
The current size of string str1 is: 11.
The capacity of string str1 is: 15.
```

## <a name="substr"></a> basic_string::substr

Kopiert eine Teilzeichenfolge höchstens einer beliebigen Anzahl von Zeichen aus einer Zeichenfolge, beginnend an einer angegebenen Position.

```cpp
basic_string<CharType, Traits, Allocator> substr(
    size_type _Off = 0,
    size_type count = npos) const;
```

### <a name="parameters"></a>Parameter

*_Off*<br/>
Ein Index mit Standardwert 0, der das Element an der Position lokalisiert, von der die Kopie der Zeichenfolge erstellt wird.

*count*<br/>
Die Anzahl der Zeichen, die kopiert werden sollen, sofern sie vorhanden sind.

### <a name="return-value"></a>Rückgabewert

Ein Teilzeichenfolgenobjekt, das eine Kopie der Elemente der Operandenzeichenfolge ist, die an der vom ersten Argument angegebenen Position beginnt.

### <a name="example"></a>Beispiel

```cpp
// basic_string_substr.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   string  str1 ("Heterological paradoxes are persistent.");
   cout << "The original string str1 is: \n " << str1
        << endl << endl;

   basic_string <char> str2 = str1.substr ( 6 , 7 );
   cout << "The substring str1 copied is: " << str2
        << endl << endl;

   basic_string <char> str3 = str1.substr (  );
   cout << "The default substring str3 is: \n " << str3
        <<  "\n which is the entire original string." << endl;
}
```

```Output
The original string str1 is:
Heterological paradoxes are persistent.

The substring str1 copied is: logical

The default substring str3 is:
Heterological paradoxes are persistent.
which is the entire original string.
```

## <a name="swap"></a> basic_string::swap

Tauschen Sie den Inhalt von zwei Zeichenfolgen aus.

```cpp
void swap(
    basic_string<CharType, Traits, Allocator>& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Die Quellzeichenfolge, deren Elemente mit denen in der Zielzeichenfolge ausgetauscht werden sollen.

### <a name="remarks"></a>Hinweise

Wenn die Zeichenfolgen, die ausgetauscht werden, über das gleiche Zuweisungsobjekt verfügen, passiert folgendes mit der Memberfunktion `swap`:

- Sie tritt in konstanter Zeit auf.

- Sie löst keine Ausnahmen aus.

- Erklärt keine Verweise, Zeiger oder Iteratoren für ungültig, die Elemente in den beiden Zeichenfolgen festlegen.

Andernfalls führt Sie proportional zur Anzahl der Elemente in den beiden kontrollierten Sequenzen eine Reihe von Elementzuweisungen und Konstruktoraufrufe aus.

### <a name="example"></a>Beispiel

```cpp
// basic_string_swap.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "Tweedledee" );
   string s2 ( "Tweedledum" );
   cout << "Before swapping string s1 and s2:" << endl;
   cout << " The basic_string s1 = " << s1 << "." << endl;
   cout << " The basic_string s2 = " << s2 << "." << endl;

   s1.swap ( s2 );
   cout << "After swapping string s1 and s2:" << endl;
   cout << " The basic_string s1 = " << s1 << "." << endl;
   cout << " The basic_string s2 = " << s2 << "." << endl;
}
```

```Output
Before swapping string s1 and s2:
The basic_string s1 = Tweedledee.
The basic_string s2 = Tweedledum.
After swapping string s1 and s2:
The basic_string s1 = Tweedledum.
The basic_string s2 = Tweedledee.
```

## <a name="traits_type"></a> basic_string::traits_type

Ein Typ für die Zeichenmerkmale der in einer Zeichenfolge gespeicherten Elemente.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für den zweiten Vorlagenparameter `Traits`.

Für den Typ `string`, dies ist äquivalent zum **Char_traits\<Char >**.

### <a name="example"></a>Beispiel

Im Beispiel für [copy](../standard-library/char-traits-struct.md#copy) wird verdeutlicht, wie `traits_type` deklariert und verwendet wird.

## <a name="value_type"></a> basic_string::value_type

Ein Typ, der die Art der in einer Zeichenfolge gespeicherten Zeichen darstellt.

```cpp
typedef typename allocator_type::value_type value_type;
```

### <a name="remarks"></a>Hinweise

Dies ist äquivalent zum `traits_type::char_type` entspricht **Char** für Objekte vom Typ `string`.

### <a name="example"></a>Beispiel

```cpp
// basic_string_value_type.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   basic_string<char>::value_type ch1 = 'G';

   char ch2 = 'H';

   cout << "The character ch1 is: " << ch1 << "." << endl;
   cout << "The character ch2 is: " << ch2 << "." << endl;
}
```

```Output
The character ch1 is: G.
The character ch2 is: H.
```

## <a name="see-also"></a>Siehe auch

[\<string>](../standard-library/string.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
