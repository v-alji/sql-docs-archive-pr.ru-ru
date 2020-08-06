---
title: Настройки фильтра | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.filtersettings.f1
ms.assetid: 1b401d7d-db8a-4ba1-acb1-b8dec14e3311
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d82d5f38eb460f392f1eb2ed3387ce3d97757db5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655612"
---
# <a name="filter-settings"></a><span data-ttu-id="2603b-102">Настройки фильтра</span><span class="sxs-lookup"><span data-stu-id="2603b-102">Filter Settings</span></span>
  <span data-ttu-id="2603b-103">Диалоговое окно **Настройки фильтра** позволяет определить фильтры для сеток монитора репликации.</span><span class="sxs-lookup"><span data-stu-id="2603b-103">The **Filter Settings** dialog box lets you define filters for grids in Replication Monitor.</span></span> <span data-ttu-id="2603b-104">Например, чтобы показать на вкладке **Все подписки** только активные подписки, выберите **Состояние** в столбце **Имя столбца** , **Равен** в столбце **Оператор** и **Активна** в столбце **Значение1** .</span><span class="sxs-lookup"><span data-stu-id="2603b-104">For example, to show only those subscriptions that are active on the **All Subscriptions** tab, select **Status** from the **Column Name** column, **Equals** from the **Operator** column, and **Active** from the **Value1** column.</span></span> <span data-ttu-id="2603b-105">После определения фильтра, основанного на одном или нескольких столбцах, этот фильтр применяется так, чтобы в сетке отображалось только подмножество строк, удовлетворяющих критериям фильтрации.</span><span class="sxs-lookup"><span data-stu-id="2603b-105">After you define a filter that is based one or more columns, the filter is applied so that the grid displays only the subset of rows that match the filter criteria.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2603b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2603b-106">Options</span></span>  
 <span data-ttu-id="2603b-107">**Имя столбца**</span><span class="sxs-lookup"><span data-stu-id="2603b-107">**Column Name**</span></span>  
 <span data-ttu-id="2603b-108">Имя столбца, по которому нужно выполнить фильтрацию.</span><span class="sxs-lookup"><span data-stu-id="2603b-108">Select the name of the column on which you want to filter.</span></span> <span data-ttu-id="2603b-109">Фильтрацию можно выполнять по одному или нескольким столбцам.</span><span class="sxs-lookup"><span data-stu-id="2603b-109">You can base a filter on one or more columns.</span></span>  
  
 <span data-ttu-id="2603b-110">**Оператор**</span><span class="sxs-lookup"><span data-stu-id="2603b-110">**Operator**</span></span>  
 <span data-ttu-id="2603b-111">Выберите оператор для фильтра, например **Меньше**или Равно.</span><span class="sxs-lookup"><span data-stu-id="2603b-111">Select an operator for the filter, such as **Less than or Equal to**.</span></span>  
  
 <span data-ttu-id="2603b-112">**Значение1** и **Значение2**</span><span class="sxs-lookup"><span data-stu-id="2603b-112">**Value1** and **Value2**</span></span>  
 <span data-ttu-id="2603b-113">Введите или выберите значение для фильтра.</span><span class="sxs-lookup"><span data-stu-id="2603b-113">Enter or select a value for the filter.</span></span> <span data-ttu-id="2603b-114">Для большинства операторов нужно только значение в первом столбце **Значение1** , но для операторов **В диапазоне** и **Вне диапазона** требуется значение столбца **Значение2** .</span><span class="sxs-lookup"><span data-stu-id="2603b-114">Most operators only require a value in the **Value1** column, but the **Between** and **Not Between** operators also require a value in the **Value2** column.</span></span>  
  
 <span data-ttu-id="2603b-115">**Очистить фильтр**</span><span class="sxs-lookup"><span data-stu-id="2603b-115">**Clear Filter**</span></span>  
 <span data-ttu-id="2603b-116">Нажмите эту кнопку для очистки всех ранее определенных фильтров.</span><span class="sxs-lookup"><span data-stu-id="2603b-116">Click this button to clear all filters that have been defined.</span></span> <span data-ttu-id="2603b-117">Для удаления одного фильтра выделите строку фильтра и нажмите клавишу «DELETE».</span><span class="sxs-lookup"><span data-stu-id="2603b-117">To remove a single filter, select the filter row and press the Delete key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2603b-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="2603b-118">See Also</span></span>  
 [<span data-ttu-id="2603b-119">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="2603b-119">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
