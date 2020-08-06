---
title: Основные сведения о синхронных и асинхронных преобразованиях | Документы Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- transformations [Integration Services], synchronous and asynchronous
- asynchronous transformations [Integration Services]
- data flow components [Integration Services], synchronous and asynchronous
- synchronous transformations [Integration Services]
ms.assetid: 0bc2bda5-3f8a-49c2-aaf1-01dbe4c3ebba
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 386d3786cb969ad93a92b8ebae2a41f046fb39bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656458"
---
# <a name="understanding-synchronous-and-asynchronous-transformations"></a><span data-ttu-id="14462-102">Основные сведения о синхронных и асинхронных преобразованиях</span><span class="sxs-lookup"><span data-stu-id="14462-102">Understanding Synchronous and Asynchronous Transformations</span></span>
  <span data-ttu-id="14462-103">Чтобы понять разницу между синхронным и асинхронным преобразованием в службах [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], проще всего начать с основных сведений о синхронном преобразовании.</span><span class="sxs-lookup"><span data-stu-id="14462-103">To understand the difference between a synchronous and an asynchronous transformation in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], it is easiest to start with an understanding of a synchronous transformation.</span></span> <span data-ttu-id="14462-104">Если синхронное преобразование соответствует требованиям пользователя, может потребоваться асинхронное преобразование.</span><span class="sxs-lookup"><span data-stu-id="14462-104">If a synchronous transformation does not meet your needs, your design might require an asynchronous transformation.</span></span>

## <a name="synchronous-transformations"></a><span data-ttu-id="14462-105">Синхронные преобразования</span><span class="sxs-lookup"><span data-stu-id="14462-105">Synchronous Transformations</span></span>
 <span data-ttu-id="14462-106">При синхронном преобразовании входящие строки обрабатываются и передаются в поток данных по одной строке за один раз.</span><span class="sxs-lookup"><span data-stu-id="14462-106">A synchronous transformation processes incoming rows and passes them on in the data flow one row at a time.</span></span> <span data-ttu-id="14462-107">Выход происходит синхронно с входом, то есть одновременно.</span><span class="sxs-lookup"><span data-stu-id="14462-107">Output is synchronous with input, meaning that it occurs at the same time.</span></span> <span data-ttu-id="14462-108">По этой причине для обработки заданной строки преобразованию не требуются сведения о других строках в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="14462-108">Therefore, to process a given row, the transformation does not need information about other rows in the data set.</span></span> <span data-ttu-id="14462-109">В реальном применении строки группируются в буферы по мере передачи из одного компонента в следующий, но эти буферы прозрачны для пользователя, и можно считать, что каждая строка обрабатывается отдельно.</span><span class="sxs-lookup"><span data-stu-id="14462-109">In the actual implementation, rows are grouped into buffers as they pass from one component to the next, but these buffers are transparent to the user, and you can assume that each row is processed separately.</span></span>

 <span data-ttu-id="14462-110">Примером синхронного преобразования является преобразование «Конвертация данных».</span><span class="sxs-lookup"><span data-stu-id="14462-110">An example of a synchronous transformation is the Data Conversion transformation.</span></span> <span data-ttu-id="14462-111">Для каждой входящей строки преобразуется значение в указанном столбце, и строка перенаправляется дальше.</span><span class="sxs-lookup"><span data-stu-id="14462-111">For each incoming row, it converts the value in the specified column and sends the row on its way.</span></span> <span data-ttu-id="14462-112">Каждая отдельная операция конвертации выполняется независимо от всех других строк в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="14462-112">Each discrete conversion operation is independent of all the other rows in the data set.</span></span>

 <span data-ttu-id="14462-113">В [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] сценариях и программировании вы указываете синхронное преобразование путем поиска идентификатора входных данных компонента и присвоения его `SynchronousInputID` свойству выходов компонента.</span><span class="sxs-lookup"><span data-stu-id="14462-113">In [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] scripting and programming, you specify a synchronous transformation by looking up the ID of a component's input and assigning it to the `SynchronousInputID` property of the component's outputs.</span></span> <span data-ttu-id="14462-114">Подсистема обработки потока данных обрабатывает каждую строку входных данных и отправляет ее автоматически в указанное место назначения.</span><span class="sxs-lookup"><span data-stu-id="14462-114">This tells the data flow engine to process each row from the input and send each row automatically to the specified outputs.</span></span> <span data-ttu-id="14462-115">Если нужно, чтобы каждая строка направлялась на каждый выход, необходимо создать дополнительный код для вывода данных.</span><span class="sxs-lookup"><span data-stu-id="14462-115">If you want every row to go to every output, you do not have to write any additional code to output the data.</span></span> <span data-ttu-id="14462-116">При использовании свойства `ExclusionGroup` для указания, что строки должны направляться на тот или иной выход, как при преобразовании «Условное разбиение», необходимо вызвать метод `DirectRow`, чтобы выбрать место назначения для каждой строки.</span><span class="sxs-lookup"><span data-stu-id="14462-116">If you use the `ExclusionGroup` property to specify that rows should only go to one or another of a group of outputs, as in the Conditional Split transformation, you must call the `DirectRow` method to select the appropriate destination for each row.</span></span> <span data-ttu-id="14462-117">Для выхода ошибок необходимо вызвать метод `DirectErrorRow`, чтобы направлять проблемные строки на выход ошибок, а не на выход по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="14462-117">When you have an error output, you must call `DirectErrorRow` to send rows with problems to the error output instead of the default output.</span></span>

## <a name="asynchronous-transformations"></a><span data-ttu-id="14462-118">Асинхронные преобразования</span><span class="sxs-lookup"><span data-stu-id="14462-118">Asynchronous Transformations</span></span>
 <span data-ttu-id="14462-119">Если нет возможности обрабатывать каждую строку независимо от всех остальных строк, может потребоваться асинхронное преобразование.</span><span class="sxs-lookup"><span data-stu-id="14462-119">You might decide that your design requires an asynchronous transformation when it is not possible to process each row independently of all other rows.</span></span> <span data-ttu-id="14462-120">Иными словами, нельзя передавать каждую строку в поток данных по мере обработки, а вместо этого требуется выводить данные асинхронно или не одновременно с входом.</span><span class="sxs-lookup"><span data-stu-id="14462-120">In other words, you cannot pass each row along in the data flow as it is processed, but instead must output data asynchronously, or at a different time, than the input.</span></span> <span data-ttu-id="14462-121">Например, в следующих сценариях требуется асинхронное преобразование.</span><span class="sxs-lookup"><span data-stu-id="14462-121">For example, the following scenarios require an asynchronous transformation:</span></span>

-   <span data-ttu-id="14462-122">Компоненту требуется получить несколько буферов данных, прежде чем выполнить обработку.</span><span class="sxs-lookup"><span data-stu-id="14462-122">The component has to acquire multiple buffers of data before it can perform its processing.</span></span> <span data-ttu-id="14462-123">Примером является преобразование «Сортировка», при котором компоненту нужно обработать полный набор строк за одну операцию.</span><span class="sxs-lookup"><span data-stu-id="14462-123">An example is the Sort transformation, where the component has to process the complete set of rows in a single operation.</span></span>

-   <span data-ttu-id="14462-124">Компонент должен объединить строки из нескольких источников.</span><span class="sxs-lookup"><span data-stu-id="14462-124">The component has to combine rows from multiple inputs.</span></span> <span data-ttu-id="14462-125">Примером является преобразование «Слияние», при котором компонент должен исследовать несколько строк из каждого источника и объединить их в порядке сортировки.</span><span class="sxs-lookup"><span data-stu-id="14462-125">An example is the Merge transformation, where the component has to examine multiple rows from each input and then merge them in sorted order.</span></span>

-   <span data-ttu-id="14462-126">Между входными и выходными строками нет однозначного соответствия.</span><span class="sxs-lookup"><span data-stu-id="14462-126">There is no one-to-one correspondence between input rows and output rows.</span></span> <span data-ttu-id="14462-127">Примером является преобразование «Статистическая обработка», при котором компонент должен добавить к выходным данным строку, содержащую вычисленные статистические значения.</span><span class="sxs-lookup"><span data-stu-id="14462-127">An example is the Aggregate transformation, where the component has to add a row to the output to hold the computed aggregate values.</span></span>

 <span data-ttu-id="14462-128">При создании сценариев и программ для служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] асинхронное преобразование указывается следующим образом: значение 0 назначается свойству `SynchronousInputID` выходных данных компонента.</span><span class="sxs-lookup"><span data-stu-id="14462-128">In [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] scripting and programming, you specify an asynchronous transformation by assigning a value of 0 to the `SynchronousInputID` property of the component's outputs.</span></span> <span data-ttu-id="14462-129">.</span><span class="sxs-lookup"><span data-stu-id="14462-129">.</span></span> <span data-ttu-id="14462-130">Подсистема обработки потока данных не отправляет каждую строку автоматически на выход.</span><span class="sxs-lookup"><span data-stu-id="14462-130">This tells the data flow engine not to send each row automatically to the outputs.</span></span> <span data-ttu-id="14462-131">Затем требуется написать код для явной отправки каждой строки на соответствующий выход, добавив ее в новый выходной буфер, созданный для выходных данных асинхронного преобразования.</span><span class="sxs-lookup"><span data-stu-id="14462-131">Then you must write code to send each row explicitly to the appropriate output by adding it to the new output buffer that is created for the output of an asynchronous transformation.</span></span>

> [!NOTE]
>  <span data-ttu-id="14462-132">Поскольку компонент-источник тоже должен явно добавить каждую строку, считываемую из источника данных, в выходные буферы, действия источника напоминают преобразование с асинхронным выходом.</span><span class="sxs-lookup"><span data-stu-id="14462-132">Since a source component must also explicitly add each row that it reads from the data source to its output buffers, a source resembles a transformation with asynchronous outputs.</span></span>

 <span data-ttu-id="14462-133">Также можно создать асинхронное преобразование, имитирующее синхронное преобразование, путем явного копирования каждой входной строки в выходные данные.</span><span class="sxs-lookup"><span data-stu-id="14462-133">It would also be possible to create an asynchronous transformation that emulates a synchronous transformation by explicitly copying each input row to the output.</span></span> <span data-ttu-id="14462-134">С помощью этого подхода можно переименовывать столбцы или преобразовывать типы или форматы данных.</span><span class="sxs-lookup"><span data-stu-id="14462-134">By using this approach, you could rename columns or convert data types or formats.</span></span> <span data-ttu-id="14462-135">Однако этот подход снижает производительность.</span><span class="sxs-lookup"><span data-stu-id="14462-135">However this approach degrades performance.</span></span> <span data-ttu-id="14462-136">Можно получить те же результаты с более высокой производительностью, используя встроенные компоненты служб Integration Services, такие как «Копирование столбца» или «Конвертация данных».</span><span class="sxs-lookup"><span data-stu-id="14462-136">You can achieve the same results with better performance by using built-in Integration Services components, such as Copy Column or Data Conversion.</span></span>

<span data-ttu-id="14462-137">![Значок Integration Services (маленький)](media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="14462-137">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="14462-138">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="14462-138">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="14462-139">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="14462-139">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="14462-140">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="14462-140">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="14462-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="14462-141">See Also</span></span>
 <span data-ttu-id="14462-142">[Создание синхронного преобразования с помощью компонента скрипта](data-flow/transformations/script-component.md) [Создание асинхронного преобразования с помощью компонента скрипта](extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md) [Разработка пользовательского компонента преобразования с помощью синхронных выходных](extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md) данных [Разработка пользовательского компонента преобразования с асинхронными выходами](extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md)</span><span class="sxs-lookup"><span data-stu-id="14462-142">[Creating a Synchronous Transformation with the Script Component](data-flow/transformations/script-component.md) [Creating an Asynchronous Transformation with the Script Component](extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md) [Developing a Custom Transformation Component with Synchronous Outputs](extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md) [Developing a Custom Transformation Component with Asynchronous Outputs](extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md)</span></span>

