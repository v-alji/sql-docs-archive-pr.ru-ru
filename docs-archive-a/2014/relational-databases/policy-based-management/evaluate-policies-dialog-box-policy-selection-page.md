---
title: Диалоговое окно "Выполнение политик", страница "Выбор политики" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.runnow.f1
ms.assetid: 20075fbe-0b48-42c8-b747-690f1aa23dcf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f68a1ccc7873b6a05d2641ddaa87e8d5b0e5c6d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729358"
---
# <a name="evaluate-policies-dialog-box-policy-selection-page"></a><span data-ttu-id="84b84-102">Диалоговое окно «Выполнение политик», страница «Выбор политики»</span><span class="sxs-lookup"><span data-stu-id="84b84-102">Evaluate Policies Dialog Box, Policy Selection Page</span></span>
  <span data-ttu-id="84b84-103">Используйте это диалоговое окно для оценки политик управления на основе политик.</span><span class="sxs-lookup"><span data-stu-id="84b84-103">Use this dialog box to evaluate Policy-Based Management policies.</span></span> <span data-ttu-id="84b84-104">При выборе страницы **Результаты оценки** можно применить политики к элементам в наборе целей, которые не соответствуют политикам.</span><span class="sxs-lookup"><span data-stu-id="84b84-104">By selecting the **Evaluation Results** page, you can apply policies to the items in a target set that do not comply with the policies.</span></span>  
  
## <a name="options"></a><span data-ttu-id="84b84-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="84b84-105">Options</span></span>  
 <span data-ttu-id="84b84-106">**Source**</span><span class="sxs-lookup"><span data-stu-id="84b84-106">**Source**</span></span>  
 <span data-ttu-id="84b84-107">Задает источник политик.</span><span class="sxs-lookup"><span data-stu-id="84b84-107">Specifies the source of the policies.</span></span> <span data-ttu-id="84b84-108">Чтобы изменить источник, нажмите кнопку обзора (**...**), чтобы открыть диалоговое окно **Выбор источника** .</span><span class="sxs-lookup"><span data-stu-id="84b84-108">To change the source, click the Browse (**...**) button to open the **Select Source** dialog box.</span></span>  
  
 <span data-ttu-id="84b84-109">**Файлы**</span><span class="sxs-lookup"><span data-stu-id="84b84-109">**Files**</span></span>  
 <span data-ttu-id="84b84-110">Введите путь к файлу, содержащему политику управления на основе политик, или нажмите кнопку обзора (**...**), чтобы выбрать файл.</span><span class="sxs-lookup"><span data-stu-id="84b84-110">Type the path of a file that contains a Policy-Based Management policy, or use the Browse (**...**) button to select the file.</span></span>  
  
 <span data-ttu-id="84b84-111">**Server**</span><span class="sxs-lookup"><span data-stu-id="84b84-111">**Server**</span></span>  
 <span data-ttu-id="84b84-112">Выберите, чтобы подключиться к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , содержащего нужную политику.</span><span class="sxs-lookup"><span data-stu-id="84b84-112">Select to connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that contains the policy that you want.</span></span>  
  
 <span data-ttu-id="84b84-113">**Политики: политика**</span><span class="sxs-lookup"><span data-stu-id="84b84-113">**Policies: Policy**</span></span>  
 <span data-ttu-id="84b84-114">Нажмите, чтобы открыть диалоговое окно для указанной политики.</span><span class="sxs-lookup"><span data-stu-id="84b84-114">Click to open the policy dialog box for the specified policy.</span></span>  
  
 <span data-ttu-id="84b84-115">**Политики: категория**</span><span class="sxs-lookup"><span data-stu-id="84b84-115">**Policies: Category**</span></span>  
 <span data-ttu-id="84b84-116">Категория политики.</span><span class="sxs-lookup"><span data-stu-id="84b84-116">The category of the policy.</span></span> <span data-ttu-id="84b84-117">Поле доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="84b84-117">This box is read-only.</span></span>  
  
 <span data-ttu-id="84b84-118">**Политики: аспект**</span><span class="sxs-lookup"><span data-stu-id="84b84-118">**Policies: Facet**</span></span>  
 <span data-ttu-id="84b84-119">Аспект, реализуемый политикой.</span><span class="sxs-lookup"><span data-stu-id="84b84-119">The facet implemented by the policy.</span></span> <span data-ttu-id="84b84-120">Поле доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="84b84-120">This box is read-only.</span></span>  
  
 <span data-ttu-id="84b84-121">**Давать**</span><span class="sxs-lookup"><span data-stu-id="84b84-121">**Evaluate**</span></span>  
 <span data-ttu-id="84b84-122">Запускает политику в режиме оценки.</span><span class="sxs-lookup"><span data-stu-id="84b84-122">Runs the policy in evaluation mode.</span></span> <span data-ttu-id="84b84-123">Создает отчет о соответствии политике для набора целей, но не изменяет конфигурацию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и не обеспечивает соблюдение политики в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="84b84-123">This generates a compliance report for the target set but does not reconfigure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or enforce future compliance.</span></span>  
  
## <a name="possible-errors"></a><span data-ttu-id="84b84-124">Возможные ошибки</span><span class="sxs-lookup"><span data-stu-id="84b84-124">Possible Errors</span></span>  
  
-   <span data-ttu-id="84b84-125">**Цели не найдены**</span><span class="sxs-lookup"><span data-stu-id="84b84-125">**No targets found**</span></span>  
  
     <span data-ttu-id="84b84-126">Набор целей может быть пустым по любой из следующих причин.</span><span class="sxs-lookup"><span data-stu-id="84b84-126">The target set could be empty due to any of the following reasons:</span></span>  
  
    -   <span data-ttu-id="84b84-127">В экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] нет целей с типом, указанным в политике.</span><span class="sxs-lookup"><span data-stu-id="84b84-127">There are no targets on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] of the type specified by the policy.</span></span>  
  
    -   <span data-ttu-id="84b84-128">Ограничение сервера может исключить экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , содержащий цель.</span><span class="sxs-lookup"><span data-stu-id="84b84-128">The server restriction might exclude the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that contains the target.</span></span>  
  
    -   <span data-ttu-id="84b84-129">Если политика задана для объекта в базе данных (таблицы, представления или пользователя), возможно, база данных не может подписаться на категорию политики.</span><span class="sxs-lookup"><span data-stu-id="84b84-129">If the policy is on an object in a database (for example a table, view, or user) the database might not subscribe to the category of the policy.</span></span>  
  
    -   <span data-ttu-id="84b84-130">Фильтр целевого набора может исключить все цели в данном экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84b84-130">The target-set filter might exclude all targets on this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="84b84-131">Тип целевого сервера отличается от типа сервера, на котором оценивается политика.</span><span class="sxs-lookup"><span data-stu-id="84b84-131">The target server type is different from the server type on which the policy is evaluated.</span></span> <span data-ttu-id="84b84-132">Например, в компоненте [!INCLUDE[ssDE](../../includes/ssde-md.md)]при попытке оценки политики, созданной для служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], будет получен пустой набор целей.</span><span class="sxs-lookup"><span data-stu-id="84b84-132">For example, in the [!INCLUDE[ssDE](../../includes/ssde-md.md)], if you try to evaluate a policy that has been created for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you will receive an empty target set</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84b84-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="84b84-133">See Also</span></span>  
 <span data-ttu-id="84b84-134">[Администрирование серверов с помощью управления на основе политик](administer-servers-by-using-policy-based-management.md) </span><span class="sxs-lookup"><span data-stu-id="84b84-134">[Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md) </span></span>  
 [<span data-ttu-id="84b84-135">Диалоговое окно «Выполнение политик», страница «Результаты выполнения»</span><span class="sxs-lookup"><span data-stu-id="84b84-135">Evaluate Policies Dialog Box, Evaluation Results Page</span></span>](evaluate-policies-dialog-box-evaluation-results-page.md)  
  
  
