---
title: Verwaltete Ressourcen (Eigenschaftenseite)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCManagedResourceCompilerTool.ResourceFileName
- VC.Project.VCManagedResourceCompilerTool.OutputFileName
- VC.Project.VCManagedResourceCompilerTool.DefaultLocalizedResources
helpviewer_keywords:
- Managed Resources property page
ms.assetid: 80b80384-ee55-494d-9f0e-907bb98cfc19
ms.openlocfilehash: 394aac779fceb4d9d5918e4a5ad36eee8be896ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321461"
---
# <a name="managed-resources-property-page"></a>Verwaltete Ressourcen (Eigenschaftenseite)

Aktiviert Einstellungen für den Ressourcencompiler.

Die Eigenschaftenseite **Verwaltete Ressourcen** enthält die folgenden Eigenschaften:

- **Logischer Ressourcenname**

   Gibt den *logischen Namen* der generierten RESOURCES-Zwischendatei an. Der logische Name ist der Name, der zum Laden der Ressource verwendet wird. Wenn kein logischer Name angegeben wird, wird der Dateiname der Ressourcendatei (RESX) als logischer Name verwendet.

- **Name der Ausgabedatei**

   Gibt den Namen der endgültigen Ausgabedatei an, zu der diese Ressourcendatei (RESX) beiträgt.

- **Standardmäßig lokalisierte Ressourcen**

   Gibt an, ob die angegebene RESX-Datei zu den Standardressourcen oder einer Satelliten-DLL beiträgt.

Informationen zum Zugreifen auf die **verwaltete Ressourcen** auf der Seite finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

## <a name="see-also"></a>Siehe auch

[Verwenden des Ressourcencompilers (RC-Befehlszeile)](/windows/desktop/menurc/using-rc-the-rc-command-line-)<br>
[Referenz für C++-Projekt Seite](property-pages-visual-cpp.md)<br>
[/ASSEMBLYRESOURCE (Verwaltete Ressource einbetten)](assemblyresource-embed-a-managed-resource.md)
