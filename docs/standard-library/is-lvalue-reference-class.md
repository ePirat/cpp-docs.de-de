---
title: is_lvalue_reference-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_lvalue_reference
helpviewer_keywords:
- is_lvalue_reference class
- is_lvalue_reference
ms.assetid: 7f11896b-935c-4de1-9c87-9d0127f904e2
ms.openlocfilehash: e032522e790b7027886ba1a6199ed7fdf86c0936
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351942"
---
# <a name="islvaluereference-class"></a>is_lvalue_reference-Klasse

Testet, ob es sich beim Typ um einen lvalue-Verweis handelt.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_lvalue_reference;
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz dieses typprädikats ist true, wenn der Typ *Ty* ist ein Verweis auf ein Objekt oder eine Funktion ist, andernfalls "false". Beachten Sie, dass *Ty* möglicherweise nicht in ein Rvalue-Verweis. Weitere Informationen zu „rvalues“ finden Sie unter [Rvalue Reference Declarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md) (Rvalue-Verweisdeklarator: &&).

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[Lvalues und Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
