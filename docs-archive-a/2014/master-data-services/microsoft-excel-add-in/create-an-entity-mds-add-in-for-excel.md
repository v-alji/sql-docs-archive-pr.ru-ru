---
title: Создание сущности (надстройка MDS для Excel) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: d354abb3-88fe-4b40-a374-f6256b84ffae
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 87ad67f7347da87c67afc11590df6775af4cf3d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654385"
---
# <a name="create-an-entity-mds-add-in-for-excel"></a><span data-ttu-id="605e8-102">Создание сущности (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="605e8-102">Create an Entity (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="605e8-103">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]администраторы могут создавать новые сущности для хранения данных.</span><span class="sxs-lookup"><span data-stu-id="605e8-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], administrators can create new entities to store data.</span></span> <span data-ttu-id="605e8-104">При создании сущности необходимо загрузить по крайней мере небольшую выборку данных, которые нужно сохранить.</span><span class="sxs-lookup"><span data-stu-id="605e8-104">When you create an entity you should load at least a sampling of the data you want to store.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="605e8-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="605e8-105">Prerequisites</span></span>  
 <span data-ttu-id="605e8-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="605e8-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="605e8-107">необходимо иметь разрешение на доступ к функциональным областям **Администрирование системы** и **Обозреватель** ;</span><span class="sxs-lookup"><span data-stu-id="605e8-107">You must have permission to access the **System Administration** and **Explorer** functional areas.</span></span>  
  
-   <span data-ttu-id="605e8-108">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="605e8-108">You must be a model administrator.</span></span> <span data-ttu-id="605e8-109">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="605e8-109">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="605e8-110">Должна существовать модель, в которой создается сущность.</span><span class="sxs-lookup"><span data-stu-id="605e8-110">You must have an existing model to create the entity in.</span></span> <span data-ttu-id="605e8-111">Дополнительные сведения см. в разделе [Создание модели (службы Master Data Services)](../create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="605e8-111">For more information, see [Create a Model &#40;Master Data Services&#41;](../create-a-model-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="605e8-112">Убедитесь, что данные соответствуют следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="605e8-112">Ensure that your data meets the following requirements:</span></span>  
  
    -   <span data-ttu-id="605e8-113">в данных должна быть строка заголовка.</span><span class="sxs-lookup"><span data-stu-id="605e8-113">The data should have a header row.</span></span>  
  
    -   <span data-ttu-id="605e8-114">Удобно иметь столбцы **Имя** и **Код** .</span><span class="sxs-lookup"><span data-stu-id="605e8-114">It is helpful to have **Name** and **Code** columns.</span></span> <span data-ttu-id="605e8-115">**Код** — это уникальный идентификатор для каждой строки.</span><span class="sxs-lookup"><span data-stu-id="605e8-115">**Code** is a unique identifier for each row.</span></span>  
  
    -   <span data-ttu-id="605e8-116">Должна быть по крайней мере одна строка данных помимо заголовка.</span><span class="sxs-lookup"><span data-stu-id="605e8-116">You should have at least one row of data other than the header.</span></span> <span data-ttu-id="605e8-117">Необязательно, чтобы значения присутствовали во всех столбцах, но имеющиеся данные должны отражать данные, которые будут храниться в сущности.</span><span class="sxs-lookup"><span data-stu-id="605e8-117">All columns do not need values, but the data should be representative of the data that will be in the entity.</span></span>  
  
    -   <span data-ttu-id="605e8-118">Если имеется столбец, содержащий уникальный идентификатор (в MDS он называется **Код**), убедитесь в том, что значения в нем уникальны.</span><span class="sxs-lookup"><span data-stu-id="605e8-118">If you have a column that contains a unique identifier (known in MDS as **Code**), ensure that the values are unique.</span></span> <span data-ttu-id="605e8-119">Если ни в одном столбце нет идентификаторов, можно создавать их автоматически при создании сущности.</span><span class="sxs-lookup"><span data-stu-id="605e8-119">If no column contains identifiers, you can have them generated automatically when you create the entity.</span></span>  
  
    -   <span data-ttu-id="605e8-120">Убедитесь, что в ячейках нет формул.</span><span class="sxs-lookup"><span data-stu-id="605e8-120">Ensure that no cells contain formulas.</span></span>  
  
    -   <span data-ttu-id="605e8-121">Убедитесь, что в ячейках нет временных значений.</span><span class="sxs-lookup"><span data-stu-id="605e8-121">Ensure that no cells contain time values.</span></span> <span data-ttu-id="605e8-122">В MDS можно сохранять значения даты, но не значения времени.</span><span class="sxs-lookup"><span data-stu-id="605e8-122">Date values can be saved in MDS but time values cannot.</span></span>  
  
### <a name="to-create-an-entity-and-load-data"></a><span data-ttu-id="605e8-123">Создание сущности и загрузка данных</span><span class="sxs-lookup"><span data-stu-id="605e8-123">To create an entity and load data</span></span>  
  
1.  <span data-ttu-id="605e8-124">Откройте или создайте лист Excel, содержащий данные, которые нужно загрузить.</span><span class="sxs-lookup"><span data-stu-id="605e8-124">Open or create an Excel worksheet that contains data you want to load.</span></span>  
  
2.  <span data-ttu-id="605e8-125">Выделите ячейки, которые нужно загрузить в новую сущность.</span><span class="sxs-lookup"><span data-stu-id="605e8-125">Select the cells you want to load into the new entity.</span></span>  
  
3.  <span data-ttu-id="605e8-126">На вкладке **Основные данные** в группе **Построить модель** нажмите кнопку **Создать сущность**.</span><span class="sxs-lookup"><span data-stu-id="605e8-126">On the **Master Data** tab, in the **Build Model** group, click **Create Entity**.</span></span>  
  
4.  <span data-ttu-id="605e8-127">Подключитесь к репозиторию MDS, если появится соответствующий запрос.</span><span class="sxs-lookup"><span data-stu-id="605e8-127">If you are prompted to connect to an MDS repository, connect.</span></span>  
  
5.  <span data-ttu-id="605e8-128">В диалоговом окне **Создание сущности** оставьте диапазон по умолчанию или измените его, чтобы применить к данным, которые нужно загрузить.</span><span class="sxs-lookup"><span data-stu-id="605e8-128">In the **Create Entity** dialog box, leave the default range or change it to apply to the data you want to load.</span></span>  
  
6.  <span data-ttu-id="605e8-129">Не снимайте флажок **Данные содержат заголовки** .</span><span class="sxs-lookup"><span data-stu-id="605e8-129">Do not clear the **My data has headers** check box.</span></span>  
  
7.  <span data-ttu-id="605e8-130">Выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="605e8-130">From the **Model** list, select a model.</span></span>  
  
8.  <span data-ttu-id="605e8-131">Выберите версию из списка **Версия** .</span><span class="sxs-lookup"><span data-stu-id="605e8-131">From the **Version** list, select a version.</span></span>  
  
9. <span data-ttu-id="605e8-132">В поле **Новое имя сущности** введите имя сущности.</span><span class="sxs-lookup"><span data-stu-id="605e8-132">In the **New entity name** box, type a name for the entity.</span></span>  
  
10. <span data-ttu-id="605e8-133">В списке **Код** выберите столбец, который содержит уникальные идентификаторы, или задайте автоматическое создание кодов.</span><span class="sxs-lookup"><span data-stu-id="605e8-133">From the **Code** list, select the column that contains unique identifiers or have codes generated automatically.</span></span>  
  
11. <span data-ttu-id="605e8-134">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="605e8-134">Optional.</span></span> <span data-ttu-id="605e8-135">В списке **Имя** выберите столбец, который содержит имена для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="605e8-135">From the **Name** list, select a column that contains names for each member.</span></span>  
  
12. <span data-ttu-id="605e8-136">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="605e8-136">Click **OK**.</span></span> <span data-ttu-id="605e8-137">После успешного создания сущности отображается строка с новым заголовком, выделяются ячейки, а имя листа изменяется на имя сущности.</span><span class="sxs-lookup"><span data-stu-id="605e8-137">When the entity has been created successfully, a new header row is displayed, the cells are highlighted, and the sheet name is updated to match the entity name.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="605e8-138">Next Steps</span><span class="sxs-lookup"><span data-stu-id="605e8-138">Next Steps</span></span>  
  
-   <span data-ttu-id="605e8-139">Для просмотра возникших ошибок в группе **Публикация и проверка** нажмите кнопку **Показать состояние**.</span><span class="sxs-lookup"><span data-stu-id="605e8-139">To view errors that occurred, in the **Publish and Validate** group, click **Show Status**.</span></span> <span data-ttu-id="605e8-140">Отображаются столбцы ValidationStatus и InputStatus.</span><span class="sxs-lookup"><span data-stu-id="605e8-140">ValidationStatus and InputStatus columns are displayed.</span></span> <span data-ttu-id="605e8-141">Дополнительные сведения см. в разделе [Проверка данных (надстройка MDS для Excel)](validating-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="605e8-141">For more information, see [Validating Data &#40;MDS Add-in for Excel&#41;](validating-data-mds-add-in-for-excel.md).</span></span>  
  
-   <span data-ttu-id="605e8-142">Убедитесь, что созданные атрибуты имеют запланированный тип данных.</span><span class="sxs-lookup"><span data-stu-id="605e8-142">Confirm that the attributes were created as the data type you expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="605e8-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="605e8-143">See Also</span></span>  
 [<span data-ttu-id="605e8-144">Создание атрибута на основе домена (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="605e8-144">Create a Domain-based Attribute &#40;MDS Add-in for Excel&#41;</span></span>](create-a-domain-based-attribute-mds-add-in-for-excel.md)  
  
  
