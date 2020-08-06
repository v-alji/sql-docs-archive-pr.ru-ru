---
title: Редактор источника OData (страница «соединение») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- Sql12.dts.designer.odatasource.connection.f1
ms.assetid: 20bcd347-4547-4fad-b182-9571030101df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6ecd0d060ea2197ae7174325b654645fefa23505
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665420"
---
# <a name="odata-source-editor-connection-page"></a><span data-ttu-id="406b3-102">Редактор источника OData (страница «Подключение»)</span><span class="sxs-lookup"><span data-stu-id="406b3-102">OData Source Editor (Connection Page)</span></span>
  <span data-ttu-id="406b3-103">Страница **Диспетчер соединений** диалогового окна **Редактор источника OData** служит для выбора диспетчера соединений OData для источника.</span><span class="sxs-lookup"><span data-stu-id="406b3-103">Use the **Connection** page of the **OData Source Editor** dialog box to select the OData connection manager for the OData source.</span></span> <span data-ttu-id="406b3-104">На этой странице также можно задать путь к коллекции или ресурсу, а также параметры запроса, чтобы указать, какие данные нужно получить из источника OData.</span><span class="sxs-lookup"><span data-stu-id="406b3-104">This page also lets you specify a collection or a resource path and any query options to indicate what data needs to be retrieved from the OData source.</span></span> <span data-ttu-id="406b3-105">Дополнительные сведения об источнике OData см. в разделе [OData Source](data-flow/odata-source.md).</span><span class="sxs-lookup"><span data-stu-id="406b3-105">To learn more about the OData source, see [OData Source](data-flow/odata-source.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="406b3-106">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="406b3-106">Static Options</span></span>  
 <span data-ttu-id="406b3-107">**Диспетчер соединений OData**</span><span class="sxs-lookup"><span data-stu-id="406b3-107">**OData connection manager**</span></span>  
 <span data-ttu-id="406b3-108">Выберите из списка существующий диспетчер соединений или создайте новое соединение, нажав кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="406b3-108">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="406b3-109">**Создать**</span><span class="sxs-lookup"><span data-stu-id="406b3-109">**New**</span></span>  
 <span data-ttu-id="406b3-110">Создайте новый диспетчер соединений с помощью диалогового окна **Редактор диспетчера соединений OData** .</span><span class="sxs-lookup"><span data-stu-id="406b3-110">Create a new connection manager by using the **OData Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="406b3-111">**Использование пути к коллекции или ресурсу**</span><span class="sxs-lookup"><span data-stu-id="406b3-111">**Use collection or resource path**</span></span>  
 <span data-ttu-id="406b3-112">Укажите метод выбора данных из источника.</span><span class="sxs-lookup"><span data-stu-id="406b3-112">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="406b3-113">Параметр</span><span class="sxs-lookup"><span data-stu-id="406b3-113">Option</span></span>|<span data-ttu-id="406b3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="406b3-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="406b3-115">Коллекция</span><span class="sxs-lookup"><span data-stu-id="406b3-115">Collection</span></span>|<span data-ttu-id="406b3-116">Извлечение данных из источника OData с помощью имени коллекции.</span><span class="sxs-lookup"><span data-stu-id="406b3-116">Retrieve data from the OData source by using a collection name.</span></span>|  
|<span data-ttu-id="406b3-117">Путь к ресурсу</span><span class="sxs-lookup"><span data-stu-id="406b3-117">Resource Path</span></span>|<span data-ttu-id="406b3-118">Извлечение данных из источника OData с помощью пути к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="406b3-118">Retrieve data from the OData source by using a resource path.</span></span>|  
  
 <span data-ttu-id="406b3-119">**Параметры запроса**</span><span class="sxs-lookup"><span data-stu-id="406b3-119">**Query options**</span></span>  
 <span data-ttu-id="406b3-120">Укажите параметры запроса.</span><span class="sxs-lookup"><span data-stu-id="406b3-120">Specify options for the query.</span></span>  <span data-ttu-id="406b3-121">Например: $top=5</span><span class="sxs-lookup"><span data-stu-id="406b3-121">For example: $top=5</span></span>  
  
 <span data-ttu-id="406b3-122">**URL-адрес канала**</span><span class="sxs-lookup"><span data-stu-id="406b3-122">**Feed url**</span></span>  
 <span data-ttu-id="406b3-123">Отображает доступный только для чтения URL-адрес канала на основе параметров, выбранных в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="406b3-123">Displays the read-only Feed URL based on options you selected on this dialog box.</span></span>  
  
 <span data-ttu-id="406b3-124">**Предварительный просмотр**</span><span class="sxs-lookup"><span data-stu-id="406b3-124">**Preview**</span></span>  
 <span data-ttu-id="406b3-125">Предварительный просмотр результатов в диалоговом окне **Предварительный просмотр** .</span><span class="sxs-lookup"><span data-stu-id="406b3-125">Preview results by using the **Preview** dialog box.</span></span> <span data-ttu-id="406b3-126">В окне**Предварительный просмотр** может отображаться до 20 строк.</span><span class="sxs-lookup"><span data-stu-id="406b3-126">**Preview** can display up to 20 rows.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="406b3-127">Динамические параметры</span><span class="sxs-lookup"><span data-stu-id="406b3-127">Dynamic Options</span></span>  
  
### <a name="use-collection-or-resource-path--collection"></a><span data-ttu-id="406b3-128">Использование пути к коллекции или ресурсу = коллекция</span><span class="sxs-lookup"><span data-stu-id="406b3-128">Use collection or resource path = Collection</span></span>  
 <span data-ttu-id="406b3-129">**Коллекция**</span><span class="sxs-lookup"><span data-stu-id="406b3-129">**Collection**</span></span>  
 <span data-ttu-id="406b3-130">Выберите коллекцию из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="406b3-130">Select a collection from the drop-down list.</span></span>  
  
### <a name="use-collection-or-resource-path--resource-path"></a><span data-ttu-id="406b3-131">Использование пути к коллекции или ресурсу = путь к ресурсу</span><span class="sxs-lookup"><span data-stu-id="406b3-131">Use collection or resource path = Resource Path</span></span>  
 <span data-ttu-id="406b3-132">**Путь к ресурсу**</span><span class="sxs-lookup"><span data-stu-id="406b3-132">**Resource path**</span></span>  
 <span data-ttu-id="406b3-133">Введите путь к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="406b3-133">Type a resource path.</span></span> <span data-ttu-id="406b3-134">Например: Employees</span><span class="sxs-lookup"><span data-stu-id="406b3-134">For example: Employees</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="406b3-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="406b3-135">See Also</span></span>  
 <span data-ttu-id="406b3-136">[Редактор источника OData — страница &#40;столбцы&#41;](../../2014/integration-services/odata-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="406b3-136">[OData Source Editor &#40;Columns Page&#41;](../../2014/integration-services/odata-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="406b3-137">[Редактор источника OData &#40;страница "вывод ошибок"&#41;](../../2014/integration-services/odata-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="406b3-137">[OData Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/odata-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="406b3-138">Диспетчер соединений OData</span><span class="sxs-lookup"><span data-stu-id="406b3-138">OData Connection Manager</span></span>](connection-manager/odata-connection-manager.md)  
  
  
