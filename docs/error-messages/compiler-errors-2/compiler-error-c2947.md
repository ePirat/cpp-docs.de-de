---
title: Compilerfehler C2947
ms.date: 11/04/2016
f1_keywords:
- C2947
helpviewer_keywords:
- C2947
ms.assetid: 6c056f62-ec90-4883-8a67-aeeb6ec13546
ms.openlocfilehash: 3738c257192134eedb8554b0d875023862441416
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227215"
---
# <a name="compiler-error-c2947"></a>Compilerfehler C2947

erwartet ' >' gefunden. zum Beenden Konstrukt "Syntax"

Eine generische oder Vorlagenklasse Argumentliste wurde möglicherweise nicht ordnungsgemäß beendet.

C2947 kann auch durch Syntaxfehler generiert werden.

Im folgende Beispiel wird die C2947 generiert:

```
// C2947.cpp
// compile with: /c
template <typename T>=   // C2947
// try the following line instead
// template <typename T>
struct A {};
```