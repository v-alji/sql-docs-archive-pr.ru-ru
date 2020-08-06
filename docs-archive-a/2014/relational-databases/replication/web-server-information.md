---
title: Сведения о веб-сервере | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.webserverinformation.f1
ms.assetid: 86d72275-45c7-459f-98cf-f5a366ed279c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f7b461ed26b3e234f083add3312e256e164efc9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658185"
---
# <a name="web-server-information"></a><span data-ttu-id="f7abf-102">Сведения о веб-сервере</span><span class="sxs-lookup"><span data-stu-id="f7abf-102">Web Server Information</span></span>
  <span data-ttu-id="f7abf-103">Сведения о веб-сервере необходимы для использования функции веб-синхронизации при репликации слиянием.</span><span class="sxs-lookup"><span data-stu-id="f7abf-103">Web server information is required to use the Web synchronization option for merge replication.</span></span> <span data-ttu-id="f7abf-104">Дополнительные сведения о конфигурации для веб-синхронизации см. в статье [Настройка веб-синхронизации](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="f7abf-104">For information about configuring Web synchronization, see [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f7abf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f7abf-105">Options</span></span>  
 <span data-ttu-id="f7abf-106">**Адрес веб-сервера**</span><span class="sxs-lookup"><span data-stu-id="f7abf-106">**Web server address**</span></span>  
 <span data-ttu-id="f7abf-107">Если адрес веб-сервера задан на страницах **Моментальный снимок — FTP и Интернет** диалогового окна **Свойства публикации**, он отображается в этом текстовом поле как адрес по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f7abf-107">If you specified a Web server address in the **FTP Snapshot andInternet** page of the **Publication Properties** dialog box, it appears in this text box as a default.</span></span> <span data-ttu-id="f7abf-108">Можно принять значение по умолчанию или ввести полный адрес веб-сервера [!INCLUDE[msCoName](../../includes/msconame-md.md)] IIS, синхронизирующего данную подписку.</span><span class="sxs-lookup"><span data-stu-id="f7abf-108">Either accept the default or enter a fully qualified Web server address for the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) server that synchronizes this subscription.</span></span>  
  
 <span data-ttu-id="f7abf-109">**Как будет соединяться с веб-сервером каждый подписчик**</span><span class="sxs-lookup"><span data-stu-id="f7abf-109">**How will each Subscriber connect to the Web server?**</span></span>  
 <span data-ttu-id="f7abf-110">Позволяет указать тип проверки подлинности, используемой для подключения к веб-серверу.</span><span class="sxs-lookup"><span data-stu-id="f7abf-110">Specify the type of authentication used to connect to the Web server.</span></span> <span data-ttu-id="f7abf-111">Рекомендуется использовать обычную проверку подлинности для подключений к серверу IIS в сопряжении с безопасным протоколом Secure Sockets Layer (SSL).</span><span class="sxs-lookup"><span data-stu-id="f7abf-111">It is recommended to use Basic Authentication for connections to the IIS server in conjunction with Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="f7abf-112">Если выбрана обычная проверка подлинности, введите имя входа и пароль, которые будут использоваться для подключения подписчика к серверу IIS.</span><span class="sxs-lookup"><span data-stu-id="f7abf-112">If you select Basic Authentication, enter the login and password that will be used to connect from the Subscriber to the IIS server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7abf-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="f7abf-113">See Also</span></span>  
 <span data-ttu-id="f7abf-114">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="f7abf-114">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="f7abf-115">[Просмотр и изменение свойств подписки по запросу](view-and-modify-pull-subscription-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f7abf-115">[View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md) </span></span>  
 <span data-ttu-id="f7abf-116">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span><span class="sxs-lookup"><span data-stu-id="f7abf-116">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span></span>  
 <span data-ttu-id="f7abf-117">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="f7abf-117">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 [<span data-ttu-id="f7abf-118">Web Synchronization for Merge Replication</span><span class="sxs-lookup"><span data-stu-id="f7abf-118">Web Synchronization for Merge Replication</span></span>](web-synchronization-for-merge-replication.md)  
  
  
