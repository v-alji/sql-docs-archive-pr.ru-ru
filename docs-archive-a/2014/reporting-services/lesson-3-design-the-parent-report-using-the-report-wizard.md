---
title: Занятие 3. Проектирование родительского отчета с использованием мастера отчетов | Документы Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2f69dcd3-cd6d-45a9-a62a-ba6f5f3179d8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f3cb6a0972a2bb63e82e80c02b3ce90912ba01c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656233"
---
# <a name="lesson-3-design-the-parent-report-using-the-report-wizard"></a><span data-ttu-id="b9ef4-102">Занятие 3. Проектирование родительского отчета с использованием мастера отчетов</span><span class="sxs-lookup"><span data-stu-id="b9ef4-102">Lesson 3: Design the Parent Report using the Report Wizard</span></span>
  <span data-ttu-id="b9ef4-103">После создания подключения к данным и таблицы данных для родительского отчета следующий шаг состоит в проектировании родительского отчета в конструкторе отчетов с помощью мастера отчетов.</span><span class="sxs-lookup"><span data-stu-id="b9ef4-103">After you create a data connection and a data table for the parent report, your next step is to design the parent report using the Report Wizard in Report Designer.</span></span> <span data-ttu-id="b9ef4-104">Дополнительные сведения о конструкторе отчетов см. в разделе [Разработка отчетов с использованием конструктора отчетов (SSRS)](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b9ef4-104">For more information about Report Designer, see [Design Reports with Report Designer &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span></span>  
  
### <a name="to-design-the-parent-report-using-the-report-wizard"></a><span data-ttu-id="b9ef4-105">Проектирование родительского отчета с использованием мастера отчетов</span><span class="sxs-lookup"><span data-stu-id="b9ef4-105">To design the parent report using the Report Wizard</span></span>  
  
1.  <span data-ttu-id="b9ef4-106">Обязательно выберите в **обозревателе решений**веб-сайт верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="b9ef4-106">Make sure that the top-level website is selected in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="b9ef4-107">Щелкните правой кнопкой мыши веб-сайт и выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="b9ef4-107">Right-click on the website and select **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="b9ef4-108">В диалоговом окне **Добавление нового элемента** выберите **Мастер отчетов**, введите имя файла отчета и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="b9ef4-108">In the **Add New Item** dialog box, select **Report Wizard**, enter a name for the report file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="b9ef4-109">Запустится мастер отчетов.</span><span class="sxs-lookup"><span data-stu-id="b9ef4-109">This launches the Report Wizard.</span></span>  
  
4.  <span data-ttu-id="b9ef4-110">На странице **Свойства набора данных** в поле **Источник данных** выберите набор данных **DataSet1** , созданный на [занятии 2: определение подключения к данным и таблицы данных для родительского отчета](lesson-2-define-a-data-connection-and-data-table-for-parent-report.md).</span><span class="sxs-lookup"><span data-stu-id="b9ef4-110">On the **Dataset Properties** page, in the **Data source** box, select the **DataSet1** you created in [Lesson 2: Define a Data Connection and Data Table for Parent Report](lesson-2-define-a-data-connection-and-data-table-for-parent-report.md).</span></span>  
    <span data-ttu-id="b9ef4-111">Значение поля **Доступные наборы данных** автоматически изменится на **DataTable** (созданную ранее таблицу данных).</span><span class="sxs-lookup"><span data-stu-id="b9ef4-111">The **Available datasets** box is automatically updated with the **DataTable** you created above.</span></span>  
  
5.  <span data-ttu-id="b9ef4-112">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9ef4-112">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="b9ef4-113">На странице **Размещение полей** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b9ef4-113">In the **Arrange Fields** page do the following:</span></span>  
  
    1.  <span data-ttu-id="b9ef4-114">Перетащите элементы **ProductID**, **Name**, **ProductNumber**, **SafetyStockLevel**и **ReorderLevel** из области **Доступные поля** в поле **Значения** .</span><span class="sxs-lookup"><span data-stu-id="b9ef4-114">Drag **ProductID**, **Name**, **ProductNumber**, **SafetyStockLevel**, and **ReorderLevel** from **Available fields** to the **Values** box.</span></span>  
  
    2.  <span data-ttu-id="b9ef4-115">Щелкните стрелку рядом с полем **Сумма (ProductID)**, **Сумма (SafetyStockLevel)**, **Sum (ReorderLevel)** и отмените выбор **суммы** .</span><span class="sxs-lookup"><span data-stu-id="b9ef4-115">Click the arrow next to **Sum(ProductID)**, **Sum(SafetyStockLevel)**, **Sum(ReorderLevel)** and clear the **Sum** selection.</span></span>  
  
7.  <span data-ttu-id="b9ef4-116">Дважды нажмите кнопку **Далее** , а затем кнопку **Готово** , чтобы закрыть **Мастер отчетов**.</span><span class="sxs-lookup"><span data-stu-id="b9ef4-116">Click **Next** twice, then click **Finish** to close the **Report Wizard**.</span></span>  
  
     <span data-ttu-id="b9ef4-117">В результате создается RDLC-файл.</span><span class="sxs-lookup"><span data-stu-id="b9ef4-117">You've now created the .rdlc file.</span></span> <span data-ttu-id="b9ef4-118">Файл откроется в конструкторе отчетов.</span><span class="sxs-lookup"><span data-stu-id="b9ef4-118">The file opens in Report Designer.</span></span> <span data-ttu-id="b9ef4-119">Спроектированный вами табликс появится в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="b9ef4-119">The tablix you designed is now displayed in the design surface.</span></span>  
  
8.  <span data-ttu-id="b9ef4-120">Сохраните RDLC-файл.</span><span class="sxs-lookup"><span data-stu-id="b9ef4-120">Save the .rdlc file.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="b9ef4-121">Следующая задача</span><span class="sxs-lookup"><span data-stu-id="b9ef4-121">Next Task</span></span>  
 <span data-ttu-id="b9ef4-122">Тем самым с помощью мастера отчетов был успешно спроектирован родительский отчет.</span><span class="sxs-lookup"><span data-stu-id="b9ef4-122">You have successfully designed the parent report using the Report Wizard.</span></span> <span data-ttu-id="b9ef4-123">После этого необходимо создать подключение к данным и таблицу данных для дочернего отчета.</span><span class="sxs-lookup"><span data-stu-id="b9ef4-123">Next, you will create a data connection and a data table for the child report.</span></span>  
  
  
