---
title: Projekt- und Projektmappendateien
ms.date: 05/06/2019
helpviewer_keywords:
- project files [C++]
- file types [C++], makefiles
- .sdf, browsing database file
- Makefile projects
- browsing database file, .sdf
- file types [C++], project files
ms.assetid: 5823b954-36cf-42d3-8fd5-25bab3ef63d9
ms.openlocfilehash: 37bfd1a6db2087e97ab76d3d06ed6f56e59b96e3
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707418"
---
# <a name="project-and-solution-files"></a>Projekt- und Projektmappendateien

Die folgenden Dateien werden erstellt, wenn Sie ein Projekt in Visual Studio erstellen. Sie werden verwendet, um die Projektdateien in der Projektmappe zu verwalten.

|Dateiname|Speicherort für das Verzeichnis|Speicherort für den Projektmappen-Explorer|Beschreibung|
|--------------|------------------------|--------------------------------|-----------------|
|*Solname*.sln|*Projname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die *Projektmappendatei*. Es werden alle Elemente eines Projekts oder mehrerer Projekte in einer einzigen Projektmappe organisiert.|
|*Projname*.suo|*Projname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die Datei mit den *Projektmappenoptionen*. Darin werden die Anpassungen für die Projektmappe gespeichert, damit jedes Mal, wenn Sie ein Projekt oder eine Datei in der Projektmappe öffnen, die gewünschte Darstellung und das gewünschte Verhalten vorhanden ist.|
|*Projname*.vcxproj|*Projname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die *Projektdatei*. Die für das Projekt spezifischen Informationen werden darin gespeichert. (In früheren Versionen hieß diese Datei *Projname*.vcproj oder *Projname*.dsp.) Ein Beispiel für eine C++-Projektdatei (.vcxproj) finden Sie unter [Project Files (Projektdateien)](project-files.md).|
|*Projname*.vcxitems|*Projname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die *Projektdatei mit freigegebenen Elementen*. Das Projekt wird nicht erstellt.  Stattdessen kann von einem anderen C++-Projekt auf das Projekt verwiesen werden, und die darin enthaltenen Dateien werden Bestandteil des Buildprozesses des verweisenden Projekts. Dies kann zum Freigeben von allgemeinem Code für plattformübergreifende C++-Projekte verwendet werden.|
|*Projname*.sdf|*Projname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die Datei zum *Durchsuchen der Datenbank*. Sie unterstützt Such-und Navigationsfeatures, wie z.B. **Gehe zu Definition**, **Alle Verweise suchen** und **Klassenansicht**. Sie wird durch die Analyse der Headerdateien generiert.|
|*Projname*.vcxproj.filters|*Projname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die *Filterdatei*. Sie gibt an, wo eine Datei, die der Projektmappe hinzugefügt wird, abgelegt werden soll. Zum Beispiel wird eine H-Datei im Knoten **Headerdateien** abgelegt.|
|*Projname*.vcxproj.user|*Projname*|Wird im Projektmappen-Explorer nicht angezeigt.|Die *Migrationsbenutzerdatei*. Nachdem ein Projekt von Visual Studio 2008 migriert wurde, enthält diese Datei Informationen, die aus einer beliebigen .vsprops-Datei konvertiert wurden.|
|*Projname*.idl|*Projname*|Quelle|(Projektspezifisch) Enthält den Interface Description Language (IDL)-Quellcode für eine Steuerelement-Typbibliothek. Diese Datei wird von Visual C++ verwendet, um eine Typbibliothek zu generieren. Mithilfe der generierten Bibliothek wird die Schnittstelle des Steuerelements anderen Automatisierungsclients zur Verfügung gestellt. Weitere Informationen finden Sie im Windows SDK unter [Interface Definition (IDL) File (Schnittstellendefinitionsdatei)](/windows/desktop/Rpc/the-interface-definition-language-idl-file).|
|Readme.txt|*Projname*|Projekt|Die *Infodatei*. Sie wird vom Anwendungs-Assistenten generiert und beschreibt die Dateien in einem Projekt.|

## <a name="see-also"></a>Siehe auch

[Für Visual Studio C++-Projekte erstellte Dateitypen](file-types-created-for-visual-cpp-projects.md)
