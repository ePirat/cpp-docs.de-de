---
title: Compilerfehler C3204
ms.date: 11/04/2016
f1_keywords:
- C3204
helpviewer_keywords:
- C3204
ms.assetid: 06e578da-0262-48c8-b2ae-be1cd6d28884
ms.openlocfilehash: 4c34ad35916f01323a72102c7099d4afd0ab17be
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402722"
---
# <a name="compiler-error-c3204"></a>Compilerfehler C3204

"_alloca" kann nicht innerhalb eines catch-Blocks aufgerufen werden

Dieser Fehler tritt auf, wenn Sie einen Aufruf von [_alloca](../../c-runtime-library/reference/alloca.md) innerhalb eines catch-Blocks verwenden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3204 generiert:

```
// C3204.cpp
// compile with: /EHsc
#include <malloc.h>

void ShowError(void)
{
   try
   {
   }
   catch(...)
   {
      _alloca(1);   // C3204
   }
}
```