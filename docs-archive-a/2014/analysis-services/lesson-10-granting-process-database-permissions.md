---
title: Предоставление разрешений на обработку базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 69ba952e-09ae-49a9-9297-00e32e8e89a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6ada30e3fb509bd1ffd210485ce0e34b7bf86fb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654556"
---
# <a name="granting-process-database-permissions"></a><span data-ttu-id="e37ff-102">Предоставление разрешений на обработку базы данных</span><span class="sxs-lookup"><span data-stu-id="e37ff-102">Granting Process Database Permissions</span></span>
  <span data-ttu-id="e37ff-103">После установки экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]все члены роли администратора сервера [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] в этом экземпляре получают разрешения уровня сервера для выполнения любых задач в пределах этого экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e37ff-103">After you install an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], all members of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server administrator role in that instance have server-wide permissions to perform any task within the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="e37ff-104">По умолчанию другие пользователи не имеют разрешения на администрирование или просмотр объектов данного экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e37ff-104">By default, no other users have any permission to administer or view any objects in the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>

 <span data-ttu-id="e37ff-105">Член роли администратора сервера может предоставлять пользователям административный доступ на уровне сервера, включая их в эту роль.</span><span class="sxs-lookup"><span data-stu-id="e37ff-105">A member of the server administrator role can grant users administrative access on a server-wide basis by making them members of the role.</span></span> <span data-ttu-id="e37ff-106">Член роли администратора сервера имеет ограниченные права, но также может открывать пользователям доступ, предоставляя им ограниченный или полный набор разрешений на администрирование или доступ на уровне базы данных.</span><span class="sxs-lookup"><span data-stu-id="e37ff-106">A member of the server administrator role can also grant users access on a more limited basis by granting them limited or complete administrative or access permissions at the database level.</span></span> <span data-ttu-id="e37ff-107">Ограниченные права на администрирование включают в себя разрешения на обработку или определение чтения на уровне базы данных, куба или измерения.</span><span class="sxs-lookup"><span data-stu-id="e37ff-107">Limited administrative permissions include process or read definition permissions at the database, cube, or dimension level.</span></span>

 <span data-ttu-id="e37ff-108">В задачах этого раздела будет определена роль безопасности «Обработка объектов базы данных», которая предоставляет членам этой роли разрешение на обработку всех объектов базы данных, не предоставляя прав на просмотр данных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="e37ff-108">In the tasks in this topic, you will define a Process Database Objects security role that grants members of the role permission to process all database objects, but no permission to view data within the database.</span></span>

## <a name="defining-a-process-database-objects-security-role"></a><span data-ttu-id="e37ff-109">Определение роли «Обработка объектов базы данных»</span><span class="sxs-lookup"><span data-stu-id="e37ff-109">Defining a Process Database Objects Security Role</span></span>

1.  <span data-ttu-id="e37ff-110">В обозревателе решений щелкните правой кнопкой мыши элемент **Роли** и выберите команду **Создать роль** , чтобы открыть конструктор ролей.</span><span class="sxs-lookup"><span data-stu-id="e37ff-110">In Solution Explorer, right-click **Roles** and then click **New Role** to open the Role Designer.</span></span>

2.  <span data-ttu-id="e37ff-111">Установите флажок **Обработка базы данных** .</span><span class="sxs-lookup"><span data-stu-id="e37ff-111">Click the **Process database** check box.</span></span>

3.  <span data-ttu-id="e37ff-112">В окно свойств измените свойство **Name** для этой новой роли на `Process Database Objects Role` .</span><span class="sxs-lookup"><span data-stu-id="e37ff-112">In the Properties window, change the **Name** property for this new role to `Process Database Objects Role`.</span></span>

     <span data-ttu-id="e37ff-113">![конструктор ролей](../../2014/tutorials/media/l10-security-1.png "конструктор ролей")</span><span class="sxs-lookup"><span data-stu-id="e37ff-113">![Role Designer](../../2014/tutorials/media/l10-security-1.png "Role Designer")</span></span>

4.  <span data-ttu-id="e37ff-114">Перейдите на вкладку **Членство** конструктора ролей и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e37ff-114">Switch to the **Membership** tab of Role Designer and click **Add**.</span></span>

5.  <span data-ttu-id="e37ff-115">Введите учетные записи пользователей домена Windows или группы, которые будут членами этой роли.</span><span class="sxs-lookup"><span data-stu-id="e37ff-115">Enter the accounts of the Windows domain users or groups who will be members of this role.</span></span> <span data-ttu-id="e37ff-116">Щелкните **Проверить имена** , чтобы проверить сведения об учетных записях, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e37ff-116">Click **Check Names** to verify the account information, and then click **OK**.</span></span>

6.  <span data-ttu-id="e37ff-117">Перейдите на вкладку **Кубы** конструктора ролей.</span><span class="sxs-lookup"><span data-stu-id="e37ff-117">Switch to the **Cubes** tab of Role Designer.</span></span>

     <span data-ttu-id="e37ff-118">Обратите внимание, что члены этой роли имеют разрешение на обработку этой базы данных, но не имеют разрешения на доступ к данным в кубе учебника по службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] и не имеют доступа к локальному кубу и детализации, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="e37ff-118">Notice that members of this role have permissions to process this database, but have no permission to access the data in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube and have no local cube/drillthrough access, as shown in the following image.</span></span>

     <span data-ttu-id="e37ff-119">![Вкладка «Кубы» конструктора ролей](../../2014/tutorials/media/l10-security-2.png "Вкладка «Кубы» конструктора ролей")</span><span class="sxs-lookup"><span data-stu-id="e37ff-119">![Cubes tab of Role Designer](../../2014/tutorials/media/l10-security-2.png "Cubes tab of Role Designer")</span></span>

7.  <span data-ttu-id="e37ff-120">Перейдите на вкладку **Измерения** конструктора ролей.</span><span class="sxs-lookup"><span data-stu-id="e37ff-120">Switch to the **Dimensions** tab of Role Designer.</span></span>

     <span data-ttu-id="e37ff-121">Обратите внимание, что члены этой роли имеют разрешения на обработку всех объектов измерения этой базы данных и по умолчанию имеют разрешения на чтение для каждого объекта измерения в базе данных учебника по службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e37ff-121">Notice that members of this role have permissions to process all dimension objects in this database, and, by default, have read permissions to access each dimension object in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial database.</span></span>

8.  <span data-ttu-id="e37ff-122">В меню **Сборка** выберите команду **Развернуть Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="e37ff-122">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

     <span data-ttu-id="e37ff-123">Роль «Обработка объектов базы данных» определена и развернута.</span><span class="sxs-lookup"><span data-stu-id="e37ff-123">You have now successfully defined and deployed the Process Database Objects security role.</span></span> <span data-ttu-id="e37ff-124">После развертывания куба в производственной среде администраторы развернутого куба могут по мере необходимости добавлять пользователей в эту роль, чтобы передавать ответственность за обработку определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="e37ff-124">After a cube is deployed to the production environment, the administrators of the deployed cube can add users to this role as required to delegate processing responsibilities to specific users.</span></span>

> [!NOTE]
>  <span data-ttu-id="e37ff-125">Завершенный проект десятого занятия доступен для загрузки и установки образцов.</span><span class="sxs-lookup"><span data-stu-id="e37ff-125">A completed project for Lesson 10 is available by downloading and installing the samples.</span></span> <span data-ttu-id="e37ff-126">Дополнительные сведения см. [в разделе Установка образцов данных и проектов для учебника по многомерному моделированию Analysis Services](install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="e37ff-126">For more information, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e37ff-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="e37ff-127">See Also</span></span>
 [<span data-ttu-id="e37ff-128">Роли и разрешения (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="e37ff-128">Roles and Permissions &#40;Analysis Services&#41;</span></span>](multidimensional-models/roles-and-permissions-analysis-services.md)


