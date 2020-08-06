---
title: Компоненты сервера ядра OLAP | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services, architecture
- ports [Analysis Services]
- XML/A listener
- server architecture [Analysis Services]
ms.assetid: 5193c976-9dcd-459c-abba-8c3c44e7a7f2
author: minewiskan
ms.author: owend
ms.openlocfilehash: b60d721a69213ad52536830b49b40d6bb82a3811
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740544"
---
# <a name="olap-engine-server-components"></a><span data-ttu-id="470d2-102">Серверные компоненты ядра OLAP</span><span class="sxs-lookup"><span data-stu-id="470d2-102">OLAP Engine Server Components</span></span>
  <span data-ttu-id="470d2-103">Серверный компонент компонента [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] — это **msmdsrv.exe** приложение, которое выполняется как служба Windows.</span><span class="sxs-lookup"><span data-stu-id="470d2-103">The server component of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] is the **msmdsrv.exe** application, which runs as a Windows service.</span></span> <span data-ttu-id="470d2-104">Оно состоит из компонентов безопасности, компонента прослушивания XML для аналитики (XMLA), компонента обработчика запросов и множества других внутренних компонентов, выполняющих следующие функции:</span><span class="sxs-lookup"><span data-stu-id="470d2-104">This application consists of security components, an XML for Analysis (XMLA) listener component, a query processor component and numerous other internal components that perform the following functions:</span></span>

-   <span data-ttu-id="470d2-105">Синтаксический анализ инструкций, получаемых от клиентов</span><span class="sxs-lookup"><span data-stu-id="470d2-105">Parsing statements received from clients</span></span>

-   <span data-ttu-id="470d2-106">Управление метаданными</span><span class="sxs-lookup"><span data-stu-id="470d2-106">Managing metadata</span></span>

-   <span data-ttu-id="470d2-107">Обработка транзакций</span><span class="sxs-lookup"><span data-stu-id="470d2-107">Handling transactions</span></span>

-   <span data-ttu-id="470d2-108">Обработка вычислений</span><span class="sxs-lookup"><span data-stu-id="470d2-108">Processing calculations</span></span>

-   <span data-ttu-id="470d2-109">Сохранение измерения и данных ячеек</span><span class="sxs-lookup"><span data-stu-id="470d2-109">Storing dimension and cell data</span></span>

-   <span data-ttu-id="470d2-110">Создание агрегатов</span><span class="sxs-lookup"><span data-stu-id="470d2-110">Creating aggregations</span></span>

-   <span data-ttu-id="470d2-111">Планирование запросов</span><span class="sxs-lookup"><span data-stu-id="470d2-111">Scheduling queries</span></span>

-   <span data-ttu-id="470d2-112">Кэширование объектов</span><span class="sxs-lookup"><span data-stu-id="470d2-112">Caching objects</span></span>

-   <span data-ttu-id="470d2-113">Управление ресурсами сервера</span><span class="sxs-lookup"><span data-stu-id="470d2-113">Managing server resources</span></span>

## <a name="architectural-diagram"></a><span data-ttu-id="470d2-114">Архитектурная диаграмма</span><span class="sxs-lookup"><span data-stu-id="470d2-114">Architectural Diagram</span></span>
 <span data-ttu-id="470d2-115">Экземпляр служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] запускается как изолированная служба, взаимодействие с этой службой происходит через XMLA с использованием протокола HTTP или TCP.</span><span class="sxs-lookup"><span data-stu-id="470d2-115">An [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance runs as a stand-alone service and communication with the service occurs through XML for Analysis (XMLA), by using either HTTP or TCP.</span></span> <span data-ttu-id="470d2-116">Объекты AMO — это прослойка между приложением пользователя и экземпляром служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="470d2-116">AMO is a layer between the user application and the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="470d2-117">Они предоставляют доступ к административным объектам служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="470d2-117">This layer provides access to [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] administrative objects.</span></span> <span data-ttu-id="470d2-118">Объект AMO — это библиотека классов, которая принимает команды от клиентского приложения и преобразует их в XMLA-сообщения для экземпляра служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="470d2-118">AMO is a class library that takes commands from a client application and converts those commands into XMLA messages for the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="470d2-119">Объекты AMO представляют объекты экземпляра служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , как классы для приложения конечного пользователя, с элементами-методами, запускающими команды и элементами-свойствами, хранящими данные объектов служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="470d2-119">AMO presents [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance objects as classes to the end user application, with method members that run commands and property members that hold the data for the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] objects.</span></span>

 <span data-ttu-id="470d2-120">Следующий рисунок отображает архитектуру компонентов служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], включая все главные элементы, запущенные на экземпляре служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], и все пользовательские компоненты, взаимодействующие с этим экземпляром.</span><span class="sxs-lookup"><span data-stu-id="470d2-120">The following illustration shows the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] components architecture, including all major elements running within the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance and all user components that interact with the instance.</span></span> <span data-ttu-id="470d2-121">Рисунок также отображает, что единственным путем доступа к экземпляру является прослушиватель XML для аналитики или использование протокола HTTP или TCP.</span><span class="sxs-lookup"><span data-stu-id="470d2-121">The illustration also shows that the only way to access the instance is by using the XML for Analysis (XMLA) Listener, either by using HTTP or TCP.</span></span>

 <span data-ttu-id="470d2-122">![Диаграмма архитектуры системы служб Analysis Services](../../../analysis-services/dev-guide/media/analysisservicessystemarchitecture.gif "Диаграмма архитектуры системы служб Analysis Services")</span><span class="sxs-lookup"><span data-stu-id="470d2-122">![Analysis Services System Architecture Diagram](../../../analysis-services/dev-guide/media/analysisservicessystemarchitecture.gif "Analysis Services System Architecture Diagram")</span></span>

## <a name="xmla-listener"></a><span data-ttu-id="470d2-123">Прослушиватель XML для аналитики</span><span class="sxs-lookup"><span data-stu-id="470d2-123">XMLA Listener</span></span>
 <span data-ttu-id="470d2-124">Компонент прослушивателя XML для аналитики обрабатывает все XMLA-взаимодействия между службами [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] и их клиентами.</span><span class="sxs-lookup"><span data-stu-id="470d2-124">The XMLA listener component handles all XMLA communications between [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] and its clients.</span></span> <span data-ttu-id="470d2-125">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] `Port` Параметр конфигурации в файле msmdsrv.ini можно использовать для указания порта, который [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] прослушивает экземпляр.</span><span class="sxs-lookup"><span data-stu-id="470d2-125">The [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] `Port` configuration setting in the msmdsrv.ini file can be used to specify a port on which an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance listens.</span></span> <span data-ttu-id="470d2-126">Значение 0 указывает на то, что [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] прослушивает порт по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="470d2-126">A value of 0 in this file indicates that [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] listen on the default port.</span></span> <span data-ttu-id="470d2-127">По умолчанию службы [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] пользуются следующими TCP-портами:</span><span class="sxs-lookup"><span data-stu-id="470d2-127">Unless otherwise specified, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] uses the following default TCP ports:</span></span>

|<span data-ttu-id="470d2-128">Порт</span><span class="sxs-lookup"><span data-stu-id="470d2-128">Port</span></span>|<span data-ttu-id="470d2-129">Описание</span><span class="sxs-lookup"><span data-stu-id="470d2-129">Description</span></span>|
|----------|-----------------|
|<span data-ttu-id="470d2-130">2383</span><span class="sxs-lookup"><span data-stu-id="470d2-130">2383</span></span>|<span data-ttu-id="470d2-131">Экземпляр по умолчанию [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="470d2-131">Default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|
|<span data-ttu-id="470d2-132">2382</span><span class="sxs-lookup"><span data-stu-id="470d2-132">2382</span></span>|<span data-ttu-id="470d2-133">Перенаправитель для других экземпляров [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="470d2-133">Redirector for other instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|
|<span data-ttu-id="470d2-134">Динамически назначается при запуске сервера</span><span class="sxs-lookup"><span data-stu-id="470d2-134">Dynamically assigned at server startup</span></span>|<span data-ttu-id="470d2-135">Именованный экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="470d2-135">Named instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|

 <span data-ttu-id="470d2-136">Дополнительные сведения см. в разделе [Настройка брандмауэра Windows для разрешения Analysis Servicesного доступа](../../instances/configure-the-windows-firewall-to-allow-analysis-services-access.md) .</span><span class="sxs-lookup"><span data-stu-id="470d2-136">See [Configure the Windows Firewall to Allow Analysis Services Access](../../instances/configure-the-windows-firewall-to-allow-analysis-services-access.md) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="470d2-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="470d2-137">See Also</span></span>
 <span data-ttu-id="470d2-138">[Правила именования объектов &#40;Analysis Services&#41;](object-naming-rules-analysis-services.md) [физическую архитектуру &#40;Analysis Services — многомерные данные&#41;](understanding-microsoft-olap-physical-architecture.md) [логическая архитектура &#40;Analysis Services — многомерные данные&#41;](../olap-logical/understanding-microsoft-olap-logical-architecture.md)</span><span class="sxs-lookup"><span data-stu-id="470d2-138">[Object Naming Rules &#40;Analysis Services&#41;](object-naming-rules-analysis-services.md) [Physical Architecture &#40;Analysis Services - Multidimensional Data&#41;](understanding-microsoft-olap-physical-architecture.md) [Logical Architecture &#40;Analysis Services - Multidimensional Data&#41;](../olap-logical/understanding-microsoft-olap-logical-architecture.md)</span></span>


