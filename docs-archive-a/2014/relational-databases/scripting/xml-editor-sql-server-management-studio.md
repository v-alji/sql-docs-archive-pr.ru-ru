---
title: Редактор XML
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.editorxml.f1
- sql12.swb.xmleditor.f1
- vs.xmleditor
- sql12.swb.editor.xml.f1
helpviewer_keywords:
- XML Designer [SQL Server Management Studio]
ms.assetid: 0824a5ce-e67b-4b53-98d9-d371faf2d23c
author: rothja
ms.author: jroth
ms.openlocfilehash: b7c3bbbda4f5a31c4d83b559c1aa623ca2aff89f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667669"
---
# <a name="xml-editor-sql-server-management-studio"></a><span data-ttu-id="1e38c-102">Редактор XML (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="1e38c-102">XML Editor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="1e38c-103">Предоставляет набор визуальных средств для работы с XML-схемами, наборами данных ADO.NET и XML-документами.</span><span class="sxs-lookup"><span data-stu-id="1e38c-103">Provides a set of visual tools for working with XML Schemas, ADO.NET datasets, and XML documents.</span></span> <span data-ttu-id="1e38c-104">Конструктор XML поддерживает язык определения схем XML (XSD), определенный консорциумом World Wide Web (WC3).</span><span class="sxs-lookup"><span data-stu-id="1e38c-104">The XML Designer supports the XML Schema Definition (XSD) language defined by the World Wide Web Consortium (WC3).</span></span> <span data-ttu-id="1e38c-105">Этот конструктор не поддерживает определения DTD (определения типов файлов) или другие языки XML-схем, например XDR (XML-Data Reduced).</span><span class="sxs-lookup"><span data-stu-id="1e38c-105">The designer does not support DTDs (document type definitions) or other XML schema languages, such as XDR (XML-Data Reduced).</span></span>  
  
 <span data-ttu-id="1e38c-106">Чтобы открыть конструктор, добавить набор данных, XML-схему или XML-файл к проекту или открыть любой файл одного из типов, перечисленных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="1e38c-106">To display the designer, add a dataset, XML Schema, or XML file to your project or open any of the file types listed in the table below.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="1e38c-107">Команда **Отменить** отсутствует при работе в представлении «Схема».</span><span class="sxs-lookup"><span data-stu-id="1e38c-107">There is no **Undo** command when working in Schema view.</span></span> <span data-ttu-id="1e38c-108">Тщательно спланируйте свою работу и чаще сохраняйте файлы.</span><span class="sxs-lookup"><span data-stu-id="1e38c-108">Plan your work carefully and save your files often.</span></span>  
  
 <span data-ttu-id="1e38c-109">Конструктор предоставляет следующие три представления (или режима) для работы с XML-файлами, XML-схемами и наборами данных.</span><span class="sxs-lookup"><span data-stu-id="1e38c-109">The designer provides the following three views (or modes) to work on XML files, XML Schemas, and datasets:</span></span>  
  
|<span data-ttu-id="1e38c-110">Представление</span><span class="sxs-lookup"><span data-stu-id="1e38c-110">View</span></span>|<span data-ttu-id="1e38c-111">Description</span><span class="sxs-lookup"><span data-stu-id="1e38c-111">Description</span></span>|<span data-ttu-id="1e38c-112">Поддерживаемые типы файлов</span><span class="sxs-lookup"><span data-stu-id="1e38c-112">File types supported</span></span>|  
|----------|-----------------|--------------------------|  
|<span data-ttu-id="1e38c-113">**Схема**</span><span class="sxs-lookup"><span data-stu-id="1e38c-113">**Schema**</span></span>|<span data-ttu-id="1e38c-114">Для визуального создания и изменения XML-схем и наборов данных ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="1e38c-114">For visually creating and modifying XML Schemas and ADO.NET datasets.</span></span>|<span data-ttu-id="1e38c-115">.xsd</span><span class="sxs-lookup"><span data-stu-id="1e38c-115">.xsd</span></span>|  
|<span data-ttu-id="1e38c-116">**Data**</span><span class="sxs-lookup"><span data-stu-id="1e38c-116">**Data**</span></span>|<span data-ttu-id="1e38c-117">Для визуального изменения файлов XML-данных в структурированной сетке данных.</span><span class="sxs-lookup"><span data-stu-id="1e38c-117">For visually modifying XML data files in a structured data grid.</span></span>|<span data-ttu-id="1e38c-118">XML</span><span class="sxs-lookup"><span data-stu-id="1e38c-118">.xml</span></span>|  
|<span data-ttu-id="1e38c-119">**XML**</span><span class="sxs-lookup"><span data-stu-id="1e38c-119">**XML**</span></span>|<span data-ttu-id="1e38c-120">Для редактирования кода XML; редактор кода предоставляет цветовое выделение синтаксиса и технологию IntelliSense, включая команды «Завершить слово» и «Показать элементы».</span><span class="sxs-lookup"><span data-stu-id="1e38c-120">For editing XML; the source editor provides color-coding and IntelliSense, including Complete Word and List Members.</span></span>|<span data-ttu-id="1e38c-121">.xml .xsd .xslt .wsdl.web.resx.tdl.wsf.hta.disco.vsdisco.config</span><span class="sxs-lookup"><span data-stu-id="1e38c-121">.xml .xsd .xslt .wsdl.web.resx.tdl.wsf.hta.disco.vsdisco.config</span></span>|  
|<span data-ttu-id="1e38c-122">**Инструкция ShowPlan**</span><span class="sxs-lookup"><span data-stu-id="1e38c-122">**ShowPlan**</span></span>|<span data-ttu-id="1e38c-123">Выводит планы запросов xml, созданные в режиме SET SHOWPLAN_XML ON.</span><span class="sxs-lookup"><span data-stu-id="1e38c-123">Displays xml query plans created using the SET SHOWPLAN_XML ON option.</span></span>|<span data-ttu-id="1e38c-124">.showplan</span><span class="sxs-lookup"><span data-stu-id="1e38c-124">.showplan</span></span>|  
  
## <a name="schema-view"></a><span data-ttu-id="1e38c-125">Представление схемы</span><span class="sxs-lookup"><span data-stu-id="1e38c-125">Schema View</span></span>  
 <span data-ttu-id="1e38c-126">Представление схемы предоставляет визуальное отображение элементов, атрибутов, типов и т. д., которые делают наглядными XML-схемы и наборы данных ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="1e38c-126">Schema view provides a visual representation of the elements, attributes, types, and so on, that make up XML Schemas and ADO.NET datasets.</span></span>  
  
 <span data-ttu-id="1e38c-127">В представлении схемы можно конструировать схемы и наборы данных, перенося элементы в области конструктора с вкладки области элементов «XML-схема» или из обозревателя серверов.</span><span class="sxs-lookup"><span data-stu-id="1e38c-127">In Schema view you can construct schemas and datasets by dropping elements on the design surface from either the XML Schema tab of the Toolbox or from Server Explorer.</span></span> <span data-ttu-id="1e38c-128">Кроме того, можно добавить в конструктор элементы, щелкнув область конструктора правой кнопкой мыши и выбрав пункт «Добавить» из контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="1e38c-128">Additionally, you can add elements to the designer by right-clicking the design surface and selecting Add from the shortcut menu.</span></span>  
  
 <span data-ttu-id="1e38c-129">В представлении схемы можно:</span><span class="sxs-lookup"><span data-stu-id="1e38c-129">In Schema view you can:</span></span>  
  
-   <span data-ttu-id="1e38c-130">создавать и изменять существующие XML-схемы и наборы данных ADO.NET;</span><span class="sxs-lookup"><span data-stu-id="1e38c-130">Construct and modify existing XML Schemas and ADO.NET datasets</span></span>  
  
-   <span data-ttu-id="1e38c-131">создавать и изменять связи между таблицами;</span><span class="sxs-lookup"><span data-stu-id="1e38c-131">Create and edit relationships between tables</span></span>  
  
-   <span data-ttu-id="1e38c-132">создавать и изменять ключи;</span><span class="sxs-lookup"><span data-stu-id="1e38c-132">Create and edit keys</span></span>  
  
-   <span data-ttu-id="1e38c-133">формировать наборы данных ADO.NET из XML-схем.</span><span class="sxs-lookup"><span data-stu-id="1e38c-133">Generate ADO.NET datasets from XML Schemas</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e38c-134">Расположение элементов в представлении схемы сохраняется в файле с расширением XSX, который можно увидеть, нажав кнопку **Показать все файлы** на панели инструментов в обозревателе решений и развернув файл с расширением XSD.</span><span class="sxs-lookup"><span data-stu-id="1e38c-134">The layout of elements in Schema view is stored in the .xsx file, which can be seen by clicking **Show All Files** in the Solution Explorer toolbar, and then expanding the .xsd file.</span></span> <span data-ttu-id="1e38c-135">Если XSX-файлы отсутствуют, это значит, что XSD-файл никогда не открывался в конструкторе XML.</span><span class="sxs-lookup"><span data-stu-id="1e38c-135">If there is no .xsx file present, it means the .xsd file has never been opened in the XML Designer.</span></span>  
  
### <a name="customizing-schema-view"></a><span data-ttu-id="1e38c-136">Настройка представления схемы</span><span class="sxs-lookup"><span data-stu-id="1e38c-136">Customizing Schema View</span></span>  
 <span data-ttu-id="1e38c-137">Следующие функции изменяют визуальное расположение элементов в представлении схемы:</span><span class="sxs-lookup"><span data-stu-id="1e38c-137">The following features modify the visual layout of elements in Schema view:</span></span>  
  
-   <span data-ttu-id="1e38c-138">изменение масштаба;</span><span class="sxs-lookup"><span data-stu-id="1e38c-138">Zooming</span></span>  
  
-   <span data-ttu-id="1e38c-139">развертывание или свертывание вложенных элементов;</span><span class="sxs-lookup"><span data-stu-id="1e38c-139">Expanding or collapsing of nested elements</span></span>  
  
-   <span data-ttu-id="1e38c-140">автоматическое расположение элементов;</span><span class="sxs-lookup"><span data-stu-id="1e38c-140">Automatically arranging layout of elements</span></span>  
  
-   <span data-ttu-id="1e38c-141">сброс до стандартного состояния свернутых элементов.</span><span class="sxs-lookup"><span data-stu-id="1e38c-141">Resetting default state of collapsed elements</span></span>  
  
##### <a name="to-expand-hidden-nested-elements"></a><span data-ttu-id="1e38c-142">Развертывание скрытых вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="1e38c-142">To expand hidden nested elements</span></span>  
  
-   <span data-ttu-id="1e38c-143">Щелкните значок «плюс» внизу элемента.</span><span class="sxs-lookup"><span data-stu-id="1e38c-143">Click the plus icon on the bottom of the element.</span></span>  
  
##### <a name="to-collapse-nested-elements"></a><span data-ttu-id="1e38c-144">Сворачивание вложенных элементов</span><span class="sxs-lookup"><span data-stu-id="1e38c-144">To collapse nested elements</span></span>  
  
-   <span data-ttu-id="1e38c-145">Щелкните значок «минус» у самого нижнего элемента, который должен остаться в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="1e38c-145">Click the minus icon on the bottom-most element that you want to appear on the designer.</span></span>  
  
## <a name="data-view"></a><span data-ttu-id="1e38c-146">Представление данных</span><span class="sxs-lookup"><span data-stu-id="1e38c-146">Data View</span></span>  
 <span data-ttu-id="1e38c-147">Представление данных предоставляет сетку данных для изменения XML-файлов.</span><span class="sxs-lookup"><span data-stu-id="1e38c-147">Data view provides a data grid that can be used to modify .xml files.</span></span> <span data-ttu-id="1e38c-148">В этом представлении можно изменять только содержимое XML-файла (но не теги и структуру).</span><span class="sxs-lookup"><span data-stu-id="1e38c-148">Only the content (but not the tags and structure) in an XML file can be edited in Data view.</span></span>  
  
 <span data-ttu-id="1e38c-149">В представлении "Данные" предусмотрено две отдельные области: **Таблицы данных** и **Данные**.</span><span class="sxs-lookup"><span data-stu-id="1e38c-149">There are two separate areas in Data view: **Data Tables** and **Data**.</span></span> <span data-ttu-id="1e38c-150">Область **Таблица данных** — это список взаимоотношений, определенных в XML-файле в порядке вложенности (от самых внешних к самым внутренним).</span><span class="sxs-lookup"><span data-stu-id="1e38c-150">The **Data Tables** area is a list of relations defined in the XML file, in the order of its nesting (from the outermost to the innermost).</span></span> <span data-ttu-id="1e38c-151">Область **Данные** — это сетка данных, отображающая данные на основании выбора в области «Таблица данных».</span><span class="sxs-lookup"><span data-stu-id="1e38c-151">The **Data** area is a data grid that displays data based on the selection in the Data Tables area.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e38c-152">Новые файлы XML не содержат данных и не могут отображаться в представлении данных.</span><span class="sxs-lookup"><span data-stu-id="1e38c-152">Newly created XML files contain no data and therefore cannot be displayed in Data view.</span></span> <span data-ttu-id="1e38c-153">Есть также некоторые XML-документы, для которых не может быть применено представление данных.</span><span class="sxs-lookup"><span data-stu-id="1e38c-153">There are also some instances of XML documents where data view cannot be invoked at all.</span></span> <span data-ttu-id="1e38c-154">Хотя XML считается корректным форматом, при попытке переключения на неструктурированные данные представление "Данные" выдает следующее сообщение: "Документ сформирован правильно, однако он содержит структуру, которую невозможно отобразить в представлении данных".</span><span class="sxs-lookup"><span data-stu-id="1e38c-154">Although the XML would be considered well formed, if it is not structured data trying to switch to Data view will generate the following message: "Although this document is well formed, it contains structure that Data View cannot display."</span></span>  
  
 <span data-ttu-id="1e38c-155">В представлении данных можно:</span><span class="sxs-lookup"><span data-stu-id="1e38c-155">In Data view you can:</span></span>  
  
-   <span data-ttu-id="1e38c-156">вручную заполнять таблицы данных;</span><span class="sxs-lookup"><span data-stu-id="1e38c-156">Manually populate data tables</span></span>  
  
-   <span data-ttu-id="1e38c-157">изменять существующие таблицы данных;</span><span class="sxs-lookup"><span data-stu-id="1e38c-157">Edit existing data tables</span></span>  
  
-   <span data-ttu-id="1e38c-158">формировать XML-схемы из XML-документа.</span><span class="sxs-lookup"><span data-stu-id="1e38c-158">Generate an XML Schema from an XML document</span></span>  
  
## <a name="xml-view"></a><span data-ttu-id="1e38c-159">Представление XML</span><span class="sxs-lookup"><span data-stu-id="1e38c-159">XML View</span></span>  
 <span data-ttu-id="1e38c-160">Представление XML — это редактор для работы с кодом XML, обеспечивающий технологию IntelliSense и выделение кода цветом.</span><span class="sxs-lookup"><span data-stu-id="1e38c-160">XML view provides an editor for editing raw XML and provides IntelliSense and color coding.</span></span> <span data-ttu-id="1e38c-161">Завершение операторов доступно при работе с файлами XSD и XML, для которых есть соответствующие схемы.</span><span class="sxs-lookup"><span data-stu-id="1e38c-161">Statement completion is available when working on .xsd files and .xml files that have an associated schema.</span></span> <span data-ttu-id="1e38c-162">Введите, \< чтобы инициировать тег, и отобразится список элементов, допустимых в этом расположении.</span><span class="sxs-lookup"><span data-stu-id="1e38c-162">Type \< to initiate a tag and you will be presented with a list of elements that are valid at that location.</span></span> <span data-ttu-id="1e38c-163">После ввода элемента и нажатия клавиши ПРОБЕЛ программа выводит список атрибутов, поддерживаемых данным элементом.</span><span class="sxs-lookup"><span data-stu-id="1e38c-163">After you type the element name and press the SPACEBAR, you will be presented with a list of attributes that the element supports.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="1e38c-164">недоступны на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="1e38c-164">IntelliSense options are not available on the toolbar.</span></span> <span data-ttu-id="1e38c-165">Для доступа к этим параметрам в XML-редакторе в меню **Правка** выберите пункт **технология IntelliSense**.</span><span class="sxs-lookup"><span data-stu-id="1e38c-165">When in the XML Editor, to access the options, on the **Edit** menu, click **IntelliSense**.</span></span>  
  
## <a name="showplan-view"></a><span data-ttu-id="1e38c-166">Представление инструкции SHOWPLAN</span><span class="sxs-lookup"><span data-stu-id="1e38c-166">SHOWPLAN view</span></span>  
 <span data-ttu-id="1e38c-167">Планы запросов можно сохранить в XML-формате, если они создавались с использованием параметра SET SHOWPLAN_XML ON.</span><span class="sxs-lookup"><span data-stu-id="1e38c-167">Query plans can be saved in XML format when created using SET SHOWPLAN_XML ON option.</span></span> <span data-ttu-id="1e38c-168">Дважды щелкните мышью по файлу с расширением SHOWPLAN, чтобы открыть план запроса.</span><span class="sxs-lookup"><span data-stu-id="1e38c-168">Double-click a file with the .showplan extension to open the query plan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e38c-169">См. также:</span><span class="sxs-lookup"><span data-stu-id="1e38c-169">See Also</span></span>  
 [<span data-ttu-id="1e38c-170">Сохранение плана выполнения в формате XML</span><span class="sxs-lookup"><span data-stu-id="1e38c-170">Save an Execution Plan in XML Format</span></span>](../performance/save-an-execution-plan-in-xml-format.md)  
  
  
