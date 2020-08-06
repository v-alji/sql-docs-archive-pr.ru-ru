---
title: Редактор преобразования "Уточняющий запрос" (страница "Дополнительно") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.advanced.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: f3395c65-0320-47f9-8d83-daaa082d8713
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 23f235ef0506da7ac808d832db6ac36d53cfa604
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664324"
---
# <a name="lookup-transformation-editor-advanced-page"></a><span data-ttu-id="9a7ae-102">Редактор преобразования «Уточняющий запрос» (страница «Дополнительно»)</span><span class="sxs-lookup"><span data-stu-id="9a7ae-102">Lookup Transformation Editor (Advanced Page)</span></span>
  <span data-ttu-id="9a7ae-103">Используйте вкладку **Дополнительно** диалогового окна **Редактор преобразования «Уточняющий запрос»** для настройки частичного кэширования и для изменения инструкции SQL для преобразования «Уточняющий запрос».</span><span class="sxs-lookup"><span data-stu-id="9a7ae-103">Use the **Advanced** page of the **Lookup Transformation Editor** dialog box to configure partial caching and to modify the SQL statement for the Lookup transformation.</span></span>  
  
 <span data-ttu-id="9a7ae-104">Дополнительные сведения о преобразовании «Уточняющий запрос» см. в разделе [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="9a7ae-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9a7ae-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="9a7ae-105">Options</span></span>  
 <span data-ttu-id="9a7ae-106">**Размер кэша (32-разрядная версия)**</span><span class="sxs-lookup"><span data-stu-id="9a7ae-106">**Cache size (32-bit)**</span></span>  
 <span data-ttu-id="9a7ae-107">Настройте размер кэша (в мегабайтах) для 32-разрядных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="9a7ae-107">Adjust the  cache size (in megabytes) for 32-bit computers.</span></span> <span data-ttu-id="9a7ae-108">Значение по умолчанию 5.</span><span class="sxs-lookup"><span data-stu-id="9a7ae-108">The default value is 5 megabytes.</span></span>  
  
 <span data-ttu-id="9a7ae-109">**Размер кэша (64-разрядная версия)**</span><span class="sxs-lookup"><span data-stu-id="9a7ae-109">**Cache size (64-bit)**</span></span>  
 <span data-ttu-id="9a7ae-110">Настройте размер кэша (в мегабайтах) для 64-разрядных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="9a7ae-110">Adjust the cache size (in megabytes) for 64-bit computers.</span></span> <span data-ttu-id="9a7ae-111">Значение по умолчанию 5.</span><span class="sxs-lookup"><span data-stu-id="9a7ae-111">The default value is 5 megabytes.</span></span>  
  
 <span data-ttu-id="9a7ae-112">**Включить кэширование для строк с несовпадающими записями**</span><span class="sxs-lookup"><span data-stu-id="9a7ae-112">**Enable cache for rows with no matching entries**</span></span>  
 <span data-ttu-id="9a7ae-113">Кэшировать строки без совпадающих элементов в эталонном наборе данных.</span><span class="sxs-lookup"><span data-stu-id="9a7ae-113">Cache rows with no matching entries in the reference dataset.</span></span>  
  
 <span data-ttu-id="9a7ae-114">**Размещение из кэша**</span><span class="sxs-lookup"><span data-stu-id="9a7ae-114">**Allocation from cache**</span></span>  
 <span data-ttu-id="9a7ae-115">Задать долю кэша (в процентах), которую следует выделять для строк без совпадающих элементов в эталонном наборе данных.</span><span class="sxs-lookup"><span data-stu-id="9a7ae-115">Specify the percentage of the cache to allocate for rows with no matching entries in the reference dataset.</span></span>  
  
 <span data-ttu-id="9a7ae-116">**Изменить инструкцию SQL**</span><span class="sxs-lookup"><span data-stu-id="9a7ae-116">**Modify the SQL statement**</span></span>  
 <span data-ttu-id="9a7ae-117">Изменить инструкцию SQL, которая используется для формирования эталонного набора данных.</span><span class="sxs-lookup"><span data-stu-id="9a7ae-117">Modify the SQL statement that is used to generate the reference dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a7ae-118">Дополнительная инструкция SQL, которую можно указать на этой странице, заменяет имя таблицы, указанное на странице **Соединение\*\*\*\*Редактора преобразования «Уточняющий запрос»**.</span><span class="sxs-lookup"><span data-stu-id="9a7ae-118">The optional SQL statement that you specify on this page overrides and replaces the table name that you specified on the **Connection** page of the **Lookup Transformation Editor**.</span></span> <span data-ttu-id="9a7ae-119">Дополнительные сведения см. в разделе [Редактор преобразования "Уточняющий запрос" (страница "Соединение")](../../2014/integration-services/lookup-transformation-editor-connection-page.md).</span><span class="sxs-lookup"><span data-stu-id="9a7ae-119">For more information, see [Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md).</span></span>  
  
 <span data-ttu-id="9a7ae-120">**Задать параметры**</span><span class="sxs-lookup"><span data-stu-id="9a7ae-120">**Set Parameters**</span></span>  
 <span data-ttu-id="9a7ae-121">Сопоставить входные столбцы с параметрами, используя диалоговое окно **Установка параметров запроса** .</span><span class="sxs-lookup"><span data-stu-id="9a7ae-121">Map input columns to parameters by using the **Set Query Parameters** dialog box.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="9a7ae-122">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="9a7ae-122">External Resources</span></span>  
 <span data-ttu-id="9a7ae-123">Запись в блоге [Режимы кэша уточняющих запросов](https://go.microsoft.com/fwlink/?LinkId=219518) на сайте blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="9a7ae-123">Blog entry, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) on blogs.msdn.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a7ae-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="9a7ae-124">See Also</span></span>  
 <span data-ttu-id="9a7ae-125">[Редактор преобразования "Уточняющий запрос" &#40;общие&#41;страницы](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="9a7ae-125">[Lookup Transformation Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="9a7ae-126">[Редактор преобразования "Уточняющий запрос" &#40;страница подключения&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="9a7ae-126">[Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span></span>  
 <span data-ttu-id="9a7ae-127">[Редактор преобразования «Уточняющий запрос» &#40;столбцов&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="9a7ae-127">[Lookup Transformation Editor &#40;Columns Page&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span></span>  
 <span data-ttu-id="9a7ae-128">[Редактор преобразования "Уточняющий запрос" &#40;страница "вывод ошибок"&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="9a7ae-128">[Lookup Transformation Editor &#40;Error Output Page&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="9a7ae-129">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="9a7ae-129">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="9a7ae-130">преобразование «Нечеткий уточняющий запрос»</span><span class="sxs-lookup"><span data-stu-id="9a7ae-130">Fuzzy Lookup Transformation</span></span>](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
