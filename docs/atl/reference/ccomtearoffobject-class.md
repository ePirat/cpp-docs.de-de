---
title: CComTearOffObject-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
ms.openlocfilehash: fd35b1e9e69c97402dd1ec357fd25fa1dcd5dd49
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259416"
---
# <a name="ccomtearoffobject-class"></a>CComTearOffObject-Klasse

Diese Klasse implementiert eine Tearoff Schnittstelle.

## <a name="syntax"></a>Syntax

```
template<class Base>
class CComTearOffObject : public Base
```

#### <a name="parameters"></a>Parameter

*Basis*<br/>
Abgeleitet von die Klasse abtrennbare `CComTearOffObjectBase` und die Schnittstellen Ihre abtrennbare-Objekt, das unterstützt werden sollen.

ATL implementiert die abtrennbare Schnittstellen in zwei Phasen – die `CComTearOffObjectBase` Methoden verarbeiten die verweiszählung und `QueryInterface`, während `CComTearOffObject` implementiert [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown).

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComTearOffObject::CComTearOffObject](#ccomtearoffobject)|Der Konstruktor.|
|[CComTearOffObject::~CComTearOffObject](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComTearOffObject::AddRef](#addref)|Inkrementiert den Verweiszähler für eine `CComTearOffObject` Objekt.|
|[CComTearOffObject::QueryInterface](#queryinterface)|Gibt einen Zeiger auf die Klasse abtrennbare oder die Besitzerklasse auf die angeforderte Schnittstelle zurück.|
|[CComTearOffObject::Release](#release)|Dekrementiert den Verweiszähler für eine `CComTearOffObject` Objekt aus, und es zerstört.|

### <a name="ccomtearoffobjectbase-methods"></a>CComTearOffObjectBase-Methoden

|||
|-|-|
|[CComTearOffObjectBase](#ccomtearoffobjectbase)|Konstruktor.|

### <a name="ccomtearoffobjectbase-data-members"></a>CComTearOffObjectBase-Datenmember

|||
|-|-|
|[m_pOwner](#m_powner)|Ein Zeiger auf eine `CComObject` die Besitzerklasse abgeleitet.|

## <a name="remarks"></a>Hinweise

`CComTearOffObject` implementiert eine Tearoff Schnittstelle als separates Objekt, das instanziiert wird, nur, wenn für diese Schnittstelle abgefragt wird. Die abtrennbare wird gelöscht, wenn dessen Verweiszähler auf 0 (null) ist. In der Regel erstellen Sie eine Schnittstelle für abtrennbare für eine Schnittstelle, die nur selten verwendet wird, da einen Vtable-Zeiger mit einem abtrennbare in alle Instanzen von Ihrem Hauptobjekt gespeichert werden.

Sollten Sie die Klasse implementiert die abtrennbare aus Ableitung `CComTearOffObjectBase` und über beliebige Schnittstellen Ihre abtrennbare-Objekt, das unterstützt werden sollen. `CComTearOffObjectBase` ist für die Besitzerklasse und das Threadmodell vorlagenbasiert. Die Besitzerklasse ist die Klasse des Objekts, für die ein abtrennbare implementiert wird. Wenn Sie ein Threadmodell nicht angeben, wird die Standard-Threadmodell verwendet.

Erstellen Sie eine COM-Zuordnung für die abtrennbare-Klasse. Wenn ATL der abtrennbare instanziiert wird, erstellt es `CComTearOffObject<CYourTearOffClass>` oder `CComCachedTearOffObject<CYourTearOffClass>`.

Z. B. in dem Beispiel BEEPER der `CBeeper2` Klasse ist die Klasse abtrennbare und `CBeeper` Klasse ist die Besitzerklasse:

[!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`Base`

`CComTearOffObject`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="addref"></a>  CComTearOffObject::AddRef

Inkrementiert den Verweiszähler des dem `CComTearOffObject` Objekt von einem.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der bei der Diagnose hilfreich und Tests sein kann.

##  <a name="ccomtearoffobject"></a>  CComTearOffObject::CComTearOffObject

Der Konstruktor.

```
CComTearOffObject(void* pv);
```

### <a name="parameters"></a>Parameter

*pv*<br/>
[in] Zeiger, der auf einen Zeiger auf konvertiert werden, wird eine `CComObject<Owner>` Objekt.

### <a name="remarks"></a>Hinweise

Der Besitzer der Verweiszähler inkrementiert um eins.

##  <a name="dtor"></a>  CComTearOffObject:: ~ CComTearOffObject

Der Destruktor.

```
~CComTearOffObject();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordnete Ressourcen frei, ruft FinalRelease und verringert das Modul Anzahl von Sperren.

##  <a name="ccomtearoffobjectbase"></a>  CComTearOffObject::CComTearOffObjectBase

Der Konstruktor.

```
CComTearOffObjectBase();
```

### <a name="remarks"></a>Hinweise

Initialisiert die [M_pOwner](#m_powner) Datenmember auf NULL.

##  <a name="m_powner"></a>  CComTearOffObject::m_pOwner

Ein Zeiger auf eine [CComObject](../../atl/reference/ccomobject-class.md) abgeleitetes Objekt aus *Besitzer*.

```
CComObject<Owner>* m_pOwner;
```

### <a name="parameters"></a>Parameter

*Besitzer*<br/>
[in] Die Klasse, die für die ein abtrennbare implementiert wird.

### <a name="remarks"></a>Hinweise

Der Zeiger wird während der Erstellung auf NULL initialisiert.

##  <a name="queryinterface"></a>  CComTearOffObject::QueryInterface

Ruft einen Zeiger auf die angeforderte Schnittstelle ab.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parameter

*iid*<br/>
[in] Die IID der Schnittstelle angefordert wird.

*ppvObject*<br/>
[out] Ein Zeiger auf den Schnittstellenzeiger vom *Iid*, oder NULL, wenn die Schnittstelle nicht gefunden wird.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Fragt zunächst nach Ihrer Klasse abtrennbare Schnittstellen ab. Wenn die Schnittstelle nicht vorhanden, Abfragen für die Schnittstelle in dem Objekt ist. Wenn die angeforderte Schnittstelle wird `IUnknown`, gibt die `IUnknown` des Besitzers.

##  <a name="release"></a>  CComTearOffObject::Release

Dekrementiert den Verweiszähler um eins und, wenn der Verweiszähler NULL ist, löscht der `CComTearOffObject`.

```
STDMETHOD_ULONG Release();
```

### <a name="return-value"></a>Rückgabewert

In nicht-Debug-Builds gibt immer 0 (null) zurück. In Debugbuilds müssen Sie einen Wert aus, der möglicherweise bei der Diagnose hilfreich oder Tests zurück.

## <a name="see-also"></a>Siehe auch

[CComCachedTearOffObject-Klasse](../../atl/reference/ccomcachedtearoffobject-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
