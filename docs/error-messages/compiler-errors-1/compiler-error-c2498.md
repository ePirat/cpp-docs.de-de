---
title: Compilerfehler C2498
ms.date: 11/04/2016
f1_keywords:
- C2498
helpviewer_keywords:
- C2498
ms.assetid: 0839f12c-aaa4-4a02-bb33-7f072715dd14
ms.openlocfilehash: 1087dbb2297058f752e0a15776e4a7185e32a5c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360464"
---
# <a name="compiler-error-c2498"></a>Compilerfehler C2498

'Funktion': "Novtable" kann nur auf Klassendeklarationen oder Definitionen angewendet werden

Dieser Fehler kann verursacht werden, mithilfe von `__declspec(novtable)` mit einer Funktion.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2498 generiert:

```
// C2498.cpp
// compile with: /c
void __declspec(novtable) f() {}   // C2498
class __declspec(novtable) A {};   // OK
```