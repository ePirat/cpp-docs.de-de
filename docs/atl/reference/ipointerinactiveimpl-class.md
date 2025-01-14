---
title: IPointerInactiveImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl::GetActivationPolicy
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveMouseMove
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveSetCursor
helpviewer_keywords:
- IPointerInactive ATL implementation
- inactive objects
- IPointerInactiveImpl class
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
ms.openlocfilehash: d7d9f048fceb3a569b024d7fe2b87f30a828b68e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274827"
---
# <a name="ipointerinactiveimpl-class"></a>IPointerInactiveImpl-Klasse

Diese Klasse implementiert `IUnknown` und [IPointerInactive](/windows/desktop/api/ocidl/nn-ocidl-ipointerinactive) Schnittstellenmethoden.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class IPointerInactiveImpl
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `IPointerInactiveImpl`.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IPointerInactiveImpl::GetActivationPolicy](#getactivationpolicy)|Ruft die aktuelle Activation-Richtlinie für das Objekt ab. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IPointerInactiveImpl::OnInactiveMouseMove](#oninactivemousemove)|Benachrichtigt, dass das Objekt, das der Mauszeiger darüber befindet, verschoben wurde, der angibt, des Objekts der Mausereignisse ausgelöst werden kann. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IPointerInactiveImpl::OnInactiveSetCursor](#oninactivesetcursor)|Legt den Mauszeiger für die inaktiven Objekt fest. Die ATL-Implementierung gibt E_NOTIMPL zurück.|

## <a name="remarks"></a>Hinweise

Einem inaktiven Objekt ist eine, die einfach geladen oder ausgeführt wird. Anders als ein aktives Objekt ist kann keinem inaktiven Objekt Tastatur- und Windows-Meldungen erhalten. Inaktive Objekte wird daher weniger Ressourcen und werden in der Regel effizienter.

Die [IPointerInactive](/windows/desktop/api/ocidl/nn-ocidl-ipointerinactive) Schnittstelle ermöglicht es, ein Objekt, um ein mindestlevel an Mausinteraktionen in inaktiven verbleibende zu unterstützen. Diese Funktion ist besonders nützlich für Steuerelemente.

Klasse `IPointerInactiveImpl` implementiert die `IPointerInactive` Methoden durch eine einfache Rückkehr E_NOTIMPL. Aber sie implementiert `IUnknown` durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus wird erstellt.

**Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IPointerInactive`

`IPointerInactiveImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="getactivationpolicy"></a>  IPointerInactiveImpl::GetActivationPolicy

Ruft die aktuelle Activation-Richtlinie für das Objekt ab.

```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPointerInactive::GetActivationPolicy](/windows/desktop/api/ocidl/nf-ocidl-ipointerinactive-getactivationpolicy) in das Windows SDK.

##  <a name="oninactivemousemove"></a>  IPointerInactiveImpl::OnInactiveMouseMove

Benachrichtigt, dass das Objekt, das der Mauszeiger darüber befindet, verschoben wurde, der angibt, des Objekts der Mausereignisse ausgelöst werden kann.

```
HRESULT OnInactiveMouseMove(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPointerInactive::OnInactiveMouseMove](/windows/desktop/api/ocidl/nf-ocidl-ipointerinactive-oninactivemousemove) in das Windows SDK.

##  <a name="oninactivesetcursor"></a>  IPointerInactiveImpl::OnInactiveSetCursor

Legt den Mauszeiger für die inaktiven Objekt fest.

```
HRESULT OnInactiveSetCursor(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL fSetAlways);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPointerInactive::OnInactiveSetCursor](/windows/desktop/api/ocidl/nf-ocidl-ipointerinactive-oninactivesetcursor) in das Windows SDK.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
