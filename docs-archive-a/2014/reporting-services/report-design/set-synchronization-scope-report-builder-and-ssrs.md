---
title: Задание области действия синхронизации (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6f4a11e6-6151-47be-a43f-e3dbf6c0e737
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3efbb7774d5116c9b3a18457291434f2a05aac7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654798"
---
# <a name="set-synchronization-scope-report-builder-and-ssrs"></a><span data-ttu-id="2238e-102">Задание области действия синхронизации (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="2238e-102">Set Synchronization Scope (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2238e-103">Индикаторы показывают значения данных с проведением синхронизации по всему диапазону значений индикаторов в пределах указанной области действия.</span><span class="sxs-lookup"><span data-stu-id="2238e-103">Indicators convey data values by synchronizing across the range of indicator values within a specified scope.</span></span> <span data-ttu-id="2238e-104">По умолчанию областью действия родительского контейнера индикатора является объект, который содержит индикатор, такой как таблица или матрица.</span><span class="sxs-lookup"><span data-stu-id="2238e-104">By default, the scope is the parent container of the indicator such as the table or matrix that contains the indicator.</span></span> <span data-ttu-id="2238e-105">Синхронизацию индикатора можно менять в зависимости от разметки отчета.</span><span class="sxs-lookup"><span data-stu-id="2238e-105">You can change the synchronization of the indicator depending on the layout of your report.</span></span> <span data-ttu-id="2238e-106">Например, если в такой области данных, как таблица, есть группа строк, можно выбрать эту группу в качестве области индикатора.</span><span class="sxs-lookup"><span data-stu-id="2238e-106">For example, if a data region such as a table has a row group, you can specify the group as the indicator scope.</span></span> <span data-ttu-id="2238e-107">Индикатор позволяет также пропускать синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="2238e-107">The indicator can also omit synchronization.</span></span>  
  
 <span data-ttu-id="2238e-108">Такие параметры, как единицы измерения, можно задать с помощью выражений.</span><span class="sxs-lookup"><span data-stu-id="2238e-108">Options such as measurement units can be set by using expressions.</span></span> <span data-ttu-id="2238e-109">Дополнительные сведения см. в разделе [Выражения (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2238e-109">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="2238e-110">Общие сведения о работе и определении областей действия в отчетах см. в разделе [Область выражения для суммирования, агрегатов и встроенных коллекций &#40;построитель отчетов и службы SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="2238e-110">For general information about understanding and setting scope within reports, see [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-synchronization-scope-of-an-indicator"></a><span data-ttu-id="2238e-111">Изменение области действия синхронизации индикатора</span><span class="sxs-lookup"><span data-stu-id="2238e-111">To change the synchronization scope of an indicator</span></span>  
  
1.  <span data-ttu-id="2238e-112">Щелкните правой кнопкой мыши индикатор, который необходимо изменить, и выберите **Свойства индикатора**.</span><span class="sxs-lookup"><span data-stu-id="2238e-112">Right click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="2238e-113">Нажмите кнопку **Значения и состояния** на левой панели.</span><span class="sxs-lookup"><span data-stu-id="2238e-113">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="2238e-114">В списке **Область действия синхронизации** щелкните область действия, которую необходимо применить.</span><span class="sxs-lookup"><span data-stu-id="2238e-114">In the **Synchronization scope** list, click the scope that you want to apply.</span></span>  
  
     <span data-ttu-id="2238e-115">Всегда доступен параметр **(Нет)** , который удаляет область действия синхронизации из индикатора.</span><span class="sxs-lookup"><span data-stu-id="2238e-115">The **(None)** option, which removes synchronization scope from the indicator, is always available.</span></span> <span data-ttu-id="2238e-116">Наличие других параметров зависит от макета конкретного отчета.</span><span class="sxs-lookup"><span data-stu-id="2238e-116">Other options depend on the layout of your report.</span></span>  
  
     <span data-ttu-id="2238e-117">Нажмите кнопку **Выражение** (*fx*), чтобы изменить выражение, задающее область действия (необязательно).</span><span class="sxs-lookup"><span data-stu-id="2238e-117">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the scope.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2238e-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="2238e-118">See Also</span></span>  
 [<span data-ttu-id="2238e-119">Индикаторы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="2238e-119">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
