---
title: is_move_constructible-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_move_constructible
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
ms.openlocfilehash: 1b1e450338a123c51b80f40f2369207c8b987cd6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383632"
---
# <a name="ismoveconstructible-class"></a>is_move_constructible-Klasse

Testet, ob der Typ einen Bewegungskonstruktor aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der auszuwertende Typ.

## <a name="remarks"></a>Hinweise

Ein typprädikat, der auf "true" den Typ ergibt *T* mithilfe eines Verschiebevorgangs konstruiert werden kann. Dieses Prädikat entspricht `is_constructible<T, T&&>`.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
