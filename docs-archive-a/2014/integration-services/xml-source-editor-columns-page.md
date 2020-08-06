---
title: Редактор источника «XML» (страница «Столбцы») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.xmlsourceadapter.columns.f1
helpviewer_keywords:
- XML Source Editor
ms.assetid: 5162c400-b2fc-4711-af0f-609132fbaaad
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0b9433b7a2c4f08f9e0c70d568f8fc037ceb7c6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736503"
---
# <a name="xml-source-editor-columns-page"></a><span data-ttu-id="34968-102">Редактор источника «XML» (страница «Столбцы»)</span><span class="sxs-lookup"><span data-stu-id="34968-102">XML Source Editor (Columns Page)</span></span>
  <span data-ttu-id="34968-103">Узел **Столбцы** диалогового окна **Редактор источника "XML"** используется для настройки соответствия выходного столбца внешнему (исходному) столбцу.</span><span class="sxs-lookup"><span data-stu-id="34968-103">Use the **Columns** node of the **XML Source Editor** dialog box to map an output column to an external (source) column.</span></span>  
  
 <span data-ttu-id="34968-104">Дополнительные сведения об источнике XML см. в разделе [XML Source](data-flow/xml-source.md).</span><span class="sxs-lookup"><span data-stu-id="34968-104">For more information about the XML source, see [XML Source](data-flow/xml-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="34968-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="34968-105">Options</span></span>  
 <span data-ttu-id="34968-106">**Доступные внешние столбцы**</span><span class="sxs-lookup"><span data-stu-id="34968-106">**Available External Columns**</span></span>  
 <span data-ttu-id="34968-107">Просмотр списка доступных внешних столбцов источника данных.</span><span class="sxs-lookup"><span data-stu-id="34968-107">View the list of available external columns in the data source.</span></span> <span data-ttu-id="34968-108">В этой таблице нельзя добавлять или удалять столбцы.</span><span class="sxs-lookup"><span data-stu-id="34968-108">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="34968-109">**Внешний столбец**</span><span class="sxs-lookup"><span data-stu-id="34968-109">**External Column**</span></span>  
 <span data-ttu-id="34968-110">Просмотр внешних (исходных) столбцов в том порядке, в котором их будет считывать задача.</span><span class="sxs-lookup"><span data-stu-id="34968-110">View external (source) columns in the order in which the task will read them.</span></span> <span data-ttu-id="34968-111">Этот порядок можно изменить, сначала очистив выделенные столбцы в таблице, отображаемой в редакторе, а затем выбрав внешние столбцы из списка в другом порядке.</span><span class="sxs-lookup"><span data-stu-id="34968-111">You can change this order by first clearing the selected columns in the table displayed in the editor, and then selecting external columns from the list in a different order.</span></span>  
  
 <span data-ttu-id="34968-112">**Выходной столбец**</span><span class="sxs-lookup"><span data-stu-id="34968-112">**Output Column**</span></span>  
 <span data-ttu-id="34968-113">Введите уникальное имя для каждого выходного столбца.</span><span class="sxs-lookup"><span data-stu-id="34968-113">Provide a unique name for each output column.</span></span> <span data-ttu-id="34968-114">По умолчанию используется имя выбранного внешнего (исходного) столбца, однако можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="34968-114">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="34968-115">Выбранное имя будет отображаться в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34968-115">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34968-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="34968-116">See Also</span></span>  
 <span data-ttu-id="34968-117">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="34968-117">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="34968-118">[Редактор источника "XML" &#40;страница "Диспетчер соединений"&#41;](../../2014/integration-services/xml-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="34968-118">[XML Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/xml-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="34968-119">[Редактор источника "XML" &#40;страница "вывод ошибок"&#41;](../../2014/integration-services/xml-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="34968-119">[XML Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/xml-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="34968-120">Извлечение данных с помощью XML-источника</span><span class="sxs-lookup"><span data-stu-id="34968-120">Extract Data by Using the XML Source</span></span>](data-flow/extract-data-by-using-the-xml-source.md)  
  
  
