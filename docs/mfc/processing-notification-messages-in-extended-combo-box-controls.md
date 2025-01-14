---
title: Verarbeiten von Benachrichtigungsmeldungen in erweiterten Kombinationsfeld-Steuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes [MFC], notifications
- notifications [MFC], extended combo box controls
ms.assetid: 4e442758-d054-4746-bb1a-6ff84accb127
ms.openlocfilehash: 1890267f26ef43fd1dbf8fdea28f02e3d882d475
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378192"
---
# <a name="processing-notification-messages-in-extended-combo-box-controls"></a>Verarbeiten von Benachrichtigungsmeldungen in erweiterten Kombinationsfeld-Steuerelementen

Wenn Benutzer mit dem erweiterten Kombinationsfeld interagieren, sendet das Steuerelement (`CComboBoxEx`) Benachrichtigungen an sein übergeordnetes Fenster, normalerweise ein Ansichts- oder Dialogfeldobjekt. Behandeln Sie diese Nachrichten, wenn Sie darauf reagieren möchten. Wenn der Benutzer die Dropdownliste aktiviert oder im Bearbeitungsfeld des Steuerelements klickt, wird z. B. die CBEN_BEGINEDIT-Benachrichtigung gesendet.

Verwenden Sie das Eigenschaftenfenster, um der übergeordneten Klasse Benachrichtigungshandler für die Nachrichten hinzuzufügen, die Sie implementieren möchten.

In der folgenden Liste sind die verschiedenen Benachrichtigungen beschrieben, die vom erweiterten Kombinationsfeld-Steuerelement gesendet werden.

- CBEN_BEGINEDIT gesendet, wenn der Benutzer die Dropdownliste aktiviert oder im Bearbeitungsfeld des Steuerelements klickt.

- CBEN_DELETEITEM gesendet, wenn ein Element gelöscht wurde.

- CBEN_DRAGBEGIN wird gesendet, wenn der Benutzer beginnt, das Bild des angezeigten Elements auf den editierteil des Steuerelements zu ziehen.

- CBEN_ENDEDIT gesendet, wenn der Benutzer einen Vorgang im Editierfeld abgeschlossen hat oder ein Element aus der Dropdownliste des Steuerelements ausgewählt hat.

- CBEN_GETDISPINFO gesendet, um Anzeigeinformationen zu einem Rückrufelement abzurufen.

- CBEN_INSERTITEM gesendet, wenn ein neues Element im Steuerelement eingefügt wurde.

## <a name="see-also"></a>Siehe auch

[Verwenden von CComboBoxEx](../mfc/using-ccomboboxex.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
