---
title: RuntimeClassType-Enumeration
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
ms.openlocfilehash: 80e8a120f7e3666721ff839a2a696388a64d734e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035957"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType-Enumeration

Gibt den Typ der [RuntimeClass](runtimeclass-class.md) -Instanz, die unterstützt wird.

## <a name="syntax"></a>Syntax

```cpp
enum RuntimeClassType;
```

## <a name="members"></a>Member

### <a name="values"></a>Werte

|Name|Beschreibung|
|----------|-----------------|
|`ClassicCom`|Eine klassische COM-Runtime-Klasse.|
|`Delegate`|Entspricht `ClassicCom`.|
|`InhibitFtmBase`|Deaktiviert die `FtmBase` -Unterstützung während der `__WRL_CONFIGURATION_LEGACY__` ist nicht definiert.|
|`InhibitWeakReference`|Deaktiviert die Unterstützung von schwachen Verweis.|
|`WinRt`|Eine Windows-Runtime-Klasse.|
|`WinRtClassicComMix`|Die Kombination aus `WinRt` und `ClassicCom`.|

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](microsoft-wrl-namespace.md)