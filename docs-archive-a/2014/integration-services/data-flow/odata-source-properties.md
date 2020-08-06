---
title: Свойства источника OData | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4fde5bb0-6d78-4ec4-8f0b-67f91c53fe99
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8139f79ed595ca3e6204f96823f6bc95e6fb40df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750039"
---
# <a name="odata-source-properties"></a><span data-ttu-id="e2983-102">Свойства источника OData</span><span class="sxs-lookup"><span data-stu-id="e2983-102">OData Source Properties</span></span>
  <span data-ttu-id="e2983-103">Если щелкнуть правой кнопкой **Источник OData** в потоке данных и выбрать **Свойства**, то свойства компонента **Источник OData** будут отображены в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="e2983-103">When you right-click **OData Source** in the data flow and click **Properties**, you will see properties for the **OData Source** component in the **Properties** window.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e2983-104">Свойство</span><span class="sxs-lookup"><span data-stu-id="e2983-104">Property</span></span>|<span data-ttu-id="e2983-105">Описание</span><span class="sxs-lookup"><span data-stu-id="e2983-105">Description</span></span>|  
|<span data-ttu-id="e2983-106">CollectionName</span><span class="sxs-lookup"><span data-stu-id="e2983-106">CollectionName</span></span>|<span data-ttu-id="e2983-107">Имя коллекции, которую необходимо получить из службы OData.</span><span class="sxs-lookup"><span data-stu-id="e2983-107">Name of the collection you wish to retrieve from the OData service.</span></span> <span data-ttu-id="e2983-108">Свойство **CollectionName** используется в том случае, когда значение **UseResourcePath** равно False.</span><span class="sxs-lookup"><span data-stu-id="e2983-108">The **CollectionName** property is used when **UseResourcePath** is False.</span></span><br /><br /> <span data-ttu-id="e2983-109">Это свойство поддерживает выражения, что позволяет задать значение во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e2983-109">This property is expression-able, allowing the value to be set at runtime.</span></span> <span data-ttu-id="e2983-110">Но если метаданные коллекции не соответствуют метаданным, которые использовались во время разработки, то произойдет ошибка проверки, из-за чего выполнение потока данных приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="e2983-110">However, if the metadata of the collection does not match the metadata that was used at design time, a validation error will occur, causing the data flow execution to fail.</span></span>|  
|<span data-ttu-id="e2983-111">DefaultStringLength</span><span class="sxs-lookup"><span data-stu-id="e2983-111">DefaultStringLength</span></span>|<span data-ttu-id="e2983-112">Это значение указывает длину по умолчанию для строковых столбцов без максимальной длины.</span><span class="sxs-lookup"><span data-stu-id="e2983-112">This value specifies default length for string columns that have no max length.</span></span><br /><br /> <span data-ttu-id="e2983-113">**По умолчанию:** 4000</span><span class="sxs-lookup"><span data-stu-id="e2983-113">**Default:** 4000</span></span>|  
|<span data-ttu-id="e2983-114">Запрос</span><span class="sxs-lookup"><span data-stu-id="e2983-114">Query</span></span>|<span data-ttu-id="e2983-115">Параметры запроса OData.</span><span class="sxs-lookup"><span data-stu-id="e2983-115">The OData query parameters.</span></span> <span data-ttu-id="e2983-116">Это свойство поддерживает выражения и может быть задано во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e2983-116">This property is expression-able and can be set at runtime.</span></span>|  
|<span data-ttu-id="e2983-117">ResourcePath</span><span class="sxs-lookup"><span data-stu-id="e2983-117">ResourcePath</span></span>|<span data-ttu-id="e2983-118">Это свойство используется в том случае, когда необходимо указать полный путь к ресурсу, а не просто выбрать имя коллекции.</span><span class="sxs-lookup"><span data-stu-id="e2983-118">Use this property when you need to specify a full resource path, rather than just selecting a collection name.</span></span> <span data-ttu-id="e2983-119">Это свойство используется в том случае, если значение **UseResourcePath** равно True.</span><span class="sxs-lookup"><span data-stu-id="e2983-119">This property is used when **UseResourcePath** is True.</span></span>|  
|<span data-ttu-id="e2983-120">UseResourcePath</span><span class="sxs-lookup"><span data-stu-id="e2983-120">UseResourcePath</span></span>|<span data-ttu-id="e2983-121">Если задано значение True, то значение **ResourcePath** добавляется к базовому URL-адресу для определения расположения канала OData.</span><span class="sxs-lookup"><span data-stu-id="e2983-121">When set to True, the **ResourcePath** value is appended to the base URL to determine the OData feed location.</span></span> <span data-ttu-id="e2983-122">Если значение равно False, то используется значение **CollectionName** .</span><span class="sxs-lookup"><span data-stu-id="e2983-122">When set to False, the **CollectionName** value is used.</span></span><br /><br /> <span data-ttu-id="e2983-123">**По умолчанию:** IsFalse</span><span class="sxs-lookup"><span data-stu-id="e2983-123">**Default:** False</span></span>|  
  
  
