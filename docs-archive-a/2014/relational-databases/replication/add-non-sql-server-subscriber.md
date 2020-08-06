---
title: Добавление подписчика, отличного от подписчика SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.addnonsqlsubscriber.f1
ms.assetid: 21beeaa0-4b9e-48da-be63-1b9ff14e03d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e36d048b11fcc71b27ab0ab2ee815b0284187c4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664884"
---
# <a name="add-non-sql-server-subscriber"></a><span data-ttu-id="234c3-102">Добавить подписчик, отличный от подписчика SQL Server</span><span class="sxs-lookup"><span data-stu-id="234c3-102">Add Non-SQL Server Subscriber</span></span>
  <span data-ttu-id="234c3-103">Репликация поддерживает принудительные подписки на моментальные снимки и публикации транзакций для подписчиков Oracle и IBM DB2.</span><span class="sxs-lookup"><span data-stu-id="234c3-103">Replication supports creating push subscriptions to snapshot and transactional publications for Oracle and IBM DB2 Subscribers.</span></span>  
  
## <a name="options"></a><span data-ttu-id="234c3-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="234c3-104">Options</span></span>  
 <span data-ttu-id="234c3-105">**Тип добавляемого подписчика:**</span><span class="sxs-lookup"><span data-stu-id="234c3-105">**Type of Subscriber to add**</span></span>  
 <span data-ttu-id="234c3-106">Выберите подписчик Oracle или подписчик IBM DB2.</span><span class="sxs-lookup"><span data-stu-id="234c3-106">Select an Oracle Subscriber or IBM DB2 Subscriber.</span></span> <span data-ttu-id="234c3-107">Дополнительные сведения о поддержке таких подписчиков см. в статье [Подписчики, отличные от подписчиков SQL Server](non-sql/non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="234c3-107">For more information about support for these Subscribers, see [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md).</span></span>  
  
 <span data-ttu-id="234c3-108">**Имя источника данных**</span><span class="sxs-lookup"><span data-stu-id="234c3-108">**Data source name**</span></span>  
 <span data-ttu-id="234c3-109">Данное имя позволяет найти базу данных в сети.</span><span class="sxs-lookup"><span data-stu-id="234c3-109">The name used to locate the database on a network.</span></span> <span data-ttu-id="234c3-110">Строка соединения с базой данных, формируемая репликацией, содержит имя источника данных, имя входа, пароль и параметры соединения, указанные на странице **Безопасность агента распространителя** данного мастера.</span><span class="sxs-lookup"><span data-stu-id="234c3-110">Replication produces a connection string for the database using the data source name, combined with the login, password, and any connection options you specify in the **Distribution Agent Security** page in this wizard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="234c3-111">[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не проверяет имя источника данных и строку подключения, пока агент распространителя не попытается инициализировать подписку.</span><span class="sxs-lookup"><span data-stu-id="234c3-111">The data source name and connection string are not validated by [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] until the Distribution Agent attempts to initialize the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="234c3-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="234c3-112">See Also</span></span>  
 <span data-ttu-id="234c3-113">[Создание подписки для подписчика, отличного от подписчика SQL Server](create-a-subscription-for-a-non-sql-server-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="234c3-113">[Create a Subscription for a Non-SQL Server Subscriber](create-a-subscription-for-a-non-sql-server-subscriber.md) </span></span>  
 <span data-ttu-id="234c3-114">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span><span class="sxs-lookup"><span data-stu-id="234c3-114">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span></span>  
 [<span data-ttu-id="234c3-115">Подписка на публикации</span><span class="sxs-lookup"><span data-stu-id="234c3-115">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
