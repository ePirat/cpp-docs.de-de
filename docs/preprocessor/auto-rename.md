---
title: auto_rename
ms.date: 11/04/2016
f1_keywords:
- auto_rename
helpviewer_keywords:
- auto_rename attribute
ms.assetid: 1075f3ab-f6fc-4e04-8e22-ebe02695a567
ms.openlocfilehash: ba07b8532ba64c99f835e59d7c71aac8e3f2b03d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336685"
---
# <a name="autorename"></a>auto_rename

**C++-spezifisch**

Benennt für C++ reservierte Wörter um, indem dem Variablennamen zwei Unterstriche (__) angefügt werden, um potenzielle Namenskonflikte zu vermeiden.

## <a name="syntax"></a>Syntax

```
auto_rename
```

## <a name="remarks"></a>Hinweise

Dieses Attribut wird verwendet, wenn Sie eine Typbibliothek importierten, die eine oder mehrere für C++ reservierte Wörter (Schlüsselwörter oder Makros) als Variablennamen verwendet.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)