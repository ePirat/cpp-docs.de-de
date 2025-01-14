---
title: imaxabs
ms.date: 04/05/2018
apiname:
- imaxabs
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- imaxabs
helpviewer_keywords:
- imaxabs function
ms.assetid: de2566a3-1415-4e9a-91b5-7ac3a49ebf5e
ms.openlocfilehash: a7492e08c3a078698292923ce395524ab5327ecf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157492"
---
# <a name="imaxabs"></a>imaxabs

Berechnet den absoluten Wert einer ganzen Zahl beliebiger Größe.

## <a name="syntax"></a>Syntax

```C
intmax_t imaxabs(
   intmax_t n
);
```

### <a name="parameters"></a>Parameter

*n*<br/>
Ganzzahliger Wert.

## <a name="return-value"></a>Rückgabewert

Die **Imaxabs** Funktion gibt den absoluten Wert des Arguments zurück. Es gibt keine Fehlerrückgabe.

> [!NOTE]
> Da der Bereich von negativen ganzen Zahlen, die mithilfe von dargestellt werden können **Intmax_t** ist größer als der entsprechende Bereich von positiven ganzen Zahlen, die dargestellt werden können, ist es möglich, ein Argument bereitgestellt **Imaxabs** die kann nicht konvertiert werden. Wenn der Absolute Wert des Arguments nicht durch den Rückgabetyp dargestellt werden kann nicht eingeben, wird das Verhalten der **Imaxabs** ist nicht definiert.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**imaxabs**|\<inttypes.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_imaxabs.c
// Build using: cl /W3 /Tc crt_imaxabs.c
// This example calls imaxabs to compute an
// absolute value, then displays the results.

#include <stdio.h>
#include <stdlib.h>
#include <inttypes.h>

int main(int argc, char *argv[])
{
   intmax_t x = LLONG_MIN + 2;

   printf("The absolute value of %lld is %lld\n", x, imaxabs(x));
}
```

```Output
The absolute value of -9223372036854775806 is 9223372036854775806
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
[_cabs](cabs.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)<br/>
