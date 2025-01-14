---
title: 'Zeitliche Steuerung der Ausnahmebehandlung: Eine Zusammenfassung'
ms.date: 05/07/2019
helpviewer_keywords:
- sequence [C++]
- sequence, of handlers
- exception handling [C++], timing
- setjmpex.h
- termination handlers [C++], timing
- setjmp.h
- handlers [C++], order of exception
- structured exception handling [C++], timing
ms.assetid: 5d1da546-73fd-4673-aa1a-7ac0f776c420
ms.openlocfilehash: 7b52252454e27d622e412f490360a025dfc97838
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221902"
---
# <a name="timing-of-exception-handling-a-summary"></a>Zeitliche Steuerung der Ausnahmebehandlung: Eine Zusammenfassung

Ein Beendigungshandler wird ausgeführt, unabhängig davon, wie die **__try** -Anweisungsblock beendet wird. Ursachen gehören das Herausspringen aus dem **__try** Block, eine `longjmp` -Anweisung, die überträgt die Steuerung aus den Block, und das Entladen des Stapels aufgrund einer Ausnahmebehandlung.

> [!NOTE]
>  Microsoft C++ -Compiler unterstützt zwei Arten von der `setjmp` und `longjmp` Anweisungen. Die schnelle Version umgeht die Abbruchbehandlung, ist jedoch effizienter. Um diese Version zu verwenden, schließen Sie die Datei \<setjmp.h >. Die andere Version unterstützt die Abbruchbehandlung, wie im vorherigen Abschnitt beschrieben. Um diese Version zu verwenden, schließen Sie die Datei \<setjmpex.h >. Die Leistungssteigerung der schnellen Version hängt von der Hardwarekonfiguration ab.

Das Betriebssystem führt alle Abbruchbehandlungen in der richtigen Reihenfolge aus, bevor ein anderer Code ausgeführt werden kann, einschließlich des Texts eines Ausnahmehandlers.

Wenn die Ursache für die Unterbrechung eine Ausnahme ist, muss das System erst den Filterteil einer oder mehrerer Ausnahmehandler ausführen, bevor entschieden wird, was beendet werden soll. Die Reihenfolge der Ereignisse lautet:

1. Eine Ausnahme wird ausgelöst.

1. Das System untersucht die Hierarchie der aktiven Ereignishandler und führt den Filter des Handlers mit der höchsten Rangstufe aus. Hierbei handelt es sich um den Ausnahmehandler, der im Hinblick auf Blöcke und Funktionsaufrufe zuletzt installiert wurde und am tiefsten geschachtelt ist.

1. Wenn dieser Filter die Steuerung übergibt (0 zurückgibt), wird der Prozess fortgesetzt, bis ein Filter gefunden wird, der die Steuerung nicht übergibt.

1. Wenn dieser Filter-1 zurückgegeben wird, wird die Ausführung fortgesetzt, wo die Ausnahme wurde ausgelöst und findet keine Beendigung statt.

1. Wenn der Filter 1 zurückgibt, werden folgende Ereignisse ausgelöst:

   - Das System entlädt den Stapel und löscht alle Stapelrahmen zwischen dem gerade ausgeführten Code (bei dem die Ausnahme ausgelöst wurde) und dem Stapelrahmen, der den Ausnahmehandler enthält, der nun die Steuerung übernimmt.

   - Beim Entladen des Stapels wird jeder Beendigungshandler im Stapel ausgeführt.

   - Der Ausnahmehandler selbst wird ausgeführt.

   - Die Steuerung wird nach dem Ende des Ausnahmehandlers an die Codezeile übergeben.

## <a name="see-also"></a>Siehe auch

[Schreiben eines Beendigungshandlers](../cpp/writing-a-termination-handler.md)<br/>
[Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)