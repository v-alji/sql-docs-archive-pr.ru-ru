---
title: Изменение секции DirectQuery (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f9df1e66-dd23-41b4-95eb-af110d10eda4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 43d14785f72d9bfe6406e2b81d3f1b97e9b7cc2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657421"
---
# <a name="change-the-directquery-partition-ssas-tabular"></a><span data-ttu-id="6840e-102">Изменение секции DirectQuery (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="6840e-102">Change the DirectQuery Partition (SSAS Tabular)</span></span>
  <span data-ttu-id="6840e-103">Поскольку только одну секцию в таблице можно определить как секцию DirectQuery, службы Analysis Services по умолчанию используют первую секцию, созданную в таблице.</span><span class="sxs-lookup"><span data-stu-id="6840e-103">Because only one partition in a table can be designated as the DirectQuery partition, by default, Analysis Services uses the first partition that was created in the table.</span></span> <span data-ttu-id="6840e-104">При создании проекта модели секцию DirectQuery можно изменять с помощью диалогового окна «Диспетчер секций» в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6840e-104">During model project authoring, you can change the DirectQuery partition by using the Partition Manager dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="6840e-105">Для развернутых моделей изменить секцию DirectQuery можно с помощью среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6840e-105">For deployed models, you can change the DirectQuery partition by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
### <a name="change-the-directquery-partition-for-a-tabular-model-project"></a><span data-ttu-id="6840e-106">Изменение секции DirectQuery для проекта табличной модели</span><span class="sxs-lookup"><span data-stu-id="6840e-106">Change the DirectQuery partition for a tabular model project</span></span>  
  
1.  <span data-ttu-id="6840e-107">В конструкторе моделей в среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]щелкните таблицу (вкладку), содержащую секционированную таблицу.</span><span class="sxs-lookup"><span data-stu-id="6840e-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], in the model designer, click on the table (tab) that contains the partitioned table.</span></span>  
  
2.  <span data-ttu-id="6840e-108">В меню **Таблица** выберите **Секции**.</span><span class="sxs-lookup"><span data-stu-id="6840e-108">Click on the **Table** menu, and then click **Partitions**.</span></span>  
  
3.  <span data-ttu-id="6840e-109">В **диспетчере секций**секцией является текущая секция DirectQuery, имя которой содержит префикс **(DirectQuery)** .</span><span class="sxs-lookup"><span data-stu-id="6840e-109">In **Partition Manager**, the partition that is the current Direct Query partition in indicated by the prefix **(DirectQuery)** on the partition name.</span></span>  
  
     <span data-ttu-id="6840e-110">Выберите другую секцию в списке **Секции** , затем выберите **Установить в качестве DirectQuery**.</span><span class="sxs-lookup"><span data-stu-id="6840e-110">Select a different partition from the **Partitions** list, and then click **Set as DirectQuery**.</span></span> <span data-ttu-id="6840e-111">Кнопка **Установить в качестве DirectQuery** неактивна, если выбрана текущая секция DirectQuery, и не отображается, если в модели не поддерживается режим прямых запросов.</span><span class="sxs-lookup"><span data-stu-id="6840e-111">The **Set as DirectQuery** button is not enabled when the current DirectQuery partition is selected, and is not visible if the model has not been enabled for Direct Query mode.</span></span>  
  
4.  <span data-ttu-id="6840e-112">При необходимости измените параметры обработки и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6840e-112">If necessary, change the processing options, and then click **OK**.</span></span>  
  
### <a name="change-the-directquery-partition-for-a-deployed-tabular-model"></a><span data-ttu-id="6840e-113">Изменение секции DirectQuery для развернутой табличной модели</span><span class="sxs-lookup"><span data-stu-id="6840e-113">Change the DirectQuery partition for a deployed tabular model</span></span>  
  
1.  <span data-ttu-id="6840e-114">В [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]откройте шаблон базы данных в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="6840e-114">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the model database in Object Explorer.</span></span>  
  
2.  <span data-ttu-id="6840e-115">Разверните узел **Таблицы** , щелкните правой кнопкой мыши секционированную таблицу и выберите команду **Секции**.</span><span class="sxs-lookup"><span data-stu-id="6840e-115">Expand the **Tables** node, then right-click the partitioned table, and then select **Partitions**.</span></span>  
  
     <span data-ttu-id="6840e-116">Имя секции, определенной для использования в режиме DirectQuery, имеет префикс (DirectQuery).</span><span class="sxs-lookup"><span data-stu-id="6840e-116">The partition that is designated for use with DirectQuery mode has the prefix (DirectQuery) on the partition name.</span></span>  
  
3.  <span data-ttu-id="6840e-117">Чтобы перейти к другой секции, щелкните значок **Прямой запрос** на панели инструментов, чтобы открыть диалоговое окно **Настройка секции DirectQuery** .</span><span class="sxs-lookup"><span data-stu-id="6840e-117">To change to a different partition, click the **Direct Query** toolbar icon to open the **Set DirectQuery Partition** dialog box.</span></span> <span data-ttu-id="6840e-118">Значок панели инструментов DirectQuery недоступен в моделях, не поддерживающих прямые запросы.</span><span class="sxs-lookup"><span data-stu-id="6840e-118">The DirectQuery toolbar icon is not available on models that have not been enabled for Direct Query.</span></span>  
  
4.  <span data-ttu-id="6840e-119">Выберите другую секцию в раскрывающемся списке **Имя секции** и при необходимости измените параметры обработки.</span><span class="sxs-lookup"><span data-stu-id="6840e-119">Choose a different partition from the **Partition Name** dropdown list, and then change processing options on the partition if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6840e-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="6840e-120">See Also</span></span>  
 [<span data-ttu-id="6840e-121">Секции (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="6840e-121">Partitions &#40;SSAS Tabular&#41;</span></span>](tabular-models/partitions-ssas-tabular.md)  
  
  
