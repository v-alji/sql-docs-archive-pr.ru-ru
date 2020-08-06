---
title: Занятие 5. Проектирование родительского отчета с использованием мастера отчетов | Документы Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 19a3f927-ea97-4f40-a5f8-cd5f2598e4da
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f188a914fc2a2bb8370843191a31474a54c02aa8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656227"
---
# <a name="lesson-5-design-the-child-report-using-the-report-wizard"></a><span data-ttu-id="500a6-102">Занятие 5. Проектирование родительского отчета с использованием мастера отчетов</span><span class="sxs-lookup"><span data-stu-id="500a6-102">Lesson 5: Design the Child Report using the Report Wizard</span></span>
  <span data-ttu-id="500a6-103">После создания подключения к данным и таблицы данных для дочернего отчета следующий шаг состоит в проектировании дочернего отчета в конструкторе отчетов с помощью мастера отчетов.</span><span class="sxs-lookup"><span data-stu-id="500a6-103">After you create a data connection and data table for the child report, your next step is to design the child report using the Report Wizard in Report Designer.</span></span> <span data-ttu-id="500a6-104">Дополнительные сведения о конструкторе отчетов см. в разделе [Разработка отчетов с использованием конструктора отчетов (SSRS)](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="500a6-104">For more information about Report Designer, see [Design Reports with Report Designer &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span></span>  
  
### <a name="to-design-the-child-report-using-the-report-wizard"></a><span data-ttu-id="500a6-105">Проектирование дочернего отчета с использованием мастера отчетов</span><span class="sxs-lookup"><span data-stu-id="500a6-105">To design the child report using the Report Wizard</span></span>  
  
1.  <span data-ttu-id="500a6-106">Обязательно выберите в **обозревателе решений**веб-сайт верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="500a6-106">Make sure that the top-level website is selected in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="500a6-107">Щелкните правой кнопкой мыши веб-сайт и выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="500a6-107">Right-click on the website and select **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="500a6-108">В диалоговом окне **Добавление нового элемента** нажмите кнопку **Мастер отчетов**, введите имя файла отчета и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="500a6-108">In the **Add New Item** dialog box, click **Report Wizard**, enter a name for the report file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="500a6-109">Запустится мастер отчетов.</span><span class="sxs-lookup"><span data-stu-id="500a6-109">This launches the Report Wizard.</span></span>  
  
4.  <span data-ttu-id="500a6-110">На странице « **Свойства набора** данных» в поле **источник данных** щелкните **DataSet2**.</span><span class="sxs-lookup"><span data-stu-id="500a6-110">In the **Dataset Properties** page, in the **Data source** box, click **DataSet2**.</span></span>  
  
     <span data-ttu-id="500a6-111">Значение, указанное в поле **Доступные наборы данных** , автоматически изменится. В нем будет указана созданная ранее таблица данных.</span><span class="sxs-lookup"><span data-stu-id="500a6-111">The **Available datasets** box is automatically updated with the DataTable you created.</span></span>  
  
5.  <span data-ttu-id="500a6-112">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="500a6-112">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="500a6-113">На странице **Размещение полей** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="500a6-113">In the **Arrange Fields** page do the following:</span></span>  
  
    1.  <span data-ttu-id="500a6-114">Перетащите элементы **ProductID**, **PurchaseOrderID**, **PurchaseOrderDetailID**, **OrderQty**, **ReceivedQty**, **RejectedQty**и **StockedQty** из области **Доступные поля** в поле **Значения** .</span><span class="sxs-lookup"><span data-stu-id="500a6-114">Drag **ProductID**, **PurchaseOrderID**, **PurchaseOrderDetailID**, **OrderQty**, **ReceivedQty**, **RejectedQty**, and **StockedQty** from **Available Fields** to the **Values** box.</span></span>  
  
    2.  <span data-ttu-id="500a6-115">Щелкните стрелку рядом с полем **Сумма (ProductID)**, **Сумма (PurchaseOrderID)**, **Сумма (PurchaseOrderDetailID)**, **Сумма (OrderQty)**, **Сумма (ReceivedQty)**, **Сумма (RejectedQty)** и **Сумма (StockedQty)** и отмените выбор **суммы** .</span><span class="sxs-lookup"><span data-stu-id="500a6-115">Click the arrow next to **Sum(ProductID)**, **Sum(PurchaseOrderID)**, **Sum(PurchaseOrderDetailID)**, **Sum(OrderQty)**, **Sum(ReceivedQty)**, **Sum(RejectedQty)**, and **Sum(StockedQty)** and clear the **Sum** selection.</span></span>  
  
7.  <span data-ttu-id="500a6-116">Дважды нажмите кнопку **Далее** , а затем кнопку **Готово** , чтобы закрыть **Мастер отчетов**.</span><span class="sxs-lookup"><span data-stu-id="500a6-116">Click **Next** twice, then click **Finish** to close the **Report Wizard**.</span></span>  
  
     <span data-ttu-id="500a6-117">В результате создается RDLC-файл.</span><span class="sxs-lookup"><span data-stu-id="500a6-117">You've now created the .rdlc file.</span></span> <span data-ttu-id="500a6-118">Файл откроется в конструкторе отчетов.</span><span class="sxs-lookup"><span data-stu-id="500a6-118">The file opens in Report Designer.</span></span> <span data-ttu-id="500a6-119">Спроектированный вами табликс появится в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="500a6-119">The tablix you designed is now displayed in the design surface.</span></span>  
  
8.  <span data-ttu-id="500a6-120">Добавьте в открытый RDLC-файл параметр, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="500a6-120">With the .rdlc file open, add a parameter by doing the following:</span></span>  
  
    1.  <span data-ttu-id="500a6-121">Щелкните **Параметры** в области **данных отчета** , а затем нажмите кнопку **Добавить параметры**.</span><span class="sxs-lookup"><span data-stu-id="500a6-121">Click **Parameters** in the **Report Data** pane, and then click **Add Parameters**.</span></span>  
  
    2.  <span data-ttu-id="500a6-122">Введите **productid** в поле **Имя** .</span><span class="sxs-lookup"><span data-stu-id="500a6-122">Enter **productid** in the **Name** box.</span></span>  
  
    3.  <span data-ttu-id="500a6-123">В списке **Тип данных** должно быть выбрано значение **Integer** .</span><span class="sxs-lookup"><span data-stu-id="500a6-123">Confirm that **Integer** is selected in the **Data Type** list box.</span></span>  
  
    4.  <span data-ttu-id="500a6-124">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="500a6-124">Click **OK**.</span></span>  
  
9. <span data-ttu-id="500a6-125">Сохраните RDLC-файл.</span><span class="sxs-lookup"><span data-stu-id="500a6-125">Save the .rdlc file.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="500a6-126">Следующая задача</span><span class="sxs-lookup"><span data-stu-id="500a6-126">Next Task</span></span>  
 <span data-ttu-id="500a6-127">Тем самым с помощью мастера отчетов был успешно спроектирован дочерний отчет.</span><span class="sxs-lookup"><span data-stu-id="500a6-127">You have successfully designed the child report by using the Report Wizard.</span></span> <span data-ttu-id="500a6-128">Затем в приложение для веб-сайта необходимо добавить элемент управления ReportViewer.</span><span class="sxs-lookup"><span data-stu-id="500a6-128">Next, you will add a ReportViewer control to the website application.</span></span>  
  
  
