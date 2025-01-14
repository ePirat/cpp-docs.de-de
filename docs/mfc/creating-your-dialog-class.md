---
title: Erstellen eigener Dialogfeldklassen
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
ms.openlocfilehash: bacedc49fcdabdd5dc7fb0f392a66afd3baadd06
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241757"
---
# <a name="creating-your-dialog-class"></a>Erstellen eigener Dialogfeldklassen

Erstellen Sie eine neue Dialogfeldklasse, mit der Dialogfeldressource arbeiten, für jede im Dialogfeld in Ihrem Programm.

[Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md) wird erläutert, wie zum Erstellen einer neuen Dialogfeldklasse. Beim Erstellen einer Dialogfeldklasse mit den Assistenten zum Hinzufügen einer Klasse, schreibt es die folgenden Elemente in der. H und. CPP-Dateien, die Sie angeben:

In der. H-Datei:

- Eine Klassendeklaration für die Dialogfeldklasse. Die abgeleitete Klasse wird von [CDialog](../mfc/reference/cdialog-class.md).

In der. CPP-Datei:

- Eine meldungszuordnung für die Klasse.

- Ein standard-Konstruktor für das Dialogfeld.

- Eine Überschreibung von der [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) Member-Funktion. Bearbeiten Sie diese Funktion. Es wird zum Dialogfeld Data Dialogdatenaustausch und-Validierung-Funktionen verwendet, wie weiter unten im Abschnitt [Dialogdatenaustausch und-Validierung](../mfc/dialog-data-exchange-and-validation.md).

## <a name="see-also"></a>Siehe auch

[Erstellen einer Dialogfeldklasse mit Code-Assistenten](../mfc/creating-a-dialog-class-with-code-wizards.md)<br/>
[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)
