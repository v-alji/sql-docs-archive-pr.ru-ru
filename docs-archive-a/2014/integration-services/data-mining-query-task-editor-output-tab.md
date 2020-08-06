---
title: Редактор задачи «Запрос интеллектуального анализа данных» (вкладка «Вывод») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dmquerytask.output.f1
helpviewer_keywords:
- Data Mining Query Task Editor
ms.assetid: 62f9e015-6fe0-4396-ad90-3ad51bf00025
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1508972b0487daa90f52af723d58185944a19a58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738525"
---
# <a name="data-mining-query-task-editor-output-tab"></a><span data-ttu-id="f129a-102">Редактор задачи «Запрос интеллектуального анализа данных» (вкладка «Вывод»)</span><span class="sxs-lookup"><span data-stu-id="f129a-102">Data Mining Query Task Editor (Output Tab)</span></span>
  <span data-ttu-id="f129a-103">Используйте вкладку **Выход** окна **Редактор задачи «Запрос интеллектуального анализа данных»** , чтобы указать назначение прогнозирующего запроса.</span><span class="sxs-lookup"><span data-stu-id="f129a-103">Use the **Output** tab of the **Data Mining Query Task Editor** dialog box to specify the destination of the prediction query.</span></span>  
  
 <span data-ttu-id="f129a-104">Сведения об интеллектуальном анализе данных в пакетах см. в разделах [Задача "Запрос интеллектуального анализа данных"](control-flow/data-mining-query-task.md) и [Решения для интеллектуального анализа данных](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span><span class="sxs-lookup"><span data-stu-id="f129a-104">To learn about implementing data mining in packages, see [Data Mining Query Task](control-flow/data-mining-query-task.md) and [Data Mining Solutions](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="f129a-105">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f129a-105">General Options</span></span>  
 <span data-ttu-id="f129a-106">**имя**;</span><span class="sxs-lookup"><span data-stu-id="f129a-106">**Name**</span></span>  
 <span data-ttu-id="f129a-107">Задайте уникальное имя для задачи «Запрос интеллектуального анализа данных».</span><span class="sxs-lookup"><span data-stu-id="f129a-107">Provide a unique name for the Data Mining Query task.</span></span> <span data-ttu-id="f129a-108">Это имя используется в качестве метки для значка задачи.</span><span class="sxs-lookup"><span data-stu-id="f129a-108">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f129a-109">Имена задач в пределах пакета должны быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="f129a-109">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="f129a-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f129a-110">**Description**</span></span>  
 <span data-ttu-id="f129a-111">Введите описание задачи «Запрос интеллектуального анализа данных».</span><span class="sxs-lookup"><span data-stu-id="f129a-111">Type a description of the Data Mining Query task.</span></span>  
  
## <a name="output-tab-options"></a><span data-ttu-id="f129a-112">Параметры вкладки «Вывод»</span><span class="sxs-lookup"><span data-stu-id="f129a-112">Output Tab Options</span></span>  
 <span data-ttu-id="f129a-113">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="f129a-113">**Connection**</span></span>  
 <span data-ttu-id="f129a-114">Выберите из списка диспетчер соединений или нажмите кнопку **Создать** для создания нового диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="f129a-114">Select a connection manager in the list or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="f129a-115">**Создать**</span><span class="sxs-lookup"><span data-stu-id="f129a-115">**New**</span></span>  
 <span data-ttu-id="f129a-116">Создание диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="f129a-116">Create a new connection manager.</span></span> <span data-ttu-id="f129a-117">Единственные допустимые типы диспетчеров соединений — ADO.NET и OLE DB.</span><span class="sxs-lookup"><span data-stu-id="f129a-117">Only the ADO.NET and OLE DB connection manager types can be used.</span></span>  
  
 <span data-ttu-id="f129a-118">**Выходная таблица**</span><span class="sxs-lookup"><span data-stu-id="f129a-118">**Output table**</span></span>  
 <span data-ttu-id="f129a-119">Укажите таблицу, в которую будут записываться результаты прогнозирующего запроса.</span><span class="sxs-lookup"><span data-stu-id="f129a-119">Specify the table to which the prediction query writes its results.</span></span>  
  
 <span data-ttu-id="f129a-120">**Удалить и повторно создать выходную таблицу**</span><span class="sxs-lookup"><span data-stu-id="f129a-120">**Drop and re-create the output table**</span></span>  
 <span data-ttu-id="f129a-121">Укажите, должен ли прогнозирующий запрос перезаписывать содержимое целевой таблицы путем ее удаления и повторного создания.</span><span class="sxs-lookup"><span data-stu-id="f129a-121">Indicate whether the prediction query should overwrite content in the destination table by dropping and then re-creating the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f129a-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="f129a-122">See Also</span></span>  
 <span data-ttu-id="f129a-123">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f129a-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="f129a-124">[Редактор задачи «Запрос интеллектуального анализа данных» &#40;вкладку «модель интеллектуального анализа»&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span><span class="sxs-lookup"><span data-stu-id="f129a-124">[Data Mining Query Task Editor &#40;Mining Model Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span></span>  
 <span data-ttu-id="f129a-125">[Редактор задачи "запрос интеллектуального анализа данных" &#40;вкладка "запрос"&#41;](../../2014/integration-services/data-mining-query-task-editor-query-tab.md) </span><span class="sxs-lookup"><span data-stu-id="f129a-125">[Data Mining Query Task Editor &#40;Query Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-query-tab.md) </span></span>  
 [<span data-ttu-id="f129a-126">Конструктора моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="f129a-126">Data Mining Designer</span></span>](https://docs.microsoft.com/analysis-services/data-mining/data-mining-designer)  
  
  
