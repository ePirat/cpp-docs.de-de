---
title: CD2DRectU-Klasse
ms.date: 11/04/2016
f1_keywords:
- CD2DRectU
- AFXRENDERTARGET/CD2DRectU
- AFXRENDERTARGET/CD2DRectU::CD2DRectU
- AFXRENDERTARGET/CD2DRectU::IsNull
helpviewer_keywords:
- CD2DRectU [MFC], CD2DRectU
- CD2DRectU [MFC], IsNull
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
ms.openlocfilehash: feb8af3992b9f56164ded0e3b6a4529a46fe2a1d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396287"
---
# <a name="cd2drectu-class"></a>CD2DRectU-Klasse

Ein Wrapper für `D2D1_RECT_U`.

## <a name="syntax"></a>Syntax

```
class CD2DRectU : public D2D1_RECT_U;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DRectU::CD2DRectU](#cd2drectu)|Überladen. Erstellt eine `CD2DRectU` -Sitzungsobjekts `D2D1_RECT_U` Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DRectU::IsNull](#isnull)|Gibt eine **booleschen** Wert, der angibt, ob ein Ausdruck keine gültigen Daten (NULL) enthält.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DRectU::operator CRect](#operator_crect)|Konvertiert `CD2DRectU` zu `CRect` Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`D2D1_RECT_U`

`CD2DRectU`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="cd2drectu"></a>  CD2DRectU::CD2DRectU

Erstellt ein Objekt CD2DRectU aus CRect-Objekt.

```
CD2DRectU(const CRect& rect);
CD2DRectU(const D2D1_RECT_U& rect);
  CD2DRectU(const D2D1_RECT_U* rect);

CD2DRectU(
    UINT32 uLeft = 0,
    UINT32 uTop = 0,
    UINT32 uRight = 0,
    UINT32 uBottom = 0);
```

### <a name="parameters"></a>Parameter

*rect*<br/>
Quellrechteck

*uLeft*<br/>
linke Koordinate der Quelle

*uTop*<br/>
obere Koordinate der Quelle

*uRight*<br/>
Quelle, die rechte Koordinate

*uBottom*<br/>
die untere Quellkoordinate

##  <a name="isnull"></a>  CD2DRectU::IsNull

Gibt einen booleschen Wert, der angibt, ob ein Ausdruck keine gültigen Daten (Null) enthält.

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn oben, links, unteren und rechten Werte des Rechtecks alle gleich 0 sind. andernfalls "false".

##  <a name="operator_crect"></a>  CD2DRectU::Operator CRect

CD2DRectU konvertiert in CRect-Objekt.

```
operator CRect();
```

### <a name="return-value"></a>Rückgabewert

Aktuelle Wert der D2D-Rechteck.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
