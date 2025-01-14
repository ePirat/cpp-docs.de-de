---
title: filesystem_error-Klasse
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
ms.openlocfilehash: add1e0da43a44c35f39c96e8d65e36aeea0d3afb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405156"
---
# <a name="filesystemerror-class"></a>filesystem_error-Klasse

Eine Basisklasse für alle Ausnahmen, die ausgelöst werden, um einen Systemüberlauf auf niedriger Ebene zu melden.

## <a name="syntax"></a>Syntax

```cpp
class filesystem_error    : public system_error;
```

## <a name="remarks"></a>Hinweise

Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um einen Fehler in \<filesystem>-Funktionen zu melden. Sie speichert ein Objekt des Typs `string`namens `mymesg` hier, um den Zweck der Darstellung. Es speichert zudem zwei Objekte des Typs `path`namens `mypval1` und `mypval2`.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[filesystem_error](#filesystem_error)|Erstellt eine `filesystem_error` Nachricht.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[path1](#path1)|Gibt `mypval1` zurück.|
|[path2](#path2)|Gibt `mypval2` zurück.|
|[what](#what)|Gibt einen Zeiger auf ein `NTBS` zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** \<filesystem>

**Namespace:** std::experimental::filesystem

## <a name="filesystem_error"></a> filesystem_error:: filesystem_error

Der erste Konstruktor erstellt die Meldung aus *"what_arg"* und *Ec*. Der zweite Konstruktor erstellt auch die Meldung aus *"pval1"*, die in gespeichert `mypval1`. Der dritte Konstruktor erstellt auch die Meldung aus *"pval1"*, die in gespeichert `mypval1`, und von *pval2*, die in gespeichert `mypval2`.

```cpp
filesystem_error(const string& what_arg,
    error_code ec);

filesystem_error(const string& what_arg,
    const path& pval1,
    error_code ec);

filesystem_error(const string& what_arg,
    const path& pval1,
    const path& pval2,
    error_code ec);
```

### <a name="parameters"></a>Parameter

*what_arg*<br/>
Angegebene Nachricht.

*ec*<br/>
Angegebene Fehlercode.

*mypval1*<br/>
Weitere angegebenen Meldungsparameter.

*mypval2*<br/>
Weitere Nachricht der angegebenen Parameter.

## <a name="path1"></a> filesystem_error:: path1

Die Memberfunktion gibt `mypval1` zurück.

```cpp
const path& path1() const noexcept;
```

## <a name="path2"></a> filesystem_error:: path2

Die Memberfunktion gibt `mypval2` zurück.

```cpp
const path& path2() const noexcept;
```

## <a name="what"></a> filesystem_error::What

Die Memberfunktion gibt einen Zeiger auf ein `NTBS`vorzugsweise aus besteht aus `runtime_error::what()`, `system_error::what()`, `mymesg`, `mypval1.native_string()`, und `mypval2.native_string()`.

```cpp
const char *what() const noexcept;
```

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[system_error-Klasse](../standard-library/system-error-class.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[\<exception>](../standard-library/exception.md)<br/>
