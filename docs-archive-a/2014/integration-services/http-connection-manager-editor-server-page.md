---
title: Редактор диспетчера HTTP-сеансов (страница «сервер») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.httpconnection.server.f1
helpviewer_keywords:
- HTTP Connection Manager Editor
ms.assetid: 774778a0-ece6-4971-b93f-b121d8fc1fc1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2349766b11b28ff258496dc966d554d49c7657b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655837"
---
# <a name="http-connection-manager-editor-server-page"></a><span data-ttu-id="98f3c-102">Редактор диспетчера HTTP-сеансов (страница «Сервер»)</span><span class="sxs-lookup"><span data-stu-id="98f3c-102">HTTP Connection Manager Editor (Server Page)</span></span>
  <span data-ttu-id="98f3c-103">Используйте вкладку **Сервер** диалогового окна **Редактор диспетчера HTTP-соединений** , чтобы настроить диспетчер HTTP-соединений, указав такие свойства, как URL-адрес и учетные данные безопасности.</span><span class="sxs-lookup"><span data-stu-id="98f3c-103">Use the **Server** tab of the **HTTP Connection Manager Editor** dialog box to configure the HTTP Connection Manager by specifying properties such as the URL and security credentials.</span></span> <span data-ttu-id="98f3c-104">HTTP-соединение позволяет пакету получить доступ к веб-серверу через протокол HTTP, чтобы передавать или принимать файлы.</span><span class="sxs-lookup"><span data-stu-id="98f3c-104">An HTTP connection enables a package to access a Web server by using HTTP to send or receive files.</span></span> <span data-ttu-id="98f3c-105">После настройки диспетчера HTTP-соединений можно проверить соединение.</span><span class="sxs-lookup"><span data-stu-id="98f3c-105">After configuring the HTTP Connection Manager, you can also test the connection.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="98f3c-106">Диспетчер HTTP-соединений поддерживает только анонимную проверку подлинности и обычную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="98f3c-106">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="98f3c-107">Проверка подлинности Windows не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="98f3c-107">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="98f3c-108">Дополнительные сведения о диспетчере HTTP-соединений см. в разделе [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="98f3c-108">To learn more about the HTTP connection manager, see [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span></span> <span data-ttu-id="98f3c-109">Дополнительные сведения о распространенном сценарии использования диспетчера HTTP-соединений см. в разделе [Web Service Task](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="98f3c-109">To learn more about a common usage scenario for the HTTP Connection Manager, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="98f3c-110">Варианты</span><span class="sxs-lookup"><span data-stu-id="98f3c-110">Options</span></span>  
 <span data-ttu-id="98f3c-111">**URL-адрес сервера**</span><span class="sxs-lookup"><span data-stu-id="98f3c-111">**Server URL**</span></span>  
 <span data-ttu-id="98f3c-112">Введите URL-адрес для сервера.</span><span class="sxs-lookup"><span data-stu-id="98f3c-112">Type the URL for the server.</span></span>  
  
 <span data-ttu-id="98f3c-113">Если планируется загрузить WSDL-файл с помощью кнопки **Загрузить язык WSDL** на странице **Общие** в окне **Редактор задачи «Веб-служба»** , введите URL-адрес для WSDL-файла.</span><span class="sxs-lookup"><span data-stu-id="98f3c-113">If you plan to use the **Download WSDL** button on the **General** page of the **Web Service Task Editor** to download a WSDL file, type the URL for the WSDL file.</span></span> <span data-ttu-id="98f3c-114">Этот URL-адрес заканчивается строкой «?wsdl».</span><span class="sxs-lookup"><span data-stu-id="98f3c-114">This URL ends with "?wsdl".</span></span>  
  
 <span data-ttu-id="98f3c-115">**Использовать учетные данные**</span><span class="sxs-lookup"><span data-stu-id="98f3c-115">**Use credentials**</span></span>  
 <span data-ttu-id="98f3c-116">Укажите, должен ли диспетчер HTTP-соединений использовать для проверки подлинности учетные данные безопасности пользователя.</span><span class="sxs-lookup"><span data-stu-id="98f3c-116">Specify whether you want the HTTP Connection Manager to use the user's security credentials for authentication.</span></span>  
  
 <span data-ttu-id="98f3c-117">**User name**</span><span class="sxs-lookup"><span data-stu-id="98f3c-117">**User name**</span></span>  
 <span data-ttu-id="98f3c-118">Если диспетчер HTTP-соединений использует учетные данные, необходимо указать имя пользователя, пароль и домен.</span><span class="sxs-lookup"><span data-stu-id="98f3c-118">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="98f3c-119">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="98f3c-119">**Password**</span></span>  
 <span data-ttu-id="98f3c-120">Если диспетчер HTTP-соединений использует учетные данные, необходимо указать имя пользователя, пароль и домен.</span><span class="sxs-lookup"><span data-stu-id="98f3c-120">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="98f3c-121">**Домен**</span><span class="sxs-lookup"><span data-stu-id="98f3c-121">**Domain**</span></span>  
 <span data-ttu-id="98f3c-122">Если диспетчер HTTP-соединений использует учетные данные, необходимо указать имя пользователя, пароль и домен.</span><span class="sxs-lookup"><span data-stu-id="98f3c-122">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="98f3c-123">**Использовать сертификат клиента**</span><span class="sxs-lookup"><span data-stu-id="98f3c-123">**Use client certificate**</span></span>  
 <span data-ttu-id="98f3c-124">Укажите, должен ли диспетчер HTTP-соединений использовать для проверки подлинности сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="98f3c-124">Specify whether you want the HTTP Connection Manager to use a client certificate for authentication.</span></span>  
  
 <span data-ttu-id="98f3c-125">**Сертификат**</span><span class="sxs-lookup"><span data-stu-id="98f3c-125">**Certificate**</span></span>  
 <span data-ttu-id="98f3c-126">Выберите сертификат из списка, воспользовавшись диалоговым окном **Выбор сертификата** .</span><span class="sxs-lookup"><span data-stu-id="98f3c-126">Select a certificate from the list by using the **Select Certificate** dialog box.</span></span> <span data-ttu-id="98f3c-127">Текстовое поле отображает имя, связанное с этим сертификатом.</span><span class="sxs-lookup"><span data-stu-id="98f3c-127">The text box displays the name associated with this certificate.</span></span>  
  
 <span data-ttu-id="98f3c-128">**Время ожидания (сек)**</span><span class="sxs-lookup"><span data-stu-id="98f3c-128">**Time-out (in seconds)**</span></span>  
 <span data-ttu-id="98f3c-129">Укажите время ожидания при установке соединения с веб-сервером.</span><span class="sxs-lookup"><span data-stu-id="98f3c-129">Provide a time-out for connecting to the Web server.</span></span> <span data-ttu-id="98f3c-130">По умолчанию для этого свойства устанавливается значение 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="98f3c-130">The default value of this property is 30 seconds.</span></span>  
  
 <span data-ttu-id="98f3c-131">**Размер фрагмента данных (КБ)**</span><span class="sxs-lookup"><span data-stu-id="98f3c-131">**Chunk size (in KB)**</span></span>  
 <span data-ttu-id="98f3c-132">Укажите размер фрагмента для записи данных.</span><span class="sxs-lookup"><span data-stu-id="98f3c-132">Provide a chunk size for writing data.</span></span>  
  
 <span data-ttu-id="98f3c-133">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="98f3c-133">**Test Connection**</span></span>  
 <span data-ttu-id="98f3c-134">После настройки диспетчера HTTP-подключений проверьте работоспособность соединения, нажав кнопку **Проверить соединение**.</span><span class="sxs-lookup"><span data-stu-id="98f3c-134">After configuring the HTTP Connection Manager, confirm that the connection is viable by clicking **Test Connection**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f3c-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="98f3c-135">See Also</span></span>  
 <span data-ttu-id="98f3c-136">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="98f3c-136">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="98f3c-137">Редактор диспетчера HTTP-сеансов (страница "Прокси-сервер")</span><span class="sxs-lookup"><span data-stu-id="98f3c-137">HTTP Connection Manager Editor &#40;Proxy Page&#41;</span></span>](../../2014/integration-services/http-connection-manager-editor-proxy-page.md)  
  
  
