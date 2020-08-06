---
title: Веб-синхронизация для репликации слиянием | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication synchronization [SQL Server replication]
- Internet [SQL Server replication], synchronization
- synchronization [SQL Server replication], Web Synchronization
- Web publishing [SQL Server replication], synchronization
- Web synchronization, about
- Web synchronization
ms.assetid: 84785aba-b2c1-4821-9e9d-a363c73dcb37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ef7bf5a6f77d593a90508a0b69d02f8c0db04407
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667690"
---
# <a name="web-synchronization-for-merge-replication"></a><span data-ttu-id="01769-102">Веб-синхронизация для репликации слиянием</span><span class="sxs-lookup"><span data-stu-id="01769-102">Web Synchronization for Merge Replication</span></span>
  <span data-ttu-id="01769-103">Веб-синхронизация для репликации слиянием позволяет производить репликацию данных по протоколу HTTPS и может оказаться полезной в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="01769-103">Web synchronization for merge replication lets you replicate data by using the HTTPS protocol, and is useful for the following scenarios:</span></span>

-   <span data-ttu-id="01769-104">Синхронизация данных от мобильных пользователей через Интернет.</span><span class="sxs-lookup"><span data-stu-id="01769-104">Synchronizing data from mobile users over the Internet.</span></span>

-   <span data-ttu-id="01769-105">Синхронизация данных между базами данных [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] через корпоративный брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="01769-105">Synchronizing data between [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases across a corporate firewall.</span></span>

 <span data-ttu-id="01769-106">Например, веб-синхронизацию могут использовать коммерческие представители, которым приходится много перемещаться.</span><span class="sxs-lookup"><span data-stu-id="01769-106">For example, a traveling sales representative can use Web synchronization.</span></span> <span data-ttu-id="01769-107">В компании [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)]работают коммерческие представители, которые посещают различные магазины и поставщиков в пределах обслуживаемых регионов.</span><span class="sxs-lookup"><span data-stu-id="01769-107">The company, [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], has sales representatives that travel to various stores and suppliers throughout their regions.</span></span> <span data-ttu-id="01769-108">Во время длительных путешествий представители компании останавливаются в гостиницах и нуждаются в удобном способе передачи данных по продажам и загрузки обновлений по продуктам в конце каждого дня.</span><span class="sxs-lookup"><span data-stu-id="01769-108">On longer trips the representatives stay in hotels and need a convenient way to upload sales data and download any product updates at the end of each day.</span></span>

 <span data-ttu-id="01769-109">Представители отдела информационных технологий [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] настраивают на портативных компьютерах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и включают репликацию слиянием с использованием веб-синхронизации.</span><span class="sxs-lookup"><span data-stu-id="01769-109">The [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] IT department has configured each portable computer with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and has enabled merge replication to use Web synchronization.</span></span> <span data-ttu-id="01769-110">Каждый из портативных компьютеров имеет в Интернете URL-адрес, указывающий на компоненты репликации, установленные на сервере [!INCLUDE[msCoName](../../includes/msconame-md.md)] IIS.</span><span class="sxs-lookup"><span data-stu-id="01769-110">The Merge Agent on each portable computer has an Internet URL that points to the replication components that are installed on a computer that is running [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS).</span></span> <span data-ttu-id="01769-111">Эти компоненты синхронизируют подписчика с издателем.</span><span class="sxs-lookup"><span data-stu-id="01769-111">These components synchronize the Subscriber with the Publisher.</span></span> <span data-ttu-id="01769-112">Теперь каждый торговый представитель может, не пользуясь удаленным коммутируемым соединением, подключиться через любое доступное Интернет-соединение и передать или загрузить необходимые данные.</span><span class="sxs-lookup"><span data-stu-id="01769-112">Each representative can now connect through any available Internet connection without using a remote dial-up connection, and can upload and download the appropriate data.</span></span> <span data-ttu-id="01769-113">При работе через Интернет-соединение используется протокол SSL, поэтому применение виртуальной частной сети (VPN) не потребуется.</span><span class="sxs-lookup"><span data-stu-id="01769-113">The Internet connection uses Secure Sockets Layer (SSL); therefore, a virtual private network (VPN) is not required.</span></span>

 <span data-ttu-id="01769-114">Сведения о настройке компонентов, необходимых для веб-синхронизации, см. в статьях [Настройка веб-синхронизации](configure-web-synchronization.md), [Настройка сервера IIS для веб-синхронизации](configure-iis-for-web-synchronization.md) и [Настройка сервера IIS 7 для веб-синхронизации](configure-iis-7-for-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="01769-114">For information about how to configure the components that are required for Web synchronization, see [Configure Web Synchronization](configure-web-synchronization.md), [Configure IIS for Web Synchronization](configure-iis-for-web-synchronization.md), and [Configure IIS 7 for Web Synchronization](configure-iis-7-for-web-synchronization.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="01769-115">Веб-синхронизация рассчитана на работу с портативными компьютерами, карманными и другими клиентскими устройствами.</span><span class="sxs-lookup"><span data-stu-id="01769-115">Web synchronization is designed for synchronizing data with portable computers, handheld devices, and other clients.</span></span> <span data-ttu-id="01769-116">Эта технология не предназначена для передачи больших объемов данных между серверными приложениями.</span><span class="sxs-lookup"><span data-stu-id="01769-116">Web synchronization is not intended for high-volume server-to-server applications.</span></span>

## <a name="overview-of-how-web-synchronization-works"></a><span data-ttu-id="01769-117">Обзор работы веб-синхронизации</span><span class="sxs-lookup"><span data-stu-id="01769-117">Overview of How Web Synchronization Works</span></span>
 <span data-ttu-id="01769-118">При использовании веб-синхронизации обновления на подписчике упаковываются и отсылаются в виде XML-сообщений на IIS-сервер по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="01769-118">When Web synchronization is used, updates at the Subscriber are packaged and sent as an XML message to the computer that is running IIS by using the HTTPS protocol.</span></span> <span data-ttu-id="01769-119">Компьютер, на котором работает IIS-сервер, посылает команды на издатель в двоичном формате (обычно по протоколу TCP/IP).</span><span class="sxs-lookup"><span data-stu-id="01769-119">The computer that is running IIS then sends the commands to the Publisher in a binary format, typically by using TCP/IP.</span></span> <span data-ttu-id="01769-120">Обновления на издателе отсылаются на IIS-сервер, а затем упаковываются в XML-сообщения для доставки подписчику.</span><span class="sxs-lookup"><span data-stu-id="01769-120">Updates at the Publisher are sent to the computer that is running IIS and then packaged as an XML message for delivery to the Subscriber.</span></span>

 <span data-ttu-id="01769-121">На приведенном ниже рисунке показаны некоторые из компонентов, участвующих в веб-синхронизации при репликации слиянием.</span><span class="sxs-lookup"><span data-stu-id="01769-121">The following illustration shows some of the components that are involved in Web synchronization for merge replication.</span></span>

 <span data-ttu-id="01769-122">![Компоненты веб-синхронизации и потоки данных](media/web-sync01.gif "Компоненты веб-синхронизации и потоки данных")</span><span class="sxs-lookup"><span data-stu-id="01769-122">![Web synchronization components and data flow](media/web-sync01.gif "Web synchronization components and data flow")</span></span>

 <span data-ttu-id="01769-123">Веб-синхронизация может использоваться только для подписок по запросу, поэтому на подписчике всегда будет запущен агент слияния.</span><span class="sxs-lookup"><span data-stu-id="01769-123">Web synchronization is an option only for pull subscriptions; therefore, a Merge Agent will always run on the Subscriber.</span></span> <span data-ttu-id="01769-124">Это может быть стандартный агент слияния, элемент управления ActiveX агента слияния или приложение, которое обеспечивает синхронизацию с помощью объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="01769-124">This Merge Agent can be the standard Merge Agent, the Merge Agent ActiveX control, or an application that provides synchronization through Replication Management Objects (RMO).</span></span> <span data-ttu-id="01769-125">Чтобы указать расположение компьютера, на котором работают службы IIS, используйте параметр **-интернетурл** для агент слияния.</span><span class="sxs-lookup"><span data-stu-id="01769-125">To specify the location of the computer that is running IIS, use the **-InternetUrl** parameter for the Merge Agent.</span></span>

 <span data-ttu-id="01769-126">На сервере IIS настроено средство прослушивания репликации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (replisapi.dll), которое отвечает за обработку сообщений, поступающих на сервер от издателя и от подписчиков.</span><span class="sxs-lookup"><span data-stu-id="01769-126">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener (Replisapi.dll) is configured on the computer that is running IIS and is responsible for handling messages that are sent to the server from the Publisher and Subscribers.</span></span> <span data-ttu-id="01769-127">Каждый узел в топологии обрабатывает поток XML-данных с помощью посредника репликации слиянием (replrec.dll).</span><span class="sxs-lookup"><span data-stu-id="01769-127">Each node in the topology handles the XML data stream by using the Merge Replication Reconciler (Replrec.dll).</span></span>

 <span data-ttu-id="01769-128">На всех компьютерах, участвующих в процессе веб-синхронизации, необходимо наличие[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="01769-128">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or a later version is required for all computers that participate in Web synchronization.</span></span>

### <a name="synchronization-process"></a><span data-ttu-id="01769-129">Процесс синхронизации</span><span class="sxs-lookup"><span data-stu-id="01769-129">Synchronization Process</span></span>
 <span data-ttu-id="01769-130">Во время синхронизации выполняются следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="01769-130">The following steps occur during synchronization:</span></span>

1.  <span data-ttu-id="01769-131">На подписчике запускается агент слияния.</span><span class="sxs-lookup"><span data-stu-id="01769-131">The Merge Agent is started at the Subscriber.</span></span> <span data-ttu-id="01769-132">Агент выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="01769-132">The agent does the following:</span></span>

    1.  <span data-ttu-id="01769-133">устанавливает SQL-соединение с базой данных подписки;</span><span class="sxs-lookup"><span data-stu-id="01769-133">Makes an SQL connection to the subscription database.</span></span>

    2.  <span data-ttu-id="01769-134">извлекает из базы данных все изменения;</span><span class="sxs-lookup"><span data-stu-id="01769-134">Extracts any changes from the database.</span></span>

    3.  <span data-ttu-id="01769-135">производит HTTPS-запрос к компьютеру, на котором работает IIS-сервер;</span><span class="sxs-lookup"><span data-stu-id="01769-135">Makes an HTTPS request to the computer that is running IIS.</span></span>

    4.  <span data-ttu-id="01769-136">загружает изменения данных в виде XML-сообщения.</span><span class="sxs-lookup"><span data-stu-id="01769-136">Uploads data changes as an XML message.</span></span>

2.  <span data-ttu-id="01769-137">Средство прослушивания репликации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и посредник репликации слиянием, находящиеся на IIS-сервере, выполняют следующие действия:</span><span class="sxs-lookup"><span data-stu-id="01769-137">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener and Merge Replication Reconciler that are hosted on the computer that is running IIS do the following:</span></span>

    1.  <span data-ttu-id="01769-138">обрабатывают HTTPS-запрос;</span><span class="sxs-lookup"><span data-stu-id="01769-138">Respond to the HTTPS request.</span></span>

    2.  <span data-ttu-id="01769-139">устанавливают SQL-соединение с базой данных публикации;</span><span class="sxs-lookup"><span data-stu-id="01769-139">Make an SQL connection to the publication database.</span></span>

    3.  <span data-ttu-id="01769-140">применяют переданные изменения к базе данных публикации;</span><span class="sxs-lookup"><span data-stu-id="01769-140">Apply the upload changes to the publication database.</span></span>

    4.  <span data-ttu-id="01769-141">извлекают загруженные изменения для подписчика;</span><span class="sxs-lookup"><span data-stu-id="01769-141">Extract the download changes for the Subscriber.</span></span>

    5.  <span data-ttu-id="01769-142">возвращают HTTPS-ответ на агент слияния.</span><span class="sxs-lookup"><span data-stu-id="01769-142">Send an HTTPS response back to the Merge Agent.</span></span>

3.  <span data-ttu-id="01769-143">После получения HTTPS-ответа агент слияния на подписчике применяет загруженные изменения к базе данных подписки.</span><span class="sxs-lookup"><span data-stu-id="01769-143">The Merge Agent at the Subscriber then accepts the HTTPS response and applies the download changes to the subscription database.</span></span>

## <a name="see-also"></a><span data-ttu-id="01769-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="01769-144">See Also</span></span>
 <span data-ttu-id="01769-145">[Настройка топологий веб-синхронизации](configure-web-synchronization.md) [для веб-синхронизации](topologies-for-web-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="01769-145">[Configure Web Synchronization](configure-web-synchronization.md) [Topologies for Web Synchronization](topologies-for-web-synchronization.md)</span></span>


