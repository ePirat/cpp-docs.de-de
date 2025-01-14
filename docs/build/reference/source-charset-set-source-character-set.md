---
title: / Source-CharSet (Quellzeichensatz festlegen)
ms.date: 02/06/2019
f1_keywords:
- source-charset
- /source-charset
helpviewer_keywords:
- /execution-charset compiler option
ms.assetid: d3c5bf7f-526d-4ee4-acc5-c1a02a4fc481
ms.openlocfilehash: 54f8d4d0edaa310384d19a9c9a188f96ec895eac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318211"
---
# <a name="source-charset-set-source-character-set"></a>/ Source-CharSet (Quellzeichensatz festlegen)

Können Sie dem quellzeichensatz, die für die ausführbare Datei angeben.

## <a name="syntax"></a>Syntax

```
/source-charset:[IANA_name|.CPID]
```

## <a name="arguments"></a>Argumente

**IANA_name**<br/>
Der IANA-definierten Zeichensatzname.

**CPID**<br/>
Der Codepagebezeichner als Dezimalzahl.

## <a name="remarks"></a>Hinweise

Sie können die **/Source-CharSet** Option zur Angabe einer erweiterten quellzeichensatz verwenden, wenn Ihre Quelldateien enthalten Zeichen, die nicht dargestellt werden, in der grundlegenden quellzeichensatz. Der quellzeichensatz ist die Codierung verwendet, um den Quelltext des Programms in die interne Darstellung verwendet als Eingabe für den vorverarbeitungsphasen vor der Kompilierung zu interpretieren. Die interne Darstellung wird dann in der ausführungszeichensatz zum Speichern von Zeichenfolgen und Werte in die ausführbare Datei konvertiert. Können Sie entweder die IANA Name des Zeichensatzes ISO oder ein Punkt (.) gefolgt von einer 3 bis 5 Ziffern decimal-Codepagebezeichner der zu verwendenden Zeichensatz angeben. Eine Liste der unterstützten Codepage-IDs und Namen der Zeichensatz, finden Sie unter [Codepage-IDs](/windows/desktop/Intl/code-page-identifiers).

Standardmäßig erkennt Visual Studio eine Bytereihenfolge-Marke, um festzustellen, ob die Quelldatei in eine codierte Unicode-Format, z. B. UTF-16 oder UTF-8 ist. Wenn keine Bytereihenfolge-Marke befindet, es geht davon aus die Quelldatei ist, außer Sie einen Zeichensatz Name oder die Codepage geben mit codiert mithilfe der aktuellen Codepage für Benutzer, die **/Source-CharSet** Option. Visual Studio können Sie C++-Quellcode mithilfe der verschiedenen zeichencodierungen zu speichern. Weitere Informationen zu Quell- und ausführungszeichensätze, finden Sie unter [Zeichensätze](../../cpp/character-sets.md) in der Dokumentation zur Sprache.

Dem quellzeichensatz, die Sie angeben, muss die 7-Bit-ASCII-Zeichen, die dieselben Codepunkte in Ihre Zeichensatz zugeordnet sind, oder vielen Kompilierungsfehlern wahrscheinlich führen. Ihre quellzeichensatz muss auch in den erweiterten Unicode-Zeichensatz Sicherheitsrichtlinienverwendung von UTF-8 für Zuordnung geeignete sein. Zeichen, die nicht in UTF-8 Sicherheitsrichtlinienverwendung sind, werden durch eine implementierungsspezifische Ersatz dargestellt. Der Microsoft-Compiler verwendet ein Fragezeichen nach diesen Zeichen.

Wenn Sie sowohl die Quell- und ausführungszeichensatz in UTF-8 festlegen möchten, können Sie mithilfe der **/utf-8** Compileroption als Kurzform. Dies ist äquivalent zum Angeben von **/source-Charset:utf-8 /execution-Charset:utf-8** in der Befehlszeile. Diese Optionen auch ermöglicht die **/Validate-CharSet** standardmäßig die Option.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Erweitern Sie die **Konfigurationseigenschaften**, **C/C++-**, **Befehlszeile** Ordner.

1. In **zusätzliche Optionen**, Hinzufügen der **/Source-CharSet** aus, und geben Sie Ihre bevorzugten Codierung.

1. Klicken Sie auf **OK**, um die Änderungen zu speichern.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
[/ Execution-CharSet (Ausführungszeichensatz festlegen)](execution-charset-set-execution-character-set.md)<br/>
[/utf-8 (Quelle und ausführbare Zeichensätze auf UTF-8 festlegen)](utf-8-set-source-and-executable-character-sets-to-utf-8.md)<br/>
[/validate-charset (Auf kompatible Zeichen überprüfen)](validate-charset-validate-for-compatible-characters.md)
