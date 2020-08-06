---
title: Создание секций табличной модели и управление ими (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: dab72cf0-95bc-4b63-95dc-505b5cd881c1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 58c408c712d6ac4b6bd590bd0f8c895dc1a88700
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666744"
---
# <a name="create-and-manage-tabular-model-partitions-ssas-tabular"></a><span data-ttu-id="eda95-102">Создание секций табличной модели и управление ими (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="eda95-102">Create and Manage Tabular Model Partitions (SSAS Tabular)</span></span>
  <span data-ttu-id="eda95-103">Секции разделяют таблицу на логические части.</span><span class="sxs-lookup"><span data-stu-id="eda95-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="eda95-104">Каждая секция затем может обрабатываться (обновляться) независимо от других секций.</span><span class="sxs-lookup"><span data-stu-id="eda95-104">Each partition can then be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="eda95-105">Секции, определенные для модели во время разработки модели, дублируются в модели развертывания.</span><span class="sxs-lookup"><span data-stu-id="eda95-105">Partitions defined for a model during model authoring are duplicated in a deployed model.</span></span> <span data-ttu-id="eda95-106">После развертывания можно настроить управление секциями с помощью диалогового окна **Секции** в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или с помощью скрипта.</span><span class="sxs-lookup"><span data-stu-id="eda95-106">Once deployed, you can manage those partitions by using the **Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or by using a script.</span></span> <span data-ttu-id="eda95-107">В задачах этого раздела описывается создание и управление секциями в развернутой модели.</span><span class="sxs-lookup"><span data-stu-id="eda95-107">Tasks provided in this topic describe how to create and manage partitions for a deployed model.</span></span>  
  
 <span data-ttu-id="eda95-108">В этот раздел включены следующее задачи:</span><span class="sxs-lookup"><span data-stu-id="eda95-108">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="eda95-109">Создание новой секции</span><span class="sxs-lookup"><span data-stu-id="eda95-109">To create a new partition</span></span>](#bkmk_create_new)  
  
-   [<span data-ttu-id="eda95-110">Копирование секции</span><span class="sxs-lookup"><span data-stu-id="eda95-110">To copy a partition</span></span>](#bkmk_copy)  
  
-   [<span data-ttu-id="eda95-111">Слияние двух или более секций</span><span class="sxs-lookup"><span data-stu-id="eda95-111">To merge two or more partitions</span></span>](#bkmk_merge)  
  
-   [<span data-ttu-id="eda95-112">Удаление секции</span><span class="sxs-lookup"><span data-stu-id="eda95-112">To delete a partition</span></span>](#bkmk_delete)  
  
## <a name="tasks"></a><span data-ttu-id="eda95-113">Задания</span><span class="sxs-lookup"><span data-stu-id="eda95-113">Tasks</span></span>  
 <span data-ttu-id="eda95-114">Создание секций и управление ими в развернутой базе данных с табличной моделью выполняются в диалоговом окне **Секции** среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eda95-114">To create and manage partitions for a deployed tabular model database, you will use the **Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="eda95-115">Чтобы открыть диалоговое окно **Секции** в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], щелкните таблицу правой кнопкой мыши и выберите команду **Секции**.</span><span class="sxs-lookup"><span data-stu-id="eda95-115">To view the **Partitions** dialog box, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click on a table, and then click **Partitions**.</span></span>  
  
###  <a name="to-create-a-new-partition"></a><a name="bkmk_create_new"></a><span data-ttu-id="eda95-116">Создание новой секции</span><span class="sxs-lookup"><span data-stu-id="eda95-116">To create a new partition</span></span>  
  
1.  <span data-ttu-id="eda95-117">В диалоговом окне **Секции** нажмите кнопку **Создать** .</span><span class="sxs-lookup"><span data-stu-id="eda95-117">In the **Partitions** dialog box, click the **New** button.</span></span>  
  
2.  <span data-ttu-id="eda95-118">В поле **Имя секции**введите имя секции.</span><span class="sxs-lookup"><span data-stu-id="eda95-118">In **Partition Name**, type a name for the partition.</span></span> <span data-ttu-id="eda95-119">По умолчанию к имени секции, заданной по умолчанию, будет добавляться номер, постепенно увеличивающийся для каждой новой секции.</span><span class="sxs-lookup"><span data-stu-id="eda95-119">By default, the name of the default partition will be incrementally numbered for each new partition.</span></span>  
  
3.  <span data-ttu-id="eda95-120">В поле **Инструкция SQL**введите или вставьте в окне запроса инструкцию SQL-запроса, определяющую столбцы, и любые предложения, которые необходимо включить в секцию.</span><span class="sxs-lookup"><span data-stu-id="eda95-120">In **SQL Statement**, type or paste a SQL query statement that defines the columns and any clauses you want to include in the partition into the query window.</span></span>  
  
4.  <span data-ttu-id="eda95-121">Чтобы проверить инструкцию, нажмите кнопку **Проверить синтаксис**.</span><span class="sxs-lookup"><span data-stu-id="eda95-121">To validate the statement, click **Check Syntax**.</span></span>  
  
###  <a name="to-copy-a-partition"></a><a name="bkmk_copy"></a> <span data-ttu-id="eda95-122">Копирование секции</span><span class="sxs-lookup"><span data-stu-id="eda95-122">To copy a partition</span></span>  
  
1.  <span data-ttu-id="eda95-123">В диалоговом окне **Секции** в списке **Секции** выберите секцию, которую необходимо скопировать, и нажмите кнопку **Копировать** .</span><span class="sxs-lookup"><span data-stu-id="eda95-123">In the **Partitions** dialog box, in the **Partitions** list, select the partition you want to copy, and then click the **Copy** button.</span></span>  
  
2.  <span data-ttu-id="eda95-124">В поле **Имя секции**введите новое имя секции.</span><span class="sxs-lookup"><span data-stu-id="eda95-124">In **Partition Name**, type a new name for the partition.</span></span>  
  
3.  <span data-ttu-id="eda95-125">В поле **Инструкция SQL**измените инструкцию SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="eda95-125">In **SQL Statement**, edit the SQL query statement.</span></span>  
  
###  <a name="to-merge-two-or-more-partitions"></a><a name="bkmk_merge"></a> <span data-ttu-id="eda95-126">Объединение двух или более разделов</span><span class="sxs-lookup"><span data-stu-id="eda95-126">To merge two or more partitions</span></span>  
  
-   <span data-ttu-id="eda95-127">В диалоговом окне **Секции** в списке **Секции** выберите щелчками мыши при нажатой клавише CTRL секции, которые необходимо объединить, и нажмите кнопку **Объединить** .</span><span class="sxs-lookup"><span data-stu-id="eda95-127">In the **Partitions** dialog box, in the **Partitions** list, use Ctrl+click to select the partitions you want to merge, and then click the **Merge** button.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="eda95-128">Слияние секций не обновляет их метаданные.</span><span class="sxs-lookup"><span data-stu-id="eda95-128">Merging partitions does not update the partition metadata.</span></span> <span data-ttu-id="eda95-129">Администраторам нужно изменить инструкцию SQL для получающейся в результате секции, чтобы убедиться, что все операции обработки обрабатывают все данных в объединенной секции.</span><span class="sxs-lookup"><span data-stu-id="eda95-129">Administrators must alter the SQL Statement for the resulting partition to make sure processing operations process all data in the merged partition.</span></span>  
  
###  <a name="to-delete-a-partition"></a><a name="bkmk_delete"></a><span data-ttu-id="eda95-130">Удаление секции</span><span class="sxs-lookup"><span data-stu-id="eda95-130">To delete a partition</span></span>  
  
-   <span data-ttu-id="eda95-131">В диалоговом окне **Секции** в списке **Секции** выберите секцию, которую необходимо удалить, и нажмите кнопку **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="eda95-131">In the **Partitions** dialog box, in the **Partitions** list, select the partition you want to delete, and then click the **Delete** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eda95-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="eda95-132">See Also</span></span>  
 <span data-ttu-id="eda95-133">[Секции табличной модели &#40;табличные&#41;SSAS](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="eda95-133">[Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="eda95-134">Обработка секций табличной модели (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="eda95-134">Process Tabular Model Partitions &#40;SSAS Tabular&#41;</span></span>](process-tabular-model-partitions-ssas-tabular.md)  
  
  
