---
title: Compilerfehler C2277
ms.date: 11/04/2016
f1_keywords:
- C2277
helpviewer_keywords:
- C2277
ms.assetid: 15a83b07-8731-4524-810b-267f65a7844f
ms.openlocfilehash: 5b20594df8a250a54a0fd5902e0453f7438cbbfd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389026"
---
# <a name="compiler-error-c2277"></a>Compilerfehler C2277

'Bezeichner': Adresse von dieser Memberfunktion nicht übernehmen

Die Adresse einer Memberfunktion ist nicht möglich.

Im folgende Beispiel wird die C2277 generiert:

```
// C2277.cpp
class A {
public:
   A();
};
(*pctor)() = &A::A;   // C2277
```