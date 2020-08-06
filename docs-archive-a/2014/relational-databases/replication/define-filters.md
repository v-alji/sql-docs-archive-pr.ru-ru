---
title: Определение фильтров | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replconflictviewer.definefilters.f1
helpviewer_keywords:
- Define Filters dialog box
ms.assetid: 1fa71d22-ce5a-4aae-ba05-4d755842aeac
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5154f002c5a35bc78e2eb6777f2cc7bb3d56b635
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655651"
---
# <a name="define-filters"></a><span data-ttu-id="73dc0-102">Определение фильтров</span><span class="sxs-lookup"><span data-stu-id="73dc0-102">Define Filters</span></span>
  <span data-ttu-id="73dc0-103">Диалоговое окно **Определение фильтров** позволяет определять фильтры, применяемые к конфликтам данных для просмотра подмножества этих конфликтов в данной сетке.</span><span class="sxs-lookup"><span data-stu-id="73dc0-103">The **Define Filters** dialog box allows you to define filters that you then apply to data conflicts to see a subset of the conflicts in the grid.</span></span> <span data-ttu-id="73dc0-104">Чтобы определить фильтр, выберите оператор из раскрывающегося списка **Оператор** , а затем введите значение.</span><span class="sxs-lookup"><span data-stu-id="73dc0-104">To define a filter, choose an operator from the **Operator** drop-down list box and then enter a value.</span></span> <span data-ttu-id="73dc0-105">Например, чтобы просмотреть только те конфликты, в которых проигравшей стороной является сервер **ReplTest1**, выберите **Равно** из раскрывающегося списка **Оператор** и введите **ReplTest1** в первом столбце **Значение** .</span><span class="sxs-lookup"><span data-stu-id="73dc0-105">For example, to show only those conflicts in which the conflict loser is server **ReplTest1**, select **Equal to** from the **Operator** drop-down list box and enter **ReplTest1** in the first **Value** column.</span></span>  
  
## <a name="options"></a><span data-ttu-id="73dc0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="73dc0-106">Options</span></span>  
 <span data-ttu-id="73dc0-107">**Оператор**</span><span class="sxs-lookup"><span data-stu-id="73dc0-107">**Operator**</span></span>  
 <span data-ttu-id="73dc0-108">Выберите оператор для фильтра, например **Меньше**или Равно.</span><span class="sxs-lookup"><span data-stu-id="73dc0-108">Select an operator for the filter, such as **Less than or Equal to**.</span></span>  
  
 <span data-ttu-id="73dc0-109">**Value**</span><span class="sxs-lookup"><span data-stu-id="73dc0-109">**Value**</span></span>  
 <span data-ttu-id="73dc0-110">Введите значение для фильтра.</span><span class="sxs-lookup"><span data-stu-id="73dc0-110">Enter a value for the filter.</span></span> <span data-ttu-id="73dc0-111">Для большинства операторов нужно только значение в первом столбце **Значение** , но для операторов **Между** и **Вне** необходимы значения в обоих столбцах **Значение** .</span><span class="sxs-lookup"><span data-stu-id="73dc0-111">Most operators only require a value in the first **Value** column, but the **Between** and **Not Between** operators require a value in both of the **Value** columns.</span></span>  
  
 <span data-ttu-id="73dc0-112">**Clear**</span><span class="sxs-lookup"><span data-stu-id="73dc0-112">**Clear**</span></span>  
 <span data-ttu-id="73dc0-113">Нажмите эту кнопку для сброса всех ранее определенных фильтров.</span><span class="sxs-lookup"><span data-stu-id="73dc0-113">Click this button to clear all filters that have been previously defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73dc0-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="73dc0-114">See Also</span></span>  
 <span data-ttu-id="73dc0-115">[Средство просмотра конфликтов репликации (Майкрософт) (репликация слиянием)](microsoft-replication-conflict-viewer-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="73dc0-115">[Microsoft Replication Conflict Viewer &#40;Merge Replication&#41;](microsoft-replication-conflict-viewer-merge-replication.md) </span></span>  
 [<span data-ttu-id="73dc0-116">Средство просмотра конфликтов репликации (Майкрософт) (репликация транзакций)</span><span class="sxs-lookup"><span data-stu-id="73dc0-116">Microsoft Replication Conflict Viewer &#40;Transactional Replication&#41;</span></span>](microsoft-replication-conflict-viewer-transactional-replication.md)  
  
  
