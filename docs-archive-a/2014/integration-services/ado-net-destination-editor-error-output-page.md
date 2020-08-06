---
title: Редактор назначения «ADO NET» (страница «вывод ошибок») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetdest.erroroutput.f1
ms.assetid: 1a56c3cf-fb6a-416d-a62c-bb19fe441ae5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9cfd69d3adec2aa617f5e9d3add35a1a6923804
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664454"
---
# <a name="ado-net-destination-editor-error-output-page"></a><span data-ttu-id="24d22-102">Редактор назначения «ADO.NET» (страница «Вывод ошибок»)</span><span class="sxs-lookup"><span data-stu-id="24d22-102">ADO NET Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="24d22-103">Страница **Вывод ошибок** диалогового окна **Редактор назначения «ADO.NET»** используется для задания параметров обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="24d22-103">Use the **Error Output** page of the **ADO NET Destination Editor** dialog box to specify error handling options.</span></span>  
  
 <span data-ttu-id="24d22-104">Дополнительные сведения о назначении «ADO.NET» см. в разделе [ADO NET Destination](data-flow/ado-net-destination.md).</span><span class="sxs-lookup"><span data-stu-id="24d22-104">To learn more about the ADO NET destination, see [ADO NET Destination](data-flow/ado-net-destination.md).</span></span>  
  
 <span data-ttu-id="24d22-105">**Открытие страницы «Вывод ошибок»**</span><span class="sxs-lookup"><span data-stu-id="24d22-105">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="24d22-106">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий назначение «ADO.NET».</span><span class="sxs-lookup"><span data-stu-id="24d22-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET destination.</span></span>  
  
2.  <span data-ttu-id="24d22-107">На вкладке **Поток данных** дважды щелкните назначение "ADO.NET".</span><span class="sxs-lookup"><span data-stu-id="24d22-107">On the **Data Flow** tab, double-click the ADO NET destination.</span></span>  
  
3.  <span data-ttu-id="24d22-108">В окне **Редактор назначения «ADO.NET»** нажмите кнопку **Вывод ошибок**.</span><span class="sxs-lookup"><span data-stu-id="24d22-108">In the **ADO NET Destination Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="24d22-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="24d22-109">Options</span></span>  
 <span data-ttu-id="24d22-110">**Вход или выход**</span><span class="sxs-lookup"><span data-stu-id="24d22-110">**Input or Output**</span></span>  
 <span data-ttu-id="24d22-111">Просмотрите имя входных данных.</span><span class="sxs-lookup"><span data-stu-id="24d22-111">View the name of the input.</span></span>  
  
 <span data-ttu-id="24d22-112">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="24d22-112">**Column**</span></span>  
 <span data-ttu-id="24d22-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="24d22-113">Not used.</span></span>  
  
 <span data-ttu-id="24d22-114">**Error**</span><span class="sxs-lookup"><span data-stu-id="24d22-114">**Error**</span></span>  
 <span data-ttu-id="24d22-115">Задайте действие, которое необходимо выполнить при возникновении ошибки: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="24d22-115">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="24d22-116">**См. также:** [Обработка ошибок в данных](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="24d22-116">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="24d22-117">**Усечение**</span><span class="sxs-lookup"><span data-stu-id="24d22-117">**Truncation**</span></span>  
 <span data-ttu-id="24d22-118">Не используется.</span><span class="sxs-lookup"><span data-stu-id="24d22-118">Not used.</span></span>  
  
 <span data-ttu-id="24d22-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="24d22-119">**Description**</span></span>  
 <span data-ttu-id="24d22-120">Просмотрите описание операции.</span><span class="sxs-lookup"><span data-stu-id="24d22-120">View the description of the operation.</span></span>  
  
 <span data-ttu-id="24d22-121">**Присвоить указанное значение выбранным ячейкам**</span><span class="sxs-lookup"><span data-stu-id="24d22-121">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="24d22-122">Укажите действие, которое необходимо применить ко всем выбранным ячейкам при возникновении ошибки или усечения: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="24d22-122">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="24d22-123">**Применить**</span><span class="sxs-lookup"><span data-stu-id="24d22-123">**Apply**</span></span>  
 <span data-ttu-id="24d22-124">Применить параметр обработки ошибок к выбранным ячейкам.</span><span class="sxs-lookup"><span data-stu-id="24d22-124">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24d22-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="24d22-125">See Also</span></span>  
 <span data-ttu-id="24d22-126">[Редактор назначения «ADO NET» &#40;«диспетчер соединений»&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="24d22-126">[ADO NET Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="24d22-127">Редактор назначения ADO.NET (страница "Сопоставления")</span><span class="sxs-lookup"><span data-stu-id="24d22-127">ADO NET Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/ado-net-destination-editor-mappings-page.md)  
  
  
