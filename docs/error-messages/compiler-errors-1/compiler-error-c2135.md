---
title: Compilerfehler C2135
ms.date: 11/04/2016
f1_keywords:
- C2135
helpviewer_keywords:
- C2135
ms.assetid: aa360d22-4f79-4de1-b384-93cadd10975f
ms.openlocfilehash: 0b6cc8fb8ec1c6a7b054eb48d914335460811310
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344917"
---
# <a name="compiler-error-c2135"></a>Compilerfehler C2135

'bit operator': Ungültiger Bitfeldvorgang.

Der address-of-Operator (`&`) kann nicht auf ein Bitfeld angewendet werden.

Das folgende Beispiel generiert C2135:

```
// C2135.cpp
struct S {
   int i : 1;
};

struct T {
   int j;
};
int main() {
   &S::i;   // C2135 address of a bit field
   &T::j;   // OK
}
```