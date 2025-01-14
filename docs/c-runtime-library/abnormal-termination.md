---
title: _abnormal_termination
ms.date: 11/04/2016
apiname:
- _abnormal_termination
apilocation:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _abnormal_termination
helpviewer_keywords:
- _abnormal_termination
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
ms.openlocfilehash: 213938fa830f0a924fa954d4a36a39b544473dd4
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57741286"
---
# <a name="abnormaltermination"></a>_abnormal_termination

Gibt an, ob der `__finally`-Block einer [try-finally-Anweisung](../cpp/try-finally-statement.md) eingegeben wurde, während das System eine interne Liste von Beendigungshandlern ausführt.

## <a name="syntax"></a>Syntax

```cpp
int   _abnormal_termination(
   );
```

## <a name="return-value"></a>Rückgabewert

**true**, wenn das System den Stapel *entlädt*; ansonsten **false**.

## <a name="remarks"></a>Anmerkungen

Dies ist eine interne Funktion, die zum Verwalten von Entladungsausnahmen verwendet wird. Sie sollte nicht im Benutzercode aufgerufen werden.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|_abnormal_termination|excpt.h|

## <a name="see-also"></a>Siehe auch

[try-finally-Anweisung](../cpp/try-finally-statement.md)
