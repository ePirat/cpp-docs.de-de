---
title: input_iterator_tag-Struktur
ms.date: 11/04/2016
f1_keywords:
- xutility/std::input_iterator_tag
helpviewer_keywords:
- input_iterator_tag class
- input_iterator_tag struct
ms.assetid: ad68a4c6-f315-4ce1-8b74-c1fc71bd1577
ms.openlocfilehash: 5478a8f9fa6013202a1ea8dd838eedb80b9c367e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159248"
---
# <a name="inputiteratortag-struct"></a>input_iterator_tag-Struktur

Eine Klasse, die einen Rückgabetyp für eine `iterator_category` -Funktion, die einen eingabeiterator darstellt.

## <a name="syntax"></a>Syntax

Struktur Input_iterator_tag {};

## <a name="remarks"></a>Hinweise

Die Kategorietagklassen werden als Kompiliertags für die Auswahl des Algorithmus verwendet. Die Vorlagenfunktion muss herausfinden, welche die spezifischste Kategorie ihres Iteratorarguments ist, um zur Kompilierzeit den effizientesten Algorithmus verwenden zu können. Für jeden Iterator des Typs `Iterator` muss `iterator_traits`< `Iterator`> **::iterator_category** definiert werden, um das spezifischste Kategorietag zu werden, das das Iteratorverhalten beschreibt.

Der Typ ist identisch mit **Iterator** \< **Iter**> **:: Iterator_category** beim `Iter` beschreibt ein Objekt, das als dienen kann ein Eingabe-Iterator.

## <a name="example"></a>Beispiel

Finden Sie unter [Iterator_traits](../standard-library/iterator-traits-struct.md) oder [Random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) ein Beispiel zur Verwendung für `iterator_tag`s.

## <a name="requirements"></a>Anforderungen

**Header:** \<iterator>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
