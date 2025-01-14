---
title: Standard-Dialogdatenaustauschroutinen
ms.date: 11/04/2016
helpviewer_keywords:
- standard dialog, data exchange routines
ms.assetid: c6adb7f3-f9af-4cc5-a9ea-315c5b60ad1a
ms.openlocfilehash: 05eaa86133bb55cfbf62ec68f81e7ca7d9ab169b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310005"
---
# <a name="standard-dialog-data-exchange-routines"></a>Standard-Dialogdatenaustauschroutinen

Dieses Thema enthält die standardmäßige Dialogdatenaustausch (DDX) Dialogfelddaten für allgemeine MFC-Dialogfeld-Steuerelemente verwendet werden.

> [!NOTE]
>  Der standard dialogdatenaustauschroutinen werden in den Header-Datei afxdd_.h definiert. Allerdings sollten Anwendungen afxwin.h enthalten.

### <a name="ddx-functions"></a>DDX-Funktionen

|||
|-|-|
|[DDX_CBIndex](#ddx_cbindex)|Initialisiert oder ruft den Index der aktuellen Auswahl des ein Kombinationsfeld-Steuerelement ab.|
|[DDX_CBString](#ddx_cbstring)|Initialisiert oder ruft den aktuellen Inhalt des Felds bearbeiten, der ein Kombinationsfeld-Steuerelement ab.|
|[DDX_CBStringExact](#ddx_cbstringexact)|Initialisiert oder ruft den aktuellen Inhalt des Felds bearbeiten, der ein Kombinationsfeld-Steuerelement ab.|
|[DDX_Check](#ddx_check)|Initialisiert oder ruft den aktuellen Zustand des Kontrollkästchen-Steuerelements.|
|[DDX_Control](#ddx_control)|Unterklassen ein bestimmtes Steuerelement in einem Dialogfeld.|
|[DDX_DateTimeCtrl](#ddx_datetimectrl)|Initialisiert oder ruft das Datum und/oder eine Uhrzeit-Daten von einem Datums- / Zeitauswahl-Steuerelement ab.|
|[DDX_IPAddress](#ddx_ipaddress)|Initialisiert oder der aktuelle Wert eines Steuerelements des IP-Adresse abgerufen.|
|[DDX_LBIndex](#ddx_lbindex)|Initialisiert oder ruft den Index der aktuellen Auswahl des ein Listenfeld-Steuerelement ab.|
|[DDX_LBString](#ddx_lbstring)|Initialisiert oder ruft die aktuelle Auswahl in einem Listenfeld-Steuerelement ab.|
|[DDX_LBStringExact](#ddx_lbstringexact)|Initialisiert oder ruft die aktuelle Auswahl in einem Listenfeld-Steuerelement ab.|
|[DDX_ManagedControl](#ddx_managedcontrol)|Erstellt ein .NET-Steuerelement mit Ressourcen-ID des Steuerelements übereinstimmt.|
|[DDX_MonthCalCtrl](#ddx_monthcalctrl)|Initialisiert oder ruft den aktuellen Wert von einem Monatskalender-Steuerelement ab.|
|[DDX_Radio](#ddx_radio)|Initialisiert oder ruft ab, der 0-basierte Index des Optionsfeld-Steuerelements, das derzeit in einer Optionsfeldgruppe für das Steuerelement aktiviert ist.|
|[DDX_Scroll](#ddx_scroll)|Initialisiert oder ruft die aktuelle Position des des Steuerelements einen Bildlauf-Leistenziehpunkts ab.|
|[DDX_Slider](#ddx_slider)|Initialisiert oder ruft Sie ab der aktuellen Position des Ziehpunkts für ein Schieberegler-Steuerelement.|
|[DDX_Text](#ddx_text)|Initialisiert oder ruft den aktuellen Wert eines Steuerelements bearbeiten.|

##  <a name="ddx_cbindex"></a>  DDX_CBIndex

Die `DDX_CBIndex` Funktion verwaltet die Übertragung von **Int** Daten zwischen einem Kombinationsfeld-Steuerelement in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem **Int** -Datenmember des im Dialogfeld, in der Formularansicht oder -Steuerelement View-Objekt.

```
void AFXAPI DDX_CBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die Ressourcen-ID des Kombinationsfeld-Steuerelements mit der Eigenschaft des Steuerelements verknüpft ist.

*index*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Wenn `DDX_CBIndex` aufgerufen wird, *Index* auf den Index der aktuellen Auswahl aus dem Kombinationsfeld festgelegt ist. Wenn kein Element ausgewählt ist, *Index* auf 0 festgelegt ist.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und -validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddx_cbstring"></a>  DDX_CBString

Die `DDX_CBString` Funktion verwaltet die Übertragung von `CString` Daten zwischen der Edit-Steuerelements, der ein Kombinationsfeld-Steuerelement in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem `CString` -Datenmember des im Dialogfeld, in der Formularansicht oder steuerungsansichtsobjekt.

```
void AFXAPI DDX_CBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die Ressourcen-ID des Kombinationsfeld-Steuerelements mit der Eigenschaft des Steuerelements verknüpft ist.

*value*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Wenn `DDX_CBString` aufgerufen wird, *Wert* auf aktuelle Auswahl aus dem Kombinationsfeld festgelegt ist. Wenn kein Element ausgewählt ist, *Wert* in eine Zeichenfolge der Länge Null festgelegt ist.

> [!NOTE]
>  Wenn das Kombinationsfeld ein Dropdown-Listenfeld, das ist, ist der Wert, die ausgetauscht maximal 255 Zeichen enthalten.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und -validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddx_cbstringexact"></a>  DDX_CBStringExact

Die `DDX_CBStringExact` Funktion verwaltet die Übertragung von `CString` Daten zwischen der Edit-Steuerelements, der ein Kombinationsfeld-Steuerelement in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem `CString` -Datenmember des im Dialogfeld, in der Formularansicht oder steuerungsansichtsobjekt.

```
void AFXAPI DDX_CBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die Ressourcen-ID des Kombinationsfeld-Steuerelements mit der Eigenschaft des Steuerelements verknüpft ist.

*value*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Wenn `DDX_CBStringExact` aufgerufen wird, *Wert* auf aktuelle Auswahl aus dem Kombinationsfeld festgelegt ist. Wenn kein Element ausgewählt ist, *Wert* in eine Zeichenfolge der Länge Null festgelegt ist.

> [!NOTE]
>  Wenn das Kombinationsfeld ein Dropdown-Listenfeld, das ist, ist der Wert, die ausgetauscht maximal 255 Zeichen enthalten.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und -validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddx_check"></a>  DDX_Check

Die `DDX_Check` Funktion verwaltet die Übertragung von **Int** Daten zwischen einem Kontrollkästchen-Steuerelement in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem **Int** -Datenmember des im Dialogfeld, in der Formularansicht oder -Steuerelement View-Objekt.

```
void AFXAPI DDX_Check(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die Ressourcen-ID des Kontrollkästchen-Steuerelements, das der Eigenschaft des Steuerelements zugeordnet werden soll.

*value*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Wenn `DDX_Check` aufgerufen wird, *Wert* auf den aktuellen Status des Kontrollkästchen-Steuerelements festgelegt ist. Eine Liste der möglichen Status-Werte, finden Sie unter [BM_GETCHECK](/windows/desktop/Controls/bm-getcheck) im Windows SDK.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und -validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddx_control"></a>  DDX_Control

Die `DDX_Control` Funktion Unterklassen anhand des Steuerelements *nIDC*, der im Dialogfeld, Formularansicht oder steuerungsansichtsobjekt.

```
void AFXAPI DDX_Control(
    CDataExchange* pDX,
    int nIDC,
    CWnd& rControl);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.

*nIDC*<br/>
Die Ressourcen-ID des Steuerelements auf den Unterklassen unterteilt werden.

*rControl*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, die im Zusammenhang mit dem angegebenen Steuerelement.

### <a name="remarks"></a>Hinweise

Die *pDX* -Objekt vom Framework bereitgestellt wird bei der `DoDataExchange` -Funktion aufgerufen wird. Aus diesem Grund `DDX_Control` sollte nur aufgerufen werden, in der Überschreibung der `DoDataExchange`.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und -validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddx_datetimectrl"></a>  DDX_DateTimeCtrl

Die `DDX_DateTimeCtrl` -Funktion verwaltet die Datenübertragung Datum und/oder eine Uhrzeit zwischen einem Datums- / Zeitauswahl-Steuerelement ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) in ein Dialogfeld oder Formular Objekt und entweder ein [CTime](../../atl-mfc-shared/reference/ctime-class.md) oder eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) -Datenmember des Dialogfeld oder Formular View-Objekts.

```
void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,
    int nIDC,
    CTime& value);

void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,
    int nIDC,
    COleDateTime& value);

void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung. Sie müssen nicht das Objekt gelöscht werden.

*nIDC*<br/>
Die Ressourcen-ID, der die Datums- / Zeitauswahl-Steuerelement die Membervariable zugeordnet werden soll.

*value*<br/>
In den ersten beiden Versionen, die einen Verweis auf eine `CTime` oder `COleDateTime` Membervariablen gespeichert, das Dialogfeld, Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden. In der dritten Version, die einen Verweis auf eine `CString` Data Member steuerungsansichtsobjekt.

### <a name="remarks"></a>Hinweise

Wenn `DDX_DateTimeCtrl` aufgerufen wird, *Wert* festgelegt ist, mit dem aktuellen Status der das Datum und Zeit Datumsauswahl-Steuerelement oder das Steuerelement auf festgelegt ist *Wert*, je nachdem, auf die Richtung des Exchange.

In der dritten Version, die oben genannten `DDX_DateTimeCtrl` verwaltet die Übertragung von `CString` Daten zwischen einem Datum /-Steuerelement und ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Datenmember des Steuerelementobjekts anzeigen. Die Zeichenfolge wird mit Regeln für das aktuelle Gebietsschema für die Formatierung von Datums- und Uhrzeitangaben formatiert.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und -validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

## <a name="ddx_managedcontrol"></a>  DDX_ManagedControl

Erstellt ein .NET-Steuerelement mit Ressourcen-ID des Steuerelements übereinstimmt.

### <a name="syntax"></a>Syntax

```
template <typename T>
void DDX_ManagedControl(
   CDataExchange* pDX,
   int nIDC,
   CWinFormsControl<T>& control );
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange-Klasse](cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die Ressourcen-ID des Steuerelements mit der Eigenschaft des Steuerelements verknüpft ist.

*Steuerelement*<br/>
Ein Verweis auf eine [CWinFormsControl-Klasse](cwinformscontrol-class.md) Objekt.

### <a name="remarks"></a>Hinweise

`DDX_ManagedControl` Aufrufe [CWinFormsControl::CreateManagedControl](cwinformscontrol-class.md#createmanagedcontrol) zum Erstellen eines Steuerelements mit der Resource-Steuerelement-ID übereinstimmt. Verwendung `DDX_ManagedControl` zum Erstellen von Steuerelementen aus dem Ressourcen-IDs in [CDialog::](cdialog-class.md#oninitdialog). Für den Datenaustausch verwendet müssen Sie nicht die DDX-/DDV-Funktionen mit Windows Forms-Steuerelemente verwenden.

Weitere Informationen finden Sie unter [Vorgehensweise: DDX/DDV-Datenbindung mit Windows Forms](../../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md).

### <a name="requirements"></a>Anforderungen

**Header:** afxwinforms.h

##  <a name="ddx_ipaddress"></a>  DDX_IPAddress

Die `DDX_IPAddress` -Funktion verwaltet die Übertragung von Daten zwischen einem Steuerelement für die IP-Adresse und ein Datenelement des Steuerelementobjekts anzeigen.

```
void AFXAPI DDX_IPAddress(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die Ressourcen-ID des Steuerelements IP-Adresse der Eigenschaft des Steuerelements zugeordnet werden soll.

*value*<br/>
Ein Verweis auf den DWORD-Wert, der mit dem 4-Feld-Wert, der das Steuerelement für die IP-Adresse. Die Felder ausgefüllt oder wie folgt zu lesen.

|Feld|Bits, die den Wert des Felds enthält.|
|-----------|-------------------------------------|
|3|0 bis 7|
|2|8 bis 15|
|1|16 bis 23|
|0|24 bis 31|

Verwenden Sie die Win32 [IPM_GETADDRESS](/windows/desktop/Controls/ipm-getaddress) , lesen den Wert ein, oder verwenden Sie [IPM_SETADDRESS](/windows/desktop/Controls/ipm-setaddress) um den Wert zu füllen. Diese Nachrichten werden in das Windows SDK beschrieben.

### <a name="remarks"></a>Hinweise

Wenn `DDX_IPAddress` aufgerufen wird, *Wert* wird entweder aus dem IP-Adresse-Steuerelement, gelesen oder *Wert* richtet sich an das Steuerelement, abhängig von der Richtung des Exchange.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und -validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddx_lbindex"></a>  DDX_LBIndex

Die `DDX_LBIndex` Funktion verwaltet die Übertragung von **Int** Daten zwischen einem Listenfeld-Steuerelement in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem **Int** -Datenmember des im Dialogfeld, in der Formularansicht oder -Steuerelement View-Objekt.

```
void AFXAPI DDX_LBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die Ressourcen-ID des Listenfeld-Steuerelements mit der Eigenschaft des Steuerelements verknüpft ist.

*index*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Wenn `DDX_LBIndex` aufgerufen wird, *Index* auf den Index der aktuellen Auswahl des Listenfelds festgelegt ist. Wenn kein Element ausgewählt ist, *Index* wird auf-1 festgelegt.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und -validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddx_lbstring"></a>  DDX_LBString

Die `DDX_LBString` Funktion verwaltet die Übertragung von `CString` Daten zwischen einem Listenfeld-Steuerelement in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem `CString` -Datenmember des im Dialogfeld, in der Formularansicht oder steuerungsansichtsobjekt.

```
void AFXAPI DDX_LBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die Ressourcen-ID des Listenfeld-Steuerelements mit der Eigenschaft des Steuerelements verknüpft ist.

*value*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Wenn `DDX_LBString` wird aufgerufen, um Daten in einem Listenfeld-Steuerelement, das erste Element im Steuerelement übertragen, deren Anfang übereinstimmt *Wert* ausgewählt ist. (Verwenden Sie entsprechend das gesamte Element und nicht nur ein Präfix [DDX_LBStringExact](#ddx_lbstringexact).) Wenn keine Übereinstimmungen vorhanden sind, sind keine Elemente ausgewählt. Die beim Abgleich wird Groß-/Kleinschreibung.

Wenn `DDX_LBString` wird aufgerufen, um das Übertragen von Daten aus einem Listenfeld-Steuerelement, *Wert* auf aktuelle Auswahl des Listenfelds festgelegt ist. Wenn kein Element ausgewählt ist, *Wert* in eine Zeichenfolge der Länge Null festgelegt ist.

> [!NOTE]
>  Wenn das Listenfeld ein Dropdown-Listenfeld, das ist, ist der Wert, die ausgetauscht maximal 255 Zeichen enthalten.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und -validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddx_lbstringexact"></a>  DDX_LBStringExact

Die `DDX_CBStringExact` Funktion verwaltet die Übertragung von `CString` Daten zwischen der Edit-Steuerelements, der ein Listenfeld-Steuerelement in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem `CString` -Datenmember des im Dialogfeld, in der Formularansicht oder steuerungsansichtsobjekt.

```
void AFXAPI DDX_LBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die Ressourcen-ID des Listenfeld-Steuerelements mit der Eigenschaft des Steuerelements verknüpft ist.

*value*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Wenn `DDX_LBStringExact` wird aufgerufen, um das Übertragen von Daten in einem Listenfeld-Steuerelement, das erste Element im Steuerelement, das entspricht *Wert* ausgewählt ist. (Um nur ein Präfix, statt das gesamte Element vergleichen möchten, verwenden [DDX_LBString](#ddx_lbstring).) Wenn keine Übereinstimmungen vorhanden sind, sind keine Elemente ausgewählt. Die beim Abgleich wird Groß-/Kleinschreibung.

Wenn `DDX_CBStringExact` wird aufgerufen, um das Übertragen von Daten aus einem Listenfeld-Steuerelement, *Wert* auf aktuelle Auswahl des Listenfelds festgelegt ist. Wenn kein Element ausgewählt ist, *Wert* in eine Zeichenfolge der Länge Null festgelegt ist.

> [!NOTE]
>  Wenn das Listenfeld ein Dropdown-Listenfeld, das ist, ist der Wert, die ausgetauscht maximal 255 Zeichen enthalten.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und -validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddx_monthcalctrl"></a>  DDX_MonthCalCtrl

Die `DDX_MonthCalCtrl` -Funktion verwaltet die Übertragung von Daten zwischen einem Monatskalender-Steuerelement ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) in einem Dialogfeld, Formularansicht oder steuerungsansichtsobjekts und entweder ein [CTime](../../atl-mfc-shared/reference/ctime-class.md) oder eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) -Datenmember des im Dialogfeld, in der Formularansicht oder steuerungsansichtsobjekt.

```
void AFXAPI DDX_MonthCalCtrl(
    CDataExchange* pDX,
    int nIDC,
    CTime& value);

void AFXAPI DDX_MonthCalCtrl(
    CDataExchange* pDX,
    int nIDC,
    COleDateTime& value);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung. Sie müssen nicht das Objekt gelöscht werden.

*nIDC*<br/>
Die Ressourcen-ID, der im Monatskalender-Steuerelement, die die Membervariable zugeordnet ist.

*value*<br/>
Ein Verweis auf eine `CTime` oder `COleDateTime` Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Das Steuerelement verwaltet nur einen Datumswert. Die Time-Felder in das Objekt sind Satz entsprechend der Uhrzeit der Erstellung des Fenster des Steuerelements oder den Zeitpunkt festgelegt wurde, in das Steuerelement mit einem Aufruf von `CMonthCalCtrl::SetCurSel`.

Wenn `DDX_MonthCalCtrl` aufgerufen wird, *Wert* auf den aktuellen Zustand der im Monatskalender-Steuerelement festgelegt ist.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und -validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddx_radio"></a>  DDX_Radio

Die `DDX_Radio` Funktion verwaltet die Übertragung von **Int** Daten zwischen einer Optionsfeldgruppe-Steuerelement in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem **Int** -Datenmember des im Dialogfeld, in der Formularansicht oder -Steuerelement View-Objekt. Der Wert des der **Int** Datenmember wird bestimmt, gemäß der Radio Schaltfläche in der Gruppe ausgewählt wird.

```
void AFXAPI DDX_Radio(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die Ressourcen-ID, der das erste Optionsfeld-Steuerelement in der Gruppe.

*value*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Wenn `DDX_Radio` aufgerufen wird, *Wert* auf den aktuellen Status der Gruppe "Optionsfeld-Steuerelement" festgelegt ist. Der Wert wird festgelegt, als 0-basierte Index des Optionsfeld-Steuerelements, das derzeit aktiviert ist, oder -1, wenn keine Optionsfeld-Steuerelemente werden überprüft.

Beispielsweise im Fall, in dem das erste Optionsfeld in der Gruppe ist aktiviert (der Schaltfläche mit WS_GROUP-Stil) den Wert des der **Int** Member ist 0 und so weiter.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und -validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddx_scroll"></a>  DDX_Scroll

Die `DDX_Scroll` Funktion verwaltet die Übertragung von **Int** Daten zwischen einem Bildlaufleisten-Steuerelements in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem **Int** -Datenmember des im Dialogfeld, in der Formularansicht oder Steuerelement View-Objekt.

```
void AFXAPI DDX_Scroll(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die Ressourcen-ID des Schiebeleisten-Steuerelements mit der Eigenschaft des Steuerelements verknüpft ist.

*value*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansichts- oder Steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Wenn `DDX_Scroll` aufgerufen wird, *Wert* auf die aktuelle Position des Steuerelements Thumb-Steuerelement festgelegt ist. Weitere Informationen zu den Werten, die die aktuelle Position des Steuerelements Thumb-Steuerelement zugeordnet, finden Sie unter [GetScrollPos](/windows/desktop/api/winuser/nf-winuser-getscrollpos) im Windows SDK.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und -validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddx_slider"></a>  DDX_Slider

Die `DDX_Slider` Funktion verwaltet die Übertragung von **Int** Daten zwischen einem Schieberegler-Steuerelement in einem Dialogfeld oder Formular anzeigen und eine **Int** -Datenmember des Dialogfeld oder Formular View-Objekts.

```
void AFXAPI DDX_Slider(
    CDataExchange* pDX,
    int nIDC,
    int& value);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die Ressourcen-ID des Schieberegler-Steuerelements.

*value*<br/>
Ein Verweis auf den Wert ausgetauscht werden sollen. Dieser Parameter enthält, oder legt die aktuelle Position des Schieberegler-Steuerelements fest.

### <a name="remarks"></a>Hinweise

Wenn `DDX_Slider` aufgerufen wird, *Wert* festgelegt ist, an der aktuellen Position des Ziehpunkts des Steuerelements, oder der Wert die Position, abhängig von der Richtung der Exchange-empfangen werden.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und -validierung](../../mfc/dialog-data-exchange-and-validation.md). Weitere Informationen über Schieberegler-Steuerelemente finden Sie unter [Verwenden von CSliderCtrl](../../mfc/using-csliderctrl.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddx_text"></a>  DDX_Text

Die `DDX_Text` Funktion verwaltet die Übertragung von **Int**, **UINT**, **lange**, DWORD-Wert `CString`, **"float"**, oder **doppelte** Daten zwischen einer Edit-Steuerelements in einem Dialogfeld Formularansicht oder Steuern von Ansicht und ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Datenmember des im Dialogfeld, in der Formularansicht oder steuerungsansichtsobjekt.

```
void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    BYTE& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    short& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    int& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    UINT& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    long& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    CString& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    float& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    double& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    COleCurrency& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,
    int nIDC,
    COleDateTime& value);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die ID des ein Bearbeitungssteuerelement im im Dialogfeld, in der Formularansicht oder steuerungsansichtsobjekt.

*value*<br/>
Ein Verweis auf einen Datenmember in das Dialogfeld, Formularansicht oder steuerungsansichtsobjekt. Der Datentyp des *Wert* abhängig von der überladenen Versionen `DDX_Text` Sie verwenden.

### <a name="remarks"></a>Hinweise

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und -validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

## <a name="see-also"></a>Siehe auch

[Standardroutinen zur Validierung der Dialogfelddaten](standard-dialog-data-validation-routines.md)<br/>
[Makros und globale Variablen](mfc-macros-and-globals.md)<br/>
[CWinFormsControl::CreateManagedControl](cwinformscontrol-class.md#createmanagedcontrol)<br/>
[CDialog::OnInitDialog](cdialog-class.md#oninitdialog)
