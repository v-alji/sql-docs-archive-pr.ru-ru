---
title: Диспетчер подключения кэша | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Cache connection manager
ms.assetid: bdc92038-3720-4795-8a5c-79b963f2c952
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b8a7cc8bbe9e93c385fca6257e0be2e79bd3148a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664434"
---
# <a name="cache-connection-manager"></a><span data-ttu-id="e27f5-102">диспетчер соединений с кэшем</span><span class="sxs-lookup"><span data-stu-id="e27f5-102">Cache Connection Manager</span></span>
  <span data-ttu-id="e27f5-103">Диспетчер соединений с кэшем считывает данные из преобразования кэша или из файла кэша (CAW) и может сохранить эти данные в файле кэша.</span><span class="sxs-lookup"><span data-stu-id="e27f5-103">The Cache connection manager reads data from the Cache transform or from a cache file (.caw), and can save the data to a cache file.</span></span> <span data-ttu-id="e27f5-104">Данные всегда будут храниться в памяти, вне зависимости от того, был ли настроен диспетчер соединений с кэшем для использования файла кэша.</span><span class="sxs-lookup"><span data-stu-id="e27f5-104">Whether you configure the Cache connection manager to use a cache file, the data is always stored in memory.</span></span>  
  
 <span data-ttu-id="e27f5-105">Преобразование «Преобразование кэша» записывает данные из подключенного источника данных в потоке данных в диспетчер соединений с кэшем.</span><span class="sxs-lookup"><span data-stu-id="e27f5-105">The Cache Transform transformation writes data from a connected data source in the data flow to a Cache connection manager.</span></span> <span data-ttu-id="e27f5-106">Преобразование «Уточняющий запрос» в пакете выполняет уточняющие запросы по данным.</span><span class="sxs-lookup"><span data-stu-id="e27f5-106">The Lookup transformation in a package performs lookups on the data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e27f5-107">Диспетчер соединений с кэшем не поддерживает типы данных больших двоичных объектов: DT_TEXT, DT_NTEXT и DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="e27f5-107">The Cache connection manager does not support the Binary Large Object (BLOB) data types DT_TEXT, DT_NTEXT, and DT_IMAGE.</span></span> <span data-ttu-id="e27f5-108">Если ссылочный набор данных содержит данные типа BLOB, то при попытке выполнения пакета компонент завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="e27f5-108">If the reference dataset contains a BLOB data type, the component will fail when you run the package.</span></span> <span data-ttu-id="e27f5-109">**Редактор диспетчера соединений с кэшем** можно использовать для изменения типов данных столбцов.</span><span class="sxs-lookup"><span data-stu-id="e27f5-109">You can use the **Cache Connection Manager Editor** to modify column data types.</span></span> <span data-ttu-id="e27f5-110">Дополнительные сведения см. в разделе [Cache Connection Manager Editor](../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="e27f5-110">For more information, see [Cache Connection Manager Editor](../cache-connection-manager-editor.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e27f5-111">Уровень защиты пакета не применяется к кэшируемому файлу.</span><span class="sxs-lookup"><span data-stu-id="e27f5-111">The protection level of the package does not apply to the cache file.</span></span> <span data-ttu-id="e27f5-112">Если кэшируемый файл содержит важные данные, используйте список управления доступом (ACL), чтобы запретить доступ к расположению или папке, в которой хранится файл.</span><span class="sxs-lookup"><span data-stu-id="e27f5-112">If the cache file contains sensitive information, use an access control list (ACL) to restrict access to the location or folder in which you store the file.</span></span> <span data-ttu-id="e27f5-113">Доступ следует разрешать только определенным учетным записям.</span><span class="sxs-lookup"><span data-stu-id="e27f5-113">You should enable access only to certain accounts.</span></span> <span data-ttu-id="e27f5-114">Дополнительные сведения см. в разделе [Доступ к файлам, используемым пакетами](../access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="e27f5-114">For more information, see [Access to Files Used by Packages](../access-to-files-used-by-packages.md).</span></span>  
  
## <a name="configuration-of-the-cache-connection-manager"></a><span data-ttu-id="e27f5-115">Настройка диспетчера соединений с кэшем</span><span class="sxs-lookup"><span data-stu-id="e27f5-115">Configuration of the Cache Connection Manager</span></span>  
 <span data-ttu-id="e27f5-116">Диспетчер соединений с кэшем можно настроить следующими способами.</span><span class="sxs-lookup"><span data-stu-id="e27f5-116">You can configure the Cache connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="e27f5-117">Указать, следует ли использовать файл кэша.</span><span class="sxs-lookup"><span data-stu-id="e27f5-117">Indicate whether to use a cache file.</span></span>  
  
     <span data-ttu-id="e27f5-118">Если выполнена настройка диспетчера соединений с кэшем для использования файла кэша, то диспетчер соединений выполняет одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="e27f5-118">If you configure the cache connection manager to use a cache file, the connection manager will do one of the following actions:</span></span>  
  
    -   <span data-ttu-id="e27f5-119">Сохранить данные в файле, если преобразование «Конвертация данных кэш» настроено на запись данных из источника данных в потоке данных в диспетчер соединений с кэшем.</span><span class="sxs-lookup"><span data-stu-id="e27f5-119">Save data to the file when a Cache Transform transformation is configured to write data from a data source in the data flow to the Cache connection manager.</span></span>  
  
    -   <span data-ttu-id="e27f5-120">Считать данные из файла кэша.</span><span class="sxs-lookup"><span data-stu-id="e27f5-120">Read data from the cache file.</span></span>  
  
     <span data-ttu-id="e27f5-121">Дополнительные сведения см. в разделе [Cache Transform](../data-flow/transformations/cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="e27f5-121">For more information, see [Cache Transform](../data-flow/transformations/cache-transform.md).</span></span>  
  
-   <span data-ttu-id="e27f5-122">Изменить метаданные столбцов, хранящихся в кэше.</span><span class="sxs-lookup"><span data-stu-id="e27f5-122">Change metadata for the columns stored in the cache.</span></span>  
  
-   <span data-ttu-id="e27f5-123">Обновить имя файла кэша во время выполнения с помощью выражения для установки свойства ConnectionString.</span><span class="sxs-lookup"><span data-stu-id="e27f5-123">Update the cache file name at runtime by using an expression to set the ConnectionString property.</span></span> <span data-ttu-id="e27f5-124">Дополнительные сведения см. в разделе [Использование выражений свойств в пакетах](../expressions/use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="e27f5-124">For more information, see [Use Property Expressions in Packages](../expressions/use-property-expressions-in-packages.md).</span></span>  
  
 <span data-ttu-id="e27f5-125">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="e27f5-125">You can set properties through [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="e27f5-126">Дополнительные сведения о свойствах, которые можно задавать в конструкторе служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , см. в разделе [Редактор диспетчера соединений с кэшем](../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="e27f5-126">For more information about the properties that you can set in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Designer, see [Cache Connection Manager Editor](../cache-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="e27f5-127">Дополнительные сведения о программной настройке диспетчера подключений см. в разделах <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> и [Добавление соединений программным образом](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="e27f5-127">For information about how to configure a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="e27f5-128">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="e27f5-128">Related Tasks</span></span>  
 [<span data-ttu-id="e27f5-129">Реализация преобразования "Уточняющий запрос" в режиме полного кэширования с помощью преобразования диспетчера соединений с кэшем</span><span class="sxs-lookup"><span data-stu-id="e27f5-129">Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager</span></span>](lookup-transformation-full-cache-mode-ole-db-connection-manager.md)  
  
  
