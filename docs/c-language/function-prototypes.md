---
title: Funktionsprototypen
ms.date: 11/04/2016
helpviewer_keywords:
- function prototypes
- function return types, function prototypes
- data types [C], function return types
- functions [C], return types
- prototypes [C++], function
ms.assetid: d152f8e6-971e-432c-93ca-5a91400653c2
ms.openlocfilehash: 2c75db3e1550927af57054a2cc1561d9df1567a4
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56148803"
---
# <a name="function-prototypes"></a>Funktionsprototypen

Eine Funktionsdeklaration ist der Funktionsdefinition vorangestellt und gibt den Namen, Rückgabetyp, die Speicherklasse und andere Attribute einer Funktion an. Um als Prototyp zu fungieren, muss die Funktionsdeklaration auch Typen und Bezeichner für die Argumente der Funktion festlegen.

## <a name="syntax"></a>Syntax

*declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers* *attribute-seq*<sub>opt</sub> *init-declarator-list*<sub>opt</sub> **;**

/\* *attribute-seq*<sub>opt</sub> ist Microsoft-spezifisch \*/

*declaration-specifiers*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*storage-class-specifier* *declaration-specifiers*<sub>opt</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-specifier* *declaration-specifiers*<sub>opt</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-qualifier* *declaration-specifiers*<sub>opt</sub>

*init-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator-list*  **,**  *init-declarator*

*init-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declarator* **=** *initializer*

*declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*pointer*<sub>opt</sub> *direct-declarator*

*direct-declarator*:/\* Ein Funktionsdeklarator \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*direct-declarator*  **(**  *parameter-type-list*  **)**  /\* Neuer Deklarator \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*direct-declarator*  **(**  *identifier-list*<sub>opt</sub> **)** /\* Veralteter Deklarator \*/

Der Prototyp hat das gleiche Format wie die Funktionsdefinition. Allerdings schließt er mit einem Semikolon unmittelbar nach der schließenden Klammer und hat dementsprechend keinen Text. In jedem Fall muss der Rückgabetyp dem Rückgabetyp entsprechen, der in der Funktionsdefinition angegeben wird.

Funktionsprototypen haben die folgenden wichtigen Verwendungen:

- Sie legen den Rückgabetyp für Funktionen fest, die andere Typen als **int** zurückgeben. Obwohl Funktionen, die **int**-Werte zurückgeben, keine Prototypen erfordern, werden Prototypen empfohlen.

- Ohne vollständige Prototypen werden Standardkonvertierungen ausgeführt, es wird jedoch nicht versucht, Typ oder Anzahl der Argumente anhand der Anzahl der Parameter zu überprüfen.

- Prototypen werden verwendet, um Zeiger auf Funktionen zu initialisieren, bevor diese Funktionen definiert werden.

- Die Parameterliste wird zum Überprüfen der Entsprechung der Argumente im Funktionsaufruf mit den Parametern in der Funktionsdefinition verwendet.

Der konvertierte Typ jedes Parameters bestimmt die Interpretation der Argumente, die der Funktionsaufruf auf dem Stapel ablegt. Ein Typenkonflikt zwischen einem Parameter und einem Argument kann verursachen, dass Argumente auf dem Stapel fehlinterpretiert werden. Wenn beispielsweise auf einem 16-Bit-Computer ein 16-Bit-Zeiger als Argument übergeben und dann als **long**-Parameter deklariert wird, werden die ersten 32 Bits im Stapel als **long**-Parameter interpretiert. Dieser Fehler verursacht nicht nur Probleme mit dem **long**-Parameter, sondern auch mit allen nachfolgenden Parametern. Sie können Fehler dieser Art erkennen, indem Sie vollständige Funktionsprototypen für alle Funktionen deklarieren.

Ein Prototyp richtet die Attribute einer Funktion ein, sodass Aufrufe der Funktion, die vor seiner Definition (oder in anderen Quelldateien) auftreten, auf Rückgabetyp- und Argumenttyp-Konflikte überprüfen können. Wenn Sie beispielsweise den Speicherklassenspezifizierer **static** in einem Prototyp angeben, müssen Sie die **static**-Speicherklasse auch in der Funktionsdefinition angeben.

Vollständige Parameterdeklarationen (`int a`) können mit abstrakten Deklaratoren (`int`) in der gleichen Deklaration kombiniert werden. Die folgende Deklaration ist beispielsweise gültig:

```C
int add( int a, int );
```

Der Prototyp kann sowohl den Typ als auch den Bezeichner für jeden Ausdruck einschließen, der als Argument übergeben wird. Allerdings erstreckt sich der Bereich solcher Bezeichner nur bis zum Ende der Deklaration. Der Prototyp reflektiert auch die Tatsache, dass die Anzahl der Argumente variabel ist oder dass keine Argumente übergeben werden. Ohne eine solche Liste können Konflikte nicht aufgedeckt werden, sodass der Compiler keine entsprechenden Diagnosemeldungen generieren kann. Weitere Informationen zur Typüberprüfung erhalten Sie unter [Argumente](../c-language/arguments.md).

Prototypbereich im Microsoft C-Compiler ist beim Kompilieren mit der **/Za**-Compileroption jetzt ANSI-kompatibel. Dies bedeutet, dass bei Deklaration eines **struct**-Tags oder **union**-Tags in einem Prototyp das Tag in diesem Gültigkeitsbereich eingetragen wird und nicht im globalen Gültigkeitsbereich. Zum Beispiel können Sie bei der Kompilierung mit **/Za** für ANSI-Kompatibilität diese Funktion niemals aufrufen, ohne einen Typenkonfliktfehler zu erhalten:

```C
void func1( struct S * );
```

Um den Code zu korrigieren, definieren oder deklarieren Sie **struct** oder **union** im globalen Bereich vor dem Funktionsprototyp:

```C
struct S;
void func1( struct S * );
```

Unter **/Ze** wird das Tag weiterhin im globalen Gültigkeitsbereich eingegeben.

## <a name="see-also"></a>Siehe auch

[Funktionen](../c-language/functions-c.md)
