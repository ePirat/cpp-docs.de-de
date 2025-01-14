---
title: Implementierung eines benutzerdefinierten Zeichenfolgenmanagers (grundlegende Methode)
ms.date: 11/04/2016
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
ms.openlocfilehash: c30c08217a09f600f8801bec9f50c4341e983a6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62235900"
---
# <a name="implementation-of-a-custom-string-manager-basic-method"></a>Implementierung eines benutzerdefinierten Zeichenfolgenmanagers (grundlegende Methode)

Die einfachste Möglichkeit zum Anpassen von die Speicherbelegungsschema für Zeichenfolgendaten ist die Verwendung der ATL bereitgestellten `CAtlStringMgr` -Klasse, doch bieten Sie Ihren eigenen Arbeitsspeicher speicherbelegungsroutinen. Der Konstruktor für `CAtlStringMgr` verwendet einen einzigen Parameter: einen Zeiger auf ein `IAtlMemMgr` Objekt. `IAtlMemMgr` ist eine abstrakte Basisklasse, die eine generische Schnittstelle zu einem Heap bereitstellt. Mithilfe der `IAtlMemMgr` -Schnittstelle, die `CAtlStringMgr` ordnet zuordnet, und gibt den Arbeitsspeicher frei, die zum Speichern von Zeichenfolgendaten verwendet. Sie können entweder zuerst die `IAtlMemMgr` -Schnittstelle selbst, oder verwenden Sie eine der Klassen, fünf ATL bereitgestellten Speicher-Manager. Die bereitgestellte ATL-Speicher-Manager umschließen einfach vorhandenen Memory Allocation Möglichkeiten:

- [CCRTHeap](../atl/reference/ccrtheap-class.md) dient als Wrapper für die CRT-Heap-Standardfunktionen ([Malloc](../c-runtime-library/reference/malloc.md), [kostenlose](../c-runtime-library/reference/free.md), und [Realloc](../c-runtime-library/reference/realloc.md))

- [CWin32Heap](../atl/reference/cwin32heap-class.md) umschließt, die mit ein Win32-Heap zu behandeln, [HeapAlloc](/windows/desktop/api/heapapi/nf-heapapi-heapalloc), [HeapFree](/windows/desktop/api/heapapi/nf-heapapi-heapfree), und [HeapRealloc](/windows/desktop/api/heapapi/nf-heapapi-heaprealloc)

- [Clocalheap –](../atl/reference/clocalheap-class.md) dient als Wrapper für die Win32-APIs: [LocalAlloc](/windows/desktop/api/winbase/nf-winbase-localalloc), [LocalFree](/windows/desktop/api/winbase/nf-winbase-localfree), und [LocalRealloc](/windows/desktop/api/winbase/nf-winbase-localrealloc)

- [CGlobalHeap](../atl/reference/cglobalheap-class.md) dient als Wrapper für die Win32-APIs: [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc), [GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree), und [GlobalRealloc](/windows/desktop/api/winbase/nf-winbase-globalrealloc).

- [CComHeap](../atl/reference/ccomheap-class.md) dient als Wrapper für die COM-Aufgabe Allocator-APIs: [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc), [CoTaskMemFree](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree), und [CoTaskMemRealloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemrealloc)

Für die Verwaltung die nützlichste-Klasse ist `CWin32Heap` , da es Ihnen ermöglicht, mehrere unabhängige Heaps zu erstellen. Sie auf einen separaten Heap nur für Zeichenfolgen verwenden möchten, könnten Sie z. B. Folgendes tun:

[!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_1.cpp)]

Um diese private Zeichenfolgen-Manager verwenden, um die Verwaltung des Speichers für einen `CString` Variable, übergeben Sie einen Zeiger an den Manager als Parameter an die `CString` der Variablen-Konstruktor:

[!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_2.cpp)]

## <a name="see-also"></a>Siehe auch

[Speicherverwaltung mit CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)
