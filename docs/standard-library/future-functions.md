---
title: '&lt;future&gt;-Funktionen'
ms.date: 11/04/2016
f1_keywords:
- future/std::async
- future/std::future_category
- future/std::make_error_code
- future/std::make_error_condition
- future/std::swap
ms.assetid: 1e3acc1e-736a-42dc-ade2-b2fe69aa96bc
helpviewer_keywords:
- std::async [C++]
- std::future_category [C++]
- std::make_error_code [C++]
- std::make_error_condition [C++]
- std::swap [C++]
ms.openlocfilehash: 56ae0da7e86e092cee46d24d1a2a27d9d54709e4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159508"
---
# <a name="ltfuturegt-functions"></a>&lt;future&gt;-Funktionen

||||
|-|-|-|
|[async](#async)|[future_category](#future_category)|[make_error_code](#make_error_code)|
|[make_error_condition](#make_error_condition)|[swap](#swap)|

## <a name="async"></a> async

Stellt einen *asynchronen Anbieter* dar.

```cpp
template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(Fn&& fn, ArgTypes&&... args);

template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(launch policy, Fn&& fn, ArgTypes&&... args);
```

### <a name="parameters"></a>Parameter

*policy*<br/>
Ein [launch](../standard-library/future-enums.md#launch)-Wert.

### <a name="remarks"></a>Hinweise

Definitionen von Abkürzungen:

|||
|-|-|
|*dfn*|Das Ergebnis des Aufrufs von `decay_copy(forward<Fn>(fn))`.|
|*dargs*|Die Ergebnisse des Aufrufs von `decay_copy(forward<ArgsTypes>(args...))`.|
|*Ty*|Typ `result_of<Fn(ArgTypes...)>::type`.|

Die erste Vorlagenfunktion gibt `async(launch::any, fn, args...)` zurück.

Die zweite Funktion gibt ein `future<Ty>`-Objekt zurück, dessen *assoziierter asynchroner Zustand* ein Ergebnis zusammen mit den Werten von *dfn* und *dargs* sowie ein Threadobjekt enthält, um einen separaten Ausführungsthread zu verwalten.

Sofern `decay<Fn>::type` nicht ein anderer Typ als "launch" ist, ist die zweite Funktion nicht an der Überladungsauflösung beteiligt.

Der C++-Standard gibt an, dass wenn Richtlinie launch::async ist, die Funktion einen neuen Thread erstellt. Jedoch die Microsoft-Implementierung ist derzeit nicht konforme. Er erhält seine Threads aus dem Windows-ThreadPool, was in einigen Fällen einen Thread wiederverwendet, anstatt eine neue bereitstellen kann. Dies bedeutet, dass die `launch::async` Richtlinie wird tatsächlich als implementiert `launch::async|launch::deferred`.  Eine weitere Implikation der ThreadPool-basierte Implementierung ist, dass es keine Garantie dafür, dass der Thread-lokalen Variablen zerstört werden, wenn der Thread abgeschlossen ist. Wenn der Thread wiederverwendet und, um einen neuen Aufruf von bereitgestellt `async`, die alte Variablen auch weiterhin vorhanden. Deshalb wird empfohlen, dass Sie nicht Thread-lokalen Variablen mit verwenden `async`.

Wenn *Richtlinie* ist `launch::deferred`, die Funktion kennzeichnet, dessen zugeordneten asynchronen Zustand als das enthalten einer *verzögerten Funktion* und zurückgibt. Der erste Aufruf einer nicht zeitgesteuerten Funktion, die darauf wartet, dass der entsprechende assoziierte asynchrone Zustand bereit ist, ruft effektiv die verzögerte Funktion auf, indem `INVOKE(dfn, dargs..., Ty)` ausgewertet wird.

In allen Fällen wird der assoziierte asynchrone Zustand des `future`-Objekts nicht auf *bereit* festgelegt, bis die Auswertung von `INVOKE(dfn, dargs..., Ty)` abgeschlossen ist; entweder, indem eine Ausnahme ausgelöst wird oder indem die Rückgabe auf die normale Weise erfolgt. Das Ergebnis des assoziierten asynchronen Zustands ist eine Ausnahm, sofern eine ausgelöst wurde, oder ein beliebiger Wert, der von der Auswertung zurückgegeben wird.

> [!NOTE]
> Für ein `future`-Element oder das letzte [shared_future](../standard-library/shared-future-class.md)-Element, das der Aufgabe angefügt ist, die mit `std::async` gestartet ist, wird der Destruktor blockiert, wenn die Aufgabe nicht abgeschlossen wurde. Das heißt, er wird blockiert, wenn vom Thread weder `.get()` noch `.wait()` aufgerufen wurde, und die Aufgabe noch ausgeführt wird. Wenn ein `future`-Element, das von `std::async` erhalten wurde, außerhalb des lokalen Bereich verschoben wird, muss beim Schreiben von anderem Code, bei dem es verwendet wird, beachtet werden, dass der Destruktor möglicherweise blockiert, damit der Freigabezustand in den Bereitschaftszustand wechseln kann.

Die Pseudofunktion `INVOKE` wird in [\<functional>](../standard-library/functional.md) definiert.

## <a name="future_category"></a> future_category

Gibt einen Verweis auf das [error_category](../standard-library/error-category-class.md)-Objekt zurück, das Fehler bestimmt, die `future`-Objekten zugeordnet werden.

```cpp
const error_category& future_category() noexcept;
```

## <a name="make_error_code"></a> make_error_code

Erstellt ein [error_code](../standard-library/error-code-class.md)-Objekt zusammen mit dem [error_category](../standard-library/error-category-class.md)-Objekt, mit dem [zukünftige](../standard-library/future-class.md) Fehler bestimmt werden.

```cpp
inline error_code make_error_code(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Parameter

*Errno*<br/>
Ein [future_errc](../standard-library/future-enums.md#future_errc)-Wert, mit dem die gemeldeten Fehler identifiziert werden.

### <a name="return-value"></a>Rückgabewert

`error_code(static_cast<int>(Errno), future_category());`

## <a name="make_error_condition"></a> make_error_condition

Erstellt ein [error_condition](../standard-library/error-condition-class.md)-Objekt zusammen mit dem [error_category](../standard-library/error-category-class.md)-Objekt, das [future](../standard-library/future-class.md)-Fehler bestimmt.

```cpp
inline error_condition make_error_condition(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Parameter

*Errno*<br/>
Ein [future_errc](../standard-library/future-enums.md#future_errc)-Wert, mit dem die gemeldeten Fehler identifiziert werden.

### <a name="return-value"></a>Rückgabewert

`error_condition(static_cast<int>(Errno), future_category());`

## <a name="swap"></a>  swap

Tauscht den *zugeordneten asynchronen Zustand* eines `promise`-Objekts mit dem des anderen aus.

```cpp
template <class Ty>
void swap(promise<Ty>& Left, promise<Ty>& Right) noexcept;

template <class Ty, class... ArgTypes>
void swap(packaged_task<Ty(ArgTypes...)>& Left, packaged_task<Ty(ArgTypes...)>& Right) noexcept;
```

### <a name="parameters"></a>Parameter

*Links*<br/>
Das linke `promise`-Objekt.

*Rechts*<br/>
Das rechte `promise`-Objekt.

## <a name="see-also"></a>Siehe auch

[\<future>](../standard-library/future.md)<br/>
