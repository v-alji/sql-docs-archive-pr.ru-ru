---
title: Занятие 6. Добавление в приложение элемента управления ReportViewer | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f9492a97-5609-4059-ae76-0fba111d4968
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bb04008fa47801f0500de711592a3cec45ca3dd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668096"
---
# <a name="lesson-6-add-a-reportviewer-control-to-the-application"></a><span data-ttu-id="c7856-102">Урок 6. Добавление в приложение элемента управления ReportViewer</span><span class="sxs-lookup"><span data-stu-id="c7856-102">Lesson 6: Add a ReportViewer Control to the Application</span></span>
  <span data-ttu-id="c7856-103">После завершения проектирования дочернего отчета с помощью мастера отчетов далее необходимо добавить в приложение веб-сайта элемент управления ReportViewer.</span><span class="sxs-lookup"><span data-stu-id="c7856-103">After you design the child report by using the Report Wizard, your next step is to add a ReportViewer control to the website application.</span></span>  
  
### <a name="to-add-a-reportviewer-control-to-the-application"></a><span data-ttu-id="c7856-104">Добавление элемента управления ReportViewer в приложение</span><span class="sxs-lookup"><span data-stu-id="c7856-104">To add a ReportViewer control to the application</span></span>  
  
1.  <span data-ttu-id="c7856-105">В **обозревателе решений**щелкните правой кнопкой мыши **Default.aspx**и выберите пункт **Конструктор представлений**.</span><span class="sxs-lookup"><span data-stu-id="c7856-105">In **Solution Explorer**, right-click **Default.aspx**, and then click **View Designer**.</span></span>  
  
2.  <span data-ttu-id="c7856-106">Из группы **Расширения AJAX** в окне **Панель элементов** перетащите элемент управления **ScriptManager** в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="c7856-106">From the **AJAX Extensions** group in the **Toolbox** window, drag a **ScriptManager** control to the design surface.</span></span>  
  
3.  <span data-ttu-id="c7856-107">Из группы **Отчетность** перетащите элемент управления **ReportViewer** в область конструктора, расположив его ниже элемента управления **ScriptManager** .</span><span class="sxs-lookup"><span data-stu-id="c7856-107">From the **Reporting** group, drag a **ReportViewer** control to the design surface below the **ScriptManager** control.</span></span>  
  
4.  <span data-ttu-id="c7856-108">Откройте окно **Задачи ReportViewer** , щелкнув стрелку в правом верхнем углу элемента управления **ReportViewer** .</span><span class="sxs-lookup"><span data-stu-id="c7856-108">Open the **ReportViewer Tasks** window by clicking the arrow in the top right-hand corner of the **ReportViewer** control.</span></span>  
  
5.  <span data-ttu-id="c7856-109">В поле **Выбор отчета** выберите созданный ранее родительский отчет.</span><span class="sxs-lookup"><span data-stu-id="c7856-109">In the **Choose Report** box, select Parent report you created.</span></span>  
  
     <span data-ttu-id="c7856-110">После выбора отчета экземпляры источников данных, используемых в отчете, будут созданы автоматически.</span><span class="sxs-lookup"><span data-stu-id="c7856-110">When you select a report, instances of data sources used in the report are created automatically.</span></span> <span data-ttu-id="c7856-111">Будет сформирован код для создания экземпляра каждого объекта DataTable (и его контейнера [DataSet](https://msdn.microsoft.com/library/system.data.dataset\(v=vs.100\).aspx) ).</span><span class="sxs-lookup"><span data-stu-id="c7856-111">Code is generated to instantiate each DataTable (and its [DataSet](https://msdn.microsoft.com/library/system.data.dataset\(v=vs.100\).aspx) container).</span></span> <span data-ttu-id="c7856-112">В область конструктора будут добавлены элементы управления [ObjectDataSource](https://msdn.microsoft.com/library/system.web.ui.webcontrols.objectdatasource\(v=vs.100\).aspx) , соответствующие каждому источнику данных, который используется в отчете.</span><span class="sxs-lookup"><span data-stu-id="c7856-112">An [ObjectDataSource](https://msdn.microsoft.com/library/system.web.ui.webcontrols.objectdatasource\(v=vs.100\).aspx) control is added to the design surface, corresponding to each data source used in the report.</span></span> <span data-ttu-id="c7856-113">Настройка этих элементов управления источником данных осуществляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="c7856-113">This data source control is configured automatically.</span></span>  
  
     <span data-ttu-id="c7856-114">Если вы используете Microsoft Visual Studio 2012, убедитесь, что элемент управления ObjectDataSource привязан к приложению DataSet1 с полным именем в пространстве имен проекта, если полное имя указано в раскрывающемся списке **выберите бизнес-объект** (например, Projectnamespace. DataSet1TableAdapters. ProductTableAdapter).</span><span class="sxs-lookup"><span data-stu-id="c7856-114">If you're using Microsoft Visual Studio 2012, make sure that the ObjectDataSource control is bound with DataSet1 that is fully qualified with the project namespace, if the fully qualified name is listed in the **Choose your business object** drop-down list box (for example, Projectnamespace.DataSet1TableAdapters.ProductTableAdapter).</span></span> <span data-ttu-id="c7856-115">Доступ к этому списку можно получить, щелкнув правой кнопкой мыши ObjectDataSource и выбрав пункт **Настройка источника данных**.</span><span class="sxs-lookup"><span data-stu-id="c7856-115">You access the list box by right-clicking ObjectDataSource, and then clicking **Configure Data Source**.</span></span>  
  
6.  <span data-ttu-id="c7856-116">В меню «Построение» выберите команду «Построить веб-сайт».</span><span class="sxs-lookup"><span data-stu-id="c7856-116">On the Build menu, click Build website.</span></span>  
  
     <span data-ttu-id="c7856-117">Отчет компилируется, и все ошибки, такие как синтаксические ошибки в выражениях отчета, появляются в области **Список ошибок** .</span><span class="sxs-lookup"><span data-stu-id="c7856-117">The report is compiled and any errors such as a syntax error in a report expression appear in the **Error List** area.</span></span> <span data-ttu-id="c7856-118">Щелкните **Список ошибок** в нижней части окна Visual Studio, чтобы отобразить область **Список ошибок** .</span><span class="sxs-lookup"><span data-stu-id="c7856-118">Click **Error List** at the bottom of the Visual Studio window to display the **Error List** area.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="c7856-119">Следующая задача</span><span class="sxs-lookup"><span data-stu-id="c7856-119">Next Task</span></span>  
 <span data-ttu-id="c7856-120">Тем самым в приложение веб-сайта был успешно добавлен элемент управления ReportViewer.</span><span class="sxs-lookup"><span data-stu-id="c7856-120">You have successfully added a ReportViewer control to the website application.</span></span> <span data-ttu-id="c7856-121">Затем необходимо добавить операцию детализации в родительский отчет.</span><span class="sxs-lookup"><span data-stu-id="c7856-121">Next, you will add a drillthrough action on the parent report.</span></span>  
  
  
