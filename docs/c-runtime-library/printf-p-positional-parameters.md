---
title: printf_p-Positionsparameter
ms.date: 11/04/2016
apilocation:
- msvcr120.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr80.dll
- msvcr100.dll
apitype: DLLExport
helpviewer_keywords:
- _printf_p function, positional parameters
- printf_p function, positional parameters
ms.assetid: beb4fd85-a7aa-4665-9085-2c907a5b9ab0
ms.openlocfilehash: f6ee84a68b2f40e535ed1dc76e4617a21bb29a6e
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751465"
---
# <a name="printfp-positional-parameters"></a>printf_p-Positionsparameter

Positionsparameter bieten die Möglichkeit, mithilfe einer Zahl anzugeben, welche Argumente in einem Feld in einer Formatzeichenfolge ersetzt werden sollen. Die folgenden `printf`-Positionsparameterfunktionen sind verfügbar:

| Nicht die Position angebende printf-Funktionen | Entsprechungen der Positionsparameter |
|---|---|
|[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|
|[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|[_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|
|[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|[_cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l](../c-runtime-library/reference/cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)|
|[fprintf, _fprintf_l, fwprintf, _fwprintf_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|
|[vprintf, _vprintf_l, vwprintf, _vwprintf_l](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|[_vprintf_p, _vprintf_p_l, _vwprintf_p, _vwprintf_p_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)|
|[vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|[_vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)|
|[vsprintf, _vsprintf_l, vswprintf, _vswprintf_l, \__vswprintf_l](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)|[_vsprintf_p, _vsprintf_p_l, _vswprintf_p, _vswprintf_p_l](../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)|

## <a name="how-to-specify-positional-parameters"></a>Angeben von Positionsparametern

### <a name="parameter-indexing"></a>Parameterindizierung

Standardmäßig verhalten sich Positionsfunktionen und Nicht-Positionsfunktionen identisch, wenn keine Positionsformatierung vorhanden ist. Sie geben den zu formatierenden Positionsparameter an, indem Sie `%n$` am Beginn des Formatbezeichners verwenden, wobei `n` die Position des zu formatierenden Parameters in der Parameterliste ist. Die Parameterposition beginnt bei 1 für das erste Argument nach der Formatzeichenfolge. Der Rest des Formatbezeichners folgt den gleichen Regeln wie der `printf`-Formatbezeichner. Weitere Informationen zu Formatbezeichnern finden Sie unter [Syntax der Formatangabe: printf- und wprintf-Funktionen](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

Im Folgenden finden Sie ein Beispiel für die Positionsformatierung:

```C
_printf_p("%1$s %2$s", "November", "10");
```

Dies ergibt folgende Ausgabe:

```
November 10
```

Die Reihenfolge der Zahlen muss nicht mit der Reihenfolge der Argumente übereinstimmen. Dies ist z.B. eine gültige Formatzeichenfolge:

```C
_printf_p("%2$s %1$s", "November", "10");
```

Dies ergibt folgende Ausgabe:

```
10 November
```

Im Gegensatz zu herkömmlichen Formatzeichenfolgen können Positionsparameter in einer Formatzeichenfolge mehrmals verwendet werden. Ein auf ein Objekt angewendeter

```C
_printf_p("%1$d times %1$d is %2$d", 10, 100);
```

Dies ergibt folgende Ausgabe:

```
10 times 10 is 100
```

Alle Argumente müssen mindestens einmal in der Formatzeichenfolge verwendet werden. Die maximale Anzahl von Positionsparametern, die in einer Formatzeichenfolge zulässig sind, ist durch `_ARGMAX` angegeben.

### <a name="width-and-precision"></a>Breite und Genauigkeit

Sie können `*n$` verwenden, um einen Positionsparameter als Breiten- oder Genauigkeitsbezeichner anzugeben, wobei `n` die Position des Breiten- oder Genauigkeitsbezeichners in der Parameterliste ist. Die Position des Breiten- oder Genauigkeitswerts muss unmittelbar nach dem \*-Symbol folgen. Ein auf ein Objekt angewendeter

```C
_printf_p("%1$*2$s","Hello", 10);
```

oder

```C
_printf_p("%2$*1$s", 10, "Hello");
```

### <a name="mixing-positional-and-non-positional-arguments"></a>Mischen von Positions- und Nicht-Positionsargumenten

Positionsparameter dürfen nicht mit Nicht-Positionsparametern in der gleichen Formatzeichenfolge kombiniert werden. Wenn die Positionsformatierung verwendet wird, muss diese von allen Formatbezeichnern verwendet werden. `printf_p`- und verwandte Funktionen unterstützen jedoch weiterhin Nicht-Positionsparameter in Formatzeichenfolgen ohne Positionsparameter.

## <a name="example"></a>Beispiel

```C
// positional_args.c
// Build by using: cl /W4 positional_args.c
// Positional arguments allow the specification of the order
// in which arguments are consumed in a formatting string.

#include <stdio.h>

int main()
{
    int     i = 1,
            j = 2,
            k = 3;
    double  x = 0.1,
            y = 2.22,
            z = 333.3333;
    char    *s1 = "abc",
            *s2 = "def",
            *s3 = "ghi";

    // If positional arguments are unspecified,
    // normal input order is used.
    _printf_p("%d %d %d\n", i, j, k);

    // Positional arguments are numbers followed by a $ character.
    _printf_p("%3$d %1$d %2$d\n", i, j, k);

    // The same positional argument may be reused.
    _printf_p("%1$d %2$d %1$d\n", i, j);

    // The positional arguments may appear in any order.
    _printf_p("%1$s %2$s %3$s\n", s1, s2, s3);
    _printf_p("%3$s %1$s %2$s\n", s1, s2, s3);

    // Precision and width specifiers must be int types.
    _printf_p("%3$*5$f %2$.*4$f %1$*4$.*5$f\n", x, y, z, j, k);
}
```

```Output
1 2 3
3 1 2
1 2 1
abc def ghi
ghi abc def
333.333300 2.22 0.100
```

## <a name="see-also"></a>Siehe auch

[Syntax der Formatangabe: printf- und wprintf-Funktionen](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)
