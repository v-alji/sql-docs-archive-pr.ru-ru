---
title: Диспетчер соединений служб Analysis Services | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], Analysis Services
- connection managers [Integration Services], Analysis Services
- Analysis Services connection manager
ms.assetid: 9f9cadad-a1d0-4db5-98f5-df5dbbec1be4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b5da84acd131b75ef9ea174986836265934fb44b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664448"
---
# <a name="analysis-services-connection-manager"></a><span data-ttu-id="b6e26-102">диспетчер соединений служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b6e26-102">Analysis Services Connection Manager</span></span>
  <span data-ttu-id="b6e26-103">Диспетчер соединений служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] позволяет пакету подключиться к серверу, на котором запущена база данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], или к проекту служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], который предоставляет доступ к данным куба и измерения.</span><span class="sxs-lookup"><span data-stu-id="b6e26-103">An [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager enables a package to connect to a server that runs an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project that provides access to cube and dimension data.</span></span> <span data-ttu-id="b6e26-104">При разработке пакетов в среде [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] можно подключиться только к проекту служб [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6e26-104">You can only connect to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project while developing packages in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="b6e26-105">Во время выполнения пакеты подключаются к серверу и базе данных, где был развернут проект служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6e26-105">At run time, packages connect to the server and the database to which you deployed the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span>  
  
 <span data-ttu-id="b6e26-106">Обе задачи, такие как «Выполнение инструкции DDL службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] » и «Обработка службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] », а также назначения, такие как «Обучение модели интеллектуального анализа данных», используют диспетчер соединений служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6e26-106">Both tasks, such as the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task and the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Processing task, and destinations, such as the Data Mining Model Training destination, use an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager.</span></span>  
  
 <span data-ttu-id="b6e26-107">Дополнительные сведения о базах данных [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] см. в разделе [Базы данных многомерных моделей (службы SSAS)](https://docs.microsoft.com/analysis-services/multidimensional-models/multidimensional-model-databases-ssas).</span><span class="sxs-lookup"><span data-stu-id="b6e26-107">For more information about [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases, see [Multidimensional Model Databases &#40;SSAS&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/multidimensional-model-databases-ssas).</span></span>  
  
## <a name="configuration-of-the-analysis-services-connection-manager"></a><span data-ttu-id="b6e26-108">Настройка диспетчера соединений служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b6e26-108">Configuration of the Analysis Services Connection Manager</span></span>  
 <span data-ttu-id="b6e26-109">При добавлении [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] к пакету диспетчера соединений служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] создает диспетчер соединений, который разрешается как [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] соединение во время выполнения, устанавливает свойства диспетчера соединений и добавляет его в `Connections` коллекцию пакета.</span><span class="sxs-lookup"><span data-stu-id="b6e26-109">When you add an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to a package, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that is resolved as an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="b6e26-110">Свойству `ConnectionManagerType` диспетчера соединений присваивается значение `MSOLAP100`.</span><span class="sxs-lookup"><span data-stu-id="b6e26-110">The `ConnectionManagerType` property of the connection manager is set to `MSOLAP100`.</span></span>  
  
 <span data-ttu-id="b6e26-111">Диспетчер соединений служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] можно настроить следующими способами:</span><span class="sxs-lookup"><span data-stu-id="b6e26-111">You can configure the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="b6e26-112">Ввести строку соединения, настроенную с учетом требований поставщика Microsoft OLE для служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="b6e26-112">Provide a connection string configured to meet the requirements of the Microsoft OLE Provider for Analysis Services provider.</span></span>  
  
-   <span data-ttu-id="b6e26-113">Указать экземпляр служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] или проект служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , к которому нужно подключиться.</span><span class="sxs-lookup"><span data-stu-id="b6e26-113">Specify the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] or the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to connect to.</span></span>  
  
-   <span data-ttu-id="b6e26-114">При подключении к экземпляру служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]указать метод проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b6e26-114">If you are connecting to an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], specify the authentication mode.</span></span>  
  
-   <span data-ttu-id="b6e26-115">Обозначает, будет ли соединение, созданное из диспетчера соединений, сохранено во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b6e26-115">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
 <span data-ttu-id="b6e26-116">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="b6e26-116">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="b6e26-117">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в одном из последующих разделов.</span><span class="sxs-lookup"><span data-stu-id="b6e26-117">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topic:</span></span>  
  
-   [<span data-ttu-id="b6e26-118">Справочник по пользовательскому интерфейсу: диалоговое окно "Добавление диспетчера подключений служб Analysis Services"</span><span class="sxs-lookup"><span data-stu-id="b6e26-118">Add Analysis Services Connection Manager Dialog Box UI Reference</span></span>](add-analysis-services-connection-manager-dialog-box-ui-reference.md)  
  
 <span data-ttu-id="b6e26-119">Дополнительные сведения о программной настройке диспетчера подключений см. в разделах <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> и [Добавление соединений программным образом](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="b6e26-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
