---
title: Отображение фактического плана выполнения | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- displaying execution plans
- actual execution plans
- viewing execution plans
- execution plans [SQL Server], displaying
ms.assetid: 9e583a18-5f4a-4054-bfe1-4b2a76630db6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f384e2d2752b7601fbb46b8ee7f7b56a2615651c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730545"
---
# <a name="display-an-actual-execution-plan"></a><span data-ttu-id="191e0-102">Отображение действительного плана выполнения</span><span class="sxs-lookup"><span data-stu-id="191e0-102">Display an Actual Execution Plan</span></span>
  <span data-ttu-id="191e0-103">В этой теме описывается, как создать фактические графические планы выполнения с использованием среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="191e0-103">This topic describes how to generate actual graphical execution plans by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="191e0-104">При создании фактических планов выполнения выполняются запросы или пакеты [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="191e0-104">When actual execution plans are generated, the [!INCLUDE[tsql](../../includes/tsql-md.md)] queries or batches execute.</span></span> <span data-ttu-id="191e0-105">Создаваемый план выполнения отображает фактический план выполнения запроса, который используется [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] для выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="191e0-105">The execution plan that is generated displays the actual query execution plan that the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses to execute the queries.</span></span>  
  
 <span data-ttu-id="191e0-106">Для использования этой возможности необходимо иметь соответствующие разрешения на выполнение запросов [!INCLUDE[tsql](../../includes/tsql-md.md)] , для которых создается графический план выполнения, и разрешение SHOWPLAN для всех баз данных, на которые ссылается запрос.</span><span class="sxs-lookup"><span data-stu-id="191e0-106">To use this feature, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] queries for which a graphical execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.</span></span>  
  
### <a name="to-include-an-execution-plan-for-a-query-during-execution"></a><span data-ttu-id="191e0-107">Включение плана выполнения для запроса в процессе выполнения</span><span class="sxs-lookup"><span data-stu-id="191e0-107">To include an execution plan for a query during execution</span></span>  
  
1.  <span data-ttu-id="191e0-108">На панели инструментов среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] щелкните **Запрос к компоненту Database Engine**.</span><span class="sxs-lookup"><span data-stu-id="191e0-108">On the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] toolbar, click **Database Engine Query**.</span></span> <span data-ttu-id="191e0-109">Можно также нажать на панели инструментов кнопку **Открыть файл** , выбрать существующий запрос и, открыв его, просмотреть предполагаемый план выполнения.</span><span class="sxs-lookup"><span data-stu-id="191e0-109">You can also open an existing query and display the estimated execution plan by clicking the **Open File** toolbar button and locating the existing query.</span></span>  
  
2.  <span data-ttu-id="191e0-110">Введите запрос, для которого необходимо отобразить фактический план выполнения.</span><span class="sxs-lookup"><span data-stu-id="191e0-110">Enter the query for which you would like to display the actual execution plan.</span></span>  
  
3.  <span data-ttu-id="191e0-111">В меню **запрос** выберите команду **Включить действительный план выполнения** или нажмите кнопку **Включить действительный план выполнения** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="191e0-111">On the **Query** menu, click **Include Actual Execution Plan** or click the **Include Actual Execution Plan** toolbar button</span></span>  
  
4.  <span data-ttu-id="191e0-112">Выполните запрос, нажав кнопку **Выполнить** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="191e0-112">Execute the query by clicking the **Execute** toolbar button.</span></span> <span data-ttu-id="191e0-113">План, используемый оптимизатором запросов, отображается на вкладке **План выполнения** на панели результатов.</span><span class="sxs-lookup"><span data-stu-id="191e0-113">The plan used by the query optimizer is displayed on the **Execution Plan** tab in the results pane.</span></span> <span data-ttu-id="191e0-114">Останавливая указатель мыши над логическими и физическими операторами, можно просмотреть описание и свойства операторов во всплывающих подсказках.</span><span class="sxs-lookup"><span data-stu-id="191e0-114">Pause the mouse over the logical and physical operators to view the description and properties of the operators in the displayed ToolTip.</span></span>  
  
     <span data-ttu-id="191e0-115">Также можно просмотреть свойства оператора в окне «Свойства».</span><span class="sxs-lookup"><span data-stu-id="191e0-115">Alternatively, you can view operator properties in the Properties window.</span></span> <span data-ttu-id="191e0-116">Если окно "Свойства" не отображается, щелкните правой кнопкой мыши оператор и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="191e0-116">If Properties is not visible, right-click an operator and select **Properties**.</span></span> <span data-ttu-id="191e0-117">Выберите оператор для просмотра его свойств.</span><span class="sxs-lookup"><span data-stu-id="191e0-117">Select an operator to view its properties.</span></span>  
  
5.  <span data-ttu-id="191e0-118">Изменить внешний вид отображаемого плана выполнения можно, щелкнув его правой кнопкой мыши и выбрав пункты **Увеличить масштаб**, **Уменьшить масштаб**, **Выборочное увеличение**или **Масштаб по размеру**.</span><span class="sxs-lookup"><span data-stu-id="191e0-118">You can alter the display of the execution plan by right-clicking the execution plan and selecting **Zoom In**, **Zoom Out**, **Custom Zoom**, or **Zoom to Fit**.</span></span> <span data-ttu-id="191e0-119">Пункты**Увеличить масштаб** и **Уменьшить масштаб** позволяют увеличивать или уменьшать масштаб отображения плана выполнения, в то время как пункт **Выборочное увеличение** позволяет определять собственный масштаб, например 80 процентов от полного размера.</span><span class="sxs-lookup"><span data-stu-id="191e0-119">**Zoom In** and **Zoom Out** allow you to zoom in or out on the execution plan, while **Custom Zoom** allows you to define your own zoom, such as zooming at 80 percent.</span></span> <span data-ttu-id="191e0-120">При использовании пункта**Масштаб по размеру** план выполнения масштабируется до размеров панели результатов.</span><span class="sxs-lookup"><span data-stu-id="191e0-120">**Zoom to Fit** magnifies the execution plan to fit the result pane.</span></span>  
  
  
