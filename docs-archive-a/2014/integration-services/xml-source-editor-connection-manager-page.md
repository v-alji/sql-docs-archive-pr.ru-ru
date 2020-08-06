---
title: Редактор источника «XML» (страница «Диспетчер соединений») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.xmlsourceadapter.connectionmanager.f1
helpviewer_keywords:
- XML Source Editor
ms.assetid: e6507403-a3ce-4b6f-91fc-a7de9f7b6283
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0e40ca6ef2d8fbcd10b756a2ce15f33730c367d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668424"
---
# <a name="xml-source-editor-connection-manager-page"></a><span data-ttu-id="8cd3b-102">Редактор источника «XML» (страница «Диспетчер соединений»)</span><span class="sxs-lookup"><span data-stu-id="8cd3b-102">XML Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="8cd3b-103">Используйте страницу **Диспетчер соединений** компонента **Редактор источника «XML»** для указания XML-файла и XSD-схемы, выполняющей преобразование XML-данных.</span><span class="sxs-lookup"><span data-stu-id="8cd3b-103">Use the **Connection Manager** page of the **XML Source Editor** to specify an XML file and the XSD that transforms the XML data.</span></span>  
  
 <span data-ttu-id="8cd3b-104">Дополнительные сведения об источнике XML см. в разделе [XML Source](data-flow/xml-source.md).</span><span class="sxs-lookup"><span data-stu-id="8cd3b-104">For more information about the XML source, see [XML Source](data-flow/xml-source.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="8cd3b-105">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="8cd3b-105">Static Options</span></span>  
 <span data-ttu-id="8cd3b-106">**Режим доступа к данным**</span><span class="sxs-lookup"><span data-stu-id="8cd3b-106">**Data access mode**</span></span>  
 <span data-ttu-id="8cd3b-107">Укажите метод выбора данных из источника.</span><span class="sxs-lookup"><span data-stu-id="8cd3b-107">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="8cd3b-108">Значение</span><span class="sxs-lookup"><span data-stu-id="8cd3b-108">Value</span></span>|<span data-ttu-id="8cd3b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="8cd3b-109">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8cd3b-110">Расположение XML-файла</span><span class="sxs-lookup"><span data-stu-id="8cd3b-110">XML file location</span></span>|<span data-ttu-id="8cd3b-111">Извлечь данные из XML-файла.</span><span class="sxs-lookup"><span data-stu-id="8cd3b-111">Retrieve data from an XML file.</span></span>|  
|<span data-ttu-id="8cd3b-112">XML-файл из переменной</span><span class="sxs-lookup"><span data-stu-id="8cd3b-112">XML file from variable</span></span>|<span data-ttu-id="8cd3b-113">Указать имя XML-файла в переменной.</span><span class="sxs-lookup"><span data-stu-id="8cd3b-113">Specify the XML file name in a variable.</span></span><br /><br /> <span data-ttu-id="8cd3b-114">**Дополнительные сведения** [Использование переменных в пакетах](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="8cd3b-114">**Related information**: [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="8cd3b-115">XML-данные из переменной</span><span class="sxs-lookup"><span data-stu-id="8cd3b-115">XML data from variable</span></span>|<span data-ttu-id="8cd3b-116">Извлечь XML-данные из значения переменной.</span><span class="sxs-lookup"><span data-stu-id="8cd3b-116">Retrieve XML data from a variable.</span></span>|  
  
 <span data-ttu-id="8cd3b-117">**Использовать встроенную схему**</span><span class="sxs-lookup"><span data-stu-id="8cd3b-117">**Use inline schema**</span></span>  
 <span data-ttu-id="8cd3b-118">Устанавливает, содержит ли источник XML-данных в себе XSD-схему, определяющую и проверяющую его структуру и данные.</span><span class="sxs-lookup"><span data-stu-id="8cd3b-118">Specify whether the XML source data itself contains the XSD schema that defines and validates its structure and data.</span></span>  
  
 <span data-ttu-id="8cd3b-119">**Местоположение XSD**</span><span class="sxs-lookup"><span data-stu-id="8cd3b-119">**XSD location**</span></span>  
 <span data-ttu-id="8cd3b-120">Введите путь и имя файла XSD-схемы или найдите этот файл, нажав кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="8cd3b-120">Type the path and file name of the XSD schema file, or locate the file by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="8cd3b-121">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="8cd3b-121">**Browse**</span></span>  
 <span data-ttu-id="8cd3b-122">Используйте диалоговое окно **Открыть** для выбора нужного файла XSD-схемы.</span><span class="sxs-lookup"><span data-stu-id="8cd3b-122">Use the **Open** dialog box to locate the XSD schema file.</span></span>  
  
 <span data-ttu-id="8cd3b-123">**Сформировать XSD**</span><span class="sxs-lookup"><span data-stu-id="8cd3b-123">**Generate XSD**</span></span>  
 <span data-ttu-id="8cd3b-124">Используйте диалоговое окно **Сохранение** для выбора местоположения автоматически сформированного файла XSD-схемы.</span><span class="sxs-lookup"><span data-stu-id="8cd3b-124">Use the **Save As** dialog box to select a location for the auto-generated XSD schema file.</span></span> <span data-ttu-id="8cd3b-125">Редактор формирует схему на основе структуры XML-данных.</span><span class="sxs-lookup"><span data-stu-id="8cd3b-125">The editor infers the schema from the structure of the XML data.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="8cd3b-126">Динамические параметры режима доступа к данным</span><span class="sxs-lookup"><span data-stu-id="8cd3b-126">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--xml-file-location"></a><span data-ttu-id="8cd3b-127">Режим доступа к данным = местоположение XML</span><span class="sxs-lookup"><span data-stu-id="8cd3b-127">Data access mode = XML file location</span></span>  
 <span data-ttu-id="8cd3b-128">**Местоположение XML**</span><span class="sxs-lookup"><span data-stu-id="8cd3b-128">**XML location**</span></span>  
 <span data-ttu-id="8cd3b-129">Введите путь и имя файла с XML-данными или определите расположение файла, нажав кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="8cd3b-129">Type the path and file name of the XML data file, or locate the file by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="8cd3b-130">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="8cd3b-130">**Browse**</span></span>  
 <span data-ttu-id="8cd3b-131">Используйте диалоговое окно **Открыть** для нахождения нужного файла с XML-данными.</span><span class="sxs-lookup"><span data-stu-id="8cd3b-131">Use the **Open** dialog box to locate the XML data file.</span></span>  
  
### <a name="data-access-mode--xml-file-from-variable"></a><span data-ttu-id="8cd3b-132">Режим доступа к данным = XML-файл из переменной</span><span class="sxs-lookup"><span data-stu-id="8cd3b-132">Data access mode = XML file from variable</span></span>  
 <span data-ttu-id="8cd3b-133">**Имя переменной**</span><span class="sxs-lookup"><span data-stu-id="8cd3b-133">**Variable name**</span></span>  
 <span data-ttu-id="8cd3b-134">Выберите переменную, содержащую путь и имя XML-файла.</span><span class="sxs-lookup"><span data-stu-id="8cd3b-134">Select the variable that contains the path and file name of the XML file.</span></span>  
  
### <a name="data-access-mode--xml-data-from-variable"></a><span data-ttu-id="8cd3b-135">Режим доступа к данным = XML-данные из переменной</span><span class="sxs-lookup"><span data-stu-id="8cd3b-135">Data access mode = XML data from variable</span></span>  
 <span data-ttu-id="8cd3b-136">**Имя переменной**</span><span class="sxs-lookup"><span data-stu-id="8cd3b-136">**Variable name**</span></span>  
 <span data-ttu-id="8cd3b-137">Выберите переменную, содержащую XML-данные.</span><span class="sxs-lookup"><span data-stu-id="8cd3b-137">Select the variable that contains the XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cd3b-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="8cd3b-138">See Also</span></span>  
 <span data-ttu-id="8cd3b-139">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8cd3b-139">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="8cd3b-140">[Редактор источника "XML" &#40;столбцы "&#41;](../../2014/integration-services/xml-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="8cd3b-140">[XML Source Editor &#40;Columns Page&#41;](../../2014/integration-services/xml-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="8cd3b-141">[Редактор источника "XML" &#40;страница "вывод ошибок"&#41;](../../2014/integration-services/xml-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="8cd3b-141">[XML Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/xml-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="8cd3b-142">Извлечение данных с помощью XML-источника</span><span class="sxs-lookup"><span data-stu-id="8cd3b-142">Extract Data by Using the XML Source</span></span>](data-flow/extract-data-by-using-the-xml-source.md)  
  
  
