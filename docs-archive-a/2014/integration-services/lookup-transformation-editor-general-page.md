---
title: Редактор преобразования "Уточняющий запрос" (страница "Общие") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.general.f1
ms.assetid: 4bd15e48-0feb-4f95-be91-5df58105dbfb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa178118f7e090b6a3c15c7ab9347f322461f07b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729622"
---
# <a name="lookup-transformation-editor-general-page"></a><span data-ttu-id="98bf2-102">Редактор преобразования «Уточняющий запрос» (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="98bf2-102">Lookup Transformation Editor (General Page)</span></span>
  <span data-ttu-id="98bf2-103">Используйте страницу **Общие** в диалоговом окне «Редактор преобразования "Уточняющий запрос"», чтобы выбрать режим кэширования, выбрать тип соединения и указать метод обработки строк без совпадающих записей.</span><span class="sxs-lookup"><span data-stu-id="98bf2-103">Use the **General** page of the Lookup Transformation Editor dialog box to select the cache mode, select the connection type, and specify how to handle rows with no matching entries.</span></span>  
  
 <span data-ttu-id="98bf2-104">Дополнительные сведения о преобразовании «Уточняющий запрос» см. в разделе [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="98bf2-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="98bf2-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="98bf2-105">Options</span></span>  
 <span data-ttu-id="98bf2-106">**Полное кэширование**</span><span class="sxs-lookup"><span data-stu-id="98bf2-106">**Full cache**</span></span>  
 <span data-ttu-id="98bf2-107">Формировать и загружать эталонный набор данных в кэш до запуска преобразования «Уточняющий запрос».</span><span class="sxs-lookup"><span data-stu-id="98bf2-107">Generate and load the reference dataset into cache before the Lookup transformation is executed.</span></span>  
  
 <span data-ttu-id="98bf2-108">**Частичное кэширование**</span><span class="sxs-lookup"><span data-stu-id="98bf2-108">**Partial cache**</span></span>  
 <span data-ttu-id="98bf2-109">При выполнении преобразования «Уточняющий запрос» — создать эталонный набор данных.</span><span class="sxs-lookup"><span data-stu-id="98bf2-109">Generate the reference dataset during the execution of the Lookup transformation.</span></span> <span data-ttu-id="98bf2-110">Загружать в кэш строки с совпадающими записями в эталонном наборе данных и строки без совпадающих записей в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="98bf2-110">Load the rows with matching entries in the reference dataset and the rows with no matching entries in the dataset into cache.</span></span>  
  
 <span data-ttu-id="98bf2-111">**Нет кэша**</span><span class="sxs-lookup"><span data-stu-id="98bf2-111">**No cache**</span></span>  
 <span data-ttu-id="98bf2-112">При выполнении преобразования «Уточняющий запрос» — создать эталонный набор данных.</span><span class="sxs-lookup"><span data-stu-id="98bf2-112">Generate the reference dataset during the execution of the Lookup transformation.</span></span> <span data-ttu-id="98bf2-113">Данные в кэш не загружаются.</span><span class="sxs-lookup"><span data-stu-id="98bf2-113">No data is loaded into cache.</span></span>  
  
 <span data-ttu-id="98bf2-114">**Диспетчер соединений с кэшем**</span><span class="sxs-lookup"><span data-stu-id="98bf2-114">**Cache connection manager**</span></span>  
 <span data-ttu-id="98bf2-115">Настроить преобразование «Уточняющий запрос» на использование диспетчера соединений с кэшем.</span><span class="sxs-lookup"><span data-stu-id="98bf2-115">Configure the Lookup transformation to use a Cache connection manager.</span></span> <span data-ttu-id="98bf2-116">Этот параметр доступен только в случае, если выбран параметр «Полное кэширование».</span><span class="sxs-lookup"><span data-stu-id="98bf2-116">This option is available only if the Full cache option is selected.</span></span>  
  
 <span data-ttu-id="98bf2-117">**Диспетчер соединений OLE DB**</span><span class="sxs-lookup"><span data-stu-id="98bf2-117">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="98bf2-118">Настроить преобразование «Уточняющий запрос» на использование диспетчера соединений OLE DB.</span><span class="sxs-lookup"><span data-stu-id="98bf2-118">Configure the Lookup transformation to use an OLE DB connection manager.</span></span>  
  
 <span data-ttu-id="98bf2-119">**Метод обработки строк без совпадающих элементов**</span><span class="sxs-lookup"><span data-stu-id="98bf2-119">**Specify how to handle rows with no matching entries**</span></span>  
 <span data-ttu-id="98bf2-120">Выбрать режим для обработки строк, не имеющих совпадения ни с одной из записей в эталонном наборе данных.</span><span class="sxs-lookup"><span data-stu-id="98bf2-120">Select an option for handling rows that do not match at least one entry in the reference dataset.</span></span>  
  
 <span data-ttu-id="98bf2-121">При выборе режима **Перенаправлять строки в выход несовпадающих строк**строки будут перенаправлены в выход несовпадающих строк и не будут обрабатываться как ошибки.</span><span class="sxs-lookup"><span data-stu-id="98bf2-121">When you select **Redirect rows to no match output**, the rows are redirected to a no match output and are not handled as errors.</span></span> <span data-ttu-id="98bf2-122">Параметр **Ошибка** недоступен на странице **Вывод ошибок** в диалоговом окне **Редактор преобразования «Уточняющий запрос»** .</span><span class="sxs-lookup"><span data-stu-id="98bf2-122">The **Error** option on the **Error Output** page of the **Lookup Transformation Editor** dialog box is not available.</span></span>  
  
 <span data-ttu-id="98bf2-123">При выборе любого другого параметра в списке **Метод обработки строк без совпадающих элементов** , строки будут обрабатываться как ошибки.</span><span class="sxs-lookup"><span data-stu-id="98bf2-123">When you select any other option in the **Specify how to handle rows with no matching entries** list box, the rows are handled as errors.</span></span> <span data-ttu-id="98bf2-124">Параметр **Ошибка** доступен на странице **Вывод ошибок** .</span><span class="sxs-lookup"><span data-stu-id="98bf2-124">The **Error** option on the **Error Output** page is available.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="98bf2-125">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="98bf2-125">External Resources</span></span>  
 <span data-ttu-id="98bf2-126">Запись в блоге [Режимы кэша уточняющих запросов](https://go.microsoft.com/fwlink/?LinkId=219518) на сайте blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="98bf2-126">Blog entry, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) on blogs.msdn.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98bf2-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="98bf2-127">See Also</span></span>  
 <span data-ttu-id="98bf2-128">[Диспетчер соединений с кэшем](connection-manager/cache-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="98bf2-128">[Cache Connection Manager](connection-manager/cache-connection-manager.md) </span></span>  
 <span data-ttu-id="98bf2-129">[Редактор преобразования "Уточняющий запрос" &#40;страница подключения&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="98bf2-129">[Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span></span>  
 <span data-ttu-id="98bf2-130">[Редактор преобразования «Уточняющий запрос» &#40;столбцов&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="98bf2-130">[Lookup Transformation Editor &#40;Columns Page&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span></span>  
 <span data-ttu-id="98bf2-131">[Редактор преобразования "Уточняющий запрос" &#40;страница "Дополнительно"&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="98bf2-131">[Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="98bf2-132">Редактор преобразования "Уточняющий запрос" (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="98bf2-132">Lookup Transformation Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/lookup-transformation-editor-error-output-page.md)  
  
  
