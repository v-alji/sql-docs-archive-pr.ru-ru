---
title: Отображение предполагаемого плана выполнения | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- zoom [SQL Server]
- estimated execution plan [SQL Server]
- displaying execution plans
- viewing execution plans
- execution plans [SQL Server], displaying
- customizing execution plan display [SQL Server]
- modifying execution plan display
- custom zoom [SQL Server]
ms.assetid: e94aa576-4c0c-4c54-ad05-6c3432cc615b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79c0972661d40eb9e359cf43f7a1f0b1b2ae4b0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730533"
---
# <a name="display-the-estimated-execution-plan"></a><span data-ttu-id="096c1-102">Отображение предполагаемого плана выполнения</span><span class="sxs-lookup"><span data-stu-id="096c1-102">Display the Estimated Execution Plan</span></span>
  <span data-ttu-id="096c1-103">В этом разделе описано создание графических предполагаемых планов выполнения с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="096c1-103">This topic describes how to generate graphical estimated execution plans by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="096c1-104">При создании расчетных планов выполнения запросы и пакеты [!INCLUDE[tsql](../../includes/tsql-md.md)] не выполняются.</span><span class="sxs-lookup"><span data-stu-id="096c1-104">When estimated execution plans are generated, the [!INCLUDE[tsql](../../includes/tsql-md.md)] queries or batches do not execute.</span></span> <span data-ttu-id="096c1-105">Вместо этого созданный план выполнения отображает наиболее вероятный план выполнения запроса, которому следовал бы компонент [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] при реальном выполнении запросов.</span><span class="sxs-lookup"><span data-stu-id="096c1-105">Instead, the execution plan that is generated displays the query execution plan that [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] would most probably use if the queries were actually executed.</span></span>  
  
 <span data-ttu-id="096c1-106">Для использования этой возможности пользователи должны обладать соответствующими разрешениями на запуск запроса [!INCLUDE[tsql](../../includes/tsql-md.md)] , для которого создается графический план выполнения. Кроме того, пользователям должно быть предоставлено разрешение SHOWPLAN для всех баз данных, упоминаемых в запросе.</span><span class="sxs-lookup"><span data-stu-id="096c1-106">To use this feature, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] query for which a graphical execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.</span></span>  
  
### <a name="to-display-the-estimated-execution-plan-for-a-query"></a><span data-ttu-id="096c1-107">Отображение предполагаемого плана выполнения запроса</span><span class="sxs-lookup"><span data-stu-id="096c1-107">To display the estimated execution plan for a query</span></span>  
  
1.  <span data-ttu-id="096c1-108">На панели инструментов нажмите кнопку **Запрос к ядру СУБД**.</span><span class="sxs-lookup"><span data-stu-id="096c1-108">On the toolbar, click **Database Engine Query**.</span></span> <span data-ttu-id="096c1-109">Можно также нажать на панели инструментов кнопку **Открыть файл** , выбрать существующий запрос и, открыв его, просмотреть предполагаемый план выполнения.</span><span class="sxs-lookup"><span data-stu-id="096c1-109">You can also open an existing query and display the estimated execution plan by clicking the **Open File** toolbar button and locating the existing query.</span></span>  
  
2.  <span data-ttu-id="096c1-110">Введите запрос, для которого нужно отобразить предполагаемый план выполнения.</span><span class="sxs-lookup"><span data-stu-id="096c1-110">Enter the query for which you would like to display the estimated execution plan.</span></span>  
  
3.  <span data-ttu-id="096c1-111">В меню **Запрос** выберите **Показать предполагаемый план выполнения** или нажмите на панели инструментов кнопку **Показать предполагаемый план выполнения** .</span><span class="sxs-lookup"><span data-stu-id="096c1-111">On the **Query** menu, click **Display Estimated Execution Plan** or click the **Display Estimated Execution Plan** toolbar button.</span></span> <span data-ttu-id="096c1-112">Предполагаемый план выполнения отображается на вкладке **План выполнения** на панели результатов.</span><span class="sxs-lookup"><span data-stu-id="096c1-112">The estimated execution plan is displayed on the **Execution Plan** tab in the results pane.</span></span> <span data-ttu-id="096c1-113">Для просмотра дополнительных сведений задержите указатель мыши над значками логического и физического оператора и просмотрите описание и свойства оператора в отобразившейся всплывающей подсказке.</span><span class="sxs-lookup"><span data-stu-id="096c1-113">To view additional information, pause the mouse over the logical and physical operator icons and view the description and properties of the operator in the displayed ToolTip.</span></span> <span data-ttu-id="096c1-114">Также можно просмотреть свойства оператора в окне «Свойства».</span><span class="sxs-lookup"><span data-stu-id="096c1-114">Alternatively, you can view operator properties in the Properties window.</span></span> <span data-ttu-id="096c1-115">Если "Свойства" не видны, щелкните оператор правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="096c1-115">If Properties is not visible, right-click an operator and click **Properties**.</span></span> <span data-ttu-id="096c1-116">Выберите оператор для просмотра его свойств.</span><span class="sxs-lookup"><span data-stu-id="096c1-116">Select an operator to view its properties.</span></span>  
  
4.  <span data-ttu-id="096c1-117">Чтобы изменить отображение плана выполнения, щелкните правой кнопкой мыши план выполнения и выберите **Увеличить масштаб**, **Уменьшить масштаб**, **Пользовательский масштаб**или **Масштаб по размеру**.</span><span class="sxs-lookup"><span data-stu-id="096c1-117">To alter the display of the execution plan, right-click the execution plan and select **Zoom In**, **Zoom Out**, **Custom Zoom**, or **Zoom to Fit**.</span></span> <span data-ttu-id="096c1-118">Кнопки**Увеличить масштаб** и **Уменьшить масштаб** позволяют увеличить или уменьшить план выполнения на фиксированную величину.</span><span class="sxs-lookup"><span data-stu-id="096c1-118">**Zoom In** and **Zoom Out** allow you to magnify or reduce the execution plan by fixed amounts.</span></span> <span data-ttu-id="096c1-119">**Настраиваемый масштаб** позволяет определить собственное значение, например масштаб в 80 процентов.</span><span class="sxs-lookup"><span data-stu-id="096c1-119">**Custom Zoom** allows you to define your own display magnification, such as zooming at 80 percent.</span></span> <span data-ttu-id="096c1-120">При использовании пункта**Масштаб по размеру** план выполнения масштабируется до размеров панели результатов.</span><span class="sxs-lookup"><span data-stu-id="096c1-120">**Zoom to Fit** magnifies the execution plan to fit the result pane.</span></span>  
  
  
