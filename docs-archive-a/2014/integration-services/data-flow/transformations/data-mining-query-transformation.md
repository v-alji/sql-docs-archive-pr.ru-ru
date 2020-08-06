---
title: Преобразование "Запрос интеллектуального анализа данных" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingquerytrans.f1
helpviewer_keywords:
- Data Mining Query transformation
- prediction queries [Integration Services]
ms.assetid: 7960133b-a3e1-48af-ba43-55ed78c38e71
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 278fdc3b1abd38b63f01e967e28d11983a09e682
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655284"
---
# <a name="data-mining-query-transformation"></a><span data-ttu-id="29704-102">преобразование «Запрос интеллектуального анализа данных»</span><span class="sxs-lookup"><span data-stu-id="29704-102">Data Mining Query Transformation</span></span>
  <span data-ttu-id="29704-103">Преобразование «Запрос интеллектуального анализа данных» выполняет прогнозирующие запросы на основе моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="29704-103">The Data Mining Query transformation performs prediction queries against data mining models.</span></span> <span data-ttu-id="29704-104">Это преобразование содержит построитель запросов для создания запросов расширений интеллектуального анализа данных (DMX).</span><span class="sxs-lookup"><span data-stu-id="29704-104">This transformation contains a query builder for creating Data Mining Extensions (DMX) queries.</span></span> <span data-ttu-id="29704-105">С помощью построителя запросов можно создавать пользовательские инструкции на языке расширения интеллектуального анализа данных (DMX) для оценки входа преобразования в соответствии с текущей моделью интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="29704-105">The query builder lets you create custom statements for evaluating the transformation input data against an existing mining model using the DMX language.</span></span> <span data-ttu-id="29704-106">Дополнительные сведения см. в разделе [Справочник по расширениям интеллектуального анализа данных](/sql/dmx/data-mining-extensions-dmx-reference).</span><span class="sxs-lookup"><span data-stu-id="29704-106">For more information, see [Data Mining Extensions &#40;DMX&#41; Reference](/sql/dmx/data-mining-extensions-dmx-reference).</span></span>  
  
 <span data-ttu-id="29704-107">Одно преобразование может выполнять несколько прогнозирующих запросов, если их модели созданы на основе одной и той же структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="29704-107">One transformation can execute multiple prediction queries if the models are built on the same data mining structure.</span></span> <span data-ttu-id="29704-108">Дополнительные сведения см. в разделе [интерфейсы запросов интеллектуального анализа данных](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools).</span><span class="sxs-lookup"><span data-stu-id="29704-108">For more information, see [Data Mining Query Interfaces](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools).</span></span>  
  
## <a name="configuration-of-the-data-mining-query-transformation"></a><span data-ttu-id="29704-109">Настройка преобразования «Запрос интеллектуального анализа данных»</span><span class="sxs-lookup"><span data-stu-id="29704-109">Configuration of the Data Mining Query Transformation</span></span>  
 <span data-ttu-id="29704-110">Преобразование «Запрос интеллектуального анализа данных» использует диспетчер соединений служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , чтобы подключить проект служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] или экземпляр служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , содержащие структуры и модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="29704-110">The Data Mining Query transformation uses an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] that contains the mining structure and mining models.</span></span> <span data-ttu-id="29704-111">Дополнительные сведения см. в статье [Analysis Services Connection Manager](../../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="29704-111">For more information, see [Analysis Services Connection Manager](../../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="29704-112">Это преобразование имеет один вход и один выход.</span><span class="sxs-lookup"><span data-stu-id="29704-112">This transformation has one input and one output.</span></span> <span data-ttu-id="29704-113">Вывод ошибок не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="29704-113">It does not support an error output.</span></span>  
  
 <span data-ttu-id="29704-114">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="29704-114">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="29704-115">Дополнительные сведения о свойствах, которые можно настроить при помощи диалогового окна **Редактор преобразования «Запрос интеллектуального анализа данных»** , см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="29704-115">For more information about the properties that you can set in the **Data Mining Query Transformation Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="29704-116">Редактор преобразования "Запрос интеллектуального анализа данных" (вкладка "Модель интеллектуального анализа данных")</span><span class="sxs-lookup"><span data-stu-id="29704-116">Data Mining Query Transformation Editor &#40;Mining Model Tab&#41;</span></span>](../../data-mining-query-transformation-editor-mining-model-tab.md)  
  
-   [<span data-ttu-id="29704-117">Редактор преобразования "Запрос интеллектуального анализа данных" (вкладка "Модель интеллектуального анализа данных")</span><span class="sxs-lookup"><span data-stu-id="29704-117">Data Mining Query Transformation Editor &#40;Mining Model Tab&#41;</span></span>](../../data-mining-query-transformation-editor-mining-model-tab.md)  
  
 <span data-ttu-id="29704-118">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="29704-118">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="29704-119">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="29704-119">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="29704-120">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="29704-120">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="29704-121">Пользовательские свойства преобразований</span><span class="sxs-lookup"><span data-stu-id="29704-121">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="29704-122">Дополнительные сведения о настройке свойств см. в разделе [Установление свойств компонента потока данных](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="29704-122">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
