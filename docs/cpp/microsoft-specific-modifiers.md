---
title: Microsoft-spezifische Modifizierer
ms.date: 08/16/2018
ms.assetid: 22c7178c-f854-47fa-9de6-07d23fda58e1
ms.openlocfilehash: 119e4d06d0235bbf637eefe8754668d3e90b0c52
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749723"
---
# <a name="microsoft-specific-modifiers"></a>Microsoft-spezifische Modifizierer

Dieser Abschnitt beschreibt Microsoft-spezifische Erweiterungen von C++ in den folgenden Bereichen:

- [Basierende Adressierung](based-addressing.md), die Methode mithilfe eines Zeigers als Basis aus der andere Zeiger versetzt werden können

- [Funktion-Aufrufkonventionen](calling-conventions.md)

- Erweiterte Speicherklassen-Attribute, die mit deklariert die [__declspec](declspec.md) Schlüsselwort

- Die [__w64](w64.md) Schlüsselwort

## <a name="microsoft-specific-keywords"></a>Microsoft-spezifische Schlüsselwörter

Viele der Microsoft-spezifischen Schlüsselwörter können verwendet werden, um Deklaratoren zum Bilden abgeleiteter Typen zu ändern. Weitere Informationen über Deklaratoren finden Sie unter [Deklaratoren](overview-of-declarators.md).

|Stichwort|Bedeutung|Wird verwendet, um abgeleitete Typen zu bilden?|
|-------------|-------------|---------------------------------|
|[__based](based-grammar.md)|Der folgende Name deklariert ein 32-Bit-Offset zur 32-Bit-Basis in der Deklaration.|Ja|
|[__cdecl](cdecl.md)|Der folgende Name verwendet C-Benennungs- und C-Aufrufkonventionen.|Ja|
|[__declspec](declspec.md)|Der folgende Name gibt ein Microsoft-spezifisches Speicherklassenattribut an.|Nein|
|[__fastcall](fastcall.md)|Der folgende Name deklariert eine Funktion, die Register verwendet, sofern verfügbar, anstatt des Stapels für die Argumentübergabe.|Ja|
|[__restrict](extension-restrict.md)|Ähnlich wie __declspec ([einschränken](restrict.md)), aber für die Verwendung von Variablen.|Nein|
|[__stdcall](stdcall.md)|Der folgende Name gibt eine Funktion an, die herkömmliche Aufrufkonventionen berücksichtigt.|Ja|
|[__w64](w64.md)|Markiert einen Datentyp als größer bei einem 64-Bit-Compiler.|Nein|
|[__unaligned](unaligned.md)|Gibt an, dass ein Zeiger auf einen Typ oder andere Daten nicht ausgerichtet ist.|Nein|
|[__vectorcall](vectorcall.md)|Der folgende Name deklariert eine Funktion, die Register, einschließlich SSE-Register, verwendet, sofern diese verfügbar sind, anstatt des Stapels für die Argumentübergabe.|Ja|

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](cpp-language-reference.md)
