---
title: Compilerfehler C2745
ms.date: 11/04/2016
f1_keywords:
- C2745
helpviewer_keywords:
- C2745
ms.assetid: a1c45f13-7667-4678-aa16-265304a449a1
ms.openlocfilehash: 53a218fd80c6b8261aa0dda6bcaa1c347db73458
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360306"
---
# <a name="compiler-error-c2745"></a>Compilerfehler C2745

"token": dieses Token kann nicht auf einen Bezeichner konvertiert werden

Bezeichner müssen aus zulässigen Zeichen bestehen.

Im folgende Beispiel wird die C2745 generiert:

```
// C2745.cpp
// compile with: /clr
int main() {
   int __identifier([));   // C2745
}
```