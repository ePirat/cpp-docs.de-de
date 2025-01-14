---
title: _execute_onexit_table, _initialize_onexit_table, _register_onexit_function
ms.date: 11/04/2016
apiname:
- _execute_onexit_table
- _initialize_onexit_table
- _register_onexit_function
apilocation:
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _execute_onexit_table
- process/_execute_onexit_table
- _initialize_onexit_table
- process/_initialize_onexit_table
- _register_onexit_function
- process/_register_onexit_function
helpviewer_keywords:
- _execute_onexit_table function
- _initialize_onexit_table function
- _register_onexit_function function
ms.assetid: ad9e4149-d4ad-4fdf-aaaf-cf786fcb4473
ms.openlocfilehash: 0090d5d1504f4320c122ae1e811e0af88cccdd2e
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57741627"
---
# <a name="executeonexittable-initializeonexittable-registeronexitfunction"></a>_execute_onexit_table, _initialize_onexit_table, _register_onexit_function

Verwaltet die Routinen, die zum Zeitpunkt der Beendigung aufgerufen werden sollen.

## <a name="syntax"></a>Syntax

```
int _initialize_onexit_table(
    _onexit_table_t* table
    );

int _register_onexit_function(
    _onexit_table_t* table,
    _onexit_t        function
    );

int _execute_onexit_table(
    _onexit_table_t* table
    );
```

#### <a name="parameters"></a>Parameter

*table*<br/>
[in, out]: Ein Zeiger auf die onexit-Funktionstabelle.

*function*<br/>
[in]: Ein Zeiger auf eine Funktion zum Hinzufügen zur onexit-Funktionstabelle.

## <a name="return-value"></a>Rückgabewert

Im Erfolgsfall wird 0 zurückgegeben. Andernfalls wird ein negativer Wert zurückgegeben.

## <a name="remarks"></a>Anmerkungen

Diese Funktionen sind Details zur Implementierung der Infrastruktur und unterstützen die C-Laufzeit. Sie sollten nicht direkt aus Ihrem Code aufgerufen werden. Die C-Laufzeit verwendet eine *onexit-Funktionstabelle* zum Darstellen einer Sequenz von Funktionen, die durch Aufrufe von `atexit`, `at_quick_exit` und `_onexit` registriert werden. Die Datenstruktur der onexit-Funktionstabelle ist ein undurchsichtiges Implementierungsdetail der C-Laufzeit; die Reihenfolge und Bedeutung der Datenmember ändert sich möglicherweise. Sie sollten nicht durch externen Code überprüft werden.

Die Funktion `_initialize_onexit_table` initialiseirt die onexit-Funktionstabelle auf ihren Anfangswert.  Diese Funktion muss aufgerufen werden bevor die onexit-Funktionstabelle an entweder `_register_onexit_function` oder `_execute_onexit_table` weitergegeben wird.

Die `_register_onexit_function` Funktion fügt eine Funktion an das Ende der onexit-Funktionstabelle an.

Die Funktion `_execute_onexit_table` führt alle Funktionen in der onexit-Funktion-Tabelle aus, löscht die Tabelle, und gibt dann zurück. Nach Aufruf von `_execute_onexit_table` befindet sich die Tabelle in einem ungültigen Zustand. Sie muss durch einen Aufruf von `_initialize_onexit_table` neu initialisiert werden, bevor sie erneut verwendet wird.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`_initialize_onexit_table function`, `_register_onexit_function`, `_execute_onexit_table`|C, C++: \<process.h>|

Die Funktionen `_initialize_onexit_table`, `_register_onexit_function` und `_execute_onexit_table` sind Microsoft-spezifisch. Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[atexit](../c-runtime-library/reference/atexit.md)<br/>
[exit, _Exit, _exit](../c-runtime-library/reference/exit-exit-exit.md)<br/>
[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)
