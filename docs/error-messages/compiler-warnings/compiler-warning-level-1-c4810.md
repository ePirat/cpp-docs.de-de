---
title: Compilerwarnung (Stufe 1) C4810
ms.date: 11/04/2016
f1_keywords:
- C4810
helpviewer_keywords:
- C4810
ms.assetid: 39e2cae0-9c1c-4ac1-aaa0-5f661d06085b
ms.openlocfilehash: 4701ac40d436a9f5511f2c7cec86e8183ec2f837
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406300"
---
# <a name="compiler-warning-level-1-c4810"></a>Compilerwarnung (Stufe 1) C4810

Wert von pragma pack(show) == n

Diese Warnung wird ausgegeben, wenn Sie die **show** -Option des [pack](../../preprocessor/pack.md) -Pragmas verwenden. *n* ist der aktuelle pack-Wert.

Der folgende Code zeigt z. B. die Funktionsweise der C4810-Warnung mit dem pack-Pragma:

```
// C4810.cpp
// compile with: /W1 /LD
// C4810 expected
#pragma pack(show)
#pragma pack(4)
#pragma pack(show)
```