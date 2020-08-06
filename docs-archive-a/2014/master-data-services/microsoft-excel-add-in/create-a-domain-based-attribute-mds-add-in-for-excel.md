---
title: Создание атрибута на основе домена (надстройка MDS для Excel) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 7b3e30dc-8f41-4a5d-8009-ae5a4426a64b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bda0c7f63ad380aaea5d980d2e729822ec9a3d22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654387"
---
# <a name="create-a-domain-based-attribute-mds-add-in-for-excel"></a><span data-ttu-id="7de9b-102">Создание атрибута на основе домена (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="7de9b-102">Create a Domain-based Attribute (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="7de9b-103">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]администраторы могут создать атрибут на основе домена, чтобы ограничить значения в столбце определенным набором значений.</span><span class="sxs-lookup"><span data-stu-id="7de9b-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], administrators can create a domain-based attribute when they want to constrain the values in a column to a specific set of values.</span></span>  
  
 <span data-ttu-id="7de9b-104">Значения могут уже находиться на листе или могут браться из имеющейся сущности.</span><span class="sxs-lookup"><span data-stu-id="7de9b-104">The values can already be in the worksheet or they can come from an existing entity.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7de9b-105"> Если пользователь вводит значение в столбце с ограничением, а не выбирает его из списка, при публикации в столбце **$InputStatus$** отображаются ошибки.</span><span class="sxs-lookup"><span data-stu-id="7de9b-105">If users type a value in the constrained column, rather than selecting from the list, errors are displayed in the **$InputStatus$** column when they publish.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7de9b-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="7de9b-106">Prerequisites</span></span>  
 <span data-ttu-id="7de9b-107">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="7de9b-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="7de9b-108">необходимо иметь разрешение на доступ к функциональным областям **Администрирование системы** и **Обозреватель** ;</span><span class="sxs-lookup"><span data-stu-id="7de9b-108">You must have permission to access the **System Administration** and **Explorer** functional areas.</span></span>  
  
-   <span data-ttu-id="7de9b-109">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="7de9b-109">You must be a model administrator.</span></span> <span data-ttu-id="7de9b-110">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7de9b-110">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="7de9b-111">Модель и сущность должны быть созданы ранее.</span><span class="sxs-lookup"><span data-stu-id="7de9b-111">The model and entity must already exist.</span></span>  
  
### <a name="to-perform-this-procedure"></a><span data-ttu-id="7de9b-112">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="7de9b-112">To perform this procedure:</span></span>  
  
1.  <span data-ttu-id="7de9b-113">В Excel загрузите сущность, содержащую столбец (атрибут), для которого нужно установить ограничение.</span><span class="sxs-lookup"><span data-stu-id="7de9b-113">In Excel, load the entity that contains the column (attribute) you want to constrain.</span></span> <span data-ttu-id="7de9b-114">Дополнительные сведения см. [в статье Загрузка данных из MDS в Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7de9b-114">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
2.  <span data-ttu-id="7de9b-115">Щелкните любую ячейку в столбце, который нужно ограничить.</span><span class="sxs-lookup"><span data-stu-id="7de9b-115">Click any cell in the column you want to constrain.</span></span>  
  
3.  <span data-ttu-id="7de9b-116">В группе **Построить модель** нажмите кнопку **Свойства атрибута**.</span><span class="sxs-lookup"><span data-stu-id="7de9b-116">In the **Build Model** group, click **Attribute Properties**.</span></span>  
  
4.  <span data-ttu-id="7de9b-117">В диалоговом окне **Свойства атрибута** в списке **Тип атрибута** выберите пункт **Ограниченный лист (на основе домена)**.</span><span class="sxs-lookup"><span data-stu-id="7de9b-117">In the **Attribute Properties** dialog box, in the **Attribute type** list, choose **Constrained list (domain-based)**.</span></span>  
  
5.  <span data-ttu-id="7de9b-118">В списке **Заполнить атрибут значениями из** сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="7de9b-118">In the **Populate the attribute with values from** list:</span></span>  
  
    -   <span data-ttu-id="7de9b-119">Чтобы использовать значения из листа, выберите **выбранный столбец**.</span><span class="sxs-lookup"><span data-stu-id="7de9b-119">To use values from the worksheet, choose **the selected column**.</span></span> <span data-ttu-id="7de9b-120">Будут созданы новая сущность и новая промежуточная таблица со значениями из выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="7de9b-120">A new entity and new staging table will be created with the values from the selected column.</span></span>  
  
    -   <span data-ttu-id="7de9b-121">Чтобы использовать значения из имеющейся сущности, выберите имя сущности.</span><span class="sxs-lookup"><span data-stu-id="7de9b-121">To use values from an existing entity, choose the name of the entity.</span></span>  
  
6.  <span data-ttu-id="7de9b-122">Если на предыдущем шаге был указан **выбранный столбец** , в поле **Новое имя сущности** введите имя новой сущности.</span><span class="sxs-lookup"><span data-stu-id="7de9b-122">If you chose **the selected column** in the previous step, in the **New entity name** box, type a name for the new entity.</span></span> <span data-ttu-id="7de9b-123">Оно может совпадать с именем столбца (атрибута).</span><span class="sxs-lookup"><span data-stu-id="7de9b-123">This can be the same as the column (attribute) name.</span></span>  
  
7.  <span data-ttu-id="7de9b-124">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7de9b-124">Click **OK**.</span></span> <span data-ttu-id="7de9b-125">Теперь каждая ячейка в столбце имеет список значений, из которых могут выбирать пользователи.</span><span class="sxs-lookup"><span data-stu-id="7de9b-125">Each cell in the column now has a list of values for users to choose from.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7de9b-126">Next Steps</span><span class="sxs-lookup"><span data-stu-id="7de9b-126">Next Steps</span></span>  
  
-   <span data-ttu-id="7de9b-127">Чтобы удалить или добавить значения в списке с ограничениям, загрузите сущность, на которой основан атрибут.</span><span class="sxs-lookup"><span data-stu-id="7de9b-127">To add and delete values in the constrained list, load the entity that the attribute is based on.</span></span> <span data-ttu-id="7de9b-128">Дополнительные сведения о загрузке сущностей см. в статье [Загрузка данных из MDS в Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7de9b-128">For more information on loading entities, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7de9b-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="7de9b-129">See Also</span></span>  
 <span data-ttu-id="7de9b-130">[Атрибуты на основе домена &#40;Master Data Services&#41;](../domain-based-attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="7de9b-130">[Domain-Based Attributes &#40;Master Data Services&#41;](../domain-based-attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="7de9b-131">[Создание сущности &#40;надстройка MDS для Excel&#41;](create-an-entity-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="7de9b-131">[Create an Entity &#40;MDS Add-in for Excel&#41;](create-an-entity-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="7de9b-132">Построение модели (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="7de9b-132">Building a Model &#40;MDS Add-in for Excel&#41;</span></span>](building-a-model-mds-add-in-for-excel.md)  
  
  
