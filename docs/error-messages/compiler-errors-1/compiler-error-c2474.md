---
title: Compilerfehler C2474
ms.date: 11/04/2016
f1_keywords:
- C2474
helpviewer_keywords:
- C2474
ms.assetid: 64e6c61e-6e77-480e-bcf0-b30a2fc482ac
ms.openlocfilehash: c49f38b828a41c72135ba9182d4d0f5eee4df1de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350883"
---
# <a name="compiler-error-c2474"></a>Compilerfehler C2474

"Schlüsselwort": Es fehlt ein angrenzendes Semikolon, kann entweder ein Schlüsselwort oder ein Bezeichner sein.

Der Compiler hat ein Semikolon erwartet und konnte Ihre Absicht nicht ermitteln. Fügen Sie das Semikolon hinzu, um diesen Fehler zu beheben.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2474 generiert.

```
// C2474.cpp
// compile with: /clr /c

ref class A {
   ref class B {}
   property int i;   // C2474 error
};

// OK
ref class B {
   ref class D {};
   property int i;
};

ref class E {
   ref class F {} property;
   int i;
};
```