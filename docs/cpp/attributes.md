---
title: Attribute in C++
ms.date: 05/06/2019
ms.assetid: 748340d9-8abf-4940-b0a0-91b6156a3ff8
ms.openlocfilehash: bc92e5f3e279edc6fbea7f99d52c469f9fdf04f8
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222308"
---
# <a name="attributes-in-c"></a>Attribute in C++

Der C++-Standard definiert einen Satz von Attributen und können auch Compileranbieter so definieren Sie eigene Attribute (innerhalb eines anbieterspezifische-Namespace), aber der Compiler sind erforderlich, um nur die Attribute, die gemäß dem Standard zu erkennen.

In einigen Fällen überlappen Standardattribute compilerspezifischen "declspec"-Parameter. In Visual C++ können Sie die `[[deprecated]]` Attribut anstelle von `declspec(deprecated)` und das Attribut wird von einem beliebigen konformen-Compiler erkannt werden. Für alle anderen "declspec" Parameter wie z. B. Dllimport und Dllexport gibt es noch keine Attribut Entsprechung, damit Sie weiterhin "declspec"-Syntax verwenden müssen. Attribute wirken sich nicht auf das System der Typen, und die Bedeutung eines Programms nicht ändern. Compiler ignoriert die Attributwerte, die sie nicht erkennen.

**Visual Studio 2017 Version 15.3 und höher** (verfügbar mit [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): Sie können den Namespace für alle Namen mit einem einzelnen angeben, im Rahmen einer Attributliste **mit** Introducer:

```cpp
void g() {
    [[using rpr: kernel, target(cpu,gpu)]] // equivalent to [[ rpr::kernel, rpr::target(cpu,gpu) ]]
    do task();
}
```

## <a name="c-standard-attributes"></a>C++-Standard-Attribute

In C ++ 11 Geben Sie Attribute für eine standardisierte Möglichkeit zum Kommentieren von C++-Konstrukte (einschließlich aber nicht beschränkt auf Klassen, Funktionen, Variablen und Blöcke) mit zusätzlichen Informationen, die nicht unbedingt anbieterspezifische. Ein Compiler können diese Informationen zum Generieren der informationsmeldungen oder spezielle Logik angewendet, wenn den attributierten Code zu kompilieren. Der Compiler ignoriert alle Attribute, die er nicht erkennt, was bedeutet, dass Sie Ihren eigenen benutzerdefinierten Attributen, die mit der folgenden Syntax definieren können. Attribute werden durch doppelte eckige Klammern eingeschlossen:

```cpp
[[deprecated]]
void Foo(int);
```

Attribute, die eine standardisierte Alternative zu anbieterspezifischer Erweiterungen wie z. B. #pragma-Anweisungen darstellen __declspec() (Visual C++), oder &#95; &#95;Attribut&#95; &#95; (GNU). Allerdings müssen Sie weiterhin die anbieterspezifische Konstrukte für die meisten Zwecke zu verwenden. Der Standard gibt derzeit die folgenden Attribute, die ein entsprechenden Compiler erkennen soll:

- `[[noreturn]]` Gibt an, dass eine Funktion niemals zurückgibt; Anders ausgedrückt: es immer eine Ausnahme ausgelöst. Der Compiler kann anpassen, deren kompilierungsregeln für `[[noreturn]]` Entitäten.

- `[[carries_dependency]]` Gibt an, dass die Funktion datenabhängigkeits-Reihenfolge in Bezug auf die Synchronisierung von Threads verteilt. Das Attribut kann angewendet werden, um einen oder mehrere Parameter, um anzugeben, dass das übergebene Argument eine Abhängigkeit in den Funktionstext enthält. Für die Funktion selbst, um anzugeben, dass der Rückgabewert eine Abhängigkeit aus der Funktion enthält, kann das Attribut angewendet werden. Diese Informationen können der Compiler effizienteren Code generiert.

- `[[deprecated]]` **Visual Studio 2015 und höher:** Gibt an, dass eine Funktion nicht vorgesehen ist, verwendet werden, und möglicherweise nicht vorhanden in zukünftigen Versionen einer Bibliothek-Schnittstelle. Der Compiler kann dies verwenden, um eine informationsmeldung zu generieren, wenn Clientcode versucht die Funktion aufgerufen. Kann auf die Deklaration einer Klasse, einen Typedef-Namen, eine Variable, einen nicht statischen Datenmember, eine Funktion, einen Namespace, eine Enumeration, einen Enumerator oder eine Spezialisierung einer Klassenvorlage angewendet werden.

- `[[fallthrough]]` **Visual Studio 2017 und höher:** (verfügbar mit [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)) die `[[fallthrough]]` -Attribut kann verwendet werden, im Kontext des [wechseln](switch-statement-cpp.md) Anweisungen als Hinweis für den Compiler (oder Leser der Code), die das Fallthrough-Verhalten vorgesehen ist. Microsoft C++ Compiler derzeit warnt nicht Fallthrough-Verhalten, damit Sie dieses Attribut keine Wirkung Compilerverhalten hat.

- `[[nodiscard]]` **Visual Studio 2017 Version 15.3 und höher:** (verfügbar mit [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)) gibt an, dass der Rückgabewert einer Funktion nicht verworfen werden soll. Löst die Warnung von C4834, wie im folgenden Beispiel gezeigt:

    ```cpp
    [[nodiscard]]
    int foo(int i) { return i * i; }

    int main()
    {
        foo(42); //warning C4834: discarding return value of function with 'nodiscard' attribute
        return 0;
    }
    ```

- `[[maybe_unused]]` **Visual Studio 2017 Version 15.3 und höher:** (verfügbar mit [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)) gibt an, dass die Variable, Funktion, Klasse, Typedef, nicht statischen Datenmember, Enumeration oder Spezialisierung einer Klassenvorlage absichtlich nicht verwendet werden kann. Der Compiler warnt nicht, wenn eine Entität markiert `[[maybe_unused]]` wird nicht verwendet. Eine Entität, die ohne das Attribut deklariert ist kann später mit dem Attribut und umgekehrt erneut deklariert werden. Eine Entität wird markiert, nachdem die erste Deklaration, die markiert ist, analysiert wird und für den Rest der Übersetzung von der aktuellen Übersetzungseinheit betrachtet.

## <a name="microsoft-specific-attributes"></a>Microsoft-spezifischen Attribute

- `[[gsl::suppress(rules)]]` Dieses Microsoft-spezifische Attribut wird verwendet, für das Unterdrücken von Warnungen von Überprüfungen, die erzwingen, [Richtlinien Support Library (VA)](https://github.com/Microsoft/GSL) Regeln in Code. Betrachten Sie beispielsweise mit diesem Codeausschnitt aus:

    ```cpp
    void main()
    {
        int arr[10]; // GSL warning 26494 will be fired
        int* p = arr; // GSL warning 26485 will be fired
        [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1
        {
            int* q = p + 1; // GSL warning 26481 suppressed
            p = q--; // GSL warning 26481 suppressed
        }
    }
    ```

  Das Beispiel löst Warnungen aus:

  - 26494 (Geben Sie die Regel 5: Immer ein Objekt initialisiert.)

  - 26485 (Bounds-Regel 3: Kein Array zu zeigerverfall.)

  - 26481 (Begrenzungen Regel 1: Verwenden Sie keine Zeigerarithmetik. Verwenden Sie Spanne stattdessen.)

  Die ersten beiden Warnungen ausgelöst werden, wenn Sie mit dem CppCoreCheck Code Analysetool installiert und aktiviert diesen Code kompilieren. Aber aufgrund des Attributs wird nicht die dritte Warnung ausgelöst. Sie können das gesamte begrenzungsprofil unterdrücken, indem Sie das Schreiben von [[gsl::suppress(bounds)]], ohne eine spezielle regelzahl. Der C++ Core Guidelines dienen können Sie besser und sicherer Code zu schreiben. Das Attribut unterdrücken erleichtert es, die die Warnungen zu deaktivieren, wenn sie nicht erwünscht sind.