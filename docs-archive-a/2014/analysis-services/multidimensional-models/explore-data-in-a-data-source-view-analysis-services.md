---
title: Просмотр данных в представлении источника данных (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- exploring data [Analysis Services]
- data source views [Analysis Services], exploring data
- viewing source data
ms.assetid: 2c922c35-fbcb-45b2-96b1-c7a846d8b419
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6adf9edecd807158ba1d0de3287cccd6fa8dd787
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669126"
---
# <a name="explore-data-in-a-data-source-view-analysis-services"></a><span data-ttu-id="4b7ff-102">Просмотр данных в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="4b7ff-102">Explore Data in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="4b7ff-103">Диалоговое окно **Просмотр данных** конструктора представлений источников данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] служит для просмотра данных таблицы, представления или именованного запроса в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-103">You can use the **Explore Data** dialog box in Data Source View Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to browse data for a table, view, or named query in a data source view (DSV).</span></span> <span data-ttu-id="4b7ff-104">При просмотре данных в конструкторе представлений источника данных можно видеть содержимое каждого столбца данных в выбранной таблице, представлении или именованном запросе.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-104">When you explore the data in Data Source View Designer, you can view the contents of each column of data in a selected table, view, or named query.</span></span> <span data-ttu-id="4b7ff-105">Просмотр содержимого помогает определить, все ли столбцы нужны (если именованные вычисления требуются для повышения удобства для пользователя) и возвращают ли существующие именованные вычисления и именованные запросы ожидаемые результаты.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-105">Viewing the actual contents assists you in determining whether all columns are needed, if named calculations are required to increase user friendliness and usability, and whether existing named calculations or named queries return the anticipated values.</span></span>  
  
 <span data-ttu-id="4b7ff-106">Для просмотра данных требуется активное соединение с источником или источниками данных выбранного объекта в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-106">To view data, you must have an active connection to the data source or sources for the selected object in the DSV.</span></span> <span data-ttu-id="4b7ff-107">Любые именованные вычисления в таблице также передаются в запрос.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-107">Any named calculations in a table are also sent in the query.</span></span>  
  
 <span data-ttu-id="4b7ff-108">Данные возвращаются в табличном формате, поддерживающем сортировку и копирование.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-108">The data returned in a tabular format that you can sort and copy.</span></span> <span data-ttu-id="4b7ff-109">Чтобы пересортировать строки по некоторому столбцу, щелкните его заголовок.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-109">Click on the column headers to re-sort the rows by that column.</span></span> <span data-ttu-id="4b7ff-110">Также можно выделить данные в сетки и нажать клавиши CTRL-C, чтобы скопировать их в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-110">You can also highlight data in the grid and press Ctrl-C to copy the selection to the clipboard.</span></span>  
  
 <span data-ttu-id="4b7ff-111">Также можно менять метод выборки и размер выборки.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-111">You can also control the sample method and the sample count.</span></span> <span data-ttu-id="4b7ff-112">По умолчанию возвращаются первые 5000 строк.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-112">By default, the top 5000 rows are returned.</span></span>  
  
## <a name="to-browse-data-or-change-sampling-options"></a><span data-ttu-id="4b7ff-113">Просмотр данных или изменение параметров выборки</span><span class="sxs-lookup"><span data-stu-id="4b7ff-113">To browse data or change sampling options</span></span>  
  
1.  <span data-ttu-id="4b7ff-114">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект или подключитесь к базе данных, содержащей представление источника данных, в котором нужно просмотреть данные.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-114">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to browse data.</span></span>  
  
2.  <span data-ttu-id="4b7ff-115">В обозревателе решений откройте папку **Представления источников данных** , а затем дважды щелкните представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-115">In Solution Explorer, expand the **Data Source Views** folder, and then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="4b7ff-116">Щелкните правой кнопкой мыши таблицу, представление или именованный запрос, содержащие данные, которые необходимо просмотреть, а затем выберите пункт **Просмотр данных**.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-116">Right-click the table, view, or named query that contains the data you want to view, and then click **Explore Data**.</span></span>  
  
     <span data-ttu-id="4b7ff-117">Источник данных, лежащий в основе таблицы, представления или именованного запроса в представлении источника данных, является запросом, а результаты отображаются на вкладке **Обзор \<object name> таблицы** .</span><span class="sxs-lookup"><span data-stu-id="4b7ff-117">The data source underlying the table, view, or named query in the data source view are queries, and the results appear in the **Explore \<object name> Table** tab.</span></span>  
  
4.  <span data-ttu-id="4b7ff-118">На панели инструментов **Просмотр \<object name> таблицы** щелкните значок **Параметры выборки** .</span><span class="sxs-lookup"><span data-stu-id="4b7ff-118">On the **Explore \<object name> Table** toolbar, click the **Sampling options** icon.</span></span>  
  
     <span data-ttu-id="4b7ff-119">Откроется диалоговое окно **Параметры просмотра данных** .</span><span class="sxs-lookup"><span data-stu-id="4b7ff-119">The **Data Exploration Options** dialog box opens.</span></span> <span data-ttu-id="4b7ff-120">В этом диалоговом окне можно задать метод выборки (уменьшив или увеличив количество записей выборки, по умолчанию равное 5000 строк) или размер выборки.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-120">In this dialog box you can specify the sampling method (fewer or more records than the default sampling size of 5000 rows), or sample count.</span></span>  
  
5.  <span data-ttu-id="4b7ff-121">Нажмите кнопку **ОК** или **Отмена** .</span><span class="sxs-lookup"><span data-stu-id="4b7ff-121">Click **OK** or **Cancel** as appropriate.</span></span>  
  
6.  <span data-ttu-id="4b7ff-122">Чтобы выполнить повторную выборку данных, нажмите кнопку **ресамплинг данных** на панели инструментов **Обзор \<object name> таблиц** .</span><span class="sxs-lookup"><span data-stu-id="4b7ff-122">To resample the data, click **Resample Data** on the **Explore \<object name> Table** toolbar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b7ff-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="4b7ff-123">See Also</span></span>  
 [<span data-ttu-id="4b7ff-124">Представления источников данных в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="4b7ff-124">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  
