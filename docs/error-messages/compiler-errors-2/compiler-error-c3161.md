---
title: Compilerfehler C3161
ms.date: 11/04/2016
f1_keywords:
- C3161
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
ms.openlocfilehash: 22ecc176036308699c3ad7bd8c015836be910073
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174210"
---
# <a name="compiler-error-c3161"></a>Compilerfehler C3161

'Schnittstelle': Schachteln von Klasse, Struktur, Union oder Schnittstelle in einer Schnittstelle ist nicht zulässig. Schachteln einer Schnittstelle in einer Klasse, Struktur oder Union ist nicht zulässig

Ein [__interface](../../cpp/interface.md) darf nur im globalen Gültigkeitsbereich oder in einem Namespace. Eine Klasse, Struktur oder Union kann nicht in einer Schnittstelle angezeigt.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3161 generiert.

```
// C3161.cpp
// compile with: /c
__interface X {
   __interface Y {};   // C3161 A nested interface
};
```