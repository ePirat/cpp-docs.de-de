---
title: Compilerwarnung (Stufe 4) C4816
ms.date: 11/04/2016
f1_keywords:
- C4816
helpviewer_keywords:
- C4816
ms.assetid: 60f730ae-d942-4db9-ab97-41d4a874d8da
ms.openlocfilehash: 719a950f2cc15b51dcbbb7e8f4f476f92fe326c2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349590"
---
# <a name="compiler-warning-level-4-c4816"></a>Compilerwarnung (Stufe 4) C4816

'Param': Parameter hat ein Array der Größe 0, das abgeschnitten wird (sofern das Objekt nicht als Verweis übergeben wird).

Ein Parameter für ein Objekt mit einem Array der Größe 0 wurde nicht als Verweis übergeben. Das Array wird bei der Übergabe des Objekts nicht kopiert.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4816 generiert.

```
// C4816.cpp
// compile with: /W4
#include <stdio.h>

extern "C" int printf_s(const char *, ...);

#pragma warning(disable : 4200)

struct S1
{
    int i;
    char cArr[];
};

void TestErr(S1 s1)   // C4816 param with zero-array
                      // not passed by reference
{
    printf_s("%d %c %c\n", s1.i, s1.cArr[0], s1.cArr[1]);
}

void TestOk(S1 &s1)
{
    printf_s("%d %c %c\n", s1.i, s1.cArr[0], s1.cArr[1]);
}

int main()
{
    S1 myS_1 = { 6, 'a', 'b', 'c' };
    TestErr(myS_1);
    TestOk(myS_1);
}
```