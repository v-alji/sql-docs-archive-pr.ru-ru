---
title: Извлечение данных с помощью XML-источника | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- extracting data [Integration Services]
- sources [Integration Services], XML
- XML source [Integration Services]
ms.assetid: 5d5be54c-2b7e-4957-9193-c5ea5c5d6d15
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 57758353c476badfba4cb12a1ef6b5101f16735d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751327"
---
# <a name="extract-data-by-using-the-xml-source"></a><span data-ttu-id="f23a7-102">Извлечение данных с помощью XML-источника</span><span class="sxs-lookup"><span data-stu-id="f23a7-102">Extract Data by Using the XML Source</span></span>
  <span data-ttu-id="f23a7-103">Чтобы добавить и настроить источник XML, пакет должен уже содержать не менее одной задачи потока данных.</span><span class="sxs-lookup"><span data-stu-id="f23a7-103">To add and configure an XML source, the package must already include at least one Data Flow task.</span></span>  
  
### <a name="to-extract-data-using-an-xml-source"></a><span data-ttu-id="f23a7-104">Извлечение данных с использованием XML-источника</span><span class="sxs-lookup"><span data-stu-id="f23a7-104">To extract data using an XML source</span></span>  
  
1.  <span data-ttu-id="f23a7-105">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="f23a7-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="f23a7-106">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="f23a7-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="f23a7-107">Перейдите на вкладку **Поток данных** , затем из **области элементов**перетащите источник XML в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="f23a7-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the XML source to the design surface.</span></span>  
  
4.  <span data-ttu-id="f23a7-108">Дважды щелкните источник XML.</span><span class="sxs-lookup"><span data-stu-id="f23a7-108">Double-click the XML source.</span></span>  
  
5.  <span data-ttu-id="f23a7-109">В **Редакторе XML-источника**на странице **Диспетчер соединений** выберите режим доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="f23a7-109">In the **XML Source Editor**, on the **Connection Manager** page, select a data access mode:</span></span>  
  
    -   <span data-ttu-id="f23a7-110">Для режима получения доступа **Расположение XML-файла** нажмите кнопку **Обзор** и найдите папку, содержащую XML-файл.</span><span class="sxs-lookup"><span data-stu-id="f23a7-110">For the **XML file location** access mode, click **Browse** and locate the folder that contains the XML file.</span></span>  
  
    -   <span data-ttu-id="f23a7-111">Для режима получения доступа **XML-файл из переменной** выберите пользовательскую переменную, содержащую путь XML-файла.</span><span class="sxs-lookup"><span data-stu-id="f23a7-111">For the **XML file from variable** access mode, select the user-defined variable that contains the path of the XML file.</span></span>  
  
    -   <span data-ttu-id="f23a7-112">Для режима получения доступа **XML-данные из переменной** выберите пользовательскую переменную, содержащую XML-данные.</span><span class="sxs-lookup"><span data-stu-id="f23a7-112">For the **XML data from variable** access mode, select the user-defined variable that contains the XML data.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f23a7-113">Переменные должны быть определены в области задачи потока данных, которая содержит источник XML, или в области пакета. Кроме того, переменная должна иметь строковый тип данных.</span><span class="sxs-lookup"><span data-stu-id="f23a7-113">The variables must be defined in the scope of the Data Flow task that contains the XML source, or in the scope of the package; additionally, the variable must have a string data type.</span></span>  
  
6.  <span data-ttu-id="f23a7-114">Чтобы указать, что XML-документ включает сведения о схеме, по своему усмотрению выберите **Использовать встроенную схему** .</span><span class="sxs-lookup"><span data-stu-id="f23a7-114">Optionally, select **Use inline schema** to indicate that the XML document includes schema information.</span></span>  
  
7.  <span data-ttu-id="f23a7-115">Чтобы указать внешний язык определения XML-схемы (XSD) для XML-файла, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="f23a7-115">To specify an external XML Schema definition language (XSD) schema for the XML file, do one of the following:</span></span>  
  
    -   <span data-ttu-id="f23a7-116">Нажмите кнопку **Обзор** для нахождения существующего XSD-файла.</span><span class="sxs-lookup"><span data-stu-id="f23a7-116">Click **Browse** to locate an existing XSD file.</span></span>  
  
    -   <span data-ttu-id="f23a7-117">Нажмите кнопку **Сформировать XSD** , чтобы сформировать XSD из XML-файла.</span><span class="sxs-lookup"><span data-stu-id="f23a7-117">Click **Generate XSD** to create an XSD from the XML file.</span></span>  
  
8.  <span data-ttu-id="f23a7-118">Чтобы обновить имена входных столбцов, щелкните **Столбцы** и отредактируйте значения в списке **Выходной столбец** .</span><span class="sxs-lookup"><span data-stu-id="f23a7-118">To update the names of output columns, click **Columns** and edit the values in the **Output Column** list.</span></span>  
  
9. <span data-ttu-id="f23a7-119">Чтобы настроить выход ошибок, щелкните **Вывод ошибок**.</span><span class="sxs-lookup"><span data-stu-id="f23a7-119">To configure the error output, click **Error Output**.</span></span> <span data-ttu-id="f23a7-120">Дополнительные сведения см. в разделе [Настройка вывода ошибок в компоненте потока данных](../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="f23a7-120">For more information, see [Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
10. <span data-ttu-id="f23a7-121">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f23a7-121">Click **OK**.</span></span>  
  
11. <span data-ttu-id="f23a7-122">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="f23a7-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f23a7-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="f23a7-123">See Also</span></span>  
 <span data-ttu-id="f23a7-124">[XML-источник](xml-source.md) </span><span class="sxs-lookup"><span data-stu-id="f23a7-124">[XML Source](xml-source.md) </span></span>  
 <span data-ttu-id="f23a7-125">[Преобразования служб Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="f23a7-125">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="f23a7-126">[Пути служб Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="f23a7-126">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="f23a7-127">Задача потока данных</span><span class="sxs-lookup"><span data-stu-id="f23a7-127">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
