---
title: Добавление решений в систему управления версиями | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- adding solutions
- solutions [SQL Server Management Studio], adding
ms.assetid: b9e36569-616d-4e47-9140-0978a9bfe923
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 1c72949fd8257332a36af52ab287ed326eed5274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730897"
---
# <a name="add-solutions-to-source-control"></a><span data-ttu-id="bcf11-102">Добавление решений в систему управления версиями</span><span class="sxs-lookup"><span data-stu-id="bcf11-102">Add Solutions to Source Control</span></span>
  <span data-ttu-id="bcf11-103">При добавлении решения в систему управления версиями обычно требуется добавить решение целиком со всеми проектами.</span><span class="sxs-lookup"><span data-stu-id="bcf11-103">When you add a solution to source control, you usually want to add the entire solution and all the projects it contains.</span></span> <span data-ttu-id="bcf11-104">Для добавления решения в систему управления версиями можно использовать среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bcf11-104">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to add a solution to source control.</span></span>  
  
 <span data-ttu-id="bcf11-105">Проект среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] полностью располагается на локальном диске.</span><span class="sxs-lookup"><span data-stu-id="bcf11-105">A [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] project resides completely on your local disk.</span></span> <span data-ttu-id="bcf11-106">Проекты изменяются, хранятся и собираются локально.</span><span class="sxs-lookup"><span data-stu-id="bcf11-106">You edit, save, and build projects locally.</span></span> <span data-ttu-id="bcf11-107">После добавления проекта в систему управления версиями можно использовать команду **извлечь** , чтобы проверить файлы проекта из системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="bcf11-107">After adding the project to source control, you can use the **Check Out** command to check the project's files out of source control.</span></span>  
  
### <a name="to-add-a-solution-to-source-control"></a><span data-ttu-id="bcf11-108">Добавление решения в систему управления версиями</span><span class="sxs-lookup"><span data-stu-id="bcf11-108">To add a solution to source control</span></span>  
  
1.  <span data-ttu-id="bcf11-109">В обозревателе решений выберите решение, которое необходимо добавить.</span><span class="sxs-lookup"><span data-stu-id="bcf11-109">In Solution Explorer, select the solution you want to add.</span></span>  
  
2.  <span data-ttu-id="bcf11-110">В меню **файл** укажите пункт **система управления версиями**, а затем выберите пункт **Добавить решение в систему управления версиями**.</span><span class="sxs-lookup"><span data-stu-id="bcf11-110">On the **File** menu, point to **Source Control**, and then click **Add Solution to Source Control**.</span></span>  
  
3.  <span data-ttu-id="bcf11-111">Если появится окно приглашения, зарегистрируйтесь в системе управления версиями.</span><span class="sxs-lookup"><span data-stu-id="bcf11-111">If prompted, log on to your source control provider.</span></span>  
  
4.  <span data-ttu-id="bcf11-112">Откроется диалоговое окно **Добавление в проект SourceSafe** .</span><span class="sxs-lookup"><span data-stu-id="bcf11-112">The **Add to SourceSafe Project** dialog box appears.</span></span> <span data-ttu-id="bcf11-113">Имя проекта появится в поле **проект** .</span><span class="sxs-lookup"><span data-stu-id="bcf11-113">The name of your project appears in the **Project** box.</span></span>  
  
5.  <span data-ttu-id="bcf11-114">В списке **папки** откройте папку, в которую нужно поместить проект.</span><span class="sxs-lookup"><span data-stu-id="bcf11-114">In the **Folders** list, open the folder where you want to place your project.</span></span> <span data-ttu-id="bcf11-115">Кроме того, можно нажать кнопку **создать** , чтобы создать папку с именем, отображаемым в поле **проект** .</span><span class="sxs-lookup"><span data-stu-id="bcf11-115">Alternatively, you can click **Create** to create a folder with the name displayed in the **Project** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcf11-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="bcf11-116">See Also</span></span>  
 <span data-ttu-id="bcf11-117">[Добавление решений и проектов в систему управления версиями](../../2014/database-engine/add-solutions-and-projects-to-source-control.md) </span><span class="sxs-lookup"><span data-stu-id="bcf11-117">[Add Solutions and Projects to Source Control](../../2014/database-engine/add-solutions-and-projects-to-source-control.md) </span></span>  
 [<span data-ttu-id="bcf11-118">Добавление проектов в систему управления версиями</span><span class="sxs-lookup"><span data-stu-id="bcf11-118">Add Projects to Source Control</span></span>](../../2014/database-engine/add-projects-to-source-control.md)  
  
  
