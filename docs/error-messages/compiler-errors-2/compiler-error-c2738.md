---
title: Compilerfehler C2738
ms.date: 11/04/2016
f1_keywords:
- C2738
helpviewer_keywords:
- C2738
ms.assetid: 896b4640-1ee0-4cd8-9910-de3efa30006a
ms.openlocfilehash: 8f8342f07d8062c5a1ec18d17423996c1b0dab39
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360241"
---
# <a name="compiler-error-c2738"></a>Compilerfehler C2738

'Declaration': ist mehrdeutig, oder ist kein Member von 'Typ'

Eine Funktion wurde falsch deklariert.

Im folgende Beispiel wird die C2738 generiert:

```
// C2738.cpp
struct A {
   template <class T> operator T*();
   // template <class T> operator T();
};

template <>
A::operator int() {   // C2738

// try the following line instead
// A::operator int*() {

// or use the commented member declaration

   return 0;
}
```