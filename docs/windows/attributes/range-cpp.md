---
title: Bereich (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.range
dev_langs:
- C++
helpviewer_keywords:
- range attribute
ms.assetid: f352f79e-ecb3-4cdd-9cdd-8406ef473594
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 593cfbd4b7430c3f6ac5b4f2ab1053665136ab25
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48790619"
---
# <a name="range-c"></a>range (C++)

Gibt einen Bereich der zulässigen Werte für die Argumente oder Felder, deren Werte zur Laufzeit festgelegt werden.

## <a name="syntax"></a>Syntax

```cpp
[ range(low, high) ]
```

### <a name="parameters"></a>Parameter

*low*<br/>
Der untere Bereichswert.

*high*<br/>
Der Wert des hohen Bereichs.

## <a name="remarks"></a>Hinweise

Die **Bereich** C++-Attribut hat die gleiche Funktionalität wie die [Bereich](/windows/desktop/Midl/range) MIDL-Attribut.

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_range.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface ICustom {
   HRESULT Custom([in] long l, [out, retval] long *pLong);
   HRESULT length_is1([in, range(0, 999)] long f, [in, length_is(f)] char array[10]);
   HRESULT length_is2([in, range(-99, -1)] long f, [in, length_is("f"), size_is(10)] char *array);
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Parameter für die Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)<br/>
[Datenmemberattribute](data-member-attributes.md)  