---
title: Преобразование источника данных из внедренного в общий (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data sources [Reporting Services], embedded
- data sources [Reporting Services], shared
ms.assetid: 0e099c7e-8c03-43eb-9ea3-76e52d9ebbe3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5827bab564b58e7a2b7922f01a33f550a6f523f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656173"
---
# <a name="convert-a-data-source-from-embedded-to-shared-report-builder-and-ssrs"></a><span data-ttu-id="94af0-102">Преобразование источника данных из внедренного в общий (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="94af0-102">Convert a Data Source from Embedded to Shared (Report Builder and SSRS)</span></span>
  <span data-ttu-id="94af0-103">Каждый источник данных в области данных отчета является внедренным и привязанным к определенному отчету либо общим.</span><span class="sxs-lookup"><span data-stu-id="94af0-103">Each data source in the Report Data pane is embedded and specific to the report or is shared.</span></span> <span data-ttu-id="94af0-104">В построителе отчетов общий источник данных указывает на опубликованный общий источник данных на сервере отчетов или сайте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="94af0-104">In Report Builder, a shared data source points to a published shared data source on a report server or SharePoint site.</span></span> <span data-ttu-id="94af0-105">В конструкторе отчетов общий источник данных указывает на общий источник данных в папке **Общие источники данных** в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="94af0-105">In Report Designer, a shared data source points to a shared data source in the **Shared Data Sources** folder in Solution Explorer.</span></span>  
  
 <span data-ttu-id="94af0-106">Дополнительные сведения о различиях между внедренными и общими источниками данных см. в разделе [Внедренные и общие подключения к данным или источники данных (построитель отчетов и службы SSRS)](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="94af0-106">For more information about the differences between embedded and shared data sources, see [Embedded and Shared Data Connections or Data Sources &#40;Report Builder and SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="94af0-107">Дополнительные сведения о создании общего источника данных см. в разделе [Создание внедренного или общего источника данных (службы SSRS)](../create-an-embedded-or-shared-data-source-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="94af0-107">For more information on how to create a shared data source, see [Create an Embedded or Shared Data Source &#40;SSRS&#41;](../create-an-embedded-or-shared-data-source-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="report-designer"></a><span data-ttu-id="94af0-108">конструктор отчетов</span><span class="sxs-lookup"><span data-stu-id="94af0-108">Report Designer</span></span>  
  
#### <a name="to-convert-a-data-source-from-embedded-to-shared"></a><span data-ttu-id="94af0-109">Преобразование источника данных из внедренного в общий</span><span class="sxs-lookup"><span data-stu-id="94af0-109">To convert a data source from embedded to shared</span></span>  
  
-   <span data-ttu-id="94af0-110">В области данных отчета щелкните правой кнопкой мыши источник данных и выберите команду **Преобразовать в общий источник данных**.</span><span class="sxs-lookup"><span data-stu-id="94af0-110">In the Report Data pane, right-click the data source, and then click **Convert to Shared Data Source**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="94af0-111">Если область данных отчета не отображается, в меню **Вид** выберите пункт **Данные отчета**.</span><span class="sxs-lookup"><span data-stu-id="94af0-111">If the Report Data pane is not visible, on the **View** menu, click **Report Data**.</span></span> <span data-ttu-id="94af0-112">Если панель открывается как плавающее окно, его можно пристыковать.</span><span class="sxs-lookup"><span data-stu-id="94af0-112">If the pane opens as a floating window, you can dock it.</span></span> <span data-ttu-id="94af0-113">Дополнительные сведения см. в разделе [Закрепление области данных отчета в конструкторе отчетов (службы SSRS)](../tools/dock-the-report-data-pane-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="94af0-113">For more information, see [Dock the Report Data Pane in Report Designer &#40;SSRS&#41;](../tools/dock-the-report-data-pane-in-report-designer-ssrs.md).</span></span>  
  
     <span data-ttu-id="94af0-114">В области данных отчета значок источника данных сменится значком общего источника данных.</span><span class="sxs-lookup"><span data-stu-id="94af0-114">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span> <span data-ttu-id="94af0-115">В обозревателе решений общий источник данных появится с тем же именем в папке **Общий источник данных** .</span><span class="sxs-lookup"><span data-stu-id="94af0-115">In Solution Explorer, a shared data source with the same name appears under the **Shared Data Source** folder.</span></span>  
  
### <a name="to-convert-a-data-source-from-shared-to-embedded"></a><span data-ttu-id="94af0-116">Преобразование источника данных из общего во внедренный</span><span class="sxs-lookup"><span data-stu-id="94af0-116">To convert a data source from shared to embedded</span></span>  
  
-   <span data-ttu-id="94af0-117">В области данных отчета щелкните правой кнопкой мыши источник данных, откройте диалоговое окно **Свойства источника данных** и выберите параметр **Внедренное соединение**.</span><span class="sxs-lookup"><span data-stu-id="94af0-117">In the Report Data pane, right-click the data source, open the **Data Source Properties** dialog box, and then click **Embedded Connection**.</span></span> <span data-ttu-id="94af0-118">Введите необходимые сведения.</span><span class="sxs-lookup"><span data-stu-id="94af0-118">Enter the required information.</span></span>  
  
     <span data-ttu-id="94af0-119">В области данных отчета значок источника данных сменится значком общего источника данных.</span><span class="sxs-lookup"><span data-stu-id="94af0-119">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span>  
  
## <a name="report-builder"></a><span data-ttu-id="94af0-120">построитель отчетов</span><span class="sxs-lookup"><span data-stu-id="94af0-120">Report Builder</span></span>  
  
#### <a name="to-convert-a-data-source-from-embedded-to-shared"></a><span data-ttu-id="94af0-121">Преобразование источника данных из внедренного в общий</span><span class="sxs-lookup"><span data-stu-id="94af0-121">To convert a data source from embedded to shared</span></span>  
  
-   <span data-ttu-id="94af0-122">В области данных отчета щелкните правой кнопкой мыши источник данных, чтобы открыть диалоговое окно **Свойства источника данных** , и выберите параметр **Внедренное соединение**.</span><span class="sxs-lookup"><span data-stu-id="94af0-122">In the Report Data pane, right-click the data source to open the **Data Source Properties** dialog box, and then click **Embedded Connection**.</span></span> <span data-ttu-id="94af0-123">Введите необходимые сведения.</span><span class="sxs-lookup"><span data-stu-id="94af0-123">Enter the required information.</span></span>  
  
     <span data-ttu-id="94af0-124">В области данных отчета значок источника данных сменится значком общего источника данных.</span><span class="sxs-lookup"><span data-stu-id="94af0-124">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span>  
  
#### <a name="to-convert-a-data-source-from-shared-to-embedded"></a><span data-ttu-id="94af0-125">Преобразование источника данных из общего во внедренный</span><span class="sxs-lookup"><span data-stu-id="94af0-125">To convert a data source from shared to embedded</span></span>  
  
-   <span data-ttu-id="94af0-126">В области данных отчета щелкните правой кнопкой мыши источник данных, откройте диалоговое окно **Свойства источника данных** и выберите параметр **Внедренное соединение**.</span><span class="sxs-lookup"><span data-stu-id="94af0-126">In the Report Data pane, right-click the data source, open the **Data Source Properties** dialog box, and then click **Embedded Connection**.</span></span> <span data-ttu-id="94af0-127">Введите необходимые сведения.</span><span class="sxs-lookup"><span data-stu-id="94af0-127">Enter the required information.</span></span>  
  
     <span data-ttu-id="94af0-128">В области данных отчета значок источника данных сменится значком общего источника данных.</span><span class="sxs-lookup"><span data-stu-id="94af0-128">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94af0-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="94af0-129">See Also</span></span>  
 <span data-ttu-id="94af0-130">[Управление источниками данных отчета](manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="94af0-130">[Manage Report Data Sources](manage-report-data-sources.md) </span></span>  
 [<span data-ttu-id="94af0-131">Подключения данных, Источники данных и Строки подключения в службе Reporting Services</span><span class="sxs-lookup"><span data-stu-id="94af0-131">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](../data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  
