---
title: Dialogfeld-Steuerelemente im Framework
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], creating
- dialog classes [MFC], dialog box components
- MFC dialog boxes [MFC], about MFC dialog boxes
- dialog templates [MFC], MFC framework
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
ms.openlocfilehash: 88027df7433267925e91db2d368b744cee8a9e75
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182292"
---
# <a name="dialog-box-components-in-the-framework"></a>Dialogfeld-Steuerelemente im Framework

In der MFC-Framework besteht ein Dialogfeld, das aus zwei Komponenten:

- Eine Dialogfeldvorlagen-Ressource, die das Dialogfeld-Steuerelemente und die Position angibt.

   Die Ressource speichert eine Dialogfeldvorlage aus der Windows das Dialogfeld erstellt werden soll, und zeigt ihn an. Die Vorlage gibt das Dialogfeld Eigenschaften, einschließlich, seine Größe, Position, Stil, und die Typen und Positionen der Steuerelemente für das Dialogfeld. Verwenden Sie in der Regel eine Dialogfeldvorlage als Ressource gespeichert, aber Sie können auch Ihre eigene Vorlage erstellen, im Arbeitsspeicher.

- Eine Dialogfeldklasse, aus abgeleiteten [CDialog](../mfc/reference/cdialog-class.md), um eine programmgesteuerte Schnittstelle für die Verwaltung das Dialogfeld zu gewähren.

   Ein Dialogfeld, das ist ein Fenster, und es wird in einem Windows-Fenster, wenn es sichtbar angefügt werden. Wenn das Dialogfeld erstellt wird, wird der Dialogfeldvorlagen-Ressource als Vorlage zum Erstellen von untergeordneten Fenstersteuerelemente für das Dialogfeld.

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)<br/>
[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)
