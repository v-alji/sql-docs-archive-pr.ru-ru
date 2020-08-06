---
title: Диспетчер HTTP-соединений | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- HTTP connection manager
- Web site connections [Integration Services]
- connection managers [Integration Services], HTTP
- Web server connections [Integration Services]
- connections [Integration Services], HTTP
ms.assetid: 26b2b3e1-d02c-46ca-8d31-7aef2bbc3c53
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 10c9f0778faa25aff8db4ad54ecaa8d3ccc5b359
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740199"
---
# <a name="http-connection-manager"></a><span data-ttu-id="6c0e2-102">диспетчер HTTP-соединений</span><span class="sxs-lookup"><span data-stu-id="6c0e2-102">HTTP Connection Manager</span></span>
  <span data-ttu-id="6c0e2-103">HTTP-соединение позволяет пакету получить доступ к веб-серверу через протокол HTTP, чтобы передавать или принимать файлы.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-103">An HTTP connection enables a package to access a Web server by using HTTP to send or receive files.</span></span> <span data-ttu-id="6c0e2-104">Задача "Веб-служба" из состава служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] использует этот диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-104">The Web Service task that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses this connection manager.</span></span>  
  
 <span data-ttu-id="6c0e2-105">При добавлении к пакету диспетчера HTTP-соединений [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] создает диспетчер соединений, который будет решать задачи HTTP-соединений во время работы, устанавливают свойства диспетчера соединений и добавляют его к коллекции пакета `Connections`.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-105">When you add an HTTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an HTTP connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="6c0e2-106">Свойство диспетчера соединений `ConnectionManagerType` имеет значение `HTTP.`</span><span class="sxs-lookup"><span data-stu-id="6c0e2-106">The `ConnectionManagerType` property of the connection manager is set to `HTTP.`</span></span>  
  
 <span data-ttu-id="6c0e2-107">Произвести настройку диспетчера HTTP-соединений можно следующими способами:</span><span class="sxs-lookup"><span data-stu-id="6c0e2-107">You can configure the HTTP connection manager the following ways:</span></span>  
  
-   <span data-ttu-id="6c0e2-108">Используйте учетные данные.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-108">Use credentials.</span></span> <span data-ttu-id="6c0e2-109">Если диспетчер соединений использует учетные данные, то необходимо указать имя пользователя, пароль и домен.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-109">If the connection manager uses credentials, its properties include the user name, password, and domain.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="6c0e2-110">Диспетчер HTTP-соединений поддерживает только анонимную проверку подлинности и обычную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-110">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="6c0e2-111">Проверка подлинности Windows не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-111">It does not support Windows Authentication.</span></span>  
  
-   <span data-ttu-id="6c0e2-112">Используйте сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-112">Use a client certificate.</span></span> <span data-ttu-id="6c0e2-113">Если диспетчер соединений использует сертификат клиента, то среди его свойств есть имя сертификата.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-113">If the connection manager uses a client certificate, its properties include the certificate name.</span></span>  
  
-   <span data-ttu-id="6c0e2-114">Введите время ожидания при подключении к серверу и размер фрагмента данных для записи данных.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-114">Provide a time-out for connecting to the server and a chunk size for writing data.</span></span>  
  
-   <span data-ttu-id="6c0e2-115">Используйте прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-115">Use a proxy server.</span></span> <span data-ttu-id="6c0e2-116">Прокси-сервер также может быть настроен для использования учетных данных, а также для обхода прокси-сервера и использования локальных адресов.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-116">The proxy server can also be configured to use credentials and to bypass the proxy server and use local addresses instead.</span></span>  
  
## <a name="configuration-of-the-http-connection-manager"></a><span data-ttu-id="6c0e2-117">Настройка диспетчера HTTP-соединений</span><span class="sxs-lookup"><span data-stu-id="6c0e2-117">Configuration of the HTTP Connection Manager</span></span>  
 <span data-ttu-id="6c0e2-118">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-118">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="6c0e2-119">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="6c0e2-119">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="6c0e2-120">Редактор диспетчера HTTP-сеансов (страница "Сервер")</span><span class="sxs-lookup"><span data-stu-id="6c0e2-120">HTTP Connection Manager Editor &#40;Server Page&#41;</span></span>](../http-connection-manager-editor-server-page.md)  
  
-   [<span data-ttu-id="6c0e2-121">Редактор диспетчера HTTP-сеансов (страница "Прокси-сервер")</span><span class="sxs-lookup"><span data-stu-id="6c0e2-121">HTTP Connection Manager Editor &#40;Proxy Page&#41;</span></span>](../http-connection-manager-editor-proxy-page.md)  
  
 <span data-ttu-id="6c0e2-122">Дополнительные сведения о программной настройке диспетчера соединений см. в разделе <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-122">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c0e2-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="6c0e2-123">See Also</span></span>  
 <span data-ttu-id="6c0e2-124">[Задача «веб-служба»](../control-flow/web-service-task.md) </span><span class="sxs-lookup"><span data-stu-id="6c0e2-124">[Web Service Task](../control-flow/web-service-task.md) </span></span>  
 [<span data-ttu-id="6c0e2-125">Соединения в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="6c0e2-125">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
