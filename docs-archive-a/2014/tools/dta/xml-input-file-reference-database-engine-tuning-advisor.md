---
title: Справочник по входным файлам XML (помощник по настройке ядра СУБД) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database Engine Tuning Advisor [SQL Server], XML input files
- input file reference [Database Engine Tuning Advisor]
- XML input files [Database Engine Tuning Advisor]
ms.assetid: 05e5e5f0-d6df-4336-b18e-e9bc2835a766
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3bbd38299e4921db33cbaf318883c2f0a9041d92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750395"
---
# <a name="xml-input-file-reference-database-engine-tuning-advisor"></a><span data-ttu-id="af9e3-102">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="af9e3-102">XML Input File Reference (Database Engine Tuning Advisor)</span></span>
  [!INCLUDE[ssDE](../../includes/ssde-md.md)] <span data-ttu-id="af9e3-103">может настраивать базу данных с помощью входного файла XML-данных.</span><span class="sxs-lookup"><span data-stu-id="af9e3-103">Tuning Advisor can use an XML input file to tune a database.</span></span> <span data-ttu-id="af9e3-104">Этот XML-файл определяет, какие базы данных, таблицы, файлы или таблицы рабочей нагрузки и параметры настройки должны быть использованы для сеанса настройки.</span><span class="sxs-lookup"><span data-stu-id="af9e3-104">This XML file designates which databases, tables, workload files or tables, and tuning options to use for the tuning session.</span></span> <span data-ttu-id="af9e3-105">Его можно также использовать в качестве пользовательской конфигурации для выполнения анализа вариантов.</span><span class="sxs-lookup"><span data-stu-id="af9e3-105">You can also use this file to specify a user-specified configuration to perform "what-if" analysis.</span></span>  
  
 <span data-ttu-id="af9e3-106">Входной XML-файл помощника по настройке компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] содержит иерархию элементов XML, содержащих текстовые и прочие элементы, которые определяют параметры сеанса настройки.</span><span class="sxs-lookup"><span data-stu-id="af9e3-106">A [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor XML input file contains a hierarchy of XML elements, each containing text or other elements that specify the tuning session settings.</span></span> <span data-ttu-id="af9e3-107">Входной XML-файл помощника по настройке компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] должен соответствовать стандартам XML-документов правильного формата, поэтому имена всех элементов обрабатываются с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="af9e3-107">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor XML input file must conform to the standards for well-formed XML, so all element names are case sensitive.</span></span> <span data-ttu-id="af9e3-108">Имена указываются в стиле языка Pascal, в котором принято, что первые буквы имен прописные, первая буква каждого из сцепленных слов прописная, а остальные — строчные.</span><span class="sxs-lookup"><span data-stu-id="af9e3-108">Elements are specified using Pascal case, which means that the first character is uppercase and the first letter of any subsequent concatenated word is uppercase.</span></span>  
  
 <span data-ttu-id="af9e3-109">Значения всех элементов должны соответствовать соглашениям об именах XML.</span><span class="sxs-lookup"><span data-stu-id="af9e3-109">All element values must conform to XML naming conventions.</span></span> <span data-ttu-id="af9e3-110">Дополнительные сведения об этих соглашениях см. в статье [Текстовое содержимое XML](https://go.microsoft.com/fwlink/?LinkId=7614) библиотеки MSDN.</span><span class="sxs-lookup"><span data-stu-id="af9e3-110">For more information about these conventions, see [XML Textual Content](https://go.microsoft.com/fwlink/?LinkId=7614) in the MSDN Library.</span></span>  
  
 <span data-ttu-id="af9e3-111">Обратите внимание, что этот справочник не является исчерпывающим.</span><span class="sxs-lookup"><span data-stu-id="af9e3-111">Note that this reference is not comprehensive.</span></span> <span data-ttu-id="af9e3-112">Дополнительные сведения обо всех элементах, используемых при определении входных данных XML, см. в XML-схеме помощника по настройке компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , файле DTASchema.xsd.</span><span class="sxs-lookup"><span data-stu-id="af9e3-112">For information about all the elements you can use to define XML input, refer to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor XML schema, DTASchema.xsd.</span></span>  
  
## <a name="xml-declaration"></a><span data-ttu-id="af9e3-113">XML-декларация</span><span class="sxs-lookup"><span data-stu-id="af9e3-113">XML Declaration</span></span>  
  
-   [<span data-ttu-id="af9e3-114">Данные XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="af9e3-114">XML Data &#40;SQL Server&#41;</span></span>](../../relational-databases/xml/xml-data-sql-server.md)  
  
## <a name="dtaxml-root-element"></a><span data-ttu-id="af9e3-115">Корневой элемент DTAXML</span><span class="sxs-lookup"><span data-stu-id="af9e3-115">DTAXML Root Element</span></span>  
  
-   [<span data-ttu-id="af9e3-116">Элемент DTAXML (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-116">DTAXML Element &#40;DTA&#41;</span></span>](dtaxml-element-dta.md)  
  
## <a name="dtainput-elements"></a><span data-ttu-id="af9e3-117">Элементы DTAInput</span><span class="sxs-lookup"><span data-stu-id="af9e3-117">DTAInput Elements</span></span>  
  
-   [<span data-ttu-id="af9e3-118">Элемент DTAInput (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-118">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)  
  
-   [<span data-ttu-id="af9e3-119">Элемент Server (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-119">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)  
  
-   [<span data-ttu-id="af9e3-120">Элемент Workload (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-120">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)  
  
-   [<span data-ttu-id="af9e3-121">Элемент TuningOptions (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-121">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)  
  
-   [<span data-ttu-id="af9e3-122">Элемент Configuration (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-122">Configuration Element &#40;DTA&#41;</span></span>](configuration-element-dta.md)  
  
## <a name="server-elements"></a><span data-ttu-id="af9e3-123">Элементы для описания сервера</span><span class="sxs-lookup"><span data-stu-id="af9e3-123">Server Elements</span></span>  
  
-   [<span data-ttu-id="af9e3-124">Элемент Name описания сервера (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-124">Name Element for Server &#40;DTA&#41;</span></span>](name-element-for-server-dta.md)  
  
-   [<span data-ttu-id="af9e3-125">Элемент Database описания сервера (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-125">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)  
  
## <a name="workload-elements"></a><span data-ttu-id="af9e3-126">Элементы рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="af9e3-126">Workload Elements</span></span>  
  
-   [<span data-ttu-id="af9e3-127">Элемент File (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-127">File Element &#40;DTA&#41;</span></span>](file-element-dta.md)  
  
-   [<span data-ttu-id="af9e3-128">Элемент Database для рабочей нагрузки (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-128">Database Element for Workload &#40;DTA&#41;</span></span>](database-element-for-workload-dta.md)  
  
-   [<span data-ttu-id="af9e3-129">Элемент EventString (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-129">EventString Element &#40;DTA&#41;</span></span>](eventstring-element-dta.md)  
  
## <a name="tuning-options-elements"></a><span data-ttu-id="af9e3-130">Элементы для описания параметров настройки</span><span class="sxs-lookup"><span data-stu-id="af9e3-130">Tuning Options Elements</span></span>  
  
-   [<span data-ttu-id="af9e3-131">Элемент TuningTimeInMin (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-131">TuningTimeInMin Element &#40;DTA&#41;</span></span>](tuningtimeinmin-element-dta.md)  
  
-   [<span data-ttu-id="af9e3-132">Элемент StorageBoundInMB (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-132">StorageBoundInMB Element &#40;DTA&#41;</span></span>](storageboundinmb-element-dta.md)  
  
-   [<span data-ttu-id="af9e3-133">Элемент TestServer (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-133">TestServer Element &#40;DTA&#41;</span></span>](testserver-element-dta.md)  
  
-   [<span data-ttu-id="af9e3-134">Элемент FeatureSet (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-134">FeatureSet Element &#40;DTA&#41;</span></span>](featureset-element-dta.md)  
  
-   [<span data-ttu-id="af9e3-135">Элемент Partitioning (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-135">Partitioning Element &#40;DTA&#41;</span></span>](partitioning-element-dta.md)  
  
-   [<span data-ttu-id="af9e3-136">Элемент DropOnlyMode (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-136">DropOnlyMode Element &#40;DTA&#41;</span></span>](droponlymode-element-dta.md)  
  
-   [<span data-ttu-id="af9e3-137">Элемент KeepExisting (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-137">KeepExisting Element &#40;DTA&#41;</span></span>](keepexisting-element-dta.md)  
  
-   [<span data-ttu-id="af9e3-138">Элемент OnlineIndexOperation (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-138">OnlineIndexOperation Element &#40;DTA&#41;</span></span>](onlineindexoperation-element-dta.md)  
  
-   [<span data-ttu-id="af9e3-139">Элемент DatabaseToConnect (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-139">DatabaseToConnect Element &#40;DTA&#41;</span></span>](databasetoconnect-element-dta.md)  
  
## <a name="configuration-elements"></a><span data-ttu-id="af9e3-140">Элементы для описания конфигурации</span><span class="sxs-lookup"><span data-stu-id="af9e3-140">Configuration Elements</span></span>  
  
-   [<span data-ttu-id="af9e3-141">Элемент Server описания конфигурации (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-141">Server Element for Configuration &#40;DTA&#41;</span></span>](server-element-for-configuration-dta.md)  
  
-   [<span data-ttu-id="af9e3-142">Элемент Database описания конфигурации (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-142">Database Element for Configuration &#40;DTA&#41;</span></span>](database-element-for-configuration-dta.md)  
  
-   [<span data-ttu-id="af9e3-143">Элемент Recommendation (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-143">Recommendation Element &#40;DTA&#41;</span></span>](recommendation-element-dta.md)  
  
-   [<span data-ttu-id="af9e3-144">Элемент Create (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-144">Create Element &#40;DTA&#41;</span></span>](create-element-dta.md)  
  
-   [<span data-ttu-id="af9e3-145">Элемент Index (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-145">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)  
  
-   [<span data-ttu-id="af9e3-146">Элемент Name описания индекса (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-146">Name Element for Index &#40;DTA&#41;</span></span>](name-element-for-index-dta.md)  
  
-   [<span data-ttu-id="af9e3-147">Элемент Column описания индекса (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-147">Column Element for Index &#40;DTA&#41;</span></span>](column-element-for-index-dta.md)  
  
-   [<span data-ttu-id="af9e3-148">Элемент Name описания столбца (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-148">Name Element for Column &#40;DTA&#41;</span></span>](name-element-for-column-dta.md)  
  
-   [<span data-ttu-id="af9e3-149">Элемент Filegroup описания индекса (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-149">Filegroup Element for Index &#40;DTA&#41;</span></span>](filegroup-element-for-index-dta.md)  
  
## <a name="database-elements"></a><span data-ttu-id="af9e3-150">Элементы для описания базы данных</span><span class="sxs-lookup"><span data-stu-id="af9e3-150">Database Elements</span></span>  
  
-   [<span data-ttu-id="af9e3-151">Элемент Name для базы данных (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-151">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)  
  
-   [<span data-ttu-id="af9e3-152">Элемент Schema описания базы данных (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-152">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)  
  
-   [<span data-ttu-id="af9e3-153">Элемент Name для схемы (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-153">Name Element for Schema &#40;DTA&#41;</span></span>](name-element-for-schema-dta.md)  
  
-   [<span data-ttu-id="af9e3-154">Элемент Table для схемы (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-154">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)  
  
-   [<span data-ttu-id="af9e3-155">Элемент Name описания таблицы (DTA)</span><span class="sxs-lookup"><span data-stu-id="af9e3-155">Name Element for Table &#40;DTA&#41;</span></span>](name-element-for-table-dta.md)  
  
## <a name="see-also"></a><span data-ttu-id="af9e3-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="af9e3-156">See Also</span></span>  
 [<span data-ttu-id="af9e3-157">Database Engine Tuning Advisor</span><span class="sxs-lookup"><span data-stu-id="af9e3-157">Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
