---
title: Диспетчер FTP-соединений | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- FTP connection manager
- connections [Integration Services], FTP
- connection managers [Integration Services], FTP
ms.assetid: c4f43455-29ca-44ba-ac7f-ea729b1daf93
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a402f399ba4b7e69fc1d3cbca9dd64b32217ced1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729718"
---
# <a name="ftp-connection-manager"></a><span data-ttu-id="be525-102">диспетчер FTP-соединений</span><span class="sxs-lookup"><span data-stu-id="be525-102">FTP Connection Manager</span></span>
  <span data-ttu-id="be525-103">Диспетчер FTP-соединений позволяет пакету подключаться к серверу, использующему протокол передачи файлов (FTP).</span><span class="sxs-lookup"><span data-stu-id="be525-103">An FTP connection manager enables a package to connect to a File Transfer Protocol (FTP) server.</span></span> <span data-ttu-id="be525-104">Задача "FTP", включенная в комплект служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], использует этот диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="be525-104">The FTP task that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses this connection manager.</span></span>  
  
 <span data-ttu-id="be525-105">При добавлении в пакет диспетчера FTP-сеансов службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] создают диспетчер соединений, обеспечивающий соединение с FTP во время выполнения, устанавливают свойства диспетчера соединений и добавляют диспетчер соединений в коллекцию `Connections` данного пакета.</span><span class="sxs-lookup"><span data-stu-id="be525-105">When you add an FTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that can be resolved as an FTP connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="be525-106">Свойству `ConnectionManagerType` диспетчера соединений присваивается значение `FTP`.</span><span class="sxs-lookup"><span data-stu-id="be525-106">The `ConnectionManagerType` property of the connection manager is set to `FTP`.</span></span>  
  
 <span data-ttu-id="be525-107">Диспетчер FTP-сеансов может быть настроен следующим образом.</span><span class="sxs-lookup"><span data-stu-id="be525-107">You can configure the FTP connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="be525-108">Укажите имя и порт сервера.</span><span class="sxs-lookup"><span data-stu-id="be525-108">Specify a server name and server port.</span></span>  
  
-   <span data-ttu-id="be525-109">Выберите анонимный доступ или укажите имя пользователя и пароль для обычной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="be525-109">Specify anonymous access, or provide a user name and a password for basic authentication.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="be525-110">Диспетчер FTP-соединений поддерживает только анонимную проверку подлинности и обычную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="be525-110">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="be525-111">Проверка подлинности Windows не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="be525-111">It does not support Windows Authentication.</span></span>  
  
-   <span data-ttu-id="be525-112">Задайте время ожидания, число повторных попыток и количество данных, которое будет копироваться за один раз.</span><span class="sxs-lookup"><span data-stu-id="be525-112">Set the time-out, number of retries, and the amount of data to copy at a time.</span></span>  
  
-   <span data-ttu-id="be525-113">Укажите, должен ли диспетчер FTP-сеансов использовать пассивный или активный режим.</span><span class="sxs-lookup"><span data-stu-id="be525-113">Indicate whether the FTP connection manager uses passive or active mode.</span></span>  
  
 <span data-ttu-id="be525-114">В зависимости от настройки сайта FTP, к которому подключается диспетчер FTP-сеансов, может понадобиться изменить следующие значения по умолчанию для диспетчера подключений.</span><span class="sxs-lookup"><span data-stu-id="be525-114">Depending on the configuration of the FTP site to which the FTP connection manager connects, you may need to change the following default values of the connection manager:</span></span>  
  
-   <span data-ttu-id="be525-115">Для сервера порта устанавливается значение 21.</span><span class="sxs-lookup"><span data-stu-id="be525-115">The server port is set to 21.</span></span> <span data-ttu-id="be525-116">Необходимо задать порт для прослушивания FTP-сайтом.</span><span class="sxs-lookup"><span data-stu-id="be525-116">You should specify the port that the FTP site listens to.</span></span>  
  
-   <span data-ttu-id="be525-117">Имя пользователя установлено в значение «anonymous».</span><span class="sxs-lookup"><span data-stu-id="be525-117">The user name is set to "anonymous".</span></span> <span data-ttu-id="be525-118">Необходимо предоставить учетные данные, которые требует веб-сайт FTP.</span><span class="sxs-lookup"><span data-stu-id="be525-118">You should provide the credentials that the FTP site requires.</span></span>  
  
## <a name="activepassive-modes"></a><span data-ttu-id="be525-119">Активный/пассивный режимы</span><span class="sxs-lookup"><span data-stu-id="be525-119">Active/Passive Modes</span></span>  
 <span data-ttu-id="be525-120">Диспетчер FTP-соединений может отправлять и получать данные либо в активном, либо в пассивном режиме.</span><span class="sxs-lookup"><span data-stu-id="be525-120">An FTP connection manager can send and receive files using either active mode or passive mode.</span></span> <span data-ttu-id="be525-121">В активном режиме подключение к данным инициируется сервером, а в пассивном режиме — клиентом.</span><span class="sxs-lookup"><span data-stu-id="be525-121">In active mode, the server initiates the data connection, and in passive mode, the client initiates the data connection.</span></span>  
  
## <a name="configuration-of-the-ftp-connection-manager"></a><span data-ttu-id="be525-122">Настройка диспетчера FTP-соединений</span><span class="sxs-lookup"><span data-stu-id="be525-122">Configuration of the FTP Connection Manager</span></span>  
 <span data-ttu-id="be525-123">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="be525-123">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="be525-124">Дополнительные сведения о свойствах, которые можно задавать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в статье [Редактор диспетчера FTP-сеансов](../ftp-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="be525-124">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [FTP Connection Manager Editor](../ftp-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="be525-125">Дополнительные сведения о программной настройке диспетчера подключений см. в разделах <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> и [Добавление соединений программным образом](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="be525-125">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be525-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="be525-126">See Also</span></span>  
 <span data-ttu-id="be525-127">[Задача «FTP»](../control-flow/ftp-task.md) </span><span class="sxs-lookup"><span data-stu-id="be525-127">[FTP Task](../control-flow/ftp-task.md) </span></span>  
 [<span data-ttu-id="be525-128">Соединения в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="be525-128">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
