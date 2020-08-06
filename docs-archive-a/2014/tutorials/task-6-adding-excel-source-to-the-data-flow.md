---
title: Задача 6. Добавление источника Excel в поток данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 0209055e-cb6b-4a07-909e-836596727a2c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ae183dee04619a407655026a49b189f7bb3ac6fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666909"
---
# <a name="task-6-adding-excel-source-to-the-data-flow"></a><span data-ttu-id="9a8cc-102">Задача 6. Добавление в поток данных источника Excel</span><span class="sxs-lookup"><span data-stu-id="9a8cc-102">Task 6: Adding Excel Source to the Data Flow</span></span>
  <span data-ttu-id="9a8cc-103">В этой задаче источник Excel будет добавлен в поток данных, что позволит считывать данные поставщиков из исходного файла Excel.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-103">In this task, you add an Excel Source to the data flow to read supplier data from the source Excel file.</span></span> <span data-ttu-id="9a8cc-104">Источник Excel извлекает данные из листов или диапазонов в книгах Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-104">The Excel Source extracts data from worksheets or ranges in Microsoft Excel workbooks.</span></span> <span data-ttu-id="9a8cc-105">Дополнительные сведения см. в разделе [Источник Excel](../integration-services/data-flow/excel-source.md) .</span><span class="sxs-lookup"><span data-stu-id="9a8cc-105">See [Excel Source](../integration-services/data-flow/excel-source.md) topic for more details.</span></span>

1.  <span data-ttu-id="9a8cc-106">Перетащите **Источник Excel** из области **Другие источники** на **панели элементов служб SSIS** на вкладке **Поток данных** .</span><span class="sxs-lookup"><span data-stu-id="9a8cc-106">Drag-drop **Excel Source** from **Other Sources** in **SSIS Toolbox** to the **Data Flow** tab.</span></span>

2.  <span data-ttu-id="9a8cc-107">Щелкните правой кнопкой мыши **источник Excel** на вкладке **Поток данных** и нажмите кнопку **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-107">Right-click on **Excel Source** in the **Data Flow** tab, and click **Rename**.</span></span>

3.  <span data-ttu-id="9a8cc-108">Введите **Считывание данных о поставщиках из файла Excel** и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-108">Type **Read Supplier Data from Excel File** and press **ENTER**.</span></span>

4.  <span data-ttu-id="9a8cc-109">Дважды щелкните файл **Считывание данных о поставщиках из файла Excel** , чтобы открыть диалоговое окно **Редактор источника «Excel»** .</span><span class="sxs-lookup"><span data-stu-id="9a8cc-109">Double-click **Read Supplier Data from Excel File** to launch the **Excel Source Editor** dialog box.</span></span>

5.  <span data-ttu-id="9a8cc-110">В диалоговом окне **Редактор источника «Excel»** нажмите **Создать** , чтобы создать соединение Excel.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-110">In the **Excel Source Editor** dialog box, click **New** to create an Excel connection.</span></span>

6.  <span data-ttu-id="9a8cc-111">В диалоговом окне **Диспетчер соединений Excel** выберите **Обзор**и выберите файл **Suppliers.xls** в папке **Учебник EIM** .</span><span class="sxs-lookup"><span data-stu-id="9a8cc-111">In the **Excel Connection Manager** dialog box, click **Browse**, and then select the **Suppliers.xls** file in the **EIM Tutorial** folder.</span></span> <span data-ttu-id="9a8cc-112">Убедитесь, что выбрано значение **Microsoft Excel 97-2003** в поле **Версия Excel** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-112">Confirm that **Microsoft Excel 97-2003** is selected in the **Excel Version** box and then click **OK**.</span></span>

     <span data-ttu-id="9a8cc-113">![Диалоговое окно «Диспетчер соединений» Excel](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-01.jpg "Диалоговое окно «Диспетчер соединений» Excel")</span><span class="sxs-lookup"><span data-stu-id="9a8cc-113">![Excel Connection Manager Dialog Box](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-01.jpg "Excel Connection Manager Dialog Box")</span></span>

7.  <span data-ttu-id="9a8cc-114">В диалоговом окне **Редактор источника «Excel»** выберите **IncomingSuppliers$** в раскрывающемся списке **Имя листа Excel** .</span><span class="sxs-lookup"><span data-stu-id="9a8cc-114">In the **Excel Source Editor** dialog box, select **IncomingSuppliers$** in the **Name of the Excel sheet** list box.</span></span>

     <span data-ttu-id="9a8cc-115">![Имя листа Excel — Incoming Suppliers$](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-02.jpg "Имя листа Excel — Incoming Suppliers$")</span><span class="sxs-lookup"><span data-stu-id="9a8cc-115">![Name of Excel Sheet - Incoming Suppliers$](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-02.jpg "Name of Excel Sheet - Incoming Suppliers$")</span></span>

8.  <span data-ttu-id="9a8cc-116">Нажмите кнопку **Просмотр** , чтобы просмотреть данные в файле Excel.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-116">Click **Preview** to preview the data in Excel file.</span></span>

9. <span data-ttu-id="9a8cc-117">Чтобы закрыть диалоговое окно, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="9a8cc-117">Click **OK** to close the dialog box.</span></span>

10. <span data-ttu-id="9a8cc-118">Перетащите преобразование **Очистка DQS** из области **Другие преобразования** на **панели элементов служб SSIS** на вкладку **Поток данных** в источнике **Считывание данных о поставщиках из файла Excel**.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-118">Drag-drop **DQS Cleansing** transform in **Other Transforms** on the **SSIS Toolbox** to the **Data Flow** tab under **Read Supplier Data from Excel File**.</span></span> <span data-ttu-id="9a8cc-119">Преобразование «Очистка DQS» использует службы Data Quality Services (DQS) для исправления данных путем применения утвержденных правил в базе знаний.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-119">The DQS Cleansing transformation uses Data Quality Services (DQS) to correct data by applying approved rules in the knowledge base.</span></span> <span data-ttu-id="9a8cc-120">Это преобразование во время выполнения создает проект очистки DQS на сервере служб DQS.</span><span class="sxs-lookup"><span data-stu-id="9a8cc-120">This transform, at runtime, creates a DQS cleansing project on the DQS server.</span></span> <span data-ttu-id="9a8cc-121">Дополнительные сведения см. в разделе [Преобразование «Очистка DQS»](https://msdn.microsoft.com/library/ee677619.aspx) .</span><span class="sxs-lookup"><span data-stu-id="9a8cc-121">See [DQS Cleansing Transformation](https://msdn.microsoft.com/library/ee677619.aspx) topic for more details.</span></span>

## <a name="next-step"></a><span data-ttu-id="9a8cc-122">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="9a8cc-122">Next Step</span></span>

[<span data-ttu-id="9a8cc-123">Задача 7. Добавление в поток данных преобразования "Очистка DQS"</span><span class="sxs-lookup"><span data-stu-id="9a8cc-123">Task 7: Adding DQS Cleansing Transform to the Data Flow</span></span>](task-7-adding-dqs-cleansing-transform-to-the-data-flow.md)

### <a name="see-also"></a><span data-ttu-id="9a8cc-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="9a8cc-124">See Also</span></span>

[<span data-ttu-id="9a8cc-125">Поток данных</span><span class="sxs-lookup"><span data-stu-id="9a8cc-125">Data Flow</span></span>](../integration-services/data-flow/data-flow.md)
