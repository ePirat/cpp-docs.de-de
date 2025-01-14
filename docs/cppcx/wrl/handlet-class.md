---
title: HandleT-Klasse
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Attach
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Get
- corewrappers/Microsoft::WRL::Wrappers::HandleT::handle_
- corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT
- corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
- corewrappers/Microsoft::WRL::Wrappers::HandleT::IsValid
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
- corewrappers/Microsoft::WRL::Wrappers::HandleT::~HandleT
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleT class
- Microsoft::WRL::Wrappers::HandleT::Attach method
- Microsoft::WRL::Wrappers::HandleT::Close method
- Microsoft::WRL::Wrappers::HandleT::Detach method
- Microsoft::WRL::Wrappers::HandleT::Get method
- Microsoft::WRL::Wrappers::HandleT::handle_ data member
- Microsoft::WRL::Wrappers::HandleT::HandleT, constructor
- Microsoft::WRL::Wrappers::HandleT::InternalClose method
- Microsoft::WRL::Wrappers::HandleT::IsValid method
- Microsoft::WRL::Wrappers::HandleT::operator= operator
- Microsoft::WRL::Wrappers::HandleT::~HandleT, destructor
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
ms.openlocfilehash: 6e5824da03fb85e52f413f5678ea6e0fd6c77ddd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398406"
---
# <a name="handlet-class"></a>HandleT-Klasse

Stellt ein Handle für ein Objekt dar.

## <a name="syntax"></a>Syntax

```cpp
template <typename HandleTraits>
class HandleT;
```

### <a name="parameters"></a>Parameter

*HandleTraits*<br/>
Eine Instanz von der [HandleTraits](handletraits-structure.md) abgeschrägten Designs, die allgemeinen Eigenschaften eines Handles definiert.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

Name     | Beschreibung
-------- | -----------------------------
`Traits` | Ein Synonym für `HandleTraits`.

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                | Beschreibung
----------------------------------- | --------------------------------------------------
[HandleT::HandleT](#handlet)        | Initialisiert eine neue Instanz der `HandleT`-Klasse.
[HandleT::~HandleT](#tilde-handlet) | Hebt die Initialisierung einer Instanz von der `HandleT` Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                         | Beschreibung
---------------------------- | ----------------------------------------------------------------------
[HandleT::Attach](#attach)   | Ordnet das angegebene Handle der aktuellen `HandleT` Objekt.
[HandleT::Close](#close)     | Schließt das aktuelle `HandleT` Objekt.
[HandleT::Detach](#detach)   | Hebt die Zuordnung der aktuellen `HandleT` Objekt aus der zugrunde liegende Handle.
[HandleT::Get](#get)         | Ruft den Wert, der das zugrunde liegende Handle.
[HandleT::IsValid](#isvalid) | Gibt an, ob die aktuelle `HandleT` Objekt stellt ein Handle.

### <a name="protected-methods"></a>Geschützte Methoden

Name                                     | Beschreibung
---------------------------------------- | ------------------------------------
[HandleT::InternalClose](#internalclose) | Schließt das aktuelle `HandleT` Objekt.

### <a name="public-operators"></a>Öffentliche Operatoren

Name                                   | Beschreibung
-------------------------------------- | ----------------------------------------------------------------------------------
[HandleT::operator=](#operator-assign) | Verschiebt den Wert des angegebenen `HandleT` -Objekt mit dem aktuellen `HandleT` Objekt.

### <a name="protected-data-members"></a>Geschützte Datenmember

Name                        | Beschreibung
--------------------------- | ----------------------------------------------------------------
[HandleT::handle_](#handle) | Enthält das Handle, das entspricht dem `HandleT` Objekt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`HandleT`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="tilde-handlet"></a>HandleT::~HandleT

Hebt die Initialisierung einer Instanz von der `HandleT` Klasse.

```cpp
~HandleT();
```

## <a name="attach"></a>Handlet:: Attach

Ordnet das angegebene Handle der aktuellen `HandleT` Objekt.

```cpp
void Attach(
   typename HandleTraits::Type h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Ein Handle.

## <a name="close"></a>HandleT::Close

Schließt das aktuelle `HandleT` Objekt.

```cpp
void Close();
```

### <a name="remarks"></a>Hinweise

Das Handle, das das aktuelle zugrunde liegende `HandleT` wird geschlossen, und die `HandleT` auf einen ungültigen Zustand festgelegt ist.

Wenn das Handle nicht ordnungsgemäß geschlossen wird, wird eine Ausnahme im aufrufenden Thread ausgelöst.

## <a name="detach"></a>HandleT::Detach

Hebt die Zuordnung der aktuellen `HandleT` Objekt aus der zugrunde liegende Handle.

```cpp
typename HandleTraits::Type Detach();
```

### <a name="return-value"></a>Rückgabewert

Das zugrunde liegende Handle.

### <a name="remarks"></a>Hinweise

Wenn dieser Vorgang abgeschlossen ist, die aktuelle `HandleT` auf einen ungültigen Zustand festgelegt ist.

## <a name="get"></a>HandleT::Get

Ruft den Wert, der das zugrunde liegende Handle.

```cpp
typename HandleTraits::Type Get() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle.

## <a name="handle"></a>HandleT::handle_

Enthält das Handle, das entspricht dem `HandleT` Objekt.

```cpp
typename HandleTraits::Type handle_;
```

## <a name="handlet"></a>HandleT::HandleT

Initialisiert eine neue Instanz der `HandleT`-Klasse.

```cpp
explicit HandleT(
   typename HandleTraits::Type h =
      HandleTraits::GetInvalidValue()
);

HandleT(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Ein Handle.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert ein `HandleT` -Objekt, das kein gültiges Handle für ein Objekt ist. Der zweite Konstruktor erstellt ein neues `HandleT` -Sitzungsobjekts Parameter *h*.

## <a name="internalclose"></a>HandleT::InternalClose

Schließt das aktuelle `HandleT` Objekt.

```cpp
virtual bool InternalClose();
```

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die aktuelle `HandleT` geschlossen wird, erfolgreich ist; andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

`InternalClose()` ist `protected`.

## <a name="isvalid"></a>HandleT::IsValid

Gibt an, ob die aktuelle `HandleT` Objekt stellt ein Handle.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die `HandleT` stellt ein Handle ist, andernfalls **"false"**.

## <a name="operator-assign"></a>HandleT::operator=

Verschiebt den Wert des angegebenen `HandleT` -Objekt mit dem aktuellen `HandleT` Objekt.

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Ein Rvalue-Verweis auf ein Handle.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das aktuelle `HandleT` Objekt.

### <a name="remarks"></a>Hinweise

Dieser Vorgang erklärt die `HandleT` vom Parameter angegebenen Objekts *h*.
