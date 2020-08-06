---
title: Занятие 9. создание перспектив | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 55b0f0d0-1cdf-4876-9c3d-d0c848be3f5d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 417b6a4d3b16857f48bcc2f39dc8ec4c010a2b10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739008"
---
# <a name="lesson-9-create-perspectives"></a><span data-ttu-id="3061e-102">Урок 9. Создание перспектив</span><span class="sxs-lookup"><span data-stu-id="3061e-102">Lesson 9: Create Perspectives</span></span>
  <span data-ttu-id="3061e-103">На этом занятии будет создана перспектива «Продажи через Интернет».</span><span class="sxs-lookup"><span data-stu-id="3061e-103">In this lesson, you will create an Internet Sales perspective.</span></span> <span data-ttu-id="3061e-104">Перспектива определяет просматриваемое подмножество модели, предоставляющее точки наблюдения, сосредоточенные на определенном объекте, аспекте бизнеса или приложении.</span><span class="sxs-lookup"><span data-stu-id="3061e-104">A perspective defines a viewable subset of a model that provides focused, business-specific, or application-specific viewpoints.</span></span> <span data-ttu-id="3061e-105">Когда пользователь подключается к модели с помощью перспективы, он видит в качестве полей лишь те объекты модели (таблицы, столбцы, меры, иерархии и ключевые показатели эффективности), которые определены в этой перспективе.</span><span class="sxs-lookup"><span data-stu-id="3061e-105">When a user connects to a model using a perspective, they see only those model objects (tables, columns, measures, hierarchies, and KPIs) as fields defined in that perspective.</span></span>  
  
 <span data-ttu-id="3061e-106">Перспектива «Продажи через Интернет», создаваемая на этом занятии, исключает объект таблицы «Заказчик».</span><span class="sxs-lookup"><span data-stu-id="3061e-106">The Internet Sales perspective you create in this lesson will exclude the Customer table object.</span></span> <span data-ttu-id="3061e-107">При создании перспективы, которая исключает из представления определенные объекты, такие объекты продолжают существовать в модели, однако они не видны в списке полей клиентского средства создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="3061e-107">When you create a perspective that excludes certain objects from view, that object still exists in the model; however, it is not visible in a reporting client field list.</span></span> <span data-ttu-id="3061e-108">Вычисляемые столбцы и меры, как входящие в перспективу, так и нет, все равно смогут проводить вычисления с использованием данных из исключенного объекта.</span><span class="sxs-lookup"><span data-stu-id="3061e-108">Calculated columns and measures either included in a perspective or not can still calculate from object data that is excluded.</span></span>  
  
 <span data-ttu-id="3061e-109">Цель этого занятия — описать создание перспектив и ознакомиться со средствами разработки табличных моделей.</span><span class="sxs-lookup"><span data-stu-id="3061e-109">The purpose of this lesson is to describe how to create perspectives and become familiar with the tabular model authoring tools.</span></span> <span data-ttu-id="3061e-110">Если потом развернуть эту модель и включить в нее дополнительные таблицы, можно будет создать дополнительные перспективы для определения разных точек обзора модели, например, для инвентарного учета и отдела продаж.</span><span class="sxs-lookup"><span data-stu-id="3061e-110">If you later expand this model to include additional tables, you can create additional perspectives to define different viewpoints of the model, for example, Inventory and Sales Force.</span></span>  
  
 <span data-ttu-id="3061e-111">Дополнительные сведения см. в разделе [Перспективы (табличные службы SSAS)](tabular-models/perspectives-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="3061e-111">To learn more, see [Perspectives &#40;SSAS Tabular&#41;](tabular-models/perspectives-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="3061e-112">Предполагаемое время выполнения этого занятия: **5 минут**.</span><span class="sxs-lookup"><span data-stu-id="3061e-112">Estimated time to complete this lesson: **5 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3061e-113">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="3061e-113">Prerequisites</span></span>  
 <span data-ttu-id="3061e-114">Этот раздел входит в учебник по табличному моделированию, который следует изучать в предложенном порядке.</span><span class="sxs-lookup"><span data-stu-id="3061e-114">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="3061e-115">Прежде чем выполнять задания в этом занятии, необходимо завершить предыдущее [Занятие 8. Создание ключевых показателей эффективности](lesson-7-create-key-performance-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="3061e-115">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 8: Create Key Performance Indicators](lesson-7-create-key-performance-indicators.md).</span></span>  
  
## <a name="create-perspectives"></a><span data-ttu-id="3061e-116">Создание перспектив</span><span class="sxs-lookup"><span data-stu-id="3061e-116">Create Perspectives</span></span>  
  
#### <a name="to-create-an-internet-sales-perspective"></a><span data-ttu-id="3061e-117">Создание перспективы «Продажи через Интернет»</span><span class="sxs-lookup"><span data-stu-id="3061e-117">To create an Internet Sales perspective</span></span>  
  
1.  <span data-ttu-id="3061e-118">В конструкторе моделей в меню **модель** выберите пункт **перспективы**.</span><span class="sxs-lookup"><span data-stu-id="3061e-118">In the model designer, click the **Model** menu, and then click **Perspectives**.</span></span>  
  
2.  <span data-ttu-id="3061e-119">В диалоговом окне **Перспективы** щелкните **Создать перспективу**.</span><span class="sxs-lookup"><span data-stu-id="3061e-119">In the **Perspectives** dialog box, click **New Perspective**.</span></span>  
  
3.  <span data-ttu-id="3061e-120">Чтобы переименовать перспективу, дважды щелкните заголовок столбца **Новая перспектива 1** , а затем введите `Internet Sales` .</span><span class="sxs-lookup"><span data-stu-id="3061e-120">To rename the perspective, double-click the **New Perspective 1** column heading, and then type `Internet Sales`.</span></span>  
  
4.  <span data-ttu-id="3061e-121">В поле **поля**выберите следующие таблицы: **Дата**, **География**, **продукт**, **Категория продукта**, **Подкатегория продукта**и `Internet Sales` .</span><span class="sxs-lookup"><span data-stu-id="3061e-121">In **Fields**, select the following tables **Date**, **Geography**, **Product**, **Product Category**, **Product Subcategory**, and `Internet Sales`.</span></span>  
  
     <span data-ttu-id="3061e-122">Обратите внимание, что вы исключили таблицу «Заказчик» и все ее столбцы из этой перспективы.</span><span class="sxs-lookup"><span data-stu-id="3061e-122">Notice you excluded the Customer table and all of its columns from this perspective.</span></span> <span data-ttu-id="3061e-123">Позже, в занятии 12, вы воспользуетесь функцией «Анализ в Excel» для проверки этой перспективы.</span><span class="sxs-lookup"><span data-stu-id="3061e-123">Later, in Lesson 12, you will use the Analyze in Excel feature to test this perspective.</span></span> <span data-ttu-id="3061e-124">Список полей сводной таблицы в Excel будет содержать все таблицы, кроме таблицы «Заказчик».</span><span class="sxs-lookup"><span data-stu-id="3061e-124">The Excel PivotTable Field List will include each table except the Customer table.</span></span>  
  
5.  <span data-ttu-id="3061e-125">Проверьте выбранные значения, убедитесь в том, что флажок для таблицы **Заказчик** не установлен, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3061e-125">Verify your selections, making sure the **Customer** table is not checked, and then click **OK**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3061e-126">Next Steps</span><span class="sxs-lookup"><span data-stu-id="3061e-126">Next Steps</span></span>  
 <span data-ttu-id="3061e-127">Чтобы продолжить изучение этого учебника, перейдите к следующему занятию [Занятие 10. Создание иерархий](lesson-9-create-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="3061e-127">To continue this tutorial, go to the next lesson: [Lesson 10: Create Hierarchies](lesson-9-create-hierarchies.md).</span></span>  
  
  
