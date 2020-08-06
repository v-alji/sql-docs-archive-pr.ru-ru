---
title: Назначение сервера пересылки событий (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- event forwarding servers [SQL Server]
- events [SQL Server], forwarding
- alerts [SQL Server], forwarded events
ms.assetid: 81dfcbe4-3000-4e77-99de-bf85fef63a12
author: stevestein
ms.author: sstein
ms.openlocfilehash: bc5f01507bf893d1bffc682f65a01b9ff48ffa9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737454"
---
# <a name="designate-an-events-forwarding-server-sql-server-management-studio"></a><span data-ttu-id="54542-102">Назначение сервера для перенаправления событий (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="54542-102">Designate an Events Forwarding Server (SQL Server Management Studio)</span></span>
  <span data-ttu-id="54542-103">В этом разделе описывается, как назначить сервер, на который [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] перенаправляет события в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="54542-103">This topic describes how to designate a server to which [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] forwards events in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span></span> <span data-ttu-id="54542-104">Обратите внимание, что пересылка событий применяется к событиям между серверами, а не к событиям между экземплярами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , размещенными на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="54542-104">Note that event forwarding applies to events forwarded between servers, not to events forwarded between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hosted on a single computer.</span></span> <span data-ttu-id="54542-105">Также заметьте, что для получения перенаправленных событий сервер управления предупреждениями должен быть назначен экземпляром SQL Server по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="54542-105">Also note that in order to receive forwarded events, the alerts management server must be a default instance of SQL Server.</span></span>  
  
 <span data-ttu-id="54542-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="54542-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="54542-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="54542-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="54542-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="54542-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="54542-109">**Назначение сервера перенаправления событий с помощью:**</span><span class="sxs-lookup"><span data-stu-id="54542-109">**To designate an events forwarding server, using:**</span></span>  
  
     [<span data-ttu-id="54542-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="54542-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="54542-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="54542-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="54542-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="54542-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="54542-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="54542-113">Permissions</span></span>  
 <span data-ttu-id="54542-114">Необходимо членство в предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="54542-114">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="54542-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="54542-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-designate-an-events-forwarding-server"></a><span data-ttu-id="54542-116">Назначение сервера пересылки событий</span><span class="sxs-lookup"><span data-stu-id="54542-116">To designate an events forwarding server</span></span>  
  
1.  <span data-ttu-id="54542-117">В **обозревателе объектов** щелкните значок «плюс», чтобы развернуть сервер, с которого требуется перенаправлять события на другой сервер.</span><span class="sxs-lookup"><span data-stu-id="54542-117">In **Object Explorer,** click the plus sign to expand the server from which you want to forward events to another server.</span></span>  
  
2.  <span data-ttu-id="54542-118">Щелкните правой кнопкой мыши **Агент SQL Server** и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="54542-118">Right-click **SQL Server Agent** and select **Properties**.</span></span>  

3.  <span data-ttu-id="54542-119">В диалоговом окне **Свойства агента SQL Server —**_имя_сервера_ в разделе **Выберите страницу** выберите **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="54542-119">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Select a page**, select **Advanced**.</span></span>  

4.  <span data-ttu-id="54542-120">В области **Пересылка событий SQL Server**установите флажок **Перенаправить события на другой сервер** .</span><span class="sxs-lookup"><span data-stu-id="54542-120">Under **SQL Server event forwarding**, select the **Forward events to a different server** check box.</span></span>  
  
5.  <span data-ttu-id="54542-121">В списке **Сервер** выберите сервер, а затем на вкладке **События**выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="54542-121">In the **Server** list, select a server, and then, under **Events**, select one of the following:</span></span>  
  
    -   <span data-ttu-id="54542-122">Выберите **Необработанные события** , чтобы выполнялась переадресация только событий, не обработанных локальными предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="54542-122">Select **Unhandled events** to forward only the events that have not been handled by local alerts.</span></span>  
  
    -   <span data-ttu-id="54542-123">Выберите пункт **Все события** , чтобы выполнялась переадресация всех событий вне зависимости от того, обрабатывались они локальными предупреждениями или нет.</span><span class="sxs-lookup"><span data-stu-id="54542-123">Select **All events** to forward all events regardless of whether they have been handled by local alerts.</span></span>  
  
6.  <span data-ttu-id="54542-124">В списке **Если серьезность события равна или превышает** выберите степень серьезности, при которой события переадресуются выбранному серверу.</span><span class="sxs-lookup"><span data-stu-id="54542-124">In the **If event has severity at or above** list, click the severity level at which events are forwarded to the selected server.</span></span>  
  
7.  <span data-ttu-id="54542-125">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="54542-125">When finished, click **OK**.</span></span>  
  
  
