---
title: Compilerfehler C2844
ms.date: 11/04/2016
f1_keywords:
- C2844
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
ms.openlocfilehash: 2676a32cee487595a2241359496ae9b0380126b8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62329191"
---
# <a name="compiler-error-c2844"></a>Compilerfehler C2844

'Member': ein Member der Schnittstelle "Schnittstelle" nicht möglich

Ein [Schnittstellenklasse](../../extensions/interface-class-cpp-component-extensions.md) einen Datenmember kann nicht enthalten, es sei denn, sie auch eine Eigenschaft ist.

Etwas anderes als eine Eigenschaft oder das Member-Funktion kann nicht in einer Schnittstelle. Darüber hinaus sind die Konstruktoren, Destruktoren und Operatoren nicht zulässig.

Im folgende Beispiel wird die C2844 generiert:

```
// C2844a.cpp
// compile with: /clr /c
public interface class IFace {
   int i;   // C2844
   // try the following line instead
   // property int Size;
};
```
