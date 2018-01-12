---
title: 'Platform:: Metadata-Namespace | Microsoft Docs'
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/Platform::Metadata
dev_langs: C++
helpviewer_keywords: Platform::Metadata Namespace
ms.assetid: e3e114d8-a4b0-47f0-865a-9ce9d7212e86
caps.latest.revision: "6"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ce300956045c0a111deef6d514d1699bea8d794b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="platformmetadata-namespace"></a>Platform::Metadata-Namespace
Dieser Namespace enthält Attribute, die die Deklarationen von Typen ändern.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
  
namespace Platform {  
   namespace Metadata {  
}}  
```  
  
### <a name="members"></a>Member  
 Obwohl dieser Namespace für die interne Verwendung vorgesehen ist, können Browser die folgenden Member dieses Namespace anzeigen.  
  
|name|Hinweis|  
|----------|------------|  
|Attribut|Die Basisklasse für Attribute.|  
|[Platform::Metadata::DefaultMemberAttribute-Attribut](../cppcx/platform-metadata-defaultmemberattribute-attribute.md)|Gibt die bevorzugte Funktion an, um unter mehreren möglichen überladenen Funktionen aufzurufen.|  
|[Platform::Metadata::FlagsAttribute-Attribute](../cppcx/platform-metadata-flagsattribute-attribute.md)-Flags|Deklariert eine Enumeration als Enumeration von Bitfeldern.<br /><br /> Im folgenden Beispiel wird gezeigt, wie das `Flags` -Attribut auf eine Enumeration angewendet wird.<br /><br /> `[Flags] enum class MyEnumeration { enumA = 1, enumB = 2, enumC = 3}`|  
|[Platform::Metadata::RuntimeClassNameAttribute](../cppcx/platform-metadata-runtimeclassname.md)|Stellt sicher, dass eine private Verweisklasse einen gültigen Laufzeitklasse-Namen hat.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Platform`  
  
### <a name="requirements"></a>Anforderungen  
 **Metadaten:** platform.winmd  
  
 **Namespace:** Platform::Metadata  
  
## <a name="see-also"></a>Siehe auch  
 [Platform-Namespace](platform-namespace-c-cx.md)