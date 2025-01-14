---
title: treat_as_floating_point-Struktur
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
ms.openlocfilehash: 1b7b58983032ee74ed3d88feb7325cd537e1cc2f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411941"
---
# <a name="treatasfloatingpoint-structure"></a>treat_as_floating_point-Struktur

Gibt an, ob `Rep` als Gleitkommatyp behandelt werden kann.

## <a name="syntax"></a>Syntax

```cpp
template <class Rep>
struct treat_as_floating_point : is_floating_point<Rep>;
```

## <a name="remarks"></a>Hinweise

`Rep` kann nur als Gleitkommatyp behandelt werden, wenn die Spezialisierung `treat_as_floating_point<Rep>` von [true_type](../standard-library/type-traits-typedefs.md#true_type) abgeleitet wird. Die Vorlagenklasse kann für einen benutzerdefinierten Typ abgeleitet werden.

## <a name="requirements"></a>Anforderungen

**Header:** \<chrono>

**Namespace:** std::chrono

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono>](../standard-library/chrono.md)<br/>
