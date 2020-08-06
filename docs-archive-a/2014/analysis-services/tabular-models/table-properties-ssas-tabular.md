---
title: Свойства таблицы (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.tableprop.f1
ms.assetid: 16d3347b-7e43-4a6b-9956-fdd6ede092e6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9613609c42de8fd3a4aab7aec3208dfe3d31be4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738816"
---
# <a name="table-properties-ssas-tabular"></a><span data-ttu-id="64d75-102">Свойства таблицы (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="64d75-102">Table Properties (SSAS Tabular)</span></span>
  <span data-ttu-id="64d75-103">В этом разделе описаны свойства табличной модели.</span><span class="sxs-lookup"><span data-stu-id="64d75-103">This topic describes tabular model table properties.</span></span> <span data-ttu-id="64d75-104">Описанные здесь свойства отличаются от свойств таблицы в диалоговом окне «Изменение свойств таблицы», которые определяют, какие столбцы из источника нужно импортировать.</span><span class="sxs-lookup"><span data-stu-id="64d75-104">The properties described here are different from those in the Edit Table Properties dialog box, which define which columns from the source are imported.</span></span>  
  
 <span data-ttu-id="64d75-105">Разделы данной темы:</span><span class="sxs-lookup"><span data-stu-id="64d75-105">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="64d75-106">Свойства таблицы</span><span class="sxs-lookup"><span data-stu-id="64d75-106">Table Properties</span></span>](#bkmk_properties)  
  
-   [<span data-ttu-id="64d75-107">Настройка параметров табличных свойств</span><span class="sxs-lookup"><span data-stu-id="64d75-107">To configure table property settings</span></span>](#bkmk_config_prop)  
  
##  <a name="table-properties"></a><a name="bkmk_properties"></a><span data-ttu-id="64d75-108">Свойства таблицы</span><span class="sxs-lookup"><span data-stu-id="64d75-108">Table Properties</span></span>  
 <span data-ttu-id="64d75-109">**Основной**</span><span class="sxs-lookup"><span data-stu-id="64d75-109">**Basic**</span></span>  
  
|<span data-ttu-id="64d75-110">Свойство</span><span class="sxs-lookup"><span data-stu-id="64d75-110">Property</span></span>|<span data-ttu-id="64d75-111">Параметр по умолчанию</span><span class="sxs-lookup"><span data-stu-id="64d75-111">Default Setting</span></span>|<span data-ttu-id="64d75-112">Описание</span><span class="sxs-lookup"><span data-stu-id="64d75-112">Description</span></span>|  
|--------------|---------------------|-----------------|  
|<span data-ttu-id="64d75-113">**Имя соединения**</span><span class="sxs-lookup"><span data-stu-id="64d75-113">**Connection Name**</span></span>|\<connection name>|<span data-ttu-id="64d75-114">Имя соединения с источником данных таблицы.</span><span class="sxs-lookup"><span data-stu-id="64d75-114">The name of the connection to the table's data source.</span></span><br /><br /> <span data-ttu-id="64d75-115">Чтобы изменить соединение, нажмите кнопку.</span><span class="sxs-lookup"><span data-stu-id="64d75-115">To edit the connection, click the button.</span></span>|  
|<span data-ttu-id="64d75-116">**Скрыта**</span><span class="sxs-lookup"><span data-stu-id="64d75-116">**Hidden**</span></span>|<span data-ttu-id="64d75-117">Неверно</span><span class="sxs-lookup"><span data-stu-id="64d75-117">False</span></span>|<span data-ttu-id="64d75-118">Указывает, является ли таблица скрытой при выводе отчета о списке полей клиента.</span><span class="sxs-lookup"><span data-stu-id="64d75-118">Specifies whether the table is hidden from reporting client field lists.</span></span>|  
|<span data-ttu-id="64d75-119">**Секции**</span><span class="sxs-lookup"><span data-stu-id="64d75-119">**Partitions**</span></span>||<span data-ttu-id="64d75-120">Секции для таблицы не могут отображаться в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="64d75-120">Partitions for the table cannot be displayed in the **Properties** window.</span></span> <span data-ttu-id="64d75-121">Чтобы просмотреть, создать или изменить секции, нажмите эту кнопку и откройте диспетчер секций.</span><span class="sxs-lookup"><span data-stu-id="64d75-121">To view, create, or edit partitions, click the button to open the Partition Manager.</span></span>|  
|<span data-ttu-id="64d75-122">**Исходные данные**</span><span class="sxs-lookup"><span data-stu-id="64d75-122">**Source Data**</span></span>||<span data-ttu-id="64d75-123">Исходные данные для таблицы не могут отображаться в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="64d75-123">Source data for the table cannot be displayed in the **Properties** window.</span></span> <span data-ttu-id="64d75-124">Чтобы просмотреть или изменить исходные данные, нажмите эту кнопку и откройте диалоговое окно «Изменение свойств таблицы».</span><span class="sxs-lookup"><span data-stu-id="64d75-124">To view or edit the source data, click the button to open the Edit Table Properties dialog box.</span></span>|  
|<span data-ttu-id="64d75-125">**Описание таблицы**</span><span class="sxs-lookup"><span data-stu-id="64d75-125">**Table Description**</span></span>||<span data-ttu-id="64d75-126">Текстовое описание для таблицы.</span><span class="sxs-lookup"><span data-stu-id="64d75-126">A text description for the table.</span></span><br /><br /> <span data-ttu-id="64d75-127">Если в программе [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)]навести указатель мыши на таблицу в списке полей, отобразится ее описание в виде подсказки.</span><span class="sxs-lookup"><span data-stu-id="64d75-127">In [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], if an end-user places the cursor over this table in the field list, the description appears as a tooltip.</span></span>|  
|<span data-ttu-id="64d75-128">**Имя таблицы**</span><span class="sxs-lookup"><span data-stu-id="64d75-128">**Table Name**</span></span>|\<friendly name>|<span data-ttu-id="64d75-129">Указывает понятное имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="64d75-129">Specifies the table's friendly name.</span></span> <span data-ttu-id="64d75-130">Имя таблицы можно указать при импорте с помощью мастера импорта таблиц или в любое время после импорта.</span><span class="sxs-lookup"><span data-stu-id="64d75-130">The table name can be specified when a table is imported using the Table Import Wizard or at any time after import.</span></span> <span data-ttu-id="64d75-131">Имя таблицы в модели может отличаться от имени связанной исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="64d75-131">The table name in the model can be different from the associated table at the source.</span></span> <span data-ttu-id="64d75-132">Понятное имя таблицы появляется в списке полей клиентского приложения, а также в базе данных model в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64d75-132">The table friendly name appears in the reporting client application field list as well as in the model database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>|  
  
 <span data-ttu-id="64d75-133">**Свойства отчетов**</span><span class="sxs-lookup"><span data-stu-id="64d75-133">**Reporting Properties**</span></span>  
  
 <span data-ttu-id="64d75-134">Подробное описание и сведения о настройке свойств создания отчетов см. в разделе [Свойства отчетов Power View (табличные службы SSAS)](properties-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="64d75-134">For detailed descriptions and configuration information for reporting properties, see [Power View Reporting Properties &#40;SSAS Tabular&#41;](properties-ssas-tabular.md).</span></span>  
  
|<span data-ttu-id="64d75-135">Свойство</span><span class="sxs-lookup"><span data-stu-id="64d75-135">Property</span></span>|<span data-ttu-id="64d75-136">Параметр по умолчанию</span><span class="sxs-lookup"><span data-stu-id="64d75-136">Default Setting</span></span>|<span data-ttu-id="64d75-137">Описание</span><span class="sxs-lookup"><span data-stu-id="64d75-137">Description</span></span>|  
|--------------|---------------------|-----------------|  
|<span data-ttu-id="64d75-138">**Набор полей по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="64d75-138">**Default Field Set**</span></span>|||  
|<span data-ttu-id="64d75-139">Поведение таблиц</span><span class="sxs-lookup"><span data-stu-id="64d75-139">Table Behavior</span></span>|||  
  
###  <a name="to-configure-table-property-settings"></a><a name="bkmk_config_prop"></a><span data-ttu-id="64d75-140">Настройка параметров свойств таблицы</span><span class="sxs-lookup"><span data-stu-id="64d75-140">To configure table property settings</span></span>  
  
1.  <span data-ttu-id="64d75-141">В конструкторе моделей в представлении диаграмм щелкните таблицу (вкладку) или в представлении диаграмм щелкните заголовок таблицы.</span><span class="sxs-lookup"><span data-stu-id="64d75-141">In the model designer, in Data View, click a table (tab), or, in Diagram View, click a table header.</span></span>  
  
2.  <span data-ttu-id="64d75-142">В окне **Свойства** щелкните свойство и введите значение или нажмите кнопку для открытия дополнительных параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="64d75-142">In the **Properties** window, click on a property, and then type a value or click the button for additional configuration options.</span></span>  
  
  
