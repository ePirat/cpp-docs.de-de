---
title: InvokeModeOptions-Struktur
ms.date: 03/22/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
ms.openlocfilehash: 0e5b45042c9959b87ad5db97ab755e49de469149
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035279"
---
# <a name="invokemodeoptions-structure"></a>InvokeModeOptions-Struktur

Gibt an, ob alle Ereignisse in der Warteschlange Delegaten ausgelöst werden, oder beim Beenden ausgelöst wird, nachdem ein Fehler ausgelöst wird. Die zulässigen Werte werden angegeben, der `InvokeMode` Enum.

## <a name="syntax"></a>Syntax

```cpp
enum InvokeMode
{
   StopOnFirstError = 1,
   FireAll = 2,
};

struct InvokeModeOptions
{
   static const InvokeMode invokeMode = invokeModeValue;
};
```

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](microsoft-wrl-namespace.md)<br/>
[Microsoft::wrl::AgileEventSource-Klasse](agileeventsource-class.md)