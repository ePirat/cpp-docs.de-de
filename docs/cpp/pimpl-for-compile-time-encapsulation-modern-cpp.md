---
title: pimpl für Compilierungszeitkapselung (Modern C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
ms.openlocfilehash: 6e114e2802dd4b2e5d1497867e2224be90c4752d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396105"
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>pimpl für Compilierungszeitkapselung (Modern C++)

Die *"pimpl" Idiom* ist eine moderne C++-Methode zum Ausblenden der Implementierung, um die Kopplung zu minimieren und Schnittstellen zu trennen. "Pimpl" ist die Kurzform für "-Zeiger zu Implementierung" Sie können bereits mit dem Konzept vertraut sein, aber andere Namen, wie sich zu mir Cat oder eine Compiler-Firewall-Idiom erkennbar.

## <a name="why-use-pimpl"></a>Gründe für die Verwendung von "pimpl"

Hier ist, wie das Idiom "pimpl" für den Lebenszyklus der Softwareentwicklung verbessern kann:

- Minimierung der Kompilierung Abhängigkeiten.

- Trennung von Benutzeroberfläche und Implementierung.

- Portabilität.

## <a name="pimpl-header"></a>"Pimpl"-header

```cpp
// my_class.h
class my_class {
   //  ... all public and protected stuff goes here ...
private:
   class impl; unique_ptr<impl> pimpl; // opaque type here
};
```

Das Idiom "pimpl" werden die Neuerstellung kaskadierende und fehleranfällig Objektlayouts vermieden. Es eignet sich gut für (transitiv) beliebte Typen.

## <a name="pimpl-implementation"></a>Implementierung von "pimpl"

Definieren der `impl` Klasse in der CPP-Datei.

```cpp
// my_class.cpp
class my_class::impl {  // defined privately here
  // ... all private data and functions: all of these
  //     can now change without recompiling callers ...
};
my_class::my_class(): pimpl( new impl )
{
  // ... set impl values ...
}
```

## <a name="best-practices"></a>Bewährte Methoden

Erwägen Sie, um Unterstützung für nicht auslösend Swap Spezialisierung hinzuzufügen.

## <a name="see-also"></a>Siehe auch

[Willkommen zurück bei C++ (Modern C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)
