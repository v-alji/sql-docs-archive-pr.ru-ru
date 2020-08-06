---
title: Диспетчер подключений SAP BW | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 06b166a1-a9df-48ea-a0e8-9b8d6979c0a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bc3bb32c4895c6ec8fbcf31d57e8685c74de32dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656525"
---
# <a name="sap-bw-connection-manager"></a><span data-ttu-id="073fa-102">Диспетчер соединений SAP BW</span><span class="sxs-lookup"><span data-stu-id="073fa-102">SAP BW Connection Manager</span></span>
  <span data-ttu-id="073fa-103">Диспетчер соединений SAP BW — это компонент диспетчера соединений [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW.</span><span class="sxs-lookup"><span data-stu-id="073fa-103">The SAP BW connection manager is the connection manager component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="073fa-104">Таким образом, диспетчер соединений SAP BW обеспечивает подключение к системе SAP Netweaver BW версии 7, необходимое компонентам источника и назначения [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW.</span><span class="sxs-lookup"><span data-stu-id="073fa-104">Thus, the SAP BW connection manager provides the connectivity to an SAP Netweaver BW version 7 system that the source and destination components of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW need.</span></span> <span data-ttu-id="073fa-105">(Источник и назначение SAP BW, входящие в состав пакета [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW, являются единственными компонентами служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , которые используют диспетчер соединений SAP BW.)</span><span class="sxs-lookup"><span data-stu-id="073fa-105">(The SAP BW source and destination that are part of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW package are the only [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components that use the SAP BW connection manager.)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="073fa-106">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="073fa-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="073fa-107">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="073fa-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="073fa-108">При добавлении диспетчера соединений SAP BW в пакет свойству `ConnectionManagerType` диспетчера соединений присваивается значение `SAPBI`.</span><span class="sxs-lookup"><span data-stu-id="073fa-108">When you add an SAP BW connection manager to a package, the `ConnectionManagerType` property of the connection manager is set to `SAPBI`.</span></span>  
  
## <a name="configuring-the-sap-bw-connection-manager"></a><span data-ttu-id="073fa-109">Настройка диспетчера соединений SAP BW</span><span class="sxs-lookup"><span data-stu-id="073fa-109">Configuring the SAP BW Connection Manager</span></span>  
 <span data-ttu-id="073fa-110">Диспетчер соединений SAP BW можно настроить следующими способами.</span><span class="sxs-lookup"><span data-stu-id="073fa-110">You can configure the SAP BW connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="073fa-111">Укажите клиент, имя пользователя, пароль и язык для соединения.</span><span class="sxs-lookup"><span data-stu-id="073fa-111">Provide the client, user name, password, and language for the connection.</span></span>  
  
-   <span data-ttu-id="073fa-112">Выберите, следует ли подключаться к одному серверу приложений или к группе серверов с выравниванием нагрузки.</span><span class="sxs-lookup"><span data-stu-id="073fa-112">Choose whether to connect to a single application server or to a group of load-balanced servers.</span></span>  
  
-   <span data-ttu-id="073fa-113">Укажите номер узла и системы для одного сервера приложений либо предоставьте данные о сервере сообщений, группе и идентификатор безопасности для группы серверов с выравниванием нагрузки.</span><span class="sxs-lookup"><span data-stu-id="073fa-113">Provide the host and system number for a single application server, or provide the message server, group, and SID for a group of load-balanced servers.</span></span>  
  
-   <span data-ttu-id="073fa-114">Включить пользовательское ведение журналов вызовов функций RFC для компонентов [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW.</span><span class="sxs-lookup"><span data-stu-id="073fa-114">Enable custom logging of RFC function calls for the components of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="073fa-115">(Это ведение журнала отделено от дополнительного ведения журналов, которое можно включить для пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .) Для включения записи в журнал вызовов функций RFC необходимо указать каталог, в котором будут сохранятся файлы журнала, созданные до и после каждого вызова функции RFC.</span><span class="sxs-lookup"><span data-stu-id="073fa-115">(This logging is separate from the optional logging that you can enable on [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.) To enable logging of RFC function calls, you specify a directory in which to store the log files that are created before and after each RFC function call.</span></span> <span data-ttu-id="073fa-116">(Эта функция ведения журнала создает большое количество файлов журнала в формате XML.</span><span class="sxs-lookup"><span data-stu-id="073fa-116">(This logging feature creates many log files in XML format.</span></span> <span data-ttu-id="073fa-117">Поскольку эти файлы журнала также содержат все передаваемые строки данных, для них может потребоваться много места на диске.) Если не выбрать каталог журнала, ведение журналов не будет включено.</span><span class="sxs-lookup"><span data-stu-id="073fa-117">As these log files also contain all the rows of data that are transferred, these log files may consume a large amount of disk space.) If you do not select a log directory, logging is not enabled.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="073fa-118">Если передаваемые данные содержат конфиденциальные данные, файлы журнала также будут содержать эти конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="073fa-118">If the data that is transferred contains sensitive information, the log files will also contain that sensitive information.</span></span>  
  
-   <span data-ttu-id="073fa-119">Используйте введенные значения, чтобы испытать подключение.</span><span class="sxs-lookup"><span data-stu-id="073fa-119">Use the values that you have entered to test the connection.</span></span>  
  
 <span data-ttu-id="073fa-120">Если вы не знаете все значения, необходимые для настройки диспетчера соединений, запросите их у администратора SAP.</span><span class="sxs-lookup"><span data-stu-id="073fa-120">If you do not know all the values that are required to configure the connection manager, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="073fa-121">Пошаговое руководство, в котором показано, как настроить и использовать диспетчер соединений, источник и назначение SAP BW, см. в техническом документе [Использование служб SQL Server 2008 Integration Services с SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span><span class="sxs-lookup"><span data-stu-id="073fa-121">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server 2008 Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span></span> <span data-ttu-id="073fa-122">В этом техническом документе также показано, как настроить необходимые объекты в SAP BW.</span><span class="sxs-lookup"><span data-stu-id="073fa-122">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
### <a name="using-the-ssis-designer-to-configure-the-source"></a><span data-ttu-id="073fa-123">Использование конструктора служб SSIS для настройки источника</span><span class="sxs-lookup"><span data-stu-id="073fa-123">Using the SSIS Designer to Configure the Source</span></span>  
 <span data-ttu-id="073fa-124">Дополнительные сведения о свойствах диспетчера соединений SAP BW, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="073fa-124">For more information about the properties of the SAP BW connection manager that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="073fa-125">Редактор диспетчера подключений SAP BW</span><span class="sxs-lookup"><span data-stu-id="073fa-125">SAP BW Connection Manager Editor</span></span>](../sap-bw-connection-manager-editor.md)  
  
## <a name="see-also"></a><span data-ttu-id="073fa-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="073fa-126">See Also</span></span>  
 [<span data-ttu-id="073fa-127">Компоненты Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="073fa-127">Microsoft Connector 1.1 for SAP BW Components</span></span>](../microsoft-connector-for-sap-bw-components.md)  
  
  
