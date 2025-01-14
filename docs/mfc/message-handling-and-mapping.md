---
title: Meldungsbehandlung und -zuordnung
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, messages
- message handling [MFC]
- message maps [MFC]
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
ms.openlocfilehash: 41f3432b3741019a787ee24b0f508fe8e65e0470
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383970"
---
# <a name="message-handling-and-mapping"></a>Meldungsbehandlung und -zuordnung

In diesen Abschnitten wird beschrieben, wie Meldungen und Befehle von MFC-Frameworks verarbeitet werden und wie Sie sie mit Ihren jeweiligen Handlerfunktionen verbinden.

In herkömmlichen Programmen für Windows werden die Windows-Nachrichten in einer großen Switch-Anweisung in eine Fensterprozedur verarbeitet. Stattdessen verwendet MFC [meldungszuordnungen](../mfc/message-categories.md) , direkte Nachrichten unterschiedliche Klassenmemberfunktionen zuzuordnen. Meldungszuordnungen sind effizienter als virtuelle Funktionen, die für diesen Zweck und ermöglichen Nachrichten von der am besten geeignete C++-Objekt behandelt werden, Anwendung, Dokument, anzeigen und So weiter. Sie können eine einzelne Nachricht oder einen Bereich von Nachrichten, die Befehls-IDs zuordnen oder Steuerelement-IDs.

WM_COMMAND-Meldungen, in der Regel von Menüs, Symbolleisten-Schaltflächen und Zugriffstasten generiert – auch verwenden, der meldungszuordnungsmechanismus. MFC definiert einen Standard [routing](../mfc/command-routing.md) der Command-Meldungen zwischen der Anwendung, frame-Fensters, Ansicht und aktive Dokumente in Ihrem Programm. Sie können die dieses routing bei Bedarf überschreiben.

Meldungszuordnungen geben auch eine Möglichkeit zum Aktualisieren von Benutzeroberflächenobjekten (z. B. Menüs und Symbolleisten-Schaltflächen), aktivieren oder deaktivieren diese entsprechend den aktuellen Kontext.

Allgemeine Informationen über Nachrichten und Warteschlangen in Windows finden Sie unter [Nachrichten und Warteschlangen](/windows/desktop/winmsg/messages-and-message-queues) im Windows SDK.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

- [Wie das Framework einen Message-Handler aufruft](../mfc/how-the-framework-calls-a-handler.md)

- [So durchsucht das Framework Meldungszuordnungen](../mfc/how-the-framework-searches-message-maps.md)

- [Deklarieren von Meldungshandlerfunktionen](../mfc/declaring-message-handler-functions.md)

- [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)

- [Vorgehensweise beim Anzeigen von Befehlsinformationen in der Statusleiste](../mfc/how-to-display-command-information-in-the-status-bar.md)

- [Dynamische Updates von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md)

- [Vorgehensweise: Erstellen einer Meldungszuordnung für eine Vorlagenklasse](../mfc/how-to-create-a-message-map-for-a-template-class.md)

## <a name="see-also"></a>Siehe auch

[Konzepte](../mfc/mfc-concepts.md)<br/>
[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)<br/>
[CWnd-Klasse](../mfc/reference/cwnd-class.md)<br/>
[CCmdTarget-Klasse](../mfc/reference/ccmdtarget-class.md)
