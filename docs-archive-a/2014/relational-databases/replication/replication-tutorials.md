---
title: Учебники по репликации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- tutorials [SQL Server replication]
- walkthroughs [SQL Server replication]
- replication [SQL Server], tutorials
ms.assetid: 19fbd10e-5b59-4cd0-a988-52d5d9206242
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f4d70abd6c58b3eb0fa4a53e2806ab1b3fbe9245
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655034"
---
# <a name="replication-tutorials"></a><span data-ttu-id="1ced4-102">Учебники по репликации</span><span class="sxs-lookup"><span data-stu-id="1ced4-102">Replication Tutorials</span></span>
  <span data-ttu-id="1ced4-103">Репликация включает учебники, которые могут быть использованы для изучения установки и запуска топологии репликации при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ced4-103">Replication includes tutorials that you can use to learn how to set up and run replication topologies using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="1ced4-104">В учебниках по репликации «Издатель» означает сервер, который содержит реплицируемые данные источника, а «Подписчик» — целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="1ced4-104">In the replication tutorials, "Publisher" refers to the server that contains that source data being replicated and "Subscriber" refers to the destination server.</span></span> <span data-ttu-id="1ced4-105">Издатель и подписчик могут совместно использовать один и тот же экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], но это не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="1ced4-105">The Publisher and Subscriber may share the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but it is not a requirement.</span></span> <span data-ttu-id="1ced4-106">Дополнительные сведения см. в разделе [Обзор модели публикации репликации](publish/replication-publishing-model-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1ced4-106">For more information, see [Replication Publishing Model Overview](publish/replication-publishing-model-overview.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1ced4-107">Большинство задач, представленных в этих учебниках, могут выполняться программным способом.</span><span class="sxs-lookup"><span data-stu-id="1ced4-107">Most of the tasks shown in these tutorials can be performed programmatically.</span></span> <span data-ttu-id="1ced4-108">Дополнительные сведения см. в разделе [Guide разработчика &#40;репликация&#41;](concepts/replication-developer-documentation.md).</span><span class="sxs-lookup"><span data-stu-id="1ced4-108">For more information, see [Developer's Guide &#40;Replication&#41;](concepts/replication-developer-documentation.md).</span></span>  
  
## <a name="replication-tutorials"></a><span data-ttu-id="1ced4-109">Учебники по репликации</span><span class="sxs-lookup"><span data-stu-id="1ced4-109">Replication Tutorials</span></span>  
 [<span data-ttu-id="1ced4-110">Подготовка сервера к репликации</span><span class="sxs-lookup"><span data-stu-id="1ced4-110">Preparing the Server for Replication</span></span>](tutorial-preparing-the-server-for-replication.md)  
 <span data-ttu-id="1ced4-111">Изучите как подготавливать серверы, чтобы репликация могла быть выполнена с минимумом прав доступа.</span><span class="sxs-lookup"><span data-stu-id="1ced4-111">Learn how to prepare servers so that replication can be run with least privileges.</span></span> <span data-ttu-id="1ced4-112">Прежде чем перейти к другим учебникам по репликации, необходимо закончить выполнение данного учебника.</span><span class="sxs-lookup"><span data-stu-id="1ced4-112">You must complete this tutorial before the other replication tutorials.</span></span>  
  
 [<span data-ttu-id="1ced4-113">Репликация данных между постоянно соединенными серверами</span><span class="sxs-lookup"><span data-stu-id="1ced4-113">Replicating Data Between Continuously Connected Servers</span></span>](tutorial-replicating-data-between-continuously-connected-servers.md)  
 <span data-ttu-id="1ced4-114">Изучите, как использовать репликацию транзакций для репликации данных между полностью соединенными серверами.</span><span class="sxs-lookup"><span data-stu-id="1ced4-114">Learn how to use transactional replication to replicate data between fully connected servers.</span></span>  
  
 [<span data-ttu-id="1ced4-115">Репликация данных с мобильными клиентами</span><span class="sxs-lookup"><span data-stu-id="1ced4-115">Replicating Data with Mobile Clients</span></span>](tutorial-replicating-data-with-mobile-clients.md)  
 <span data-ttu-id="1ced4-116">Изучите, как использовать репликацию слиянием для обмена данными между сервером и одним или более клиентами, которые подключаются периодически.</span><span class="sxs-lookup"><span data-stu-id="1ced4-116">Learn how to use merge replication to exchange data between a server and one or more clients that are only occasionally connected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ced4-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="1ced4-117">See Also</span></span>  
 [<span data-ttu-id="1ced4-118">Безопасность Репликация SQL Server</span><span class="sxs-lookup"><span data-stu-id="1ced4-118">SQL Server Replication Security</span></span>](security/view-and-modify-replication-security-settings.md)  
  
  
