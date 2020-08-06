---
title: Назначение резервного оператора | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- fail-safe operator [SQL Server]
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
ms.assetid: 0f4eb513-5c0a-4523-974e-e85c1deeb57f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 714ed78875bd289f2fe2d64a5699c59bce58ced0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737460"
---
# <a name="designate-a-fail-safe-operator"></a><span data-ttu-id="161be-102">Назначение резервного оператора</span><span class="sxs-lookup"><span data-stu-id="161be-102">Designate a Fail-Safe Operator</span></span>
  <span data-ttu-id="161be-103">Резервный оператор — это пользователь, который получает предупреждение, если нужный оператор недоступен.</span><span class="sxs-lookup"><span data-stu-id="161be-103">A fail-safe operator is a user who receives the alert if the designated operator cannot be reached.</span></span> <span data-ttu-id="161be-104">В этом разделе описывается, как настроить резервный оператор для получения [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] уведомлений об оповещениях агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="161be-104">This topic describes how to set a fail-safe operator to receive [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert notifications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="161be-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="161be-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="161be-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="161be-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="161be-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="161be-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="161be-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="161be-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="161be-109">**Назначение резервного оператора с помощью:**</span><span class="sxs-lookup"><span data-stu-id="161be-109">**To designate a fail-safe operator, using:**</span></span>  
  
     [<span data-ttu-id="161be-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="161be-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="161be-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="161be-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="161be-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="161be-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="161be-113">Режимы отправки уведомлений с помощью пейджера и команды **net send** будут удалены из агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в следующей версии [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="161be-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="161be-114">Старайтесь не использовать эти функции в новых разработках и предусмотрите соответствующие изменения в приложениях, которые используют их в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="161be-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="161be-115">Обратите внимание, что для использования компонента Database Mail для отправки операторам уведомлений по электронной почте и на пейджер агент SQL Server необходимо настроить для использования компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="161be-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="161be-116">Дополнительные сведения см. в разделе [Назначить предупреждения для оператора](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="161be-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="161be-117">обеспечивает доступный графический способ управления заданиями и рекомендуется для создания и управления инфраструктурой заданий.</span><span class="sxs-lookup"><span data-stu-id="161be-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="161be-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="161be-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="161be-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="161be-119">Permissions</span></span>  
 <span data-ttu-id="161be-120">Только члены предопределенной роли сервера **sysadmin** могут назначать резервных операторов.</span><span class="sxs-lookup"><span data-stu-id="161be-120">Only members of the **sysadmin** fixed server role can designate fail-safe operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="161be-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="161be-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-designate-a-fail-safe-operator"></a><span data-ttu-id="161be-122">Назначение резервного оператора</span><span class="sxs-lookup"><span data-stu-id="161be-122">To designate a fail-safe operator</span></span>  
  
1.  <span data-ttu-id="161be-123">В **обозревателе объектов** щелкните знак "плюс", чтобы развернуть сервер, который содержит оператора агента SQL Server, назначаемого в качестве резервного.</span><span class="sxs-lookup"><span data-stu-id="161be-123">In **Object Explorer,** click the plus sign to expand the server that contains the SQL Server Agent operator that you want to designate as a fail-safe.</span></span>  
  
2.  <span data-ttu-id="161be-124">Щелкните правой кнопкой мыши **Агент SQL Server** и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="161be-124">Right-click **SQL Server Agent** and select **Properties**.</span></span>  

3.  <span data-ttu-id="161be-125">В диалоговом окне **свойства агент SQL Server —**_server_name_ в разделе **Выбор страницы**выберите **система предупреждений**.</span><span class="sxs-lookup"><span data-stu-id="161be-125">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Select a page**, select **Alert System**.</span></span>  
 
4.  <span data-ttu-id="161be-126">В разделе **Резервный оператор**выберите **Включить резервный оператор**.</span><span class="sxs-lookup"><span data-stu-id="161be-126">Under **Fail-safe operator**, select **Enable fail-safe operator**.</span></span>  
  
5.  <span data-ttu-id="161be-127">В списке **Оператор** выберите оператор, который необходимо сделать резервным.</span><span class="sxs-lookup"><span data-stu-id="161be-127">In the **Operator** list, select the operator that you want to make a fail-safe.</span></span>  
  
6.  <span data-ttu-id="161be-128">Установите некоторые или все указанные флажки для выбора способа уведомления оператора: **Электронная почта**, **Пейджер**или **Net send**.</span><span class="sxs-lookup"><span data-stu-id="161be-128">Select either any or all of the following check boxes to specify how the operator will be notified: **E-mail**, **Pager**, or **Net send**.</span></span>  
  
7.  <span data-ttu-id="161be-129">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="161be-129">When finished, click **OK**.</span></span>  
  
  
