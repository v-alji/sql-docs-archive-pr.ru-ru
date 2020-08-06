---
title: Сравнение файлов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- versions [SQL Server], file comparisons
- comparing files
- file comparisons [SQL Server]
ms.assetid: 728811c4-5d7a-4420-abce-f56c5a0994d2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f29bf7098f0c73d0b672e20b973b1347349b31f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665576"
---
# <a name="compare-files"></a><span data-ttu-id="33773-102">Сравнение файлов</span><span class="sxs-lookup"><span data-stu-id="33773-102">Compare Files</span></span>
  <span data-ttu-id="33773-103">Сравнение файлов применяется для выяснения истории изменения файла до текущего состояния.</span><span class="sxs-lookup"><span data-stu-id="33773-103">You can compare files to determine how a file has progressed to its present state.</span></span> <span data-ttu-id="33773-104">Например, если в сборке проекта кода обнаружен дефект после возврата определенной версии исходного файла в систему управления версиями, можно сравнить текущую версию файла с предыдущей.</span><span class="sxs-lookup"><span data-stu-id="33773-104">For example, if you detect a defect in a build of your code project after a particular source file version is checked in, you can compare the current file version to a previous one.</span></span> <span data-ttu-id="33773-105">Это поможет выявить код, вызвавший дефект.</span><span class="sxs-lookup"><span data-stu-id="33773-105">This helps you to pinpoint the code that introduced the defect.</span></span>  
  
 <span data-ttu-id="33773-106">Среда [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] позволяет сравнивать локальную копию проекта или хранилища версий в системе управления источниками, или же два локальных файла.</span><span class="sxs-lookup"><span data-stu-id="33773-106">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to compare a local copy of a project or file to the version stored in source control, or to compare two local files.</span></span> <span data-ttu-id="33773-107">Кроме того, с помощью команды **History** можно сравнить любые две версии в системе управления версиями.</span><span class="sxs-lookup"><span data-stu-id="33773-107">Also, using the **History** command, you can compare any two source-controlled versions.</span></span>  
  
### <a name="to-compare-files"></a><span data-ttu-id="33773-108">Сравнение файлов</span><span class="sxs-lookup"><span data-stu-id="33773-108">To compare files</span></span>  
  
1.  <span data-ttu-id="33773-109">В обозревателе решений выберите проект либо один из его файлов.</span><span class="sxs-lookup"><span data-stu-id="33773-109">In Solution Explorer, select either a project or one of the project files.</span></span>  
  
2.  <span data-ttu-id="33773-110">В меню **файл** выберите пункт **система управления версиями**и нажмите кнопку **сравнить**.</span><span class="sxs-lookup"><span data-stu-id="33773-110">On the **File** menu, point to **Source Control**, and click **Compare**.</span></span>  
  
3.  <span data-ttu-id="33773-111">В диалоговом окне **Параметры различий** выберите соответствующие параметры и нажмите кнопку **отчет**.</span><span class="sxs-lookup"><span data-stu-id="33773-111">In the **Difference Options** dialog box, select the appropriate options, and then click **Report**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33773-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="33773-112">See Also</span></span>  
 <span data-ttu-id="33773-113">[Задание и получение сведений о версии](../../2014/database-engine/set-and-retrieve-version-information.md) </span><span class="sxs-lookup"><span data-stu-id="33773-113">[Set and Retrieve Version Information](../../2014/database-engine/set-and-retrieve-version-information.md) </span></span>  
 <span data-ttu-id="33773-114">[Просмотр истории файлов](../../2014/database-engine/view-file-history.md) </span><span class="sxs-lookup"><span data-stu-id="33773-114">[View File History](../../2014/database-engine/view-file-history.md) </span></span>  
 <span data-ttu-id="33773-115">[Просмотр журнала проекта](../../2014/database-engine/view-project-history.md) </span><span class="sxs-lookup"><span data-stu-id="33773-115">[View Project History](../../2014/database-engine/view-project-history.md) </span></span>  
 <span data-ttu-id="33773-116">[Просмотр состояния файла](../../2014/database-engine/view-file-status.md) </span><span class="sxs-lookup"><span data-stu-id="33773-116">[View File Status](../../2014/database-engine/view-file-status.md) </span></span>  
 [<span data-ttu-id="33773-117">Получение файлов</span><span class="sxs-lookup"><span data-stu-id="33773-117">Retrieve Files</span></span>](../../2014/database-engine/retrieve-files.md)  
  
  
