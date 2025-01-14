---
title: add_const-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_const
helpviewer_keywords:
- add_const class
- add_const
ms.assetid: 1262a1eb-8c9c-4dd6-9f43-88ba280182f1
ms.openlocfilehash: dc457fd4efba538e96200f7f42f84a73fc1b5228
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411239"
---
# <a name="addconst-class"></a>add_const-Klasse

Erstellt den „const“-Typ aus „type“.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct add_const;
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typmodifizierers enthält einen geänderten Typ, der *Ty* Wenn *Ty* ist ein Verweis, eine Funktion oder ein konstant qualifizierter Typ ist, andernfalls `const Ty`.

## <a name="example"></a>Beispiel

```cpp
// std__type_traits__add_const.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
{
    std::add_const<int>::type *p = (const int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_const<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_const<int> == int
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_const-Klasse](../standard-library/remove-const-class.md)<br/>
