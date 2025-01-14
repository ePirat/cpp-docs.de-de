---
title: Compilerfehler C3491
ms.date: 11/04/2016
f1_keywords:
- C3491
helpviewer_keywords:
- C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
ms.openlocfilehash: 12f50e48fc18fc23d078b6dbc7d21d05efa06d43
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62381084"
---
# <a name="compiler-error-c3491"></a>Compilerfehler C3491

"Var": Eine Erfassung nach Wert kann in einem nicht änderbaren Lambda nicht geändert werden.

Ein nicht änderbarer Lambda-Ausdruck kann den Wert einer Variablen nicht ändern, die nach Wert erfasst wird.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Deklarieren Sie den Lambda-Ausdruck mit dem `mutable` -Schlüsselwort, oder

- übergeben Sie die Variable per Verweis an die Erfassungsliste des Lambda-Ausdrucks.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3491 generiert, da der Text eines nicht änderbaren Lambda-Ausdrucks die Erfassungsvariable `m`ändert:

```
// C3491a.cpp

int main()
{
   int m = 55;
   [m](int n) { m = n; }(99); // C3491
}
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird der Fehler C3491 durch Deklarieren des Lambda-Ausdrucks mit dem `mutable` -Schlüsselwort behoben:

```
// C3491b.cpp

int main()
{
   int m = 55;
   [m](int n) mutable { m = n; }(99);
}
```

## <a name="see-also"></a>Siehe auch

[Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)