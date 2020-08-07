---
title: Редактор задачи «Запрос интеллектуального анализа данных» (вкладка «Модель интеллектуального анализа») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dmquerytask.miningmodel.f1
helpviewer_keywords:
- Data Mining Query Task Editor
ms.assetid: 0ede9b86-be27-471e-b012-22a65adce579
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 794365c8d15ff9725fc385bb43d51e70ffa529b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734393"
---
# <a name="data-mining-query-task-editor-mining-model-tab"></a><span data-ttu-id="aae9d-102">Редактор задачи «Запрос интеллектуального анализа данных» (вкладка «Модель интеллектуального анализа данных»)</span><span class="sxs-lookup"><span data-stu-id="aae9d-102">Data Mining Query Task Editor (Mining Model Tab)</span></span>
  <span data-ttu-id="aae9d-103">Вкладка **Модель интеллектуального анализа данных** диалогового окна **Задача «Запрос интеллектуального анализа данных»** позволяет выбрать используемые структуру и модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="aae9d-103">Use the **Mining Model** tab of the **Data Mining Query Task** dialog box to specify the mining structure and mining model to use.</span></span>  
  
 <span data-ttu-id="aae9d-104">Сведения об интеллектуальном анализе данных в пакетах см. в разделах [Задача "Запрос интеллектуального анализа данных"](control-flow/data-mining-query-task.md) и [Решения для интеллектуального анализа данных](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span><span class="sxs-lookup"><span data-stu-id="aae9d-104">To learn about implementing data mining in packages, see [Data Mining Query Task](control-flow/data-mining-query-task.md) and [Data Mining Solutions](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="aae9d-105">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="aae9d-105">General Options</span></span>  
 <span data-ttu-id="aae9d-106">**Имя**</span><span class="sxs-lookup"><span data-stu-id="aae9d-106">**Name**</span></span>  
 <span data-ttu-id="aae9d-107">Задайте уникальное имя для задачи «Запрос интеллектуального анализа данных».</span><span class="sxs-lookup"><span data-stu-id="aae9d-107">Provide a unique name for the Data Mining Query task.</span></span> <span data-ttu-id="aae9d-108">Это имя используется в качестве метки для значка задачи.</span><span class="sxs-lookup"><span data-stu-id="aae9d-108">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aae9d-109">Имена задач в пределах пакета должны быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="aae9d-109">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="aae9d-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="aae9d-110">**Description**</span></span>  
 <span data-ttu-id="aae9d-111">Введите описание задачи «Запрос интеллектуального анализа данных».</span><span class="sxs-lookup"><span data-stu-id="aae9d-111">Type a description of the Data Mining Query task.</span></span>  
  
## <a name="mining-model-tab-options"></a><span data-ttu-id="aae9d-112">Параметры вкладки «Модель интеллектуального анализа данных»</span><span class="sxs-lookup"><span data-stu-id="aae9d-112">Mining Model Tab Options</span></span>  
 <span data-ttu-id="aae9d-113">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="aae9d-113">**Connection**</span></span>  
 <span data-ttu-id="aae9d-114">Выберите из списка диспетчер соединений служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] или нажмите кнопку **Создать** для создания нового диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="aae9d-114">Select an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] connection manager in the list or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="aae9d-115">**См. также:**  [Добавление диспетчера соединений служб Analysis Services](connection-manager/analysis-services-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="aae9d-115">**Related Topics:**  [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md)</span></span>  
  
 <span data-ttu-id="aae9d-116">**Создать**</span><span class="sxs-lookup"><span data-stu-id="aae9d-116">**New**</span></span>  
 <span data-ttu-id="aae9d-117">Создает новый диспетчер соединений служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aae9d-117">Create a new [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] connection manager.</span></span>  
  
 <span data-ttu-id="aae9d-118">**См. также:** [Добавление диалогового окна "Диспетчер соединений со службами Analysis Services" в справочнике по пользовательскому интерфейсу](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)</span><span class="sxs-lookup"><span data-stu-id="aae9d-118">**Related Topics:** [Add Analysis Services Connection Manager Dialog Box UI Reference](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)</span></span>  
  
 <span data-ttu-id="aae9d-119">**Структура интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="aae9d-119">**Mining structure**</span></span>  
 <span data-ttu-id="aae9d-120">Выберите структуру интеллектуального анализа из данного списка.</span><span class="sxs-lookup"><span data-stu-id="aae9d-120">Select a mining structure in the list.</span></span>  
  
 <span data-ttu-id="aae9d-121">**Модели интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="aae9d-121">**Mining models**</span></span>  
 <span data-ttu-id="aae9d-122">Выберите модель интеллектуального анализа данных, построенную на выбранной структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="aae9d-122">Select a mining model built on the selected mining structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aae9d-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="aae9d-123">See Also</span></span>  
 <span data-ttu-id="aae9d-124">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="aae9d-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="aae9d-125">[Редактор задачи "запрос интеллектуального анализа данных" &#40;вкладка "запрос"&#41;](../../2014/integration-services/data-mining-query-task-editor-query-tab.md) </span><span class="sxs-lookup"><span data-stu-id="aae9d-125">[Data Mining Query Task Editor &#40;Query Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-query-tab.md) </span></span>  
 <span data-ttu-id="aae9d-126">[Редактор задачи "запрос интеллектуального анализа данных" &#40;вкладка "выходные данные"&#41;](../../2014/integration-services/data-mining-query-task-editor-output-tab.md) </span><span class="sxs-lookup"><span data-stu-id="aae9d-126">[Data Mining Query Task Editor &#40;Output Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-output-tab.md) </span></span>  
 [<span data-ttu-id="aae9d-127">Конструктора моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="aae9d-127">Data Mining Designer</span></span>](https://docs.microsoft.com/analysis-services/data-mining/data-mining-designer)  
  
  
