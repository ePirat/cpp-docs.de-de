---
title: Typ "int"
ms.date: 11/04/2016
helpviewer_keywords:
- int data type
- type int
- portability [C++], type int
- signed integers
ms.assetid: 0067ce9a-281e-491a-ae63-632952981e13
ms.openlocfilehash: 848c9799e7ab5cfdfd2b25cc84e55de02c673f3e
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56150011"
---
# <a name="type-int"></a>Typ "int"

Die Größe eines `int`-Elements mit oder ohne Vorzeichen ist die Standardgröße einer ganzen Zahl auf einem bestimmten Computer. Bei den 16-Bit-Betriebssystemen ist der `int`-Typ z. B. normalerweise 16 Bit oder 2 Bytes. Bei den 32-Bit-Betriebssystemen ist der `int`-Typ normalerweise 32 Bit oder 4 Bytes. Daher ist der `int`-Typ mit dem `short int`-Typ oder dem **long int**-Typ äquivalent, und der `unsigned int`-Typ ist entweder mit dem **unsigned short**-Typ oder dem `unsigned long`-Typ äquivalent, abhängig von der Zielumgebung. Die Typen `int` stehen alle für signierte Werte, es sei denn, sie sind anderweitig bezeichnet.

Die Typspezifizierer `int` und `unsigned int` (oder einfach `unsigned`) definieren bestimmte Funktionen der Programmiersprache C (z. B. den `enum`-Typ). In diesen Fällen bestimmen die Definitionen von `int` und "unsigned int" für eine bestimmte Implementierung den tatsächlichen Speicher.

**Microsoft-spezifisch**

Ganzzahlen mit Vorzeichen werden in der Zweierkomplementdarstellung ausgedrückt. Das wichtigste Bit enthält das Vorzeichen: 1 für negative Werte, 0 für positive Werte und 0. Der Wertebereich ist in [Ganzzahlige Grenzen in C++](../c-language/cpp-integer-limits.md) angegeben, was aus der LIMITS.H-Headerdatei stammt.

**Ende Microsoft-spezifisch**

> [!NOTE]
>  Die int-Typspezifizierer sowie die unsignierten int-Typspezifizierer werden in C-Programmen viel verwendet, denn sie ermöglichen es dem jeweiligen Computer, Ganzzahlenwerte auf die für den betreffenden Computer effizienteste Art zu bearbeiten. Da die Größen von int-Typen und int-Typen ohne Vorzeichen variieren, sind Programme, die abhängig von einer bestimmten int-Größe sind, möglicherweise nicht auf andere Computern übertragbar. Um Programme übertragbarer zu gestalten, können Sie Ausdrücke mit dem sizeof-Operator (in [Der Operator sizeof](../c-language/sizeof-operator-c.md) erläutert) anstelle von hartcodierten Datengrößen verwenden.

## <a name="see-also"></a>Siehe auch

[Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md)
