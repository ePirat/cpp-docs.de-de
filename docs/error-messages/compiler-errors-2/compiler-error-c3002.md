---
title: Compilerfehler C3002
ms.date: 11/04/2016
f1_keywords:
- C3002
helpviewer_keywords:
- C3002
ms.assetid: 2d4241a7-c8eb-4d43-a128-dca255d137bc
ms.openlocfilehash: 9f48021f5a32006c6a78a69500b0701cb7612d96
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300699"
---
# <a name="compiler-error-c3002"></a>Compilerfehler C3002

'Name1 Name2': Mehrere OpenMP-Direktivennamen

Mehrere Direktivennamen sind nicht zulässig.

Im folgenden Beispiel wird C3002 generiert:

```
// C3002.c
// compile with: /openmp
int main()
{
   #pragma omp parallel single   // C3002
}
```