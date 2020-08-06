---
title: Преобразование кэша | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.cachetrans.f1
helpviewer_keywords:
- Cache transform
ms.assetid: a5683fc8-9c32-4634-819e-e9815627e4f1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 34be3252a3caf344c95e13ae45cc485a8c4ffdc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665465"
---
# <a name="cache-transform"></a><span data-ttu-id="38c8e-102">преобразование кэша</span><span class="sxs-lookup"><span data-stu-id="38c8e-102">Cache Transform</span></span>
  <span data-ttu-id="38c8e-103">Преобразование «Преобразование кэша» создает ссылочный набор данных для преобразования «Уточняющий запрос», выполняя запись из подключенного источника данных в потоке данных в диспетчер соединений с кэшем.</span><span class="sxs-lookup"><span data-stu-id="38c8e-103">The Cache Transform transformation generates a reference dataset for the Lookup Transformation by writing data from a connected data source in the data flow to a Cache connection manager.</span></span> <span data-ttu-id="38c8e-104">Преобразование «Подстановка» выполняет подстановки, соединяя данные из входных столбцов подключенного источника данных и данные из столбцов в связанной базе данных.</span><span class="sxs-lookup"><span data-stu-id="38c8e-104">The Lookup transformation performs lookups by joining data in input columns from a connected data source with columns in the reference database.</span></span>  
  
 <span data-ttu-id="38c8e-105">Диспетчер соединений с кэшем можно использовать, если нужно, чтобы преобразование «Подстановка» работало в режиме полного кэширования.</span><span class="sxs-lookup"><span data-stu-id="38c8e-105">You can use the Cache connection manager when you want to configure the Lookup Transformation to run in the full cache mode.</span></span> <span data-ttu-id="38c8e-106">В этом режиме ссылочный набор данных загружается в кэш еще до запуска преобразования «Уточняющий запрос».</span><span class="sxs-lookup"><span data-stu-id="38c8e-106">In this mode, the reference dataset is loaded into cache before the Lookup Transformation runs.</span></span>  
  
 <span data-ttu-id="38c8e-107">Инструкции по настройке преобразования "Подстановка" в режиме полного кэширования с помощью диспетчера соединений с кэшем и преобразования "Преобразование кэша" см. в разделе [Реализация преобразования "Уточняющий запрос" в режиме полного кэширования с помощью диспетчера соединений с кэшем](../../connection-manager/lookup-transformation-full-cache-mode-ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="38c8e-107">For instructions on how to configure the Lookup transformation in full cache mode with the Cache connection manager and Cache Transform transformation, see [Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager](../../connection-manager/lookup-transformation-full-cache-mode-ole-db-connection-manager.md).</span></span>  
  
 <span data-ttu-id="38c8e-108">Дополнительные сведения о кэшировании ссылочного набора данных см. в разделе [Lookup Transformation](lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="38c8e-108">For more information on caching the reference dataset, see [Lookup Transformation](lookup-transformation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38c8e-109">«Преобразование кэша» записывает только уникальные строки в диспетчер соединений с кэшем.</span><span class="sxs-lookup"><span data-stu-id="38c8e-109">The Cache Transform writes only unique rows to the Cache connection manager.</span></span>  
  
 <span data-ttu-id="38c8e-110">В пределах одного пакета только одно преобразование «Преобразование кэша» может производить запись в один диспетчер соединений с кэшем.</span><span class="sxs-lookup"><span data-stu-id="38c8e-110">In a single package, only one Cache Transform can write data to the same Cache connection manager.</span></span> <span data-ttu-id="38c8e-111">Если в пакете содержится несколько преобразований «Преобразование кэша», запись в диспетчер соединений будет производить первое преобразование, вызванное при запуске пакета.</span><span class="sxs-lookup"><span data-stu-id="38c8e-111">If the package contains multiple Cache Transforms, the first Cache Transform that is called when the package runs, writes the data to the connection manager.</span></span> <span data-ttu-id="38c8e-112">Операции записи последующих преобразований «Преобразование кэша» завершатся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="38c8e-112">The write operations of subsequent Cache Transforms fail.</span></span>  
  
 <span data-ttu-id="38c8e-113">Дополнительные сведения см. в разделах [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) и [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="38c8e-113">For more information, see [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) and [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span></span>  
  
## <a name="configuration-of-the-cache-transform"></a><span data-ttu-id="38c8e-114">Настройка преобразования кэша</span><span class="sxs-lookup"><span data-stu-id="38c8e-114">Configuration of the Cache Transform</span></span>  
 <span data-ttu-id="38c8e-115">Диспетчер соединений с кэшем можно настроить на сохранение данных в файлы кэша (CAW).</span><span class="sxs-lookup"><span data-stu-id="38c8e-115">You can configure the Cache connection manager to save the data to a cache file (.caw).</span></span>  
  
 <span data-ttu-id="38c8e-116">Можно настроить преобразование «Преобразование кэша» следующими способами.</span><span class="sxs-lookup"><span data-stu-id="38c8e-116">You can configure the Cache Transform in the following ways:</span></span>  
  
-   <span data-ttu-id="38c8e-117">Указать диспетчер соединений с кэшем.</span><span class="sxs-lookup"><span data-stu-id="38c8e-117">Specify the Cache connection manager.</span></span>  
  
-   <span data-ttu-id="38c8e-118">Сопоставить входные столбцы в преобразовании «Преобразование кэша» с целевыми столбцами в диспетчере соединений с кэшем.</span><span class="sxs-lookup"><span data-stu-id="38c8e-118">Map the input columns in the Cache Transform to destination columns in the Cache connection manager.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="38c8e-119">Каждый входной столбец должен быть сопоставлен с целевым, имеющим тот же тип данных.</span><span class="sxs-lookup"><span data-stu-id="38c8e-119">Each input column must be mapped to a destination column, and the column data types must match.</span></span> <span data-ttu-id="38c8e-120">В противном случае конструктор служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] отобразит сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="38c8e-120">Otherwise, [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] Designer displays an error message.</span></span>  
  
     <span data-ttu-id="38c8e-121">**Редактор диспетчера соединений с кэшем** можно использовать для изменения типов данных, имен и других свойств столбцов.</span><span class="sxs-lookup"><span data-stu-id="38c8e-121">You can use the **Cache Connection Manager Editor** to modify column data types, names, and other column properties.</span></span>  
  
 <span data-ttu-id="38c8e-122">Свойства задаются с помощью конструктора служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38c8e-122">You can set properties through [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] Designer.</span></span> <span data-ttu-id="38c8e-123">Дополнительные сведения о свойствах, которые можно установить в диалоговом окне **Расширенный редактор** , см. в разделе [Transformation Custom Properties](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="38c8e-123">For more information about the properties that you can set in the **Advanced Editor** dialog box, see [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="38c8e-124">Дополнительные сведения о настройке свойств см. в разделе [Установление свойств компонента потока данных](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="38c8e-124">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38c8e-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="38c8e-125">See Also</span></span>  
 <span data-ttu-id="38c8e-126">[Преобразования служб Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="38c8e-126">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 [<span data-ttu-id="38c8e-127">Поток данных</span><span class="sxs-lookup"><span data-stu-id="38c8e-127">Data Flow</span></span>](../data-flow.md)  
  
  
