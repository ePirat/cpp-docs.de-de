---
title: __outbytestring
ms.date: 11/04/2016
f1_keywords:
- __outbytestring
helpviewer_keywords:
- rep outsb instruction
- __outbytestring intrinsic
- outsb instruction
ms.assetid: c9150661-9c18-427f-bae8-710bba6ed78c
ms.openlocfilehash: 41064dda6a1a0b9ad4c15f98c3f3081f08ef8db6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396612"
---
# <a name="outbytestring"></a>__outbytestring

**Microsoft-spezifisch**

Generiert die `rep outsb` -Anweisung, die die erste sendet `Count` Datenbytes verweist `Buffer` an den Port, der anhand des `Port`.

## <a name="syntax"></a>Syntax

```
void __outbytestring(
   unsigned short Port,
   unsigned char* Buffer,
   unsigned long Count
);
```

#### <a name="parameters"></a>Parameter

*Port*<br/>
[in] Der Port, der die Daten zu senden.

*Buffer*<br/>
[in] Die Daten, die über den angegebenen Port gesendet werden.

*Anzahl*<br/>
[in] Die Anzahl der Bytes an Daten gesendet werden.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__outbytestring`|x86, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese Routine ist nur als systeminterne Funktion verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)