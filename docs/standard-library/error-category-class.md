---
title: error_category-Klasse
ms.date: 11/04/2016
f1_keywords:
- system_error/std::error_category
- system_error/std::error_category::value_type
- system_error/std::error_category::default_error_condition
- system_error/std::error_category::equivalent
- system_error/std::error_category::message
- system_error/std::error_category::name
helpviewer_keywords:
- std::error_category
- std::error_category::value_type
- std::error_category::default_error_condition
- std::error_category::equivalent
- std::error_category::message
- std::error_category::name
ms.assetid: e0a71e14-852d-4905-acd6-5f8ed426706d
ms.openlocfilehash: 55ff55b2026b741a2b7062d815fe43d6d19b078b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413709"
---
# <a name="errorcategory-class"></a>error_category-Klasse

Stellt die abstrakte, allgemeine Basis für Objekte dar, die eine Fehlercodekategorie beschreibt.

## <a name="syntax"></a>Syntax

```cpp
class error_category;
```

## <a name="remarks"></a>Hinweise

`error_category` wird von zwei vordefinierten Objekten implementiert: [generic_category](../standard-library/system-error-functions.md#generic_category) und [system_category](../standard-library/system-error-functions.md#system_category).

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[value_type](#value_type)|Ein Typ, der den gespeicherten Fehlercodewert darstellt.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[default_error_condition](#default_error_condition)|Speichert den Fehlercodewert für ein Fehlerbedingungsobjekt.|
|[equivalent](#equivalent)|Gibt einen Wert zurück, der angibt, ob Fehlerobjekte gleichwertig sind.|
|[message](#message)|Gibt den Namen des angegebenen Fehlercodes zurück.|
|[name](#name)|Gibt den Namen der Kategorie zurück.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator==](#op_eq_eq)|Prüft auf Gleichheit zwischen `error_category`-Objekten.|
|[Operator!=](#op_neq)|Prüft auf Ungleichheit zwischen `error_category`-Objekten.|
|[operator<](#op_lt)|Testet, ob das [error_category](../standard-library/error-category-class.md)-Objekt kleiner ist als das `error_category`-Objekt, das für den Vergleich übergeben wurde.|

## <a name="requirements"></a>Anforderungen

**Header:** \<system_error>

**Namespace:** std

## <a name="default_error_condition"></a> error_category::default_error_condition

Speichert den Fehlercodewert für ein Fehlerbedingungsobjekt.

```cpp
virtual error_condition default_error_condition(int _Errval) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*_Errval*|Der Fehlercodewert, der in [error_condition](../standard-library/error-condition-class.md) gespeichert werden soll.|

### <a name="return-value"></a>Rückgabewert

Gibt `error_condition(_Errval, *this)`zurück.

### <a name="remarks"></a>Hinweise

## <a name="equivalent"></a> error_category::equivalent

Gibt einen Wert zurück, der angibt, ob Fehlerobjekte gleichwertig sind.

```cpp
virtual bool equivalent(value_type _Errval,
    const error_condition& _Cond) const;

virtual bool equivalent(const error_code& _Code,
    value_type _Errval) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*_Errval*|Der zu vergleichende Fehlercodewert.|
|*_Cond*|Das zu vergleichende [error_condition](../standard-library/error-condition-class.md)-Objekt.|
|*_Code*|Das zu vergleichende [error_code](../standard-library/error-code-class.md)-Objekt.|

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn Kategorie und Wert gleich; andernfalls sind **"false"**.

### <a name="remarks"></a>Hinweise

Die erste Memberfunktion gibt `*this == _Cond.category() && _Cond.value() == _Errval` zurück.

Die zweite Memberfunktion gibt `*this == _Code.category() && _Code.value() == _Errval` zurück.

## <a name="message"></a> error_category::message

Gibt den Namen des angegebenen Fehlercodes zurück.

```cpp
virtual string message(error_code::value_type val) const = 0;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*val*|Der zu beschreibende Fehlercodewert.|

### <a name="return-value"></a>Rückgabewert

Gibt einen beschreibenden Namen des Fehlercodes *Val* für die Kategorie.

### <a name="remarks"></a>Hinweise

## <a name="name"></a> error_category::name

Gibt den Namen der Kategorie zurück.

```cpp
virtual const char *name() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Gibt den Namen der Kategorie als Bytezeichenfolge zurück, die mit null endet.

### <a name="remarks"></a>Hinweise

## <a name="op_eq_eq"></a> error_category::operator==

Prüft auf Gleichheit zwischen `error_category`-Objekten.

```cpp
bool operator==(const error_category& right) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*right*|Das Objekt, das auf Gleichheit getestet werden soll.|

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Objekte gleich sind; **FALSE**, wenn die Objekte nicht gleich sind.

### <a name="remarks"></a>Hinweise

Dieser Memberoperator gibt `this == &right` zurück.

## <a name="op_neq"></a> error_category::operator!=

Prüft auf Ungleichheit zwischen `error_category`-Objekten.

```cpp
bool operator!=(const error_category& right) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*right*|Das Objekt, das auf Ungleichheit geprüft werden soll.|

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die `error_category` Objekt ist nicht gleich der `error_category` Objekt übergebenen *rechten*; andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Der Memberoperator gibt `(!*this == right)`zurück.

## <a name="op_lt"></a> error_category::operator&lt;

Testet, ob das [error_category](../standard-library/error-category-class.md)-Objekt kleiner ist als das `error_category`-Objekt, das für den Vergleich übergeben wurde.

```cpp
bool operator<(const error_category& right) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*right*|Das zu vergleichende `error_category`-Objekt.|

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn das Objekt, das an `error_category` übergeben wird, kleiner ist als das an `error_category` übergebene Objekt; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Memberoperator gibt `this < &right`zurück.

## <a name="value_type"></a> error_category::value_type

Ein Typ, der den gespeicherten Fehlercodewert darstellt.

```cpp
typedef int value_type;
```

### <a name="remarks"></a>Hinweise

Diese Typdefinition ist ein Synonym für **Int**.

## <a name="see-also"></a>Siehe auch

[<system_error>](../standard-library/system-error.md)<br/>
