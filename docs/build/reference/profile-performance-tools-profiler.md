---
title: /PROFILE (Leistungstools-Profiler)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Profile
helpviewer_keywords:
- -PROFILE linker option
- /PROFILE linker option
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
ms.openlocfilehash: 23cbccba9a8ec839252d553cc5cbafd37e66bbf9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320200"
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE (Leistungstools-Profiler)

Erstellt eine Ausgabedatei, die mit dem Leistungstoolprofiler verwendet werden kann.

## <a name="syntax"></a>Syntax

```
/PROFILE
```

## <a name="remarks"></a>Hinweise

/ PROFILE impliziert die folgenden Optionen des Linkers:

- [/OPT:REF](opt-optimizations.md)

- /OPT:NOICF

- [/INCREMENTAL:NO](incremental-link-incrementally.md)

- [/FIXED:NO](fixed-fixed-base-address.md)

/ PROFILE bewirkt, dass der Linker ein Verschiebungsabschnitt im Programmimage generiert.  Umsetzungsabschnitt kann der Profiler die Programm-Images zum Abrufen von Profildaten zu transformieren.

**/ PROFILE** ist nur in Enterprise (Entwicklung im Team)-Versionen verfügbar.  Weitere Informationen zu PREfast finden Sie unter [Codeanalyse für C/C++-Übersicht](/visualstudio/code-quality/code-analysis-for-c-cpp-overview).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Erweitern Sie die **Linker** Knoten.

1. Wählen Sie die **erweitert** Eigenschaftenseite.

1. Ändern der **Profil** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>.

### <a name="to-set-this-linker-option-within-visual-studio-cmake-project"></a>Diese Linkeroption in Visual Studio-CMake-Projekts festgelegt.

**CMake** Projekt verfügt nicht über eine **Eigenschaftenseiten**, die Optionen des Linkers können festgelegt werden durch Ändern von der Datei "cmakelists.txt".

1. Öffnen Sie die Datei "cmakelists.txt" im Stammverzeichnis Projekts an.

1. Fügen Sie folgenden Code hinzu. Weitere Informationen finden Sie unter [CMake-Verweise](https://cmake.org/cmake/help/v3.0/command/set_target_properties.html)

1. Erstellen Sie die Projektmappe neu.

```
SET_TARGET_PROPERTIES(${PROJECT_NAME} PROPERTIES LINK_FLAGS "/PROFILE")
```

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)

