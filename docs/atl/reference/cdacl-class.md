---
title: CDacl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
ms.openlocfilehash: 1beac6106b825c775012b85ccd01226c3dfab795
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258961"
---
# <a name="cdacl-class"></a>CDacl-Klasse

Diese Klasse ist ein Wrapper für eine DACL (discretionary Access Control List)-Struktur.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CDacl : public CAcl
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDacl::CDacl](#cdacl)|Der Konstruktor.|
|[CDacl::~CDacl](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDacl::AddAllowedAce](#addallowedace)|Fügt einen zulässigen ACE (Access Control Entry) die `CDacl` Objekt.|
|[CDacl::AddDeniedAce](#adddeniedace)|Fügt einen verweigerten ACE, der `CDacl` Objekt.|
|[CDacl::GetAceCount](#getacecount)|Gibt die Anzahl der ACEs (Access Control-Einträge) in der `CDacl` Objekt.|
|[CDacl::RemoveAce](#removeace)|Entfernt einen bestimmten ACE (Access Control Entry) aus der `CDacl` Objekt.|
|[CDacl::RemoveAllAces](#removeallaces)|Entfernt alle ACEs innerhalb der `CDacl` Objekt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CDacl::operator =](#operator_eq)|Zuweisungsoperator.|

## <a name="remarks"></a>Hinweise

Sicherheitsbeschreibung eines Objekts kann es sich um eine DACL enthalten. Eine DACL enthält null oder mehr ACEs (Access Control-Einträge), die identifizieren, die Benutzer und Gruppen, die das Objekt zugreifen können. Wenn eine DACL leer ist (d. h., er enthält null ACEs), kein Zugriff ausdrücklich gewährt, Zugriff wird daher implizit verweigert. Allerdings werden Wenn Sicherheitsbeschreibung des Objekts nicht über eine DACL verfügt, das Objekt ist nicht geschützt, und jeder hat vollständigen Zugriff.

Zum Abrufen der DACL eines Objekts müssen Sie den Besitzer des Objekts sein oder READ_CONTROL Zugriff auf das Objekt. Um DACLs eines Objekts zu ändern, müssen Sie über WRITE_DAC-Zugriff auf das Objekt.

Verwenden Sie die Methoden der Klasse bereitgestellt, um zu erstellen, hinzufügen, entfernen und Löschen von ACEs aus dem `CDacl` Objekt. Siehe auch [AtlGetDacl](security-global-functions.md#atlgetdacl) und [AtlSetDacl](security-global-functions.md#atlsetdacl).

Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](/windows/desktop/SecAuthZ/access-control) im Windows SDK.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CAcl](../../atl/reference/cacl-class.md)

`CDacl`

## <a name="requirements"></a>Anforderungen

**Header:** atlsecurity.h

##  <a name="addallowedace"></a>  CDacl::AddAllowedAce

Fügt einen zulässigen ACE (Access Control Entry) die `CDacl` Objekt.

```
bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>Parameter

*rSid*<br/>
Ein [CSid](../../atl/reference/csid-class.md) Objekt.

*AccessMask*<br/>
Gibt die Maske von Zugriffsrechten zugelassen werden für den angegebenen `CSid` Objekt.

*AceFlags*<br/>
Ein Satz von Bitflags, die Vererbung des ACE steuern.

*pObjectType*<br/>
Der Objekttyp.

*pInheritedObjectType*<br/>
Den geerbten Objekttyp.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn der ACE hinzugefügt wird die `CDacl` Objekt, "false" bei einem Fehler.

### <a name="remarks"></a>Hinweise

Ein `CDacl` Objekt enthält null oder mehr ACEs (Access Control-Einträge), die identifizieren, die Benutzer und Gruppen, die das Objekt zugreifen können. Diese Methode fügt einen ACE, der Zugriff auf ermöglicht die `CDacl` Objekt.

Finden Sie unter [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) eine Beschreibung der verschiedenen Flags, die festgelegt werden kann, in der `AceFlags` Parameter.

##  <a name="adddeniedace"></a>  CDacl::AddDeniedAce

Einen verweigerten ACE (Access Control Entry) hinzufügt der `CDacl` Objekt.

```
bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>Parameter

*rSid*<br/>
Ein `CSid`-Objekt.

*AccessMask*<br/>
Gibt die Maske von Zugriffsrechten verweigert werden für den angegebenen `CSid` Objekt.

*AceFlags*<br/>
Ein Satz von Bitflags, die Vererbung des ACE steuern. Der Standardwert ist 0, in der ersten Form der Methode.

*pObjectType*<br/>
Der Objekttyp.

*pInheritedObjectType*<br/>
Den geerbten Objekttyp.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn der ACE hinzugefügt wird die `CDacl` Objekt, "false" bei einem Fehler.

### <a name="remarks"></a>Hinweise

Ein `CDacl` Objekt enthält null oder mehr ACEs (Access Control-Einträge), die identifizieren, die Benutzer und Gruppen, die das Objekt zugreifen können. Diese Methode fügt einen ACE, der verweigert den Zugriff auf die `CDacl` Objekt.

Finden Sie unter [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) eine Beschreibung der verschiedenen Flags, die festgelegt werden kann, in der `AceFlags` Parameter.

##  <a name="cdacl"></a>  CDacl::CDacl

Der Konstruktor.

```
CDacl (const ACL& rhs) throw(...);
CDacl () throw();
```

### <a name="parameters"></a>Parameter

*rhs*<br/>
Eine vorhandene `ACL` (Access Control List)-Struktur.

### <a name="remarks"></a>Hinweise

Die `CDacl` -Objekt kann optional mit einer vorhandenen erstellt werden `ACL` Struktur. Es ist wichtig zu beachten, dass nur eine DACL (discretionary Access Control List), und keine SACL (System Access Control List), als dieser Parameter übergeben werden sollte. In Debugbuilds verursacht übergeben eine SACL eine ASSERTION. In Releasebuilds übergeben eine SACL bewirkt, dass die ACEs (Access Control-Einträge) in der ACL, die ignoriert werden und tritt kein Fehler auf.

##  <a name="dtor"></a>  CDacl:: ~ CDacl

Der Destruktor.

```
~CDacl () throw();
```

### <a name="remarks"></a>Hinweise

Der Destruktor gibt alle Ressourcen abgerufen werden, von dem Objekt, einschließlich aller ACEs (Access Control-Einträge), die mit frei [CDacl::RemoveAllAces](#removeallaces).

##  <a name="getacecount"></a>  CDacl::GetAceCount

Gibt die Anzahl der ACEs (Access Control-Einträge) in der `CDacl` Objekt.

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der ACEs innerhalb der `CDacl` Objekt.

##  <a name="operator_eq"></a>  CDacl::operator =

Zuweisungsoperator.

```
CDacl& operator= (const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Parameter

*rhs*<br/>
Die ACL (Access Control List) auf das vorhandene Objekt zuweisen.

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf die aktualisierte `CDacl` Objekt.

### <a name="remarks"></a>Hinweise

Sie sollten sicherstellen, dass Sie nur eine DACL (discretionary Access Control List) für diese Funktion übergeben. Übergeben eine SACL (System Access Control List) für diese Funktion verursacht eine ASSERTION in Debugbuilds jedoch, dass keine Fehler in Releasebuilds.

##  <a name="removeace"></a>  CDacl::RemoveAce

Entfernt einen bestimmten ACE (Access Control Entry) aus der `CDacl` Objekt.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Index mit dem ACE-Eintrag zu entfernen.

### <a name="remarks"></a>Hinweise

Diese Methode wird von abgeleitet [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).

##  <a name="removeallaces"></a>  CDacl::RemoveAllAces

Entfernt alle ACEs (Access Control-Einträge) innerhalb der `CDacl` Objekt.

```
void RemoveAllAces() throw();
```

### <a name="remarks"></a>Hinweise

Entfernt alle `ACE` (Access Control Entry)-Struktur (falls vorhanden) in der `CDacl` Objekt.

## <a name="see-also"></a>Siehe auch

[Beispiel für die Sicherheit](../../overview/visual-cpp-samples.md)<br/>
[CAcl-Klasse](../../atl/reference/cacl-class.md)<br/>
[ACLs](/windows/desktop/SecAuthZ/access-control-lists)<br/>
[ACEs](/windows/desktop/SecAuthZ/access-control-entries)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[Globale Sicherheitsfunktionen](../../atl/reference/security-global-functions.md)
