---
title: Compilerfehler C2486
ms.date: 11/04/2016
f1_keywords:
- C2486
helpviewer_keywords:
- C2486
ms.assetid: 436da349-6461-4e32-bfca-4f3e620108e2
ms.openlocfilehash: 8d745c03530f331da83b45c765a2cb4bb7d76d8e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364349"
---
# <a name="compiler-error-c2486"></a>Compilerfehler C2486

"__LOCAL_SIZE" nur in Funktionen mit dem "naked"-Attribut zulässig

In Assembly Inlinefunktionen, den Namen `__LOCAL_SIZE` ist reserviert für die deklarierten Funktionen mit den [naked](../../cpp/naked-cpp.md) Attribut.

Im folgende Beispiel wird die C2486 generiert:

```
// C2486.cpp
// processor: x86
void __declspec(naked) f1() {
   __asm {
      mov   eax,   __LOCAL_SIZE
   }
}
void f2() {
   __asm {
      mov   eax,   __LOCAL_SIZE   // C2486
   }
}
```