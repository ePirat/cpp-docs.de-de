---
title: _strdup_dbg, _wcsdup_dbg
ms.date: 11/04/2016
apiname:
- _strdup_dbg
- _wcsdup_dbg
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
- _wcsdup_dbg
- strdup_dbg
- _strdup_dbg
- wcsdup_dbg
helpviewer_keywords:
- _wcsdup_dbg function
- stdup_dbg function
- copying strings
- duplicating strings
- strings [C++], copying
- strings [C++], duplicating
- _strdup_dbg function
- wcsdup_dbg function
ms.assetid: 681db70c-d124-43ab-b83e-5eeea9035097
ms.openlocfilehash: 3092c27df1e39c7b719f6e7037efa202d29c9e81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353879"
---
# <a name="strdupdbg-wcsdupdbg"></a>_strdup_dbg, _wcsdup_dbg

Versionen von [_strdup und _wcsdup](strdup-wcsdup-mbsdup.md) , verwenden die Debugversion des **Malloc**.

## <a name="syntax"></a>Syntax

```C
char *_strdup_dbg(
   const char *strSource,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wcsdup_dbg(
   const wchar_t *strSource,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parameter

*strSource*<br/>
Mit NULL endende Quellzeichenfolge.

*blockType*<br/>
Angeforderter Typ des Speicherblocks: **_CLIENT_BLOCK** oder **_NORMAL_BLOCK**.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die Belegung angefordert oder **NULL**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in denen Belegung angefordert wurde, oder **NULL**.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt einen Zeiger auf den Speicherort für die kopierte Zeichenfolge oder **NULL** Wenn Speicher zugeordnet werden kann.

## <a name="remarks"></a>Hinweise

Die **_strdup_dbg** und **_wcsdup_dbg** -Funktionen sind identisch mit **_strdup** und **_wcsdup** mit dem Unterschied, dass wenn **_ DEBUGGEN von** wird definiert, verwenden Sie diese Funktionen die Debugversion von **Malloc**, **_malloc_dbg**, um Speicher für die duplizierte Zeichenfolge zu belegen. Informationen zu den Debugfunktionen von **_malloc_dbg**, finden Sie unter [_malloc_dbg](malloc-dbg.md).

In den meisten Fällen müssen Sie diese Funktionen nicht explizit aufrufen. Stattdessen definieren Sie das Flag **_CRTDBG_MAP_ALLOC**. Wenn **_CRTDBG_MAP_ALLOC** definiert ist, werden Aufrufe von **_strdup** und **_wcsdup** neu zu **_strdup_dbg** und **_ Wcsdup_dbg**, mit der *BlockType* festgelegt **_NORMAL_BLOCK**. Also, Sie müssen nicht dieser Funktionen explizit aufrufen, es sei denn, Sie möchten die Heapblöcke als markieren **_CLIENT_BLOCK**. Weitere Informationen zu den Blocktypen finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsdup_dbg**|**_strdup_dbg**|**_mbsdup**|**_wcsdup_dbg**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_strdup_dbg**, **_wcsdup_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strdup, _wcsdup, _mbsdup](strdup-wcsdup-mbsdup.md)<br/>
[Debugversionen von Heapreservierungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
