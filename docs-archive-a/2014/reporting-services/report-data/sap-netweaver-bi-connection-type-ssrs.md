---
title: Тип соединения SAP NetWeaver BI (службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f985856b-31d5-4e56-844b-8a8ee38da67e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 42806e370e20257f5de9e49d4f59dd3bb7793f20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751751"
---
# <a name="sap-netweaver-bi-connection-type-ssrs"></a><span data-ttu-id="58073-102">Тип соединения SAP NetWeaver BI (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="58073-102">SAP NetWeaver BI Connection Type (SSRS)</span></span>
  <span data-ttu-id="58073-103">Чтобы включить данные из внешнего источника данных SAP NetWeaver® Business Intelligence в отчет, необходимо иметь набор данных, основанный на источнике данных отчета типа [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58073-103">To include data from a SAP NetWeaver® Business Intelligence external data source in your report, you must have a dataset that is based on a report data source of type [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)].</span></span> <span data-ttu-id="58073-104">Этот встроенный тип источника данных основан на модуле обработки данных для поставщика данных [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework 1.0 для [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58073-104">This built-in data source type is based on the data extension for the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework Data Provider 1.0 for [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)].</span></span>  
  
 <span data-ttu-id="58073-105">Этот модуль обработки данных позволяет получать многомерные данные из контейнеров InfoCube, MultiProvider (виртуальных контейнеров InfoCube) и запросов с поддержкой веб-доступа к внешнему источнику данных [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="58073-105">This data extension enables you to retrieve multidimensional data from InfoCubes, MultiProviders (virtual InfoCubes), and Web-enabled queries that are defined on a [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)] external data source.</span></span>  
  
 <span data-ttu-id="58073-106">Используйте сведения в этом разделе для создания источника данных.</span><span class="sxs-lookup"><span data-stu-id="58073-106">Use the information in this topic to build a data source.</span></span> <span data-ttu-id="58073-107">Пошаговые инструкции см. в статьях [Добавление и проверка подключения к данным или источника данных &#40;построитель отчетов и служб SSRS&#41;](add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="58073-107">For step-by-step instructions, see [Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;](add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span></span>  
  
##  <a name="supported-versions"></a><a name="support"></a><span data-ttu-id="58073-108">Поддерживаемые версии</span><span class="sxs-lookup"><span data-stu-id="58073-108">Supported Versions</span></span>  
 <span data-ttu-id="58073-109">Поставщик данных был разработан и проверен для работы с SAP BW 3.5 и 7.0.</span><span class="sxs-lookup"><span data-stu-id="58073-109">The data provider has been developed for and tested against SAP BW 3.5 and 7.0.</span></span>  
  
-   <span data-ttu-id="58073-110">Поддержка пакета 20 для SAP BW 3.5 и 7.0</span><span class="sxs-lookup"><span data-stu-id="58073-110">Support Package 20 for SAP BW 3.5 and 7.0</span></span>  
  
 <span data-ttu-id="58073-111">Для встроенной проверки подлинности Windows был разработан и протестирован поставщик для следующих систем.</span><span class="sxs-lookup"><span data-stu-id="58073-111">For Windows Integrated Authentication the provider was developed for and tested against the following systems.</span></span>  
  
-   <span data-ttu-id="58073-112">Портал SAP 6,40. пакет поддержки 20</span><span class="sxs-lookup"><span data-stu-id="58073-112">SAP Portals 6.40 Support Package 20</span></span>  
  
-   <span data-ttu-id="58073-113">Пакет поддержки 11 порталов SAP 7.0</span><span class="sxs-lookup"><span data-stu-id="58073-113">SAP Portals 7.0 Support Package 11</span></span>  
  
-   <span data-ttu-id="58073-114">SAP Duet 1.0</span><span class="sxs-lookup"><span data-stu-id="58073-114">SAP Duet 1.0</span></span>  
  
##  <a name="connection-string"></a><a name="Connection"></a><span data-ttu-id="58073-115">Строка подключения</span><span class="sxs-lookup"><span data-stu-id="58073-115">Connection String</span></span>  
 <span data-ttu-id="58073-116">Свяжитесь с администратором базы данных, чтобы получить сведения о соединении и учетные данные, необходимые для соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="58073-116">Contact the database administrator for connection information and for the credentials to use to connect to the data source.</span></span> <span data-ttu-id="58073-117">Приведенный ниже пример строки соединения задает подключение через Интернет с использованием протокола SOAP к источнику данных [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)] на сервере, использующем порт 8000 и XML для аналитики:</span><span class="sxs-lookup"><span data-stu-id="58073-117">The following connection string example specifies an [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)] data source on a server using port 8000 and XML for Analysis Services (XMLA) over the Internet using SOAP:</span></span>  
  
```  
DataSource=http://mySAPNetWeaverBIServer:8000/sap/bw/xml/soap/xmla  
```  
  
 <span data-ttu-id="58073-118">Дополнительные примеры строк соединения см. в разделе [Подключения к данным, источники данных и строки подключения в построителе отчетов](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="58073-118">For more connection string examples, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span></span>  
  
  
  
##  <a name="credentials"></a><a name="Credentials"></a><span data-ttu-id="58073-119">Информации</span><span class="sxs-lookup"><span data-stu-id="58073-119">Credentials</span></span>  
 <span data-ttu-id="58073-120">Учетные данные необходимы для запуска запросов, локального предварительного просмотра отчетов, а также для предварительного просмотра отчетов на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="58073-120">Credentials are required to run queries, to preview the report locally, and to preview the report from the report server.</span></span>  
  
 <span data-ttu-id="58073-121">После публикации отчета может понадобиться изменить учетные данные источника данных, чтобы разрешения, необходимые для получения данных при запуске отчета на сервере отчетов, были допустимыми.</span><span class="sxs-lookup"><span data-stu-id="58073-121">After you publish your report, you may need to change the credentials for the data source so that when the report runs on the report server, the permissions to retrieve the data are valid.</span></span>  
  
 <span data-ttu-id="58073-122">Дополнительные сведения см. в разделе [подключения к данным, источники данных и строки подключения в Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) или [укажите учетные данные в построитель отчетов](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="58073-122">For more information, see [Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) or [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
  
  
##  <a name="queries"></a><a name="Query"></a><span data-ttu-id="58073-123">Запроса</span><span class="sxs-lookup"><span data-stu-id="58073-123">Queries</span></span>  
 <span data-ttu-id="58073-124">Для построения запроса многомерного выражения с помощью просмотра базовых структур данных в источнике данных можно использовать графический конструктор запросов в режиме конструктора или в режиме запроса.</span><span class="sxs-lookup"><span data-stu-id="58073-124">You can use the graphical query designer in Design or Query mode to build a Multidimensional Expression (MDX) query by browsing the underlying data structures on the data source.</span></span> <span data-ttu-id="58073-125">Чтобы увидеть результаты запроса во время конструирования, его можно запустить из конструктора запросов в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="58073-125">At design time, you can interactively run a query from the query designer to see the results.</span></span> <span data-ttu-id="58073-126">Построенный запрос определяет поля в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="58073-126">The query you build defines fields in the dataset.</span></span> <span data-ttu-id="58073-127">Во время выполнения источник данных возвращает действительные данные.</span><span class="sxs-lookup"><span data-stu-id="58073-127">At run time, the actual data is returned from the data source.</span></span> <span data-ttu-id="58073-128">Для выполнения следующих действий используйте графический конструктор запросов.</span><span class="sxs-lookup"><span data-stu-id="58073-128">Use the graphical query designer to perform the following actions:</span></span>  
  
-   <span data-ttu-id="58073-129">Для построения запроса многомерного выражения в режиме конструктора перетащите измерения, элементы, свойства элементов и ключевые числа из источника данных в панель «Данные».</span><span class="sxs-lookup"><span data-stu-id="58073-129">In Design mode, drag dimensions, members, member properties, and key figures from the data source onto a Data pane to build a Multidimensional Expression (MDX) query.</span></span> <span data-ttu-id="58073-130">Перетащите вычисляемые элементы с панели «Вычисляемые элементы» на панель «Данные», чтобы определить дополнительные поля наборов данных.</span><span class="sxs-lookup"><span data-stu-id="58073-130">Drag calculated members from the Calculated Members pane to the Data pane to define additional dataset fields.</span></span>  
  
-   <span data-ttu-id="58073-131">В режиме запроса перетащите измерения, элементы, свойства элементов и ключевые числа в панель «Запрос» или непосредственно введите в ней текст многомерного выражения.</span><span class="sxs-lookup"><span data-stu-id="58073-131">In Query mode, drag dimensions, members, member properties, and key figures onto the Query pane or type MDX text directly into the Query pane.</span></span> <span data-ttu-id="58073-132">Перетащите вычисляемые элементы с панели «Вычисляемые элементы» на панель «Данные», чтобы определить дополнительные поля наборов данных.</span><span class="sxs-lookup"><span data-stu-id="58073-132">Drag calculated members from the Calculated Members pane to the Data pane to define additional dataset fields.</span></span>  
  
 <span data-ttu-id="58073-133">При построении запросов конструктор запросов автоматически добавляет к запросу многомерных выражений свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="58073-133">As you build queries, the query designer automatically adds default properties to the MDX query.</span></span> <span data-ttu-id="58073-134">Чтобы помимо свойств по умолчанию включить другие свойства, запрос многомерных выражений нужно изменить вручную.</span><span class="sxs-lookup"><span data-stu-id="58073-134">To include properties other than default properties, you must manually modify the MDX query.</span></span>  
  
 <span data-ttu-id="58073-135">Дополнительные сведения о соответствующем конструкторе запросов см. в разделе [Пользовательский интерфейс конструктора запросов SAP NetWeaver BI (построитель отчетов)](../sap-netweaver-bi-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="58073-135">For more information about working with this query designer, see [SAP NetWeaver BI Query Designer User Interface &#40;Report Builder&#41;](../sap-netweaver-bi-query-designer-user-interface-report-builder.md).</span></span>  
  
  
  
##  <a name="extended-field-properties"></a><a name="Extended"></a> <span data-ttu-id="58073-136">Расширенные свойства поля</span><span class="sxs-lookup"><span data-stu-id="58073-136">Extended Field Properties</span></span>  
 <span data-ttu-id="58073-137">Источник данных [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)] поддерживает расширенные свойства полей.</span><span class="sxs-lookup"><span data-stu-id="58073-137">The [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)] data source supports extended field properties.</span></span> <span data-ttu-id="58073-138">Расширенные свойства полей дополняют свойства `Value` и `IsMissing`, заданные для полей набора данных с помощью модуля обработки данных.</span><span class="sxs-lookup"><span data-stu-id="58073-138">Extended field properties are properties in addition to `Value` and `IsMissing` that are defined for a dataset field by the data processing extension.</span></span> <span data-ttu-id="58073-139">Расширенные свойства включают стандартные свойства и пользовательские.</span><span class="sxs-lookup"><span data-stu-id="58073-139">Extended properties include predefined properties and custom properties.</span></span> <span data-ttu-id="58073-140">Стандартные свойства — это свойства, общие для многих источников данных.</span><span class="sxs-lookup"><span data-stu-id="58073-140">Predefined properties are properties common to multiple data sources.</span></span> <span data-ttu-id="58073-141">Пользовательские свойства уникальны для каждого источника данных.</span><span class="sxs-lookup"><span data-stu-id="58073-141">Custom properties are unique to each data source.</span></span>  
  
### <a name="working-with-field-properties"></a><span data-ttu-id="58073-142">Работа со свойствами полей</span><span class="sxs-lookup"><span data-stu-id="58073-142">Working with Field Properties</span></span>  
 <span data-ttu-id="58073-143">Расширенные свойства полей не отображаются в области данных отчета как элементы, которые можно перетащить в макет отчета.</span><span class="sxs-lookup"><span data-stu-id="58073-143">Extended field properties do not appear in the Report Data pane as items that you can drag onto your report layout.</span></span> <span data-ttu-id="58073-144">Вместо этого вы перетаскиваете в отчет родительское поле свойства, а затем меняете свойство по умолчанию с `Value` на свойство, которое требуется.</span><span class="sxs-lookup"><span data-stu-id="58073-144">Instead, you drag the parent field of the property onto the report and then change the default property from `Value` to the property you want to use.</span></span> <span data-ttu-id="58073-145">Например, если имя поля **Calendar Year/Month Level 01** создается в конструкторе запросов многомерных выражений путем перетаскивания из панели метаданных в панель запросов, в каком-то выражении вы ссылаетесь на дополнительное пользовательское свойство **Длинное имя** с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="58073-145">For example, if the field name **Calendar Year/Month Level 01** is created in an MDX query designer by dropping a level from the Metadata pane onto the Query pane, you would refer to the custom extended property **Long Name** in an expression using the following syntax:</span></span>  
  
 `=Fields!Calendar_Year_Month_Level_01("Long Name")`  
  
 <span data-ttu-id="58073-146">Имя расширенного свойства поля появляется в подсказке, когда вы наводите курсор мыши на любое поле в панели метаданных.</span><span class="sxs-lookup"><span data-stu-id="58073-146">The name for an extended field property appears in the ToolTip when you hover over a field in the Metadata pane.</span></span> <span data-ttu-id="58073-147">Дополнительные сведения о конструкторах запросов, которые можно использовать для просмотра базовых данных, см. в разделе [SAP NetWeaver BI Query Designer User Interface](sap-netweaver-bi-query-designer-user-interface.md).</span><span class="sxs-lookup"><span data-stu-id="58073-147">For more information about the query designers you can use to explore the underlying data, see [SAP NetWeaver BI Query Designer User Interface](sap-netweaver-bi-query-designer-user-interface.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="58073-148">Значения для расширенных свойств полей существуют только в случае, если источник данных предоставляет их в то время, когда создается отчет и извлекаются данные для наборов данных.</span><span class="sxs-lookup"><span data-stu-id="58073-148">Values exist for extended field properties only if the data source provides these values when your report runs and retrieves the data for its datasets.</span></span> <span data-ttu-id="58073-149">Затем можно ссылаться на эти значения свойства `Field` из любого выражения с помощью синтаксиса, указанного ниже.</span><span class="sxs-lookup"><span data-stu-id="58073-149">You can then refer to those `Field` property values from any expression using the syntax described below.</span></span> <span data-ttu-id="58073-150">Но поскольку эти поля относятся только к этому поставщику данных и не являются частью языка определения отчетов, изменения в этих значениях не сохраняются вместе с определением отчета.</span><span class="sxs-lookup"><span data-stu-id="58073-150">However, because these fields are specific to this data provider and not part of the report definition language, changes that you make to these values are not saved with the report definition.</span></span>  
  
 <span data-ttu-id="58073-151">Для ссылки на стандартные расширенные свойства используйте одно из следующих выражений:</span><span class="sxs-lookup"><span data-stu-id="58073-151">Use either of the following syntaxes to refer to predefined extended properties in an expression:</span></span>  
  
-   <span data-ttu-id="58073-152">*Fields!ИмяПоля.ИмяСвойства*</span><span class="sxs-lookup"><span data-stu-id="58073-152">*Fields!FieldName.PropertyName*</span></span>  
  
-   <span data-ttu-id="58073-153">*Полям! FieldName ("PropertyName")*</span><span class="sxs-lookup"><span data-stu-id="58073-153">*Fields!FieldName("PropertyName")*</span></span>  
  
 <span data-ttu-id="58073-154">Для обращения к пользовательским расширенным свойствам в выражении применяется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="58073-154">Use the following syntax to refer to custom extended properties in an expression:</span></span>  
  
-   <span data-ttu-id="58073-155">*Полям! FieldName ("PropertyName")*</span><span class="sxs-lookup"><span data-stu-id="58073-155">*Fields!FieldName("PropertyName")*</span></span>  
  
  
  
### <a name="predefined-field-properties"></a><span data-ttu-id="58073-156">Стандартные свойства полей</span><span class="sxs-lookup"><span data-stu-id="58073-156">Predefined Field Properties</span></span>  
 <span data-ttu-id="58073-157">В следующей таблице представлен список стандартных свойств поля, которые можно использовать для источника данных [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="58073-157">The following table provides a list of predefined field properties that you can use for an [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)] data source.</span></span>  
  
|<span data-ttu-id="58073-158">**Property**</span><span class="sxs-lookup"><span data-stu-id="58073-158">**Property**</span></span>|<span data-ttu-id="58073-159">**Type**</span><span class="sxs-lookup"><span data-stu-id="58073-159">**Type**</span></span>|<span data-ttu-id="58073-160">**Описание или ожидаемое значение**</span><span class="sxs-lookup"><span data-stu-id="58073-160">**Description or expected value**</span></span>|  
|------------------|--------------|---------------------------------------|  
|`Value`|`Object`|<span data-ttu-id="58073-161">Указывает значение данных поля.</span><span class="sxs-lookup"><span data-stu-id="58073-161">Specifies the data value of the field.</span></span>|  
|`IsMissing`|`Boolean`|<span data-ttu-id="58073-162">Указывает, найдено ли поле в результирующем наборе данных.</span><span class="sxs-lookup"><span data-stu-id="58073-162">Indicates whether the field was found in the resulting data set.</span></span>|  
|`FormattedValue`|`String`|<span data-ttu-id="58073-163">Возвращает форматированное значение для ключевой цифры.</span><span class="sxs-lookup"><span data-stu-id="58073-163">Returns a formatted value for a key figure.</span></span>|  
|`BackgroundColor`|`String`|<span data-ttu-id="58073-164">Возвращает цвет фона, заданный в базе данных для этого поля.</span><span class="sxs-lookup"><span data-stu-id="58073-164">Returns the background color defined in the database for the field.</span></span>|  
|`Color`|`String`|<span data-ttu-id="58073-165">Возвращает цвет переднего плана, заданный в базе данных для этого элемента.</span><span class="sxs-lookup"><span data-stu-id="58073-165">Returns the foreground color defined in the database for the item.</span></span>|  
|`Key`|`Object`|<span data-ttu-id="58073-166">Возвращает ключ для уровня.</span><span class="sxs-lookup"><span data-stu-id="58073-166">Returns the key for a level.</span></span>|  
|`LevelNumber`|`Integer`|<span data-ttu-id="58073-167">Для иерархий типа «родители-потомки» возвращает номер уровня или измерения.</span><span class="sxs-lookup"><span data-stu-id="58073-167">For parent-child hierarchies, returns the level or dimension number.</span></span>|  
|`ParentUniqueName`|`String`|<span data-ttu-id="58073-168">Для иерархий типа «родители-потомки» это свойство возвращает полное имя родительского уровня.</span><span class="sxs-lookup"><span data-stu-id="58073-168">For parent-child hierarchies, returns a fully qualified name of the parent level.</span></span>|  
|`UniqueName`|`String`|<span data-ttu-id="58073-169">Возвращает полное имя уровня.</span><span class="sxs-lookup"><span data-stu-id="58073-169">Returns the fully qualified name of a level.</span></span> <span data-ttu-id="58073-170">Например, `UniqueName` значение для сотрудника может быть *[0D_Company]. [ 10D_Department]. [11]*.</span><span class="sxs-lookup"><span data-stu-id="58073-170">For example, the `UniqueName` value for an employee might be *[0D_Company].[10D_Department].[11]*.</span></span>|  
  
 <span data-ttu-id="58073-171">Дополнительные сведения об использовании полей и свойств полей в выражении см. в разделе [Встроенные коллекции в выражениях (построитель отчетов и службы SSRS)](../report-design/built-in-collections-in-expressions-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="58073-171">For more information about using fields and field properties in an expression, see [Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span></span>  
  
  
  
##  <a name="remarks"></a><a name="Remarks"></a> <span data-ttu-id="58073-172">Замечания</span><span class="sxs-lookup"><span data-stu-id="58073-172">Remarks</span></span>  
 <span data-ttu-id="58073-173">Этот поставщик данных поддерживает не все режимы доставки отчетов.</span><span class="sxs-lookup"><span data-stu-id="58073-173">Not all report delivery modes are supported by this data provider.</span></span> <span data-ttu-id="58073-174">Доставка отчетов с помощью управляемых данными подписок для этого модуля обработки данных не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="58073-174">Delivering reports through data-driven subscriptions is not supported for this data processing extension.</span></span> <span data-ttu-id="58073-175">Дополнительные сведения см. в разделе [Использование внешнего источника данных для данных подписчика (управляемая данными подписка)](../subscriptions/use-an-external-data-source-for-subscriber-data-data-driven-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="58073-175">For more information, see [Use an External Data Source for Subscriber Data &#40;Data-Driven Subscription&#41;](../subscriptions/use-an-external-data-source-for-subscriber-data-data-driven-subscription.md).</span></span>  
  
 <span data-ttu-id="58073-176">Дополнительные сведения см. в разделе [Использование служб SQL Server 2008 Reporting Services совместно с SAP NetWeaver Business Intelligence](https://go.microsoft.com/fwlink/?LinkId=167352).</span><span class="sxs-lookup"><span data-stu-id="58073-176">For more information, see [Using SQL Server 2008 Reporting Services with SAP NetWeaver Business Intelligence](https://go.microsoft.com/fwlink/?LinkId=167352).</span></span>  
  
  
  
##  <a name="how-to-topics"></a><a name="HowTo"></a><span data-ttu-id="58073-177">Разделы руководства</span><span class="sxs-lookup"><span data-stu-id="58073-177">How-To Topics</span></span>  
 <span data-ttu-id="58073-178">В этом разделе содержатся пошаговые инструкции по работе с подключениями к данным, источниками данных и наборами данных.</span><span class="sxs-lookup"><span data-stu-id="58073-178">This section contains step-by-step instructions for working with data connections, data sources, and datasets.</span></span>  
  
 [<span data-ttu-id="58073-179">Добавление и проверка подключения к данным или источника данных &#40;построитель отчетов и служб SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="58073-179">Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;</span></span>](add-and-verify-a-data-connection-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="58073-180">Создание общего или внедренного набора данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="58073-180">Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;</span></span>](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="58073-181">Добавление фильтра к набору данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="58073-181">Add a Filter to a Dataset &#40;Report Builder and SSRS&#41;</span></span>](add-a-filter-to-a-dataset-report-builder-and-ssrs.md)  
  
  
  
##  <a name="related-sections"></a><a name="Related"></a> <span data-ttu-id="58073-182">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="58073-182">Related Sections</span></span>  
 <span data-ttu-id="58073-183">В этих разделах документации содержатся подробные сведения о данных отчетов, а также методические сведения об определении, настройке и использовании элементов отчетов, связанных с данными.</span><span class="sxs-lookup"><span data-stu-id="58073-183">These sections of the documentation provide in-depth conceptual information about report data, as well as procedural information about how to define, customize, and use parts of a report that are related to data.</span></span>  
  
 [<span data-ttu-id="58073-184">Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="58073-184">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-datasets-ssrs.md)  
 <span data-ttu-id="58073-185">Предоставляет общие сведения о доступе к данным отчета.</span><span class="sxs-lookup"><span data-stu-id="58073-185">Provides an overview of accessing data for your report.</span></span>  
  
 [<span data-ttu-id="58073-186">Подключения к данным, источники данных и строки подключения в построителе отчетов</span><span class="sxs-lookup"><span data-stu-id="58073-186">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../data-connections-data-sources-and-connection-strings-in-report-builder.md)  
 <span data-ttu-id="58073-187">Предоставляет сведения о подключениях к данным и источникам данных.</span><span class="sxs-lookup"><span data-stu-id="58073-187">Provides information about data connections and data sources.</span></span>  
  
 [<span data-ttu-id="58073-188">Внедренные и общие наборы данных отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="58073-188">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
 <span data-ttu-id="58073-189">Предоставляет сведения об общих и внедренных наборах данных.</span><span class="sxs-lookup"><span data-stu-id="58073-189">Provides information about embedded and shared datasets.</span></span>  
  
 [<span data-ttu-id="58073-190">Коллекция полей набора данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="58073-190">Dataset Fields Collection &#40;Report Builder and SSRS&#41;</span></span>](dataset-fields-collection-report-builder-and-ssrs.md)  
 <span data-ttu-id="58073-191">Предоставляет сведения о коллекции полей набора данных, создаваемой запросом.</span><span class="sxs-lookup"><span data-stu-id="58073-191">Provides information about the dataset field collection generated by the query.</span></span>  
  
 [<span data-ttu-id="58073-192">Источники данных, поддерживаемые службами Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="58073-192">Data Sources Supported by Reporting Services &#40;SSRS&#41;</span></span>](../create-deploy-and-manage-mobile-and-paginated-reports.md)  
 <span data-ttu-id="58073-193">Предоставляет подробные сведения о поддержке платформ и версий для каждого модуля обработки данных.</span><span class="sxs-lookup"><span data-stu-id="58073-193">Provides in-depth information about platform and version support for each data extension.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="58073-194">См. также:</span><span class="sxs-lookup"><span data-stu-id="58073-194">See Also</span></span>  
 <span data-ttu-id="58073-195">[Параметры отчета &#40;построитель отчетов и конструктор отчетов&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="58073-195">[Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="58073-196">[Фильтрация, группировка и сортировка данных &#40;построитель отчетов и SSRS&#41;](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="58073-196">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="58073-197">Выражения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="58073-197">Expressions &#40;Report Builder and SSRS&#41;</span></span>](../report-design/expressions-report-builder-and-ssrs.md)  
  
  
