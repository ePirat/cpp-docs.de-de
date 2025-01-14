---
title: time_base-Klasse
ms.date: 11/04/2016
f1_keywords:
- locale/std::time_base
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
ms.openlocfilehash: e790237e506aa32bafdb39938d841307bbc4d9c3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412019"
---
# <a name="timebase-class"></a>time_base-Klasse

Die Klasse fungiert als Basisklasse für Facets der Time_get-Vorlagenklasse, definieren nur den Aufzählungstyp `dateorder` und mehrere Konstanten dieses Typs.

## <a name="syntax"></a>Syntax

```cpp
class time_base : public locale::facet {
public:
    enum dateorder {
        no_order,
        dmy,
        mdy,
        ymd,
        ydm
    };
    time_base(size_t _Refs = 0)
    ~time_base();
};
```

## <a name="remarks"></a>Hinweise

Jede Konstante kennzeichnet eine andere Möglichkeit, die Komponenten eines Datums zu ordnen. Es gibt folgende Konstanten:

- `no_order` Gibt ohne bestimmte Reihenfolge.

- `dmy` kennzeichnet die Reihenfolge Tag, Monat, Jahr wie in 2. Dezember 1979.

- `mdy` kennzeichnet die Reihenfolge Monat, Tag, Jahr wie in Dezember 2, 1979.

- `ymd` kennzeichnet die Reihenfolge Jahr, Monat, Tag wie in 1979/12/2.

- `ydm` kennzeichnet die Reihenfolge Jahr, Tag, Monat, wie in 1979: 2 Dez.

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
