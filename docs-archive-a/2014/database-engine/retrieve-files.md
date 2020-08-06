---
title: Извлечение файлов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- version control services [SQL Server], file retrieval
- file retrieval [SQL Server]
- retrieving files
ms.assetid: 37b74426-e262-43b2-a81f-79b1fd1a36ec
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ebced9ea69f304344893289140687cd6d511e923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667376"
---
# <a name="retrieve-files"></a><span data-ttu-id="860da-102">Получение файлов</span><span class="sxs-lookup"><span data-stu-id="860da-102">Retrieve Files</span></span>
  <span data-ttu-id="860da-103">После открытия проекта, контролируемого системой управления версиями, среда [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] позволяет загрузить локальную копию файлов проекта из хранилища системы управления версиями в локальный каталог проекта.</span><span class="sxs-lookup"><span data-stu-id="860da-103">After you have opened a source-controlled project, you can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to retrieve local copies of project files from the source control store to the local directory in which the project resides.</span></span>  
  
 <span data-ttu-id="860da-104">Встроенную систему управления версиями можно использовать для получения файлов следующими способами.</span><span class="sxs-lookup"><span data-stu-id="860da-104">You can use integrated source control to retrieve files in the following ways:</span></span>  
  
-   <span data-ttu-id="860da-105">**Получить последнюю версию (recursive)** команду</span><span class="sxs-lookup"><span data-stu-id="860da-105">**Get Latest Version (Recursive)** command</span></span>  
  
     <span data-ttu-id="860da-106">Получение последней возвращенной версии выбранных файлов.</span><span class="sxs-lookup"><span data-stu-id="860da-106">Retrieves the latest checked in version of the selected files.</span></span> <span data-ttu-id="860da-107">Если выбрано решение или проект, по этой команде можно получить последнюю версию всех файлов решения или проекта.</span><span class="sxs-lookup"><span data-stu-id="860da-107">If a solution or project is selected, this command retrieves the latest version of all solution and project files.</span></span>  
  
-   <span data-ttu-id="860da-108">**Get** , команда</span><span class="sxs-lookup"><span data-stu-id="860da-108">**Get** command</span></span>  
  
     <span data-ttu-id="860da-109">Отображает диалоговое окно **Получение** , которое можно использовать для получения последней версии выбранного файла или для получения подмножества файлов в выбранном решении или проекте.</span><span class="sxs-lookup"><span data-stu-id="860da-109">Displays the **Get** dialog box, which you can use to retrieve the latest version of a selected file, or to retrieve a subset of the files in the selected solution or project.</span></span>  
  
### <a name="to-retrieve-the-latest-version-of-all-the-files-in-a-project"></a><span data-ttu-id="860da-110">Получение последней версии всех файлов проекта</span><span class="sxs-lookup"><span data-stu-id="860da-110">To retrieve the latest version of all the files in a project</span></span>  
  
1.  <span data-ttu-id="860da-111">Выберите проект в Обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="860da-111">In Solution Explorer, select the project.</span></span>  
  
2.  <span data-ttu-id="860da-112">В меню **файл** укажите пункт **система управления версиями**, а затем выберите пункт **получить последнюю версию (рекурсивно)**.</span><span class="sxs-lookup"><span data-stu-id="860da-112">On the **File** menu, point to **Source Control**, and then click **Get Latest Version (Recursive)**.</span></span>  
  
 <span data-ttu-id="860da-113">Последние версии файлов в проекте извлекаются в расположение проекта на локальном диске.</span><span class="sxs-lookup"><span data-stu-id="860da-113">The most recent versions of the files in the project are retrieved to the project location on your local disk.</span></span>  
  
#### <a name="to-retrieve-only-certain-files-in-a-project"></a><span data-ttu-id="860da-114">Получение отдельных файлов проекта</span><span class="sxs-lookup"><span data-stu-id="860da-114">To retrieve only certain files in a project</span></span>  
  
1.  <span data-ttu-id="860da-115">В обозревателе решений выберите элемент, который необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="860da-115">In Solution Explorer, select the item you want to retrieve.</span></span>  
  
2.  <span data-ttu-id="860da-116">В меню **файл** выберите пункт **система управления версиями**, а затем нажмите кнопку **получить**.</span><span class="sxs-lookup"><span data-stu-id="860da-116">On the **File** menu, point to **Source Control**, and then click **Get**.</span></span>  
  
3.  <span data-ttu-id="860da-117">В диалоговом окне **Получение** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="860da-117">In the **Get** dialog box, click **OK**.</span></span> <span data-ttu-id="860da-118">Если решение или проект выбрано в обозревателе решений, можно снять флажки, расположенные рядом с элементами, которые не нужно получать.</span><span class="sxs-lookup"><span data-stu-id="860da-118">Alternatively, if you selected a solution or project in Solution Explorer, clear the check boxes that appear next to the items you do not want to retrieve.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="860da-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="860da-119">See Also</span></span>  
 <span data-ttu-id="860da-120">[Диалоговое окно «Получение &#40;системы управления версиями»&#41;](../../2014/database-engine/get-dialog-box-source-control.md) </span><span class="sxs-lookup"><span data-stu-id="860da-120">[Get Dialog Box &#40;Source Control&#41;](../../2014/database-engine/get-dialog-box-source-control.md) </span></span>  
 <span data-ttu-id="860da-121">[Задание и получение сведений о версии](../../2014/database-engine/set-and-retrieve-version-information.md) </span><span class="sxs-lookup"><span data-stu-id="860da-121">[Set and Retrieve Version Information](../../2014/database-engine/set-and-retrieve-version-information.md) </span></span>  
 <span data-ttu-id="860da-122">[Просмотр журнала проекта](../../2014/database-engine/view-project-history.md) </span><span class="sxs-lookup"><span data-stu-id="860da-122">[View Project History](../../2014/database-engine/view-project-history.md) </span></span>  
 [<span data-ttu-id="860da-123">Просмотр состояния файла</span><span class="sxs-lookup"><span data-stu-id="860da-123">View File Status</span></span>](../../2014/database-engine/view-file-status.md)  
  
  
