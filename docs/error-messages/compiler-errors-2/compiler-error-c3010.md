---
title: Compilerfehler C3010
ms.date: 11/04/2016
f1_keywords:
- C3010
helpviewer_keywords:
- C3010
ms.assetid: e959d038-bba6-432a-9c0a-0470474de7d9
ms.openlocfilehash: c5f0d33632cb155b8365c8de421fa5eaf91421c6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350334"
---
# <a name="compiler-error-c3010"></a>Compilerfehler C3010

'Bezeichnung': Aussprung aus strukturiertem Block von OpenMP ist nicht zulässig.

Code kann nicht in einen oder aus einem OpenMP-Block springen.

Im folgenden Beispiel wird C3010 generiert:

```
// C3010.c
// compile with: /openmp
int main() {
   #pragma omp parallel
   {
      #pragma omp parallel
      {
         goto lbl3;
      }
   }
   lbl3:;   // C3010
}
```