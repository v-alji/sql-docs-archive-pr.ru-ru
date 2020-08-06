---
title: Редактор диспетчера HTTP-сеансов (страница "прокси") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.httpconnection.proxy.f1
helpviewer_keywords:
- HTTP Connection Manager Editor
ms.assetid: e831a830-49a3-49c5-8a31-9731fc4fd12e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f8269dbbeb226ffa3f56c226e1a416d99c1e3f13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655842"
---
# <a name="http-connection-manager-editor-proxy-page"></a><span data-ttu-id="dab07-102">Редактор диспетчера HTTP-соединений (страница «Прокси-сервер»)</span><span class="sxs-lookup"><span data-stu-id="dab07-102">HTTP Connection Manager Editor (Proxy Page)</span></span>
  <span data-ttu-id="dab07-103">Используйте вкладку **Прокси-сервер** диалогового окна **Редактор диспетчера HTTP-соединений** , чтобы настроить диспетчер HTTP-соединений для работы с прокси-сервером.</span><span class="sxs-lookup"><span data-stu-id="dab07-103">Use the **Proxy** tab of the **HTTP Connection Manager Editor** dialog box to configure the HTTP Connection Manager to use a proxy server.</span></span> <span data-ttu-id="dab07-104">HTTP-соединение позволяет пакету получить доступ к веб-серверу через протокол HTTP, чтобы передавать или принимать файлы.</span><span class="sxs-lookup"><span data-stu-id="dab07-104">An HTTP connection enables a package to access a Web server by using HTTP to send or receive files.</span></span>  
  
 <span data-ttu-id="dab07-105">Дополнительные сведения о диспетчере HTTP-соединений см. в разделе [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="dab07-105">To learn more about the HTTP connection manager, see [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span></span> <span data-ttu-id="dab07-106">Дополнительные сведения о распространенном сценарии использования диспетчера HTTP-соединений см. в разделе [Web Service Task](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="dab07-106">To learn more about a common usage scenario for the HTTP Connection Manager, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="dab07-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="dab07-107">Options</span></span>  
 <span data-ttu-id="dab07-108">**Использовать прокси-сервер**</span><span class="sxs-lookup"><span data-stu-id="dab07-108">**Use proxy**</span></span>  
 <span data-ttu-id="dab07-109">Укажите, должен ли диспетчер HTTP-сеансов подключаться через прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="dab07-109">Specify whether you want the HTTP Connection Manager to connect through a proxy server.</span></span>  
  
 <span data-ttu-id="dab07-110">**URL-адрес прокси-сервера**</span><span class="sxs-lookup"><span data-stu-id="dab07-110">**Proxy URL**</span></span>  
 <span data-ttu-id="dab07-111">Введите URL-адрес прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="dab07-111">Type the URL for the proxy server.</span></span>  
  
 <span data-ttu-id="dab07-112">**Не использовать прокси-сервер при локальном подключении**</span><span class="sxs-lookup"><span data-stu-id="dab07-112">**Bypass proxy on local**</span></span>  
 <span data-ttu-id="dab07-113">Укажите, должен ли диспетчер HTTP-соединений исключать прокси-сервер для локальных адресов.</span><span class="sxs-lookup"><span data-stu-id="dab07-113">Specify whether you want the HTTP Connection Manager to bypass the proxy server for local addresses.</span></span>  
  
 <span data-ttu-id="dab07-114">**Использовать учетные данные**</span><span class="sxs-lookup"><span data-stu-id="dab07-114">**Use credentials**</span></span>  
 <span data-ttu-id="dab07-115">Укажите, должен ли диспетчер HTTP-соединений использовать учетные данные для прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="dab07-115">Specify whether you want the HTTP Connection Manager to use security credentials for the proxy server.</span></span>  
  
 <span data-ttu-id="dab07-116">**User name**</span><span class="sxs-lookup"><span data-stu-id="dab07-116">**User name**</span></span>  
 <span data-ttu-id="dab07-117">Если диспетчер HTTP-соединений использует учетные данные, необходимо указать имя пользователя, пароль и домен.</span><span class="sxs-lookup"><span data-stu-id="dab07-117">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="dab07-118">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="dab07-118">**Password**</span></span>  
 <span data-ttu-id="dab07-119">Если диспетчер HTTP-соединений использует учетные данные, необходимо указать имя пользователя, пароль и домен.</span><span class="sxs-lookup"><span data-stu-id="dab07-119">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="dab07-120">**Домен**</span><span class="sxs-lookup"><span data-stu-id="dab07-120">**Domain**</span></span>  
 <span data-ttu-id="dab07-121">Если диспетчер HTTP-соединений использует учетные данные, необходимо указать имя пользователя, пароль и домен.</span><span class="sxs-lookup"><span data-stu-id="dab07-121">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="dab07-122">**Список адресов, не требующих прокси-сервера**</span><span class="sxs-lookup"><span data-stu-id="dab07-122">**Proxy bypass list**</span></span>  
 <span data-ttu-id="dab07-123">Список адресов, для которых прокси-сервер использоваться не должен.</span><span class="sxs-lookup"><span data-stu-id="dab07-123">The list of addresses for which  you want to bypass the proxy server.</span></span>  
  
 <span data-ttu-id="dab07-124">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="dab07-124">**Add**</span></span>  
 <span data-ttu-id="dab07-125">Введите адрес, для которого прокси-сервер использоваться не должен.</span><span class="sxs-lookup"><span data-stu-id="dab07-125">Type an address for which you want to bypass the proxy server.</span></span>  
  
 <span data-ttu-id="dab07-126">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="dab07-126">**Remove**</span></span>  
 <span data-ttu-id="dab07-127">Выберите адрес и затем удалите его, нажав кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="dab07-127">Select an address, and then remove it by clicking **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab07-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="dab07-128">See Also</span></span>  
 <span data-ttu-id="dab07-129">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="dab07-129">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="dab07-130">Редактор диспетчера HTTP-сеансов (страница "Сервер")</span><span class="sxs-lookup"><span data-stu-id="dab07-130">HTTP Connection Manager Editor &#40;Server Page&#41;</span></span>](../../2014/integration-services/http-connection-manager-editor-server-page.md)  
  
  
