---
title: not
ms.date: 11/04/2016
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- std::not
- std.not
- Not
helpviewer_keywords:
- not function
ms.assetid: d2ddbd5c-33c0-4aff-8961-feac155b4ba1
ms.openlocfilehash: 3abe5a5ec6cd40dd6f4e689c7c3f8ebb9eb1550f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156122"
---
# <a name="not"></a>not

Eine Alternative zu ! operator (.) verwendet.

## <a name="syntax"></a>Syntax

```C

#define not !
```

## <a name="remarks"></a>Hinweise

Das Makro gibt den Operator ! aus.

## <a name="example"></a>Beispiel

```cpp
// iso646_not.cpp
// compile with: /EHsc
#include <iostream>
#include <iso646.h>

int main( )
{
   using namespace std;
   int a = 0;

   if (!a)
      cout << "a is zero" << endl;

   if (not(a))
      cout << "a is zero" << endl;
}
```

```Output
a is zero
a is zero
```

## <a name="requirements"></a>Anforderungen

**Header:** \<iso646.h>