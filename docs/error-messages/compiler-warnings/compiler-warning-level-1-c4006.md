---
title: Compilerwarnung (Stufe 1) C4006
ms.date: 11/04/2016
f1_keywords:
- C4006
helpviewer_keywords:
- C4006
ms.assetid: f1a59819-0fd2-4361-8e3a-99e4b514b8e1
ms.openlocfilehash: 97f50bdf4454a284953bd70e83574f5d0a86d1e3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187286"
---
# <a name="compiler-warning-level-1-c4006"></a>Compilerwarnung (Stufe 1) C4006

\##undef erwartet einen Bezeichner

Die `#undef` -Direktive hat keinen Bezeichner zum Aufheben der Definition angegeben. Die Direktive wird ignoriert. Stellen Sie sicher, dass Sie einen Bezeichner angeben, um diese Warnung zu beheben. Im folgenden Beispiel wird C4006 generiert:

```
// C4006.cpp
// compile with: /W1
#undef   // C4006

// try..
// #undef TEST

int main() {
}
```