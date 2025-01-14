---
title: ISpecifyPropertyPagesImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
ms.openlocfilehash: 3f5db65d1c318677a630307f44533e51d63ec44d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197418"
---
# <a name="ispecifypropertypagesimpl-class"></a>ISpecifyPropertyPagesImpl-Klasse

Diese Klasse implementiert `IUnknown` und stellt eine Standardimplementierung von der [ISpecifyPropertyPages](/windows/desktop/api/ocidl/nn-ocidl-ispecifypropertypages) Schnittstelle.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl
   : public ISpecifyPropertyPages
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `ISpecifyPropertyPagesImpl`.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|Füllt ein Array von UUID gezählt-Werte. Jede UUID entspricht die CLSID für eine der Eigenschaftenseiten, die im Eigenschaftenblatt des Objekts angezeigt werden können.|

## <a name="remarks"></a>Hinweise

Die [ISpecifyPropertyPages](/windows/desktop/api/ocidl/nn-ocidl-ispecifypropertypages) Schnittstelle ermöglicht es einen Client zum Abrufen einer Liste von CLSIDs für die Eigenschaftenseiten, die von einem Objekt unterstützten. Klasse `ISpecifyPropertyPagesImpl` stellt eine Standardimplementierung dieser Schnittstelle bereit und implementiert `IUnknown` durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus wird erstellt.

> [!NOTE]
>  Machen Sie nicht die `ISpecifyPropertyPages` Schnittstelle, wenn das Objekt Eigenschaftenseiten nicht unterstützt.

**Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ISpecifyPropertyPages`

`ISpecifyPropertyPagesImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="getpages"></a>  ISpecifyPropertyPagesImpl::GetPages

Füllt das Array der [CAUUID](/windows/desktop/api/ocidl/ns-ocidl-tagcauuid) Struktur mit der CLSID für die Eigenschaftenseiten, die im Eigenschaftenblatt des Objekts angezeigt werden können.

```
STDMETHOD(GetPages)(CAUUID* pPages);
```

### <a name="remarks"></a>Hinweise

ATL verwendet eigenschaftenzuordnung des Objekts, um jede CLSID abzurufen.

Finden Sie unter [ISpecifyPropertyPages::GetPages](/windows/desktop/api/ocidl/nf-ocidl-ispecifypropertypages-getpages) in das Windows SDK.

## <a name="see-also"></a>Siehe auch

[IPropertyPageImpl-Klasse](../../atl/reference/ipropertypageimpl-class.md)<br/>
[IPerPropertyBrowsingImpl-Klasse](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
