---
title: '&lt;unordered_set&gt;-Funktionen'
ms.date: 11/04/2016
f1_keywords:
- unordered_set/std::swap (set)
- unordered_set/std::swap (unordered_multiset)
ms.assetid: 66b35671-4023-4411-ad50-83786580d8ee
ms.openlocfilehash: a6e005918730a2ca1f52469130e2ea2cf1547fc8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376993"
---
# <a name="ltunorderedsetgt-functions"></a>&lt;unordered_set&gt;-Funktionen

|||
|-|-|
|[swap (set)](#swap)|[swap (unordered_multiset)](#swap_unordered_multiset)|

## <a name="swap"></a> swap (unordered_set)

Vertauscht den Inhalt von zwei Containern.

```

template <class Key, class Hash, class Pred, class Alloc>
void swap(
   unordered_set <Key, Hash, Pred, Alloc>& left,
   unordered_set <Key, Hash, Pred, Alloc>& right);
```

### <a name="parameters"></a>Parameter

*Key*<br/>
Der Schlüsseltyp.

*Hash*<br/>
Der Hashfunktionsobjekttyp.

*Pred*<br/>
Der Gleichheitsvergleich-Funktionsobjekttyp.

*Alloc*<br/>
Die Zuweisungsklasse.

*left*<br/>
Der erste zu tauschende Container.

*right*<br/>
Der zweite zu tauschende Container.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion führt `left.`[unordered_set::swap](../standard-library/unordered-set-class.md#swap)`(right)` aus.

### <a name="example"></a>Beispiel

```cpp
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
Myset c1;

c1.insert('a');
c1.insert('b');
c1.insert('c');

// display contents " [c] [b] [a]"
for (Myset::const_iterator it = c1.begin();
it != c1.end(); ++it)
std::cout << " [" << *it << "]";
std::cout << std::endl;

Myset c2;

c2.insert('d');
c2.insert('e');
c2.insert('f');

c1.swap(c2);

// display contents " [f] [e] [d]"
for (Myset::const_iterator it = c1.begin();
it != c1.end(); ++it)
std::cout << " [" << *it << "]";
std::cout << std::endl;

swap(c1, c2);

// display contents " [c] [b] [a]"
for (Myset::const_iterator it = c1.begin();
it != c1.end(); ++it)
std::cout << " [" << *it << "]";
std::cout << std::endl;

return (0);
}
```

```Output

[c] [b] [a]
[f] [e] [d]
[c] [b] [a]
```

## <a name="swap_unordered_multiset"></a> swap (unordered_multiset)

Vertauscht den Inhalt von zwei Containern.

```

template <class Key, class Hash, class Pred, class Alloc>
void swap(
   unordered_multiset <Key, Hash, Pred, Alloc>& left,
   unordered_multiset <Key, Hash, Pred, Alloc>& right);
```

### <a name="parameters"></a>Parameter

*Key*<br/>
Der Schlüsseltyp.

*Hash*<br/>
Der Hashfunktionsobjekttyp.

*Pred*<br/>
Der Gleichheitsvergleich-Funktionsobjekttyp.

*Alloc*<br/>
Die Zuweisungsklasse.

*left*<br/>
Der erste zu tauschende Container.

*right*<br/>
Der zweite zu tauschende Container.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion führt `left.`[unordered_multiset::swap](../standard-library/unordered-multiset-class.md#swap)`(right)` aus.

### <a name="example"></a>Beispiel

```cpp
// std__unordered_set__u_ms_swap.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents " [c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << *it << "]";
    std::cout << std::endl;

    Myset c2;

    c2.insert('d');
    c2.insert('e');
    c2.insert('f');

    c1.swap(c2);

    // display contents " [f] [e] [d]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << *it << "]";
    std::cout << std::endl;

    swap(c1, c2);

    // display contents " [c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << *it << "]";
    std::cout << std::endl;

    return (0);
}
```

```Output

[c] [b] [a]
[f] [e] [d]
[c] [b] [a]
```

## <a name="see-also"></a>Siehe auch

[<unordered_set>](../standard-library/unordered-set.md)<br/>
