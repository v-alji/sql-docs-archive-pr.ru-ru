---
title: Редактор источника "Excel" (страница "столбцы") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelsourceadapter.columns.f1
helpviewer_keywords:
- Excel Source Editor
ms.assetid: 50024686-a18d-4824-b20e-c84123f89d0b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0713d8d3d0c1f56bf322684a924a286e8b81af55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665015"
---
# <a name="excel-source-editor-columns-page"></a><span data-ttu-id="93364-102">Редактор источника Excel (страница «Столбцы»)</span><span class="sxs-lookup"><span data-stu-id="93364-102">Excel Source Editor (Columns Page)</span></span>
  <span data-ttu-id="93364-103">Страница **Столбцы** в диалоговом окне **Редактор источника "Excel"** предназначена для сопоставления выходного столбца с каждым внешним (исходным) столбцом.</span><span class="sxs-lookup"><span data-stu-id="93364-103">Use the **Columns** page of the **Excel Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="93364-104">Дополнительные сведения об источнике Excel см. в разделе [Excel Source](data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="93364-104">To learn more about the Excel source, see [Excel Source](data-flow/excel-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="93364-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="93364-105">Options</span></span>  
 <span data-ttu-id="93364-106">**Доступные внешние столбцы**</span><span class="sxs-lookup"><span data-stu-id="93364-106">**Available External Columns**</span></span>  
 <span data-ttu-id="93364-107">Просмотр списка доступных внешних столбцов источника данных.</span><span class="sxs-lookup"><span data-stu-id="93364-107">View the list of available external columns in the data source.</span></span> <span data-ttu-id="93364-108">В этой таблице нельзя добавлять или удалять столбцы.</span><span class="sxs-lookup"><span data-stu-id="93364-108">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="93364-109">**Внешний столбец**</span><span class="sxs-lookup"><span data-stu-id="93364-109">**External Column**</span></span>  
 <span data-ttu-id="93364-110">Просмотр внешних (исходных) столбцов в том порядке, в котором их будет считывать задача.</span><span class="sxs-lookup"><span data-stu-id="93364-110">View external (source) columns in the order in which the task will read them.</span></span> <span data-ttu-id="93364-111">Этот порядок можно изменить, вначале очистив выделенные столбцы в таблице, а затем выбрав в списке внешние столбцы, идущие в другом порядке.</span><span class="sxs-lookup"><span data-stu-id="93364-111">You can change this order by first clearing the selected columns in the table discussed above, and then selecting external columns from the list in a different order.</span></span>  
  
 <span data-ttu-id="93364-112">**Выходной столбец**</span><span class="sxs-lookup"><span data-stu-id="93364-112">**Output Column**</span></span>  
 <span data-ttu-id="93364-113">Введите уникальное имя для каждого выходного столбца.</span><span class="sxs-lookup"><span data-stu-id="93364-113">Provide a unique name for each output column.</span></span> <span data-ttu-id="93364-114">По умолчанию используется имя выбранного внешнего (исходного) столбца, однако можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="93364-114">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="93364-115">Выбранное имя будет отображаться в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93364-115">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93364-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="93364-116">See Also</span></span>  
 <span data-ttu-id="93364-117">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="93364-117">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="93364-118">[Редактор источника "Excel" &#40;страница "Диспетчер соединений"&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="93364-118">[Excel Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="93364-119">[Редактор источника "Excel" &#40;страница "вывод ошибок"&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="93364-119">[Excel Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="93364-120">[Диспетчер соединений с Excel](connection-manager/excel-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="93364-120">[Excel Connection Manager](connection-manager/excel-connection-manager.md) </span></span>  
 [<span data-ttu-id="93364-121">Просмотр файлов и таблиц Excel с помощью контейнера «цикл по каждому элементу»</span><span class="sxs-lookup"><span data-stu-id="93364-121">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
