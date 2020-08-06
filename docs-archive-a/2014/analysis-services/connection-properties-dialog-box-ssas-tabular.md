---
title: Диалоговое окно «Свойства соединения» (службы SSAS — табличные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.ssmsimbi.ConnectionProperties.F1
ms.assetid: 17bae8ae-2ba0-4978-be70-61c687f59d54
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e4b0360d59f43bc932f68a846f239c4873a5aa9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656710"
---
# <a name="connection-properties-dialog-box-ssas---tabular"></a><span data-ttu-id="698b8-102">Диалоговое окно «Свойства соединения» (SSAS — табличные)</span><span class="sxs-lookup"><span data-stu-id="698b8-102">Connection Properties Dialog Box (SSAS - Tabular)</span></span>
  <span data-ttu-id="698b8-103">С помощью этой страницы в среде SQL Server Management Studio можно просматривать или изменять свойства соединения с источником данных, используемым базой данных табличной модели.</span><span class="sxs-lookup"><span data-stu-id="698b8-103">Use this page to view or modify in SQL Server Management Studio the connection properties of a data source used by a tabular model database.</span></span>  
  
 <span data-ttu-id="698b8-104">Это диалоговое окно содержит отметки времени и другие описательные сведения, а также настраиваемые свойства, которые определяют характеристики соединения.</span><span class="sxs-lookup"><span data-stu-id="698b8-104">This dialog box provides timestamps and other descriptive information, plus customizable properties that determine characteristics of the connection.</span></span>  
  
## <a name="options"></a><span data-ttu-id="698b8-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="698b8-105">Options</span></span>  
  
|<span data-ttu-id="698b8-106">Термин</span><span class="sxs-lookup"><span data-stu-id="698b8-106">Term</span></span>|<span data-ttu-id="698b8-107">Определение</span><span class="sxs-lookup"><span data-stu-id="698b8-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="698b8-108">**имя**;</span><span class="sxs-lookup"><span data-stu-id="698b8-108">**Name**</span></span>|<span data-ttu-id="698b8-109">Указывает имя источника данных.</span><span class="sxs-lookup"><span data-stu-id="698b8-109">Specifies the name of the data source.</span></span>|  
|<span data-ttu-id="698b8-110">**Идентификатор**</span><span class="sxs-lookup"><span data-stu-id="698b8-110">**ID**</span></span>|<span data-ttu-id="698b8-111">Позволяет отобразить идентификатор объекта источника данных.</span><span class="sxs-lookup"><span data-stu-id="698b8-111">Displays the identifier of the data source object.</span></span>|  
|<span data-ttu-id="698b8-112">**Описание**</span><span class="sxs-lookup"><span data-stu-id="698b8-112">**Description**</span></span>|<span data-ttu-id="698b8-113">Позволяет отобразить описание объекта источника данных.</span><span class="sxs-lookup"><span data-stu-id="698b8-113">Displays the description of the data source object.</span></span>|  
|<span data-ttu-id="698b8-114">**Отметка времени создания**</span><span class="sxs-lookup"><span data-stu-id="698b8-114">**Create Timestamp**</span></span>|<span data-ttu-id="698b8-115">Отображает дату и время создания базы данных.</span><span class="sxs-lookup"><span data-stu-id="698b8-115">Displays the date and time the database was created.</span></span>|  
|<span data-ttu-id="698b8-116">**Последнее обновление схемы**</span><span class="sxs-lookup"><span data-stu-id="698b8-116">**Last Schema Update**</span></span>|<span data-ttu-id="698b8-117">Отображает дату и время последнего обновления метаданных для базы данных.</span><span class="sxs-lookup"><span data-stu-id="698b8-117">Displays the date and time the metadata for the database was last updated.</span></span>|  
|<span data-ttu-id="698b8-118">**Строка подключения**</span><span class="sxs-lookup"><span data-stu-id="698b8-118">**Connection String**</span></span>|<span data-ttu-id="698b8-119">Отображает строку подключения, которая используется для подключения к источнику данных, предоставляющему данные в модель.</span><span class="sxs-lookup"><span data-stu-id="698b8-119">Displays the connection string used to connect to the data source that provides data to the model.</span></span>|  
|<span data-ttu-id="698b8-120">**Максимальное число соединений**</span><span class="sxs-lookup"><span data-stu-id="698b8-120">**Maximum Number of Connections**</span></span>|<span data-ttu-id="698b8-121">Задает максимальное количество клиентских соединений с этой базой данных.</span><span class="sxs-lookup"><span data-stu-id="698b8-121">Specifies the maximum number of client connections to this database.</span></span>|  
|<span data-ttu-id="698b8-122">**Изоляция**</span><span class="sxs-lookup"><span data-stu-id="698b8-122">**Isolation**</span></span>|<span data-ttu-id="698b8-123">Допустимые значения — ReadCommitted или Snapshot.</span><span class="sxs-lookup"><span data-stu-id="698b8-123">Valid values are ReadCommitted or Snapshot.</span></span> <span data-ttu-id="698b8-124">Дополнительные сведения см. в разделе [Элемент Isolation (ASSL)](https://docs.microsoft.com/bi-reference/assl/properties/isolation-element-assl).</span><span class="sxs-lookup"><span data-stu-id="698b8-124">For more information, see [Isolation Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/isolation-element-assl).</span></span>|  
|<span data-ttu-id="698b8-125">**Время ожидания запроса**</span><span class="sxs-lookup"><span data-stu-id="698b8-125">**Query Timeout**</span></span>|<span data-ttu-id="698b8-126">Задает время в секундах, представляющее время ожидания попытки извлечения данных.</span><span class="sxs-lookup"><span data-stu-id="698b8-126">Specifies the time, in seconds, after which an attempt to retrieve data is timed out.</span></span>|  
|<span data-ttu-id="698b8-127">**Управляемый поставщик**</span><span class="sxs-lookup"><span data-stu-id="698b8-127">**Managed Provider**</span></span>|<span data-ttu-id="698b8-128">Указывает имя управляемого поставщика.</span><span class="sxs-lookup"><span data-stu-id="698b8-128">Specifies the name of the managed provider.</span></span> <span data-ttu-id="698b8-129">Если соединение с источником данных использует собственный поставщик данных OLE DB, это значение остается пустым.</span><span class="sxs-lookup"><span data-stu-id="698b8-129">If the data source connection uses a native OLE DB provider, this value is empty.</span></span>|  
|<span data-ttu-id="698b8-130">**Сведения об олицетворении**</span><span class="sxs-lookup"><span data-stu-id="698b8-130">**Impersonation Info**</span></span>|<span data-ttu-id="698b8-131">Указывает учетную запись олицетворения, которая используется для подключений к базе данных во время обработки или обновления данных, запросов к реляционному хранилищу данных (через DirectQuery), внешних привязок, удаленных секций и синхронизации базы данных между получателем и источником.</span><span class="sxs-lookup"><span data-stu-id="698b8-131">Specifies the impersonation account used for database connections when processing or refreshing data, queries that run against a relational data store (via DirectQuery), out-of-line bindings, remote partitions, and database synchronization from target to source.</span></span><br /><br /> <span data-ttu-id="698b8-132">Допустимые значения включают учетную запись служб Analysis Services или конкретный набор учетных данных Windows.</span><span class="sxs-lookup"><span data-stu-id="698b8-132">Valid values include the Analysis Services service account or a specific set of Windows credentials.</span></span> <span data-ttu-id="698b8-133">Не следует задавать параметр **Использовать учетные данные текущего пользователя** или **Наследовать**.</span><span class="sxs-lookup"><span data-stu-id="698b8-133">Do not specify **Use the credentials of the current user** or **Inherit**.</span></span> <span data-ttu-id="698b8-134">Эти параметры учетных данных не поддерживаются для базы данных табличной модели.</span><span class="sxs-lookup"><span data-stu-id="698b8-134">Those credential options are not supported for a tabular model database.</span></span>|  
  
  
