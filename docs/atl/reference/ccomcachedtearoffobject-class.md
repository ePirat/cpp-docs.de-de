---
title: CComCachedTearOffObject-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::AddRef
- ATLCOM/ATL::CComCachedTearOffObject::FinalConstruct
- ATLCOM/ATL::CComCachedTearOffObject::FinalRelease
- ATLCOM/ATL::CComCachedTearOffObject::QueryInterface
- ATLCOM/ATL::CComCachedTearOffObject::Release
- ATLCOM/ATL::CComCachedTearOffObject::m_contained
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
ms.openlocfilehash: fb7821da03e1ca69c850fa1a295851faf4af4c5b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259676"
---
# <a name="ccomcachedtearoffobject-class"></a>CComCachedTearOffObject-Klasse

Diese Klasse implementiert [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) für eine Tearoff Schnittstelle.

## <a name="syntax"></a>Syntax

```
template
<class contained>
class CComCachedTearOffObject : public
    IUnknown,
public CComObjectRootEx<contained
::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Parameter

*contained*<br/>
Abgeleitet von die Klasse abtrennbare `CComTearOffObjectBase` und die Schnittstellen Ihre abtrennbare-Objekt, das unterstützt werden sollen.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComCachedTearOffObject::CComCachedTearOffObject](#ccomcachedtearoffobject)|Der Konstruktor.|
|[CComCachedTearOffObject::~CComCachedTearOffObject](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComCachedTearOffObject::AddRef](#addref)|Inkrementiert den Verweiszähler für eine `CComCachedTearOffObject` Objekt.|
|[CComCachedTearOffObject::FinalConstruct](#finalconstruct)|Ruft die `m_contained::FinalConstruct` (abtrennbare-Methode der Klasse).|
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|Ruft die `m_contained::FinalRelease` (abtrennbare-Methode der Klasse).|
|[CComCachedTearOffObject::QueryInterface](#queryinterface)|Gibt einen Zeiger auf die `IUnknown` von der `CComCachedTearOffObject` -Objekt, oder auf die angeforderte Schnittstelle in Ihrer Klasse abtrennbare auf (die Klasse `contained`).|
|[CComCachedTearOffObject::Release](#release)|Dekrementiert den Verweiszähler für eine `CComCachedTearOffObject` Objekt aus, und es zerstört, wenn der Verweiszähler auf 0 ist.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComCachedTearOffObject::m_contained](#m_contained)|Ein `CComContainedObject` abgeleitetes Objekt, von Ihrer Klasse abtrennbare (die Klasse `contained`).|

## <a name="remarks"></a>Hinweise

`CComCachedTearOffObject` implementiert [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) für eine Tearoff Schnittstelle. Diese Klasse unterscheidet sich von `CComTearOffObject` , `CComCachedTearOffObject` verfügt über eine eigene `IUnknown`getrennt von den des Besitzerobjekts `IUnknown` (der Besitzer ist das Objekt, das für die die abtrennbare erstellt wird). `CComCachedTearOffObject` behält sein eigenes Verweiszähler auf seine `IUnknown` und löscht Sie selbst, sobald dessen Verweiszähler auf 0 (null) ist. Jedoch bei einer Abfrage für eines der abtrennbare Schnittstellen, den Verweiszähler des dem des Besitzerobjekts `IUnknown` erhöht.

Wenn die `CComCachedTearOffObject` Objekt implementieren die abtrennbare bereits instanziiert wird und die Schnittstelle abtrennbare für in diesem Fall den gleichen abgefragt `CComCachedTearOffObject` Objekt wiederverwendet wird. Dagegen implementiert eine Tearoff Schnittstelle von einer `CComTearOffObject` wird erneut für abgefragt, über dem Objekt eine andere `CComTearOffObject` instanziiert.

Die Besitzerklasse implementieren muss `FinalRelease` , und rufen `Release` auf die zwischengespeicherten `IUnknown` für die `CComCachedTearOffObject`, dem wird dessen Verweiszähler verringert. Dies bewirkt, dass `CComCachedTearOffObject`des `FinalRelease` aufgerufen werden, und löschen die abtrennbare.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComCachedTearOffObject`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="addref"></a>  CComCachedTearOffObject::AddRef

Inkrementiert den Verweiszähler des dem `CComCachedTearOffObject` Objekts um 1.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der bei der Diagnose hilfreich und Tests sein kann.

##  <a name="ccomcachedtearoffobject"></a>  CComCachedTearOffObject::CComCachedTearOffObject

Der Konstruktor.

```
CComCachedTearOffObject(void* pv);
```

### <a name="parameters"></a>Parameter

*pv*<br/>
[in] Zeiger auf die `IUnknown` von der `CComCachedTearOffObject`.

### <a name="remarks"></a>Hinweise

Initialisiert die `CComContainedObject` Member [M_contained](#m_contained).

##  <a name="dtor"></a>  CComCachedTearOffObject:: ~ CComCachedTearOffObject

Der Destruktor.

```
~CComCachedTearOffObject();
```

### <a name="remarks"></a>Hinweise

Gibt Sie frei, alle zugeordneten Ressourcen und ruft [FinalRelease](#finalrelease).

##  <a name="finalconstruct"></a>  CComCachedTearOffObject::FinalConstruct

Aufrufe `m_contained::FinalConstruct` erstellen `m_contained`, wird die `CComContainedObject` <  `contained`>-Objekt für den Zugriff auf die von Ihrer Klasse abtrennbare implementierte Schnittstelle.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="finalrelease"></a>  CComCachedTearOffObject::FinalRelease

Aufrufe `m_contained::FinalRelease` freigeben `m_contained`, `CComContainedObject` <  `contained`> Objekt.

```
void FinalRelease();
```

##  <a name="m_contained"></a>  CComCachedTearOffObject::m_contained

Ein [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) von Ihrem abtrennbare-Klasse abgeleitetes Objekt.

```
CcomContainedObject <contained> m_contained;
```

### <a name="parameters"></a>Parameter

*contained*<br/>
[in] Abgeleitet von die Klasse abtrennbare `CComTearOffObjectBase` und die Schnittstellen Ihre abtrennbare-Objekt, das unterstützt werden sollen.

### <a name="remarks"></a>Hinweise

Die Methoden `m_contained` erbt werden verwendet, um die abtrennbare-Schnittstelle in Ihrer Klasse abtrennbare über des zwischengespeicherten abtrennbare Objekts zugreifen `QueryInterface`, `FinalConstruct`, und `FinalRelease`.

##  <a name="queryinterface"></a>  CComCachedTearOffObject::QueryInterface

Ruft einen Zeiger auf die angeforderte Schnittstelle ab.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parameter

*iid*<br/>
[in] Die GUID der Schnittstelle angefordert wird.

*ppvObject*<br/>
[out] Ein Zeiger auf den Schnittstellenzeiger vom *Iid*, oder NULL, wenn die Schnittstelle nicht gefunden wird.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Wenn die angeforderte Schnittstelle wird `IUnknown`, gibt einen Zeiger auf die `CComCachedTearOffObject`des eigenen `IUnknown` und inkrementiert den Verweiszähler. Andernfalls, Abfragen für die Schnittstelle abtrennbare-Klasse unter Verwendung der [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) Methode geerbt von `CComObjectRootEx`.

##  <a name="release"></a>  CComCachedTearOffObject::Release

Dekrementiert den Verweiszähler um 1 und, wenn der Verweiszähler auf 0 ist, löscht der `CComCachedTearOffObject` Objekt.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Rückgabewert

In nicht-Debug-Builds gibt immer 0 zurück. In Debugbuilds müssen Sie einen Wert aus, der möglicherweise bei der Diagnose hilfreich oder Tests zurück.

## <a name="see-also"></a>Siehe auch

[CComTearOffObject-Klasse](../../atl/reference/ccomtearoffobject-class.md)<br/>
[CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
