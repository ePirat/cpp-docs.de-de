---
title: 'WM_-Meldungen: S'
ms.date: 11/04/2016
f1_keywords:
- ON_WM_SYSDEADCHAR
- ON_WM_SYSKEYDOWN
- ON_WM_STYLECHANGING
- ON_WM_STYLECHANGED
- ON_WM_SPOOLERSTATUS
- ON_WM_SYSCHAR
- ON_WM_SETFOCUS
- ON_WM_SIZE
- ON_WM_SIZING
- ON_WM_SETCURSOR
- ON_WM_SYSCOMMAND
- ON_WM_SETTINGCHANGE
- ON_WM_SHOWWINDOW
- ON_WM_SYSKEYUP
- ON_WM_SIZECLIPBOARD
- ON_WM_SYSCOLORCHANGE
helpviewer_keywords:
- ON_WM_SIZE [MFC]
- ON_WM_SETFOCUS [MFC]
- ON_WM_SIZING [MFC]
- ON_WM_SYSCHAR [MFC]
- ON_WM_SETTINGCHANGE [MFC]
- ON_WM_SYSDEADCHAR [MFC]
- ON_WM_SHOWWINDOW [MFC]
- ON_WM_STYLECHANGING [MFC]
- ON_WM_SYSCOMMAND [MFC]
- ON_WM_STYLECHANGED [MFC]
- ON_WM_SPOOLERSTATUS [MFC]
- ON_WM_SYSCOLORCHANGE [MFC]
- ON_WM_SETCURSOR [MFC]
- ON_WM_SIZECLIPBOARD [MFC]
- ON_WM_SYSKEYUP [MFC]
- ON_WM_SYSKEYDOWN [MFC]
- WM_ messages
ms.assetid: 4b9aec79-a98f-4aa0-a3d9-110941b6dcbc
ms.openlocfilehash: 2f8bfb00172f2f4e2791374079c7eb3bb0559a76
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281511"
---
# <a name="wm-messages-s"></a>WM_-Meldungen: S

Die folgenden Einträge der Karte entsprechen der Funktionsprototypen.

|Zuordnungseintrag|Funktionsprototyp|
|---------------|------------------------|
|ON_WM_SETCURSOR( )|Afx_msg "bool" [OnSetCursor](../../mfc/reference/cwnd-class.md#onsetcursor)(CWnd *, "uint", "uint");|
|ON_WM_SETFOCUS( )|die "void" Afx_msg [OnSetFocus](../../mfc/reference/cwnd-class.md#onsetfocus)(CWnd *);|
|ON_WM_SETTINGCHANGE( )|die "void" Afx_msg [OnSettingChange](../../mfc/reference/cwnd-class.md#onsettingchange)(UINT uFlags, LPCTSTR LpszSection);|
|ON_WM_SHOWWINDOW( )|die "void" Afx_msg [OnShowWindow](../../mfc/reference/cwnd-class.md#onshowwindow)("bool", "uint");|
|ON_WM_SIZE( )|die "void" Afx_msg [OnSize](../../mfc/reference/cwnd-class.md#onsize)(UINT, Int, Int);|
|ON_WM_SIZECLIPBOARD( )|die "void" Afx_msg [OnSizeClipboard](../../mfc/reference/cwnd-class.md#onsizeclipboard)(CWnd *, HANDLE);|
|ON_WM_SIZING( )|afx_msg void [OnSizing](../../mfc/reference/cwnd-class.md#onsizing)( UINT, LPRECT );|
|ON_WM_SPOOLERSTATUS( )|die "void" Afx_msg [OnSpoolerStatus](../../mfc/reference/cwnd-class.md#onspoolerstatus)("uint", "uint");|
|ON_WM_STYLECHANGED( )|afx_msg void [OnStyleChanged](../../mfc/reference/cwnd-class.md#onstylechanged)( int, LPSTYLESTRUCT );|
|ON_WM_STYLECHANGING( )|afx_msg void [OnStyleChanging](../../mfc/reference/cwnd-class.md#onstylechanging)( int, LPSTYLESTRUCT );|
|ON_WM_SYSCHAR( )|afx_msg void [OnSysChar](../../mfc/reference/cwnd-class.md#onsyschar)( UINT, UINT, UINT );|
|ON_WM_SYSCOLORCHANGE( )|afx_msg void [OnSysColorChange](../../mfc/reference/cwnd-class.md#onsyscolorchange)( );|
|ON_WM_SYSCOMMAND( )|die "void" Afx_msg [OnSysCommand](../../mfc/reference/cwnd-class.md#onsyscommand)(UINT, LONG);|
|ON_WM_SYSDEADCHAR( )|afx_msg void [OnSysDeadChar](../../mfc/reference/cwnd-class.md#onsysdeadchar)( UINT, UINT, UINT );|
|ON_WM_SYSKEYDOWN( )|afx_msg void [OnSysKeyDown](../../mfc/reference/cwnd-class.md#onsyskeydown)( UINT, UINT, UINT );|
|ON_WM_SYSKEYUP( )|afx_msg void [OnSysKeyUp](../../mfc/reference/cwnd-class.md#onsyskeyup)( UINT, UINT, UINT );|

## <a name="see-also"></a>Siehe auch

[Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)<br/>
[Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)
