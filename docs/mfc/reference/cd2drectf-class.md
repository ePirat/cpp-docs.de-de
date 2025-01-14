---
title: CD2DRectF-Klasse
ms.date: 11/04/2016
f1_keywords:
- CD2DRectF
- AFXRENDERTARGET/CD2DRectF
- AFXRENDERTARGET/CD2DRectF::CD2DRectF
- AFXRENDERTARGET/CD2DRectF::IsNull
helpviewer_keywords:
- CD2DRectF [MFC], CD2DRectF
- CD2DRectF [MFC], IsNull
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
ms.openlocfilehash: 8e5c22fe15ce0d930f81dd16673927d5299bf630
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396274"
---
# <a name="cd2drectf-class"></a>CD2DRectF-Klasse

Ein Wrapper für `D2D1_RECT_F`.

## <a name="syntax"></a>Syntax

```
class CD2DRectF : public D2D1_RECT_F;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DRectF::CD2DRectF](#cd2drectf)|Überladen. Erstellt eine `CD2DRectF` -Sitzungsobjekts `D2D1_RECT_F` Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DRectF::IsNull](#isnull)|Gibt eine **booleschen** Wert, der angibt, ob ein Ausdruck keine gültigen Daten (NULL) enthält.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DRectF::operator CRect](#operator_crect)|Konvertiert `CD2DRectF` zu `CRect` Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`D2D1_RECT_F`

`CD2DRectF`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="cd2drectf"></a>  CD2DRectF::CD2DRectF

Erstellt ein Objekt CD2DRectF aus CRect-Objekt.

```
CD2DRectF(const CRect& rect);
CD2DRectF(const D2D1_RECT_F& rect);
  CD2DRectF(const D2D1_RECT_F* rect);

CD2DRectF(
    FLOAT fLeft = 0.,
    FLOAT fTop = 0.,
    FLOAT fRight = 0.,
    FLOAT fBottom = 0.);
```

### <a name="parameters"></a>Parameter

*rect*<br/>
Quellrechteck

*fLeft*<br/>
linke Koordinate der Quelle

*fTop*<br/>
obere Koordinate der Quelle

*fRight*<br/>
Quelle, die rechte Koordinate

*fBottom*<br/>
die untere Quellkoordinate

##  <a name="isnull"></a>  CD2DRectF::IsNull

Gibt einen booleschen Wert, der angibt, ob ein Ausdruck keine gültigen Daten (Null) enthält.

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn oben, links, unteren und rechten Werte des Rechtecks alle gleich 0 sind. andernfalls "false".

##  <a name="operator_crect"></a>  CD2DRectF::Operator CRect

CD2DRectF konvertiert in CRect-Objekt.

```
operator CRect();
```

### <a name="return-value"></a>Rückgabewert

Aktuelle Wert der D2D-Rechteck.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
