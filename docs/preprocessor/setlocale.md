---
title: setlocale
ms.date: 11/04/2016
f1_keywords:
- setlocale_CPP
- vc-pragma.setlocale
helpviewer_keywords:
- pragmas, setlocale
- setlocale pragma
ms.assetid: e60b43d9-fbdf-4c4e-ac85-805523a13b86
ms.openlocfilehash: b2f28a14b4d4585575a39dd9a936a56a84eeddc4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179619"
---
# <a name="setlocale"></a>setlocale

Definiert das Gebietsschema (Sprache und Land/Region), das beim Übersetzen von Breitzeichenkonstanten und Zeichenfolgenliteralen verwendet werden soll.

## <a name="syntax"></a>Syntax

```
#pragma setlocale( "[locale-string]" )
```

## <a name="remarks"></a>Hinweise

Da der Algorithmus zum Konvertieren von Multibytezeichen in Breitzeichen möglicherweise je nach Gebietsschema variiert oder die Kompilierung möglicherweise in einem anderen Gebietsschema, in dem eine ausführbare Datei ausgeführt wird, stattfindet, bietet dieses Pragma eine Möglichkeit, das Zielgebietsschema zur Kompilierungszeit festzulegen. Dadurch wird sichergestellt, dass die Zeichenfolgen mit Breitzeichen im richtigen Format gespeichert werden.

Der Standardwert *gebietsschemazeichenfolge* ist "".

Das Gebietsschema "C" ordnet jedes Zeichen in der Zeichenfolge in seinen Wert als eine **"wchar_t"** (kurz ohne Vorzeichen). Andere Werte, die für gültig sind `setlocale` sind als Einträge, die in befinden die [Sprachzeichenfolgen](../c-runtime-library/language-strings.md) Liste. Sie können z. B. Folgendes ausgeben:

```cpp
#pragma setlocale("dutch")
```

Die Möglichkeit, eine Sprachenzeichenfolge auszugeben, hängt von der Codepage- und der Sprachen-ID-Unterstützung Ihres Computers ab.

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)