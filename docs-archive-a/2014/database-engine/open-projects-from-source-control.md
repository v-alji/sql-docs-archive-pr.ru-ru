---
title: Открыть проекты из системы управления версиями | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], opening
- opening projects
ms.assetid: 942f93a3-e264-4ec4-ba72-a28e0509a527
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 944b121516e3782e35e213e165405b0ecceb7456
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667870"
---
# <a name="open-projects-from-source-control"></a><span data-ttu-id="302b5-102">Открытие проекта из системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="302b5-102">Open Projects from Source Control</span></span>
  <span data-ttu-id="302b5-103">Для открытия проектов непосредственно из системы управления версиями следует использовать среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="302b5-103">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to open projects directly from source control.</span></span> <span data-ttu-id="302b5-104">В этом случае среда [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] извлекает последнюю версию проекта и копирует ее на локальный диск.</span><span class="sxs-lookup"><span data-stu-id="302b5-104">When you do this, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] retrieves the latest version of the project and copies it to your local disk.</span></span> <span data-ttu-id="302b5-105">Среда [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] при этом автоматически создает решение для проекта.</span><span class="sxs-lookup"><span data-stu-id="302b5-105">The [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment also creates a solution for the project automatically.</span></span>  
  
 <span data-ttu-id="302b5-106">После открытия проекта из системы управления версиями можно извлекать и изменять файлы проекта.</span><span class="sxs-lookup"><span data-stu-id="302b5-106">After you have opened a project from source control, you can check out and modify the project files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="302b5-107">Приведенную ниже процедуру следует провести только один раз.</span><span class="sxs-lookup"><span data-stu-id="302b5-107">The following procedure should only be used once.</span></span> <span data-ttu-id="302b5-108">После этого следует открыть проект, как и любой другой проект (щелкнув **файл**, **Открыть**, а затем **проект**).</span><span class="sxs-lookup"><span data-stu-id="302b5-108">Thereafter, you should open the project like any other project (by clicking **File**, **Open**, and then **Project**).</span></span>  
  
### <a name="to-open-a-project-from-source-control"></a><span data-ttu-id="302b5-109">Открытие файла из системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="302b5-109">To open a project from source control</span></span>  
  
1.  <span data-ttu-id="302b5-110">В меню **файл** укажите пункт **система управления версиями**и выберите команду **Открыть из системы управления версиями**.</span><span class="sxs-lookup"><span data-stu-id="302b5-110">On the **File** menu, point to **Source Control**, and click **Open From Source Control**.</span></span>  
  
2.  <span data-ttu-id="302b5-111">Если будет выведено приглашение, войдите в [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="302b5-111">If prompted, log on to [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span></span>  
  
3.  <span data-ttu-id="302b5-112">В диалоговом окне **Создание локального проекта из SourceSafe** откройте папку, содержащую проект, который нужно открыть.</span><span class="sxs-lookup"><span data-stu-id="302b5-112">In the **Create local project from SourceSafe** dialog box, open the folder that contains the project to open.</span></span>  
  
4.  <span data-ttu-id="302b5-113">Диалоговое окно **Создание нового проекта в папке** изменится, чтобы указать локальный каталог, в котором будет создан проект.</span><span class="sxs-lookup"><span data-stu-id="302b5-113">The **Create a new project in the folder** box changes to identify the local directory in which the project will be created.</span></span> <span data-ttu-id="302b5-114">Если вы хотите поместить проект в другой каталог, введите путь к каталогу или нажмите кнопку **Обзор** , чтобы найти каталог на локальном диске.</span><span class="sxs-lookup"><span data-stu-id="302b5-114">If you want to place the project in a different directory, type the path to the directory or use the **Browse** button to locate the directory on your local disk.</span></span>  
  
5.  <span data-ttu-id="302b5-115">Убедитесь, что в **поле создать новый проект в папке**отображается правильная папка, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="302b5-115">In the **Create a new project in the folder box**, verify that the correct folder is displayed, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="302b5-116">В диалоговом окне **Открытие решения** выберите проект, который необходимо открыть, и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="302b5-116">In the **Open Solution** dialog box, select the project you want to open, and click **Open**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="302b5-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="302b5-117">See Also</span></span>  
 <span data-ttu-id="302b5-118">[Открытие решений и проектов из системы управления версиями](../../2014/database-engine/open-solutions-and-projects-from-source-control.md) </span><span class="sxs-lookup"><span data-stu-id="302b5-118">[Open Solutions and Projects from Source Control](../../2014/database-engine/open-solutions-and-projects-from-source-control.md) </span></span>  
 [<span data-ttu-id="302b5-119">Открытие решений из системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="302b5-119">Open Solutions from Source Control</span></span>](../../2014/database-engine/open-solutions-from-source-control.md)  
  
  
