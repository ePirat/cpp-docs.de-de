---
title: basic_ofstream-Klasse
ms.date: 11/04/2016
f1_keywords:
- fstream/std::basic_ofstream
- fstream/std::basic_ofstream::close
- fstream/std::basic_ofstream::is_open
- fstream/std::basic_ofstream::open
- fstream/std::basic_ofstream::rdbuf
- fstream/std::basic_ofstream::swap
helpviewer_keywords:
- std::basic_ofstream [C++]
- std::basic_ofstream [C++], close
- std::basic_ofstream [C++], is_open
- std::basic_ofstream [C++], open
- std::basic_ofstream [C++], rdbuf
- std::basic_ofstream [C++], swap
ms.assetid: 3bcc9c51-6dfc-4844-8fcc-22ef57c9dff1
ms.openlocfilehash: 9a8255a02c46a4ade33bd95635516e5d36fe8e64
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409797"
---
# <a name="basicofstream-class"></a>basic_ofstream-Klasse

Beschreibt ein Objekt, das das Einfügen von Elementen und codierten Objekten in einen Streampuffer der Klasse [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> mit Elementen des Typs `Elem` steuert, dessen Zeichenmerkmale von der Klasse `Tr` bestimmt werden.

## <a name="syntax"></a>Syntax

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ofstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>Parameter

*Elem*<br/>
Das grundlegende Element des Dateipuffers.

*Tr*<br/>
Die Merkmale des grundlegenden Elements des Dateipuffers (in der Regel `char_traits`< `Elem`>).

## <a name="remarks"></a>Hinweise

Wenn die **"wchar_t"** Spezialisierung `basic_ofstream` schreibt Sie in der Datei, wenn die Datei im Textmodus geöffnet wird eine MBCS-Sequenz geschrieben. Die interne Darstellung verwendet einen Puffer mit `wchar_t`-Zeichen.

Das Objekt speichert ein Objekt der Klasse `basic_filebuf`< `Elem`, `Tr`>.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie ein `basic_ofstream`-Objekt erstellt und Text in dieses Objekt geschrieben wird.

```cpp
// basic_ofstream_class.cpp
// compile with: /EHsc
#include <fstream>

using namespace std;

int main(int argc, char **argv)
{
    ofstream ofs("ofstream.txt");
    if (!ofs.bad())
    {
        ofs << "Writing to a basic_ofstream object..." << endl;
        ofs.close();
    }
}
```

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[basic_ofstream](#basic_ofstream)|Erstellt ein Objekt des Typs `basic_ofstream`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[close](#close)|Schließt eine Datei.|
|[is_open](#is_open)|Ermittelt, ob eine Datei geöffnet ist.|
|[open](#open)|Öffnet eine Datei.|
|[rdbuf](#rdbuf)|Gibt die Adresse des gespeicherten Streampuffers zurück.|
|[swap](#swap)|Tauscht den Inhalt dieses `basic_ofstream`-Objekts gegen den Inhalt des bereitgestellten `basic_ofstream`-Objekts aus.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator=](#op_eq)|Weist den Inhalt dieses Streamobjekts zu. Dies ist eine Verschiebezuweisung über einen `rvalue reference`, die keine Kopie hinterlässt.|

## <a name="requirements"></a>Anforderungen

**Header:** \<fstream>

**Namespace:** std

## <a name="basic_ofstream"></a> basic_ofstream::basic_ofstream

Erstellt ein Objekt des Typs `basic_ofstream`.

```cpp
basic_ofstream();

explicit basic_ofstream(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

explicit basic_ofstream(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

basic_ofstream(
    basic_ofstream&& right);
```

### <a name="parameters"></a>Parameter

*_Filename*<br/>
Der Name der zu öffnenden Datei.

*_Mode*<br/>
Eine der Enumerationen in [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*<br/>
Der Standardschutz bei der Dateiöffnung, der dem `shflag`-Parameter in [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md) entspricht.

*right*<br/>
Der rvalue-Verweis auf das `basic_ofstream`-Objekt, das benutzt wird, um dieses `basic_ofstream`-Objekt zu initialisieren.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert die Basisklasse durch Aufrufen von [Basic_ostream](../standard-library/basic-ostream-class.md)(`sb`), wobei `sb` das gespeicherte Objekt der Klasse [Basic_filebuf](../standard-library/basic-filebuf-class.md) <  `Elem`, `Tr`>. Er initialisiert zudem `sb` durch Aufrufen von `basic_filebuf`< `Elem`, `Tr`>.

Der zweite und dritte Konstruktor initialisiert die Basisklasse durch Aufrufen von `basic_ostream`( **sb**). Er initialisiert zudem `sb` durch Aufrufen von `basic_filebuf` <  `Elem`, `Tr`> und dann `sb`. [open](../standard-library/basic-filebuf-class.md#open)( `_Filename`, `_Mode` &#124; `ios_base::out`). Wenn die letzte Funktion einen null-Zeiger zurückgibt, ruft der Konstruktor [Setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`).

Der vierte Konstruktor ist eine Kopierfunktion. Er initialisiert das Objekt mit dem Inhalt der *rechten*, als Rvalue-Verweis behandelt.

### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie ein `basic_ofstream`-Objekt erstellt und Text in dieses Objekt geschrieben wird.

```cpp
// basic_ofstream_ctor.cpp
// compile with: /EHsc
#include <fstream>

using namespace std;

int main(int argc, char **argv)
{
    ofstream ofs("C:\\ofstream.txt");
    if (!ofs.bad())
    {
        ofs << "Writing to a basic_ofstream object..." << endl;
        ofs.close();
    }
}
```

## <a name="close"></a> basic_ofstream::close

Schließt eine Datei.

```cpp
void close();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion ruft [Rdbuf](../standard-library/basic-ifstream-class.md#rdbuf)**->**[schließen](../standard-library/basic-filebuf-class.md#close).

### <a name="example"></a>Beispiel

Sie finden ein Beispiel, in dem `close` verwendet wird, unter [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="is_open"></a> basic_ofstream::is_open

Gibt an, ob eine Datei geöffnet ist.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Datei geöffnet ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt [Rdbuf](#rdbuf) **->** [Is_open](../standard-library/basic-filebuf-class.md#is_open).

### <a name="example"></a>Beispiel

```cpp
// basic_ofstream_is_open.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main( )
{
   using namespace std;
   ifstream file;
   // Open and close with a basic_filebuf
   file.rdbuf( )->open( "basic_ofstream_is_open.txt", ios::in );
   file.close( );
   if (file.is_open())
      cout << "it's open" << endl;
   else
      cout << "it's closed" << endl;
}
```

## <a name="open"></a> basic_ofstream::open

Öffnet eine Datei.

```cpp
void open(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

void open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode);
```

### <a name="parameters"></a>Parameter

*_Filename*<br/>
Der Name der zu öffnenden Datei.

*_Mode*<br/>
Eine der Enumerationen in [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*<br/>
Der Standardschutz bei der Dateiöffnung, der dem `shflag`-Parameter in [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md) entspricht.

### <a name="remarks"></a>Hinweise

Die Memberfunktion ruft [rdbuf](#rdbuf) **->** [open](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode` &#124; `ios_base::out`) auf. Wenn diese Funktion einen null-Zeiger zurückgibt, ruft die Funktion [Setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`).

### <a name="example"></a>Beispiel

Finden Sie unter [basic_filebuf:: Open](../standard-library/basic-filebuf-class.md#open) für ein Beispiel, verwendet `open`.

## <a name="op_eq"></a> basic_ofstream::operator=

Weist den Inhalt dieses Streamobjekts zu. Dies ist eine Verschiebezuweisung über einen `rvalue reference`, die keine Kopie hinterlässt.

```cpp
basic_ofstream& operator=(basic_ofstream&& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Ein rvalue-Verweis auf ein `basic_ofstream`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt `*this`zurück.

### <a name="remarks"></a>Hinweise

Der Memberoperator ersetzt den Inhalt des Objekts anhand der Inhalte des *rechten*, als Rvalue-Verweis behandelt.

## <a name="rdbuf"></a> basic_ofstream::rdbuf

Gibt die Adresse des gespeicherten Streampuffers zurück.

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>Rückgabewert

Gibt die Adresse des gespeicherten Streampuffers zurück.

### <a name="example"></a>Beispiel

Sie finden ein Beispiel, in dem `rdbuf` verwendet wird, unter [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="swap"></a> basic_ofstream::swap

Tauscht den Inhalt von zwei `basic_ofstream`-Objekten aus.

```cpp
void swap(basic_ofstream& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Ein `lvalue`-Verweis auf ein anderes `basic_ofstream`-Objekt.

### <a name="remarks"></a>Hinweise

Die Memberfunktion tauscht den Inhalt dieses Objekts für den Inhalt des *rechten*.

## <a name="see-also"></a>Siehe auch

[basic_ostream-Klasse](../standard-library/basic-ostream-class.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>
