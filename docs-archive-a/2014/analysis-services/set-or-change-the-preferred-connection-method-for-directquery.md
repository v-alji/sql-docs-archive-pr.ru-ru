---
title: Установка или изменение предпочтительного метода подключения для DirectQuery | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f10d5678-d678-4251-8cce-4e30cfe15751
author: minewiskan
ms.author: owend
ms.openlocfilehash: 239c80ace0daa3498c8dafd8fea358ce540931d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736905"
---
# <a name="set-or-change-the-preferred-connection-method-for-directquery"></a><span data-ttu-id="63784-102">Установка или изменение предпочтительного метода подключения для DirectQuery</span><span class="sxs-lookup"><span data-stu-id="63784-102">Set or Change the Preferred Connection Method for DirectQuery</span></span>
  <span data-ttu-id="63784-103">При создании модели для использования в режиме DirectQuery необходимо сначала настроить поддержку DirectQuery в среде конструирования.</span><span class="sxs-lookup"><span data-stu-id="63784-103">When you create a model for use in DirectQuery mode, you must first configure the design environment to support use of DirectQuery.</span></span> <span data-ttu-id="63784-104">Дополнительные сведения см. в разделе [Включение режима разработки DirectQuery &#40;табличных&#41;SSAS ](tabular-models/enable-directquery-mode-in-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="63784-104">To do this, see [Enable DirectQuery Design Mode &#40;SSAS Tabular&#41;](tabular-models/enable-directquery-mode-in-ssdt.md).</span></span>  
  
 <span data-ttu-id="63784-105">Когда все готово к развертыванию модели, необходимо настроить некоторые дополнительные свойства, обеспечивающие доступ пользователей к модели с помощью одного из режимов DirectQuery:</span><span class="sxs-lookup"><span data-stu-id="63784-105">When you are ready to deploy the model, you must set some additional properties to enable users to access your model using one of the DirectQuery modes:</span></span>  
  
-   <span data-ttu-id="63784-106">Необходимо указать, какие данные должны использоваться в запросах к модели: кэшированные или из реляционного источника данных.</span><span class="sxs-lookup"><span data-stu-id="63784-106">You must indicate whether queries against the model should use cached data or the relational data source.</span></span> <span data-ttu-id="63784-107">Можно использовать только DirectQuery или гибридный режим.</span><span class="sxs-lookup"><span data-stu-id="63784-107">You can use a hybrid mode or DirectQuery only.</span></span>  
  
-   <span data-ttu-id="63784-108">Если используются разделы, следует указать, какой раздел будет использоваться в качестве источника данных DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="63784-108">If you are using partitions, you must indicate which partition to use as the DirectQuery data source.</span></span>  
  
-   <span data-ttu-id="63784-109">Необходимо настроить параметры олицетворения для пользователей, которым необходим доступ к источнику данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="63784-109">You must set impersonation options for users who will be accessing the SQL Server data source.</span></span>  
  
 <span data-ttu-id="63784-110">Эта процедура описывает, как в конструкторе настраивается предпочтительный метод подключения для модели DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="63784-110">This procedure describes how to set the preferred connection method for a DirectQuery model in the designer.</span></span> <span data-ttu-id="63784-111">Кроме того, описывается изменение этого свойства в [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] после развертывания модели.</span><span class="sxs-lookup"><span data-stu-id="63784-111">It also describes how you can change this property in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] after the model has been deployed.</span></span>  
  
### <a name="to-set-the-preferred-connection-method-for-a-directquery-model"></a><span data-ttu-id="63784-112">Настройка предпочтительного метода подключения для модели DirectQuery</span><span class="sxs-lookup"><span data-stu-id="63784-112">To set the preferred connection method for a DirectQuery model</span></span>  
  
1.  <span data-ttu-id="63784-113">В [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте файл решения для модели DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="63784-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution file for the DirectQuery model.</span></span>  
  
2.  <span data-ttu-id="63784-114">В Visual Studio в меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="63784-114">In Visual Studio, from the **Project** menu, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="63784-115">На панели **Свойства** задайте для свойства **DirectQueryMode**одно из значений, обеспечивающих использование DirectQuery:</span><span class="sxs-lookup"><span data-stu-id="63784-115">In the **Properties** pane, change the property, **DirectQueryMode**, to one of the values that support DirectQuery usage:</span></span>  
  
    -   <span data-ttu-id="63784-116">**InMemory с DirectQuery**— с этим параметром модель развертывается, но необходимо обработать кэш, прежде чем к ней можно будет выполнять запросы.</span><span class="sxs-lookup"><span data-stu-id="63784-116">**InMemory with DirectQuery**: If you use this option, the model is deployed but you must process the cache before you can run queries against the model.</span></span>  
  
    -   <span data-ttu-id="63784-117">**DirectQuery с InMemory**— с этим параметром кэш будет доступен для клиентов, если он уже обработан.</span><span class="sxs-lookup"><span data-stu-id="63784-117">**DirectQuery with InMemory**: If you use this option, the cache will be available for use by clients if it has already been processed.</span></span> <span data-ttu-id="63784-118">Если выполнить развертывание модели с этим параметром и не обработать кэш, у некоторых клиентов при попытке подключения к модели будет возникать ошибка.</span><span class="sxs-lookup"><span data-stu-id="63784-118">If you deploy the model with this setting and do not process the cache, some clients must get an error on trying to connect to the model.</span></span>  
  
    -   <span data-ttu-id="63784-119">**Только DirectQuery**— с этим параметром метаданные развертываются, но в модели нет данных.</span><span class="sxs-lookup"><span data-stu-id="63784-119">**DirectQuery only**: If you use this option, the metadata is deployed but the model has no data in it.</span></span> <span data-ttu-id="63784-120">Клиенты, пытающиеся подключиться в режиме In-Memory, будут получать ошибку, указывающую, что модель не существует или не обработана.</span><span class="sxs-lookup"><span data-stu-id="63784-120">Clients that attempt to connect using In-Memory mode will get an error, indicating that the model does not exist or has not been processed.</span></span>  
  
4.  <span data-ttu-id="63784-121">При наличии ошибок откройте в Visual Studio **Список ошибок** и решите проблемы, мешающие развернуть модель в режиме DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="63784-121">If there are errors, in Visual Studio, open the **Error List** and resolve any problems that would prevent the model from being deployed in DirectQuery mode.</span></span>  
  
### <a name="to-verify-or-change-the-preferred-connection-method-for-a-directquery-model"></a><span data-ttu-id="63784-122">Проверка или изменение предпочтительного метода подключения для модели DirectQuery</span><span class="sxs-lookup"><span data-stu-id="63784-122">To verify or change the preferred connection method for a DirectQuery model</span></span>  
  
1.  <span data-ttu-id="63784-123">В [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]подключитесь к экземпляру с развернутой моделью DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="63784-123">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to the instance where you deployed the DirectQuery model.</span></span>  
  
2.  <span data-ttu-id="63784-124">Щелкните правой кнопкой мыши шаблон базы данных и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="63784-124">Right-click the model database, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="63784-125">На панели **Свойства** задайте для свойства **DirectQueryMode**одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="63784-125">In the **Properties** pane, change the property, **DirectQueryMode**, to one of these values:</span></span>  
  
    -   <span data-ttu-id="63784-126">**Только DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="63784-126">**DirectQuery Only**</span></span>  
  
    -   <span data-ttu-id="63784-127">**InMemory с DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="63784-127">**InMemory with DirectQuery**</span></span>  
  
    -   <span data-ttu-id="63784-128">**DirectQuery с памятью**</span><span class="sxs-lookup"><span data-stu-id="63784-128">**DirectQuery with InMemory**</span></span>  
  
 <span data-ttu-id="63784-129">Обратите внимание: это те же свойства, что задавались в проекте перед развертыванием в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="63784-129">Note that these properties are the same as the properties that you set on the project before deployment in Visual Studio.</span></span> <span data-ttu-id="63784-130">Изменить предпочтительный режим подключения для режима DirectQuery можно в любое время при условии, что модель настроена на использование DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="63784-130">You can change the preferred connection mode for DirectQuery mode at any time, provided that you have configured the model to support DirectQuery usage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63784-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="63784-131">See Also</span></span>  
 <span data-ttu-id="63784-132">[Режим DirectQuery &#40;табличные&#41;SSAS](tabular-models/directquery-mode-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="63784-132">[DirectQuery Mode &#40;SSAS Tabular&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="63784-133">Включение режима конструктора DirectQuery &#40;табличных&#41;SSAS</span><span class="sxs-lookup"><span data-stu-id="63784-133">Enable DirectQuery Design Mode &#40;SSAS Tabular&#41;</span></span>](tabular-models/enable-directquery-mode-in-ssdt.md)  
  
  
