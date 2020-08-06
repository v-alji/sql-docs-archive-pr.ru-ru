---
title: Добавление проектов в систему управления версиями | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- adding projects
- projects [SQL Server Management Studio], adding
ms.assetid: fd4616b2-a564-4a66-ac53-d1f5cba213c2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0afef4ef91e4d80db7e956d03a95a2ecffe1dc4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656557"
---
# <a name="add-projects-to-source-control"></a><span data-ttu-id="aeef5-102">Добавление проектов в систему управления версиями</span><span class="sxs-lookup"><span data-stu-id="aeef5-102">Add Projects to Source Control</span></span>
  <span data-ttu-id="aeef5-103">Решения среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] могут содержать несколько проектов скриптов.</span><span class="sxs-lookup"><span data-stu-id="aeef5-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] solutions can host multiple script projects.</span></span> <span data-ttu-id="aeef5-104">Способ добавления проекта к системе управления версиями зависит от того, находится ли под управлением системы решение, к которому относится проект.</span><span class="sxs-lookup"><span data-stu-id="aeef5-104">How you add a project to source control depends upon whether the solution to which the project belongs is under source control.</span></span> <span data-ttu-id="aeef5-105">Если решение контролируется системой управления версиями, то возврат решения добавляет проект к системе управления версиями автоматически.</span><span class="sxs-lookup"><span data-stu-id="aeef5-105">If the solution is under source control, checking in the solution automatically adds the project to source control.</span></span> <span data-ttu-id="aeef5-106">Дополнительные сведения о возврате решений см. [в разделе Возврат файлов](../../2014/database-engine/check-in-files.md).</span><span class="sxs-lookup"><span data-stu-id="aeef5-106">For more information about checking in solutions, see [Check In Files](../../2014/database-engine/check-in-files.md).</span></span>  
  
 <span data-ttu-id="aeef5-107">Если решение, к которому относится проект, не находится под управлением системы управления версиями, то можно добавить это решение к системе управления версиями, и она затем автоматически добавит проект данного решения.</span><span class="sxs-lookup"><span data-stu-id="aeef5-107">If the solution that this project belongs to is not under source control, you can add that solution to source control, which then automatically adds the solution's projects.</span></span> <span data-ttu-id="aeef5-108">Дополнительные сведения о добавлении решений в систему управления версиями см. [в разделе Добавление решений в систему управления](../../2014/database-engine/add-solutions-to-source-control.md)версиями.</span><span class="sxs-lookup"><span data-stu-id="aeef5-108">For more information about adding solutions to source control, see [Add Solutions to Source Control](../../2014/database-engine/add-solutions-to-source-control.md).</span></span>  
  
 <span data-ttu-id="aeef5-109">Если не требуется добавлять решение в систему управления версиями, можно воспользоваться командой **Добавить выбор в систему управления версиями** , чтобы добавить проект вручную.</span><span class="sxs-lookup"><span data-stu-id="aeef5-109">If you do not want to add the solution to source control, you can use the **Add Selection to Source Control** command to add the project manually.</span></span>  
  
 <span data-ttu-id="aeef5-110">Объекты базы данных первоначально не защищены поставщиком управления версиями, но можно создать скрипты объектов базы данных и сохранить эти скрипты в системе управления версиями.</span><span class="sxs-lookup"><span data-stu-id="aeef5-110">Database objects are not directly protected by the source control provider, but you can create scripts of database objects and save the scripts under source control.</span></span>  
  
### <a name="to-add-a-project-to-source-control"></a><span data-ttu-id="aeef5-111">Добавление проекта к системе управления версиями</span><span class="sxs-lookup"><span data-stu-id="aeef5-111">To add a project to source control</span></span>  
  
1.  <span data-ttu-id="aeef5-112">В обозревателе решений выберите проект.</span><span class="sxs-lookup"><span data-stu-id="aeef5-112">In Solution Explorer, select a project.</span></span>  
  
2.  <span data-ttu-id="aeef5-113">В меню **файл** укажите пункт **система управления версиями**, а затем выберите команду **Добавить выбранные проекты в систему управления версиями**.</span><span class="sxs-lookup"><span data-stu-id="aeef5-113">On the **File** menu, point to **Source Control**, and then click **Add Selected Projects to Source Control**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="aeef5-114">При использовании команды **Добавить выбранные проекты в систему управления версиями** для добавления проекта, принадлежащего к решению, управляемому исходным кодом, вам будет предложено добавить проект в качестве вложенной папки решения в системе управления версиями или добавить проект в отдельную папку.</span><span class="sxs-lookup"><span data-stu-id="aeef5-114">If you use the **Add Selected Projects to Source Control** command to add a project that belongs to a source-controlled solution, you are prompted whether you want to add the project as a subfolder of the source-controlled solution or to add the project as a separate folder.</span></span>  
  
3.  <span data-ttu-id="aeef5-115">Если появится окно приглашения, зарегистрируйтесь в системе управления версиями.</span><span class="sxs-lookup"><span data-stu-id="aeef5-115">If prompted, log on to your source control provider.</span></span>  
  
4.  <span data-ttu-id="aeef5-116">Откроется диалоговое окно **Добавление в проект SourceSafe** .</span><span class="sxs-lookup"><span data-stu-id="aeef5-116">The **Add to SourceSafe Project** dialog box appears.</span></span> <span data-ttu-id="aeef5-117">Имя проекта появится в поле **проект** .</span><span class="sxs-lookup"><span data-stu-id="aeef5-117">The name of your project appears in the **Project** box.</span></span>  
  
5.  <span data-ttu-id="aeef5-118">В списке **папки** откройте папку, в которую нужно поместить проект.</span><span class="sxs-lookup"><span data-stu-id="aeef5-118">In the **Folders** list, open the folder where you want to place your project.</span></span> <span data-ttu-id="aeef5-119">Кроме того, можно нажать кнопку **создать** , чтобы создать папку с именем, отображаемым в поле **проект** .</span><span class="sxs-lookup"><span data-stu-id="aeef5-119">Alternatively, you can click **Create** to create a folder with the name displayed in the **Project** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeef5-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="aeef5-120">See Also</span></span>  
 [<span data-ttu-id="aeef5-121">Добавление решений и проектов в систему управления версиями</span><span class="sxs-lookup"><span data-stu-id="aeef5-121">Add Solutions and Projects to Source Control</span></span>](../../2014/database-engine/add-solutions-and-projects-to-source-control.md)  
  
  
