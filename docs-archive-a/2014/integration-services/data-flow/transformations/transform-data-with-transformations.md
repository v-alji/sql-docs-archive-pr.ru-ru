---
title: Преобразование данных с помощью преобразований | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data flow [Integration Services], transformations
- transformations [Integration Services], about transformations
- transforming data [Integration Services]
ms.assetid: e1340b6f-ef75-4b14-af6f-823586eff0ed
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 952d8ea4eeea2dd8010a17a2b3deba41447b6231
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668450"
---
# <a name="transform-data-with-transformations"></a><span data-ttu-id="414a1-102">Преобразование данных с помощью преобразований</span><span class="sxs-lookup"><span data-stu-id="414a1-102">Transform Data with Transformations</span></span>
  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="414a1-103">включают три различных типа компонентов потока данных: источники, преобразования и назначения.</span><span class="sxs-lookup"><span data-stu-id="414a1-103">includes three types of data flow components: sources, transformations, and destinations.</span></span>  
  
 <span data-ttu-id="414a1-104">На следующей диаграмме показан простой поток данных, который имеет источник, два преобразования и назначение.</span><span class="sxs-lookup"><span data-stu-id="414a1-104">The following diagram shows a simple data flow that has a source, two transformations, and a destination.</span></span>  
  
 <span data-ttu-id="414a1-105">![Data flow](../../media/mw-dts-08.gif "Поток данных") (Поток данных)</span><span class="sxs-lookup"><span data-stu-id="414a1-105">![Data flow](../../media/mw-dts-08.gif "Data flow")</span></span>  
  
 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="414a1-106">обеспечивают следующие функциональные возможности:</span><span class="sxs-lookup"><span data-stu-id="414a1-106">transformations provide the following functionality:</span></span>  
  
-   <span data-ttu-id="414a1-107">разделение, копирование и объединение наборов строк и выполнение операций уточняющего запроса;</span><span class="sxs-lookup"><span data-stu-id="414a1-107">Splitting, copying, and merging rowsets and performing lookup operations.</span></span>  
  
-   <span data-ttu-id="414a1-108">обновление значений столбца и создание новых столбцов путем применения преобразований, таких как изменение нижнего регистра в верхний регистр;</span><span class="sxs-lookup"><span data-stu-id="414a1-108">Updating column values and creating new columns by applying transformations such as changing lowercase to uppercase.</span></span>  
  
-   <span data-ttu-id="414a1-109">выполнение операций бизнес-аналитики, таких как очистка данных, интеллектуальный анализ текста или выполнение запросов прогноза интеллектуального анализа данных;</span><span class="sxs-lookup"><span data-stu-id="414a1-109">Performing business intelligence operations such as cleaning data, mining text, or running data mining prediction queries.</span></span>  
  
-   <span data-ttu-id="414a1-110">создание новых наборов строк, содержащих статистические или упорядоченные значения, образцы данных, сведенные данные или данные, сведение которых отменено;</span><span class="sxs-lookup"><span data-stu-id="414a1-110">Creating new rowsets that consist of aggregate or sorted values, sample data, or pivoted and unpivoted data.</span></span>  
  
-   <span data-ttu-id="414a1-111">выполнение задач, таких как экспорт и импорт данных, предоставление данных аудита, работа с медленно изменяющимися измерениями.</span><span class="sxs-lookup"><span data-stu-id="414a1-111">Performing tasks such as exporting and importing data, providing audit information, and working with slowly changing dimensions.</span></span>  
  
 <span data-ttu-id="414a1-112">Дополнительные сведения см. в статье [Integration Services Transformations](integration-services-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="414a1-112">For more information, see [Integration Services Transformations](integration-services-transformations.md).</span></span>  
  
 <span data-ttu-id="414a1-113">Также можно создавать пользовательские преобразования.</span><span class="sxs-lookup"><span data-stu-id="414a1-113">You can also write custom transformations.</span></span> <span data-ttu-id="414a1-114">Дополнительные сведения см. в разделах [Разработка пользовательского компонента потока данных](../../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) и [Разработка компонентов потока данных определенных типов](../../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md).</span><span class="sxs-lookup"><span data-stu-id="414a1-114">For more information, see [Developing a Custom Data Flow Component](../../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) and [Developing Specific Types of Data Flow Components](../../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md).</span></span>  
  
 <span data-ttu-id="414a1-115">После добавления преобразования к конструктору потока данных, но до настройки преобразования нужно подключить преобразование к потоку данных путем подключения к входу данного преобразования выхода другого преобразования или источника в потоке данных.</span><span class="sxs-lookup"><span data-stu-id="414a1-115">After you add the transformation to the data flow designer, but before you configure the transformation, you connect the transformation to the data flow by connecting the output of another transformation or source in the data flow to the input of this transformation.</span></span> <span data-ttu-id="414a1-116">Соединитель компонентов потока данных называется путем.</span><span class="sxs-lookup"><span data-stu-id="414a1-116">The connector between two data flow components is called a path.</span></span> <span data-ttu-id="414a1-117">Дополнительные сведения о соединении компонентов и работе с путями см. в разделе [Соединение компонентов с путями](../../connect-components-with-paths.md).</span><span class="sxs-lookup"><span data-stu-id="414a1-117">For more information about connecting components and working with paths, see [Connect Components with Paths](../../connect-components-with-paths.md).</span></span>  
  
### <a name="to-add-a-transformation-to-a-data-flow"></a><span data-ttu-id="414a1-118">Добавление преобразования к потоку данных</span><span class="sxs-lookup"><span data-stu-id="414a1-118">To add a transformation to a data flow</span></span>  
  
-   [<span data-ttu-id="414a1-119">Добавление или удаление компонента в потоке данных</span><span class="sxs-lookup"><span data-stu-id="414a1-119">Add or Delete a Component in a Data Flow</span></span>](../add-or-delete-a-component-in-a-data-flow.md)  
  
### <a name="to-connect-a-transformation-to-a-data-flow"></a><span data-ttu-id="414a1-120">Подключение преобразования к потоку данных</span><span class="sxs-lookup"><span data-stu-id="414a1-120">To connect a transformation to a data flow</span></span>  
  
-   [<span data-ttu-id="414a1-121">Соединение компонентов в потоке данных</span><span class="sxs-lookup"><span data-stu-id="414a1-121">Connect Components in a Data Flow</span></span>](../connect-components-in-a-data-flow.md)  
  
### <a name="to-set-the-properties-of-a-transformation"></a><span data-ttu-id="414a1-122">Установка свойства преобразования</span><span class="sxs-lookup"><span data-stu-id="414a1-122">To set the properties of a transformation</span></span>  
  
-   [<span data-ttu-id="414a1-123">Установление свойств компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="414a1-123">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="see-also"></a><span data-ttu-id="414a1-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="414a1-124">See Also</span></span>  
 <span data-ttu-id="414a1-125">[Задача потока данных](../../control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="414a1-125">[Data Flow Task](../../control-flow/data-flow-task.md) </span></span>  
 <span data-ttu-id="414a1-126">[Поток данных](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="414a1-126">[Data Flow](../data-flow.md) </span></span>  
 <span data-ttu-id="414a1-127">[Соединение компонентов с путями](../../connect-components-with-paths.md) </span><span class="sxs-lookup"><span data-stu-id="414a1-127">[Connect Components with Paths](../../connect-components-with-paths.md) </span></span>  
 <span data-ttu-id="414a1-128">[Обработка ошибок в данных](../error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="414a1-128">[Error Handling in Data](../error-handling-in-data.md) </span></span>  
 [<span data-ttu-id="414a1-129">Поток данных</span><span class="sxs-lookup"><span data-stu-id="414a1-129">Data Flow</span></span>](../data-flow.md)  
  
  
