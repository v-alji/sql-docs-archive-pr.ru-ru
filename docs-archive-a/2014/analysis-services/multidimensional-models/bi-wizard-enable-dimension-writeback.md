---
title: Включить обратную запись в измерение | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying dimensions
- writeback [Analysis Services], setting up
- dimensions [Analysis Services], Business Intelligence enhancements
- Business Intelligence enhancements [Analysis Services], writeback
- dimensions [Analysis Services], writeback
- writeback [Analysis Services]
- dimensions [Analysis Services], modifying
- manual dimension structure modifications
ms.assetid: a4b5eb5a-366d-4fc8-ad0d-5bdb8e7b4163
author: minewiskan
ms.author: owend
ms.openlocfilehash: cba4a54e8a51d022c6f84a4c81d32f359a95692a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657373"
---
# <a name="enable-dimension-writeback"></a><span data-ttu-id="fd376-102">Разрешение обратной записи в измерение</span><span class="sxs-lookup"><span data-stu-id="fd376-102">Enable Dimension Writeback</span></span>
  <span data-ttu-id="fd376-103">Добавьте расширение обратной записи в куб или измерение, чтобы пользователи могли вручную изменять структуру и элементы измерения.</span><span class="sxs-lookup"><span data-stu-id="fd376-103">Add the dimension writeback enhancement to a cube or dimension to allow users to manually modify the dimension structure and members.</span></span> <span data-ttu-id="fd376-104">Обновления измерений, доступных для записи, записываются прямо в таблицу измерения.</span><span class="sxs-lookup"><span data-stu-id="fd376-104">Updates to a write-enabled dimension are recorded directly in the dimension table.</span></span> <span data-ttu-id="fd376-105">Это расширение изменяет настройку свойства `WriteEnabled` для измерения.</span><span class="sxs-lookup"><span data-stu-id="fd376-105">This enhancement changes the `WriteEnabled` property setting for a dimension.</span></span>  
  
 <span data-ttu-id="fd376-106">Чтобы добавить обратную запись в измерение, используйте мастер бизнес-аналитики и выберите параметр **Включить обратную запись в измерение** на странице **Выбор расширения** .</span><span class="sxs-lookup"><span data-stu-id="fd376-106">To add dimension writeback, you use the Business Intelligence Wizard, and select the **Enable dimension writeback** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="fd376-107">После этого мастер отобразит шаги, позволяющие выбрать измерение, к которому необходимо применить обратную запись, и установить этот параметр для выбранного измерения.</span><span class="sxs-lookup"><span data-stu-id="fd376-107">This wizard then guides you through the steps of selecting a dimension to which you want to apply dimension writeback and setting this option for the selected dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fd376-108">Обратная запись поддерживается только для реляционных баз данных SQL Server и киосков данных.</span><span class="sxs-lookup"><span data-stu-id="fd376-108">Writeback is supported for SQL Server relational databases and data marts only.</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="fd376-109">Выбор измерения</span><span class="sxs-lookup"><span data-stu-id="fd376-109">Selecting a Dimension</span></span>  
 <span data-ttu-id="fd376-110">На первой странице **Включение обратной записи в измерение** мастера указывается измерение, к которому необходимо применить обратную запись.</span><span class="sxs-lookup"><span data-stu-id="fd376-110">On the first **Enable Dimension Writeback** page of the wizard, you specify the dimension to which you want to apply dimension writeback.</span></span> <span data-ttu-id="fd376-111">Добавление расширения обратной записи в измерение к этому выбранному измерению приведет к изменениям измерения.</span><span class="sxs-lookup"><span data-stu-id="fd376-111">The dimension writeback enhancement added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="fd376-112">Эти изменения будут наследоваться всеми кубами, включающими выбранное измерение.</span><span class="sxs-lookup"><span data-stu-id="fd376-112">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="setting-dimension-writeback-capability"></a><span data-ttu-id="fd376-113">Установка возможности обратной записи в измерение</span><span class="sxs-lookup"><span data-stu-id="fd376-113">Setting Dimension Writeback Capability</span></span>  
 <span data-ttu-id="fd376-114">На второй странице мастера — **Включение обратной записи в измерение** — непосредственно задается параметр **Включить обратную запись в измерение** .</span><span class="sxs-lookup"><span data-stu-id="fd376-114">On the second **Enable Dimension Writeback** page of the wizard, you actually set the **Enable writeback in the dimension** option.</span></span> <span data-ttu-id="fd376-115">При выборе этого параметра свойство `WriteEnabled` измерения автоматически устанавливается равным `True`.</span><span class="sxs-lookup"><span data-stu-id="fd376-115">Selecting this option automatically sets the `WriteEnabled` property of the dimension to `True`.</span></span> <span data-ttu-id="fd376-116">При снятии этого флажка это свойство автоматически устанавливается равным `False`.</span><span class="sxs-lookup"><span data-stu-id="fd376-116">Clearing this option automatically sets the property to `False`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd376-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="fd376-117">Remarks</span></span>  
 <span data-ttu-id="fd376-118">при создании нового элемента необходимо включить в измерение каждый атрибут.</span><span class="sxs-lookup"><span data-stu-id="fd376-118">When you create a new member, you must include every attribute in a dimension.</span></span> <span data-ttu-id="fd376-119">Нельзя вставить элемент, не указав значение ключевого атрибута измерения.</span><span class="sxs-lookup"><span data-stu-id="fd376-119">You cannot insert a member without specifying a value for the key attribute of the dimension.</span></span> <span data-ttu-id="fd376-120">Следовательно, на создание элементов оказывают влияние любые ограничения (такие как ключевые значения, отличные от NULL), установленные в таблице измерений;</span><span class="sxs-lookup"><span data-stu-id="fd376-120">Therefore, creating members is subject to any constraints (such as non-null key values) that are defined on the dimension table.</span></span> <span data-ttu-id="fd376-121">Необходимо также учитывать столбцы, дополнительно задаваемые такими свойствами измерения, как `CustomRollupColumn`, `CustomRollupPropertiesColumn` или `UnaryOperatorColumn`.</span><span class="sxs-lookup"><span data-stu-id="fd376-121">You should also consider columns optionally specified by dimension properties, such as columns specified in the `CustomRollupColumn`, `CustomRollupPropertiesColumn` or the `UnaryOperatorColumn` dimension properties.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="fd376-122">При использовании SQL Azure в качестве источника данных для выполнения обратной записи в базу данных служб Analysis Services происходит сбой операции.</span><span class="sxs-lookup"><span data-stu-id="fd376-122">If you use SQL Azure as a data source to perform writeback into an Analysis Services database, the operation fails.</span></span> <span data-ttu-id="fd376-123">Это сделано намеренно, поскольку параметр поставщика, разрешающий несколько активных результирующих наборов (MARS), не включен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fd376-123">This is by design, because the provider option that enables multiple active result sets (MARS) is not turned on by default.</span></span>  
>   
>  <span data-ttu-id="fd376-124">Для поддержки MARS и возможности обратной записи необходимо добавить следующий параметр в строку подключения:</span><span class="sxs-lookup"><span data-stu-id="fd376-124">The workaround is to add the following setting in the connection string, to support MARS and to enable writeback:</span></span>  
>   
>  `"MultipleActiveResultSets=True"`  
>   
>  <span data-ttu-id="fd376-125">Дополнительные сведения см. в разделе [Использование множественных активных результирующих наборов (MARS)](../../relational-databases/native-client/features/using-multiple-active-result-sets-mars.md).</span><span class="sxs-lookup"><span data-stu-id="fd376-125">For more information see [Using Multiple Active Result Sets &#40;MARS&#41;](../../relational-databases/native-client/features/using-multiple-active-result-sets-mars.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd376-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="fd376-126">See Also</span></span>  
 [<span data-ttu-id="fd376-127">Измерения, доступные для записи</span><span class="sxs-lookup"><span data-stu-id="fd376-127">Write-Enabled Dimensions</span></span>](../multidimensional-models-olap-logical-dimension-objects/write-enabled-dimensions.md)  
  
  
