---
title: Compilerfehler C3189
ms.date: 11/04/2016
f1_keywords:
- C3189
helpviewer_keywords:
- C3189
ms.assetid: b254de79-931e-4a59-a9f4-1c690d90ca5e
ms.openlocfilehash: b2de290178657ae427b5ad7999c511ae7ff9f1eb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300640"
---
# <a name="compiler-error-c3189"></a>Compilerfehler C3189

"Typeid\<abstrakten Deklarator geben >': Diese Syntax wird nicht mehr unterstützt, verwenden Sie:: Typeid stattdessen

Ein veraltetes [Typeid](../../extensions/typeid-cpp-component-extensions.md) wurde verwendet, verwenden Sie das neue Formular.

Im folgende Beispiel wird die C3189 generiert:

```
// C3189.cpp
// compile with: /clr
int main() {
   System::Type^ t  = typeid<System::Object>;   // C3189
   System::Type^ t2  = System::Object::typeid;   // OK
}
```