---
title: Compilerfehler C2046
ms.date: 11/04/2016
f1_keywords:
- C2046
helpviewer_keywords:
- C2046
ms.assetid: f0c8f9dd-dbd7-4c4a-8838-fde54208ec71
ms.openlocfilehash: b502c70c62d87d6807f586e289aaa5c67be9f048
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182833"
---
# <a name="compiler-error-c2046"></a>Compilerfehler C2046

Schlüsselwort "case" ungültig

Das `case` -Schlüsselwort darf nur in einer `switch` -Anweisung enthalten sein.

Im folgenden Beispiel wird C2046 generiert:

```
// C2046.cpp
int main() {
   case 0:   // C2046
}
```

Mögliche Lösung:

```
// C2046b.cpp
int main() {
   int i = 0;

   switch(i) {
      case 0:
      break;

      default:
      break;
   }
}
```