---
title: Открыть решения из системы управления версиями | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- opening solutions
- solutions [SQL Server Management Studio], opening
ms.assetid: a96a1f0d-0183-4587-a3b0-4598309cbdd2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 808a4851bcc1f51690b2ba924a859bcccf9a6adb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667868"
---
# <a name="open-solutions-from-source-control"></a><span data-ttu-id="ea8a8-102">Открытие решений из системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="ea8a8-102">Open Solutions from Source Control</span></span>
  <span data-ttu-id="ea8a8-103">Среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] можно использовать для открытия решений непосредственно из системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="ea8a8-103">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to open solutions directly from source control.</span></span> <span data-ttu-id="ea8a8-104">В этом случае среда Studio создает копию последней версии файлов решения в указанном месте.</span><span class="sxs-lookup"><span data-stu-id="ea8a8-104">When you do this, the Studio environment creates a copy of the latest version of the solution files at the location you specify.</span></span>  
  
 <span data-ttu-id="ea8a8-105">Если копии решения на локальном диске не существует, то, прежде чем использовать среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] для извлечения решения или получения его файлов, следует открыть проект из системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="ea8a8-105">If a local copy of the solution does not exist on your local disk, you must open the project from source control before you can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to check out the solution or retrieve solution files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea8a8-106">Если локальная копия решения, открываемого из системы управления версиями, уже существует, следует подтвердить ее перезапись.</span><span class="sxs-lookup"><span data-stu-id="ea8a8-106">If you already have a local copy of the solution you are opening from source control, you are prompted to overwrite the local copy.</span></span>  
  
### <a name="to-open-a-solution-from-source-control"></a><span data-ttu-id="ea8a8-107">Открытие решения из системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="ea8a8-107">To open a solution from source control</span></span>  
  
1.  <span data-ttu-id="ea8a8-108">В меню **файл** укажите пункт **система управления версиями**и выберите команду **Открыть из системы управления версиями**.</span><span class="sxs-lookup"><span data-stu-id="ea8a8-108">On the **File** menu, point to **Source Control**, and click **Open From Source Control**.</span></span>  
  
2.  <span data-ttu-id="ea8a8-109">Если будет выведено приглашение, войдите в [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="ea8a8-109">If prompted, log on to [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span></span>  
  
3.  <span data-ttu-id="ea8a8-110">В диалоговом окне **Создание локального проекта из SourceSafe** выберите папку, содержащую решение, которое необходимо открыть, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ea8a8-110">In the **Create local project from SourceSafe** dialog box, select the folder that contains the solution you want to open, and click **OK**.</span></span>  
  
4.  <span data-ttu-id="ea8a8-111">Если Рабочая папка для решения уже существует на локальном диске, диалоговое окно **Создание нового проекта в папке** изменится и определит локальный каталог.</span><span class="sxs-lookup"><span data-stu-id="ea8a8-111">If a working folder for the solution already exists on your local disk drive, the **Create a new project in the folder** box changes to identify the local directory.</span></span> <span data-ttu-id="ea8a8-112">Если для решения не существует рабочей папки, можно ввести вручную или выбрать имя каталога, в котором будет открыто решение.</span><span class="sxs-lookup"><span data-stu-id="ea8a8-112">If no working folder for the solution exists, you can type or browse to the local directory in which the solution should be opened.</span></span>  
  
5.  <span data-ttu-id="ea8a8-113">В диалоговом окне **Открытие решения** выберите файл решения и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ea8a8-113">In the **Open Solution** dialog box, select the solution file, and click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea8a8-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="ea8a8-114">See Also</span></span>  
 [<span data-ttu-id="ea8a8-115">Открытие проекта из системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="ea8a8-115">Open Projects from Source Control</span></span>](../../2014/database-engine/open-projects-from-source-control.md)  
  
  
