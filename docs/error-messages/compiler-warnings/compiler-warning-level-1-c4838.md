---
title: Compilerwarnung (Stufe 1) C4838
ms.date: 11/04/2016
f1_keywords:
- C4838
helpviewer_keywords:
- C4838
ms.assetid: fea07924-5feb-4ed4-99b5-1a8c41d28db6
ms.openlocfilehash: dcb7062c751320a9f9c612b42caf6d018047d8d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62380837"
---
# <a name="compiler-warning-level-1-c4838"></a>Compilerwarnung (Stufe 1) C4838

Konvertierung von 'type_1' zu 'type_2' erfordert eine einschränkende Konvertierung

Eine implizite einschränkende Konvertierung wurde gefunden, bei der Initialisierung von Aggregat oder eine Liste mit.

Die Programmiersprache C ermöglicht implizite einschränkende Konvertierungen in Zuweisungen und Initialisierung und C++-aufgespielte, auch wenn unerwartete einschränkende eine Ursache für viele Fehler in Code ist. Um den Code sicherer zu gestalten, erfordert der C++-standard eine diagnosemeldung aus, tritt eine einschränkende Konvertierung in eine Initialisierungsliste. In Visual C++ ist die Diagnose ist [Compilerfehler C2397](../../error-messages/compiler-errors-1/compiler-error-c2397.md) bei Verwendung der einheitliche Initialisierungssyntax unterstützt Visual Studio 2015 ab. Der Compiler generiert C4838 Warnung, wenn mit der Liste oder aggregatinitialisierungssyntax von Visual Studio 2013 unterstützt werden.

Eine einschränkende Konvertierung kann kein Problem sein, wenn Sie wissen, dass die Bandbreite der konvertierten Werte in der Ziel-eingepasst werden kann. In diesem Fall wissen Sie mehr als der Compiler übernimmt. Wenn Sie eine einschränkende Konvertierung bewusst machen, stellen Sie Ihre Absichten explizit über eine statische Umwandlung. Andernfalls gibt diese Warnmeldung wird fast immer, dass Sie einen Fehler in Ihrem Code verfügen. Sie können ihn beheben, indem Sie sicherstellen, dass die Objekte, die Sie initialisieren aufweisen, die groß genug, um die Eingaben zu verarbeiten sind.

Im folgenden Beispiel wird die C4838 generiert und zeigt eine Möglichkeit, das Problem zu beheben:

```
// C4838.cpp -- C++ narrowing conversion diagnostics
// Compile by using: cl /EHsc C4838.cpp

struct S1 {
    int m1;
    double m2, m3;
};

void function_C4838(double d1) {
    double ad[] = { 1, d1 }; // OK
    int ai[] = { 1, d1 };    // warning C4838
    S1 s11 = { 1, 2, d1 };   // OK
    S1 s12 { d1, 2, 3 };     // warning C4838
    S1 s13 { static_cast<int>(d1), 2, 3 }; // possible fix for C4838
}
```