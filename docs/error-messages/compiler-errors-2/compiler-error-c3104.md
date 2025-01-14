---
title: Compilerfehler C3104
ms.date: 11/04/2016
f1_keywords:
- C3104
helpviewer_keywords:
- C3104
ms.assetid: b5648d47-e5d3-4b45-a3c0-f46e04eae731
ms.openlocfilehash: fee023809246634f2f3da266a718e45861eae76e
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447838"
---
# <a name="compiler-error-c3104"></a>Compilerfehler C3104

Unzulässiges Attributargument.

Sie haben ein ungültiges Argument für ein Attribut angegeben.

Finden Sie unter [Attributparametertypen](../../extensions/attribute-parameter-types-cpp-component-extensions.md) für Weitere Informationen.

Dieser Fehler kann infolge einer konformitätsverbesserung für Compiler, die für Visual Studio 2005 durchgeführt wurde generiert werden: beim Übergeben von verwalteten Arrays auf benutzerdefinierte Attribute, ist der Typ des Arrays nicht mehr aus der Liste aggregatinitialisierung abgeleitet. Der Compiler ist nun erforderlich, um den Typ des Arrays als auch für die Initialisiererliste anzugeben.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3104 generiert.

```
// C3104a.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::Class)]
public ref struct ABC : public Attribute {
   ABC(array<int>^){}
   array<double> ^ param;
};

[ABC( {1,2,3}, param = {2.71, 3.14})]   // C3104
// try the following line instead
// [ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]
ref struct AStruct{};
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3104 generiert.

```
// C3104b.cpp
// compile with: /clr /c
// C3104 expected
using namespace System;

int func() {
   return 0;
}

[attribute(All)]
ref class A {
public:
   A(int) {}
};

// Delete the following 2 lines to resolve.
[A(func())]
ref class B {};

// OK
[A(0)]
ref class B {};
```
