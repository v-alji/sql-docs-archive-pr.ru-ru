---
title: Транзакции (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Master Data Services], about transactions
- transactions [Master Data Services]
ms.assetid: 4cd2fa6f-9c76-4b7a-ae18-d4e5fd2f03f5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c693b550e0c1adb8f5910d99c7125c85f41abb8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740106"
---
# <a name="transactions-master-data-services"></a><span data-ttu-id="f1518-102">Транзакции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f1518-102">Transactions (Master Data Services)</span></span>
  <span data-ttu-id="f1518-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]транзакция регистрируется при каждом выполнении действия с элементом.</span><span class="sxs-lookup"><span data-stu-id="f1518-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a transaction is recorded each time action is taken on a member.</span></span> <span data-ttu-id="f1518-104">Все пользователи могут просматривать транзакции, а администраторы также могут их обращать (отменять).</span><span class="sxs-lookup"><span data-stu-id="f1518-104">Transactions can be viewed by all users and reversed by administrators.</span></span> <span data-ttu-id="f1518-105">Транзакции отображают дату, время и пользователя, выполнившего действие, а также другие сведения.</span><span class="sxs-lookup"><span data-stu-id="f1518-105">Transactions show the date, time, and user who took the action, along with other details.</span></span> <span data-ttu-id="f1518-106">Пользователь может добавить к транзакции заметку, чтобы указать причину выполнения транзакции.</span><span class="sxs-lookup"><span data-stu-id="f1518-106">Users can add an annotation to a transaction, to indicate why a transaction took place.</span></span>  
  
## <a name="when-transaction-are-recorded"></a><span data-ttu-id="f1518-107">Время регистрации транзакций</span><span class="sxs-lookup"><span data-stu-id="f1518-107">When Transaction Are Recorded</span></span>  
 <span data-ttu-id="f1518-108">Транзакции записываются, когда элементы:</span><span class="sxs-lookup"><span data-stu-id="f1518-108">Transactions are recorded when members:</span></span>  
  
-   <span data-ttu-id="f1518-109">создаются, удаляются или повторно активируются;</span><span class="sxs-lookup"><span data-stu-id="f1518-109">Are created, deleted, or reactivated.</span></span>  
  
-   <span data-ttu-id="f1518-110">изменяют значения своих атрибутов;</span><span class="sxs-lookup"><span data-stu-id="f1518-110">Have attribute values changed.</span></span>  
  
-   <span data-ttu-id="f1518-111">перемещаются по иерархии.</span><span class="sxs-lookup"><span data-stu-id="f1518-111">Are moved in a hierarchy.</span></span>  
  
 <span data-ttu-id="f1518-112">Когда бизнес-правила изменяют значения атрибутов, транзакции не регистрируются.</span><span class="sxs-lookup"><span data-stu-id="f1518-112">Transactions are not recorded when business rules change attribute values.</span></span>  
  
## <a name="view-and-manage-transactions"></a><span data-ttu-id="f1518-113">Просмотр и управление транзакциями</span><span class="sxs-lookup"><span data-stu-id="f1518-113">View and Manage Transactions</span></span>  
 <span data-ttu-id="f1518-114">В функциональной области **Обозреватель** вы можете просматривать сделанные вами транзакции и добавлять к ним заметки (примечания).</span><span class="sxs-lookup"><span data-stu-id="f1518-114">In the **Explorer** functional area, you can view and annotate (add comments to) the transactions that you made yourself.</span></span>  
  
 <span data-ttu-id="f1518-115">В функциональной области **Управление версиями** администратор может просматривать все транзакции всех пользователей для моделей, к которым у них имеется доступ, а также обращать любые такие транзакции.</span><span class="sxs-lookup"><span data-stu-id="f1518-115">In the **Version Management** functional area, administrators can view all transactions for all users for the models they have access to, and reverse any of these transactions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1518-116">Администраторы могут просматривать все транзакции всех пользователей до тех пор, если только в функциональной области **Управление версиями** для них не задан уровень разрешений только для чтения.</span><span class="sxs-lookup"><span data-stu-id="f1518-116">Administrators can view all transactions for all users as long as they don't have the read-only permission level applied in the **Version Management** functional area .</span></span> <span data-ttu-id="f1518-117">Например, если у администратора есть разрешение только на чтение и разрешение на обновление, он не сможет просматривать транзакции других пользователей, так как разрешение только на чтение имеет приоритет над разрешением на обновление.</span><span class="sxs-lookup"><span data-stu-id="f1518-117">For example, if the read-only permission and update permission level is set for the administrator, the administrator will not be able to see other user transactions because the read-only permission will take precedence over the update permission.</span></span>

## <a name="system-settings"></a><span data-ttu-id="f1518-118">Системные настройки</span><span class="sxs-lookup"><span data-stu-id="f1518-118">System Settings</span></span>  
 <span data-ttu-id="f1518-119">В программе [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] имеется параметр, который определяет, записываются ли транзакции для промежуточных записей.</span><span class="sxs-lookup"><span data-stu-id="f1518-119">There is a setting in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] that affects whether or not transactions are recorded when records are staged.</span></span> <span data-ttu-id="f1518-120">Эта настройка влияет только на SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="f1518-120">This setting affects SQL Server 2008 R2 only.</span></span> <span data-ttu-id="f1518-121">Этот параметр можно настроить в программе [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] или непосредственно в таблице системных параметров в базе данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f1518-121">You can adjust this setting in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] or directly in the System Settings table in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="f1518-122">Дополнительные сведения см. в разделе [Системные параметры (службы Master Data Services)](system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f1518-122">For more information, see [System Settings &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span></span>  
  
 <span data-ttu-id="f1518-123">При импорте данных из этой версии [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]можно указать, следует ли вести журнал транзакций при инициировании хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="f1518-123">When importing data in this version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you can specify whether or not to log transactions when initiating the stored procedure.</span></span> <span data-ttu-id="f1518-124">Дополнительные сведения см. в разделе [Промежуточная хранимая процедура (службы Master Data Services)](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f1518-124">For more information, see [Staging Stored Procedure &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span></span>  
  
## <a name="concurrency"></a><span data-ttu-id="f1518-125">Параллелизм</span><span class="sxs-lookup"><span data-stu-id="f1518-125">Concurrency</span></span>  
 <span data-ttu-id="f1518-126">Если значение определенной сущности одновременно отображается в нескольких сеансах обозревателя, это значение может изменяться одновременно несколькими пользователями.</span><span class="sxs-lookup"><span data-stu-id="f1518-126">If a particular entity value is shown simultaneously in more than one Explorer session, concurrent edits to the same value are possible.</span></span> <span data-ttu-id="f1518-127">Службы MDS не обнаруживают одновременные изменения автоматически.</span><span class="sxs-lookup"><span data-stu-id="f1518-127">Concurrent edits will not be detected automatically by MDS.</span></span> <span data-ttu-id="f1518-128">Такая ситуация возможна, когда несколько пользователей работают в обозревателе служб MDS в веб-браузере, например в нескольких сеансах, на нескольких вкладках браузера или в нескольких его окнах либо из-под нескольких учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="f1518-128">This can occur when multiple users use the MDS Explorer in the Web browser from multiple sessions, for example from multiple computers, multiple browser tabs or windows, or multiple user accounts.</span></span>  
  
 <span data-ttu-id="f1518-129">Несколько пользователей могут обновлять одно значение сущности без ошибок несмотря на то, что транзакции включены.</span><span class="sxs-lookup"><span data-stu-id="f1518-129">More than one user can update the same entity values without error despite transactions being enabled.</span></span> <span data-ttu-id="f1518-130">Обычно приоритет получает изменение, которое по времени было внесено последним.</span><span class="sxs-lookup"><span data-stu-id="f1518-130">Typically the last edit to the value in a sequence of time will take precedence.</span></span> <span data-ttu-id="f1518-131">Администратор может просмотреть конфликты, возникающие при одновременном внесении нескольких одинаковых изменений, в журнале транзакций и вручную разрешить их.</span><span class="sxs-lookup"><span data-stu-id="f1518-131">The duplicate edit conflict can be manually observed in the transaction history and can be reversed manually by the administrator.</span></span> <span data-ttu-id="f1518-132">В журнале транзакций отображаются отдельные транзакции для **предыдущего значения** и **нового значения** для рассматриваемого атрибута из каждого сеанса, однако конфликты, возникающие, если для одного старого значения существуют несколько **новых значений** , автоматически не разрешаются.</span><span class="sxs-lookup"><span data-stu-id="f1518-132">The transaction history will show the individual transactions for the **Prior value** and **New value** for the attribute in question from each session, but will not automatically resolve the conflict when multiple **New Values** exist for the same old value.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f1518-133">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="f1518-133">Related Tasks</span></span>  
  
|<span data-ttu-id="f1518-134">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="f1518-134">Task Description</span></span>|<span data-ttu-id="f1518-135">Раздел</span><span class="sxs-lookup"><span data-stu-id="f1518-135">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="f1518-136">Отмена действия путем обращения транзакции (только администраторы).</span><span class="sxs-lookup"><span data-stu-id="f1518-136">Undo an action by reversing a transaction (administrators only).</span></span>|[<span data-ttu-id="f1518-137">Отмена транзакции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f1518-137">Reverse a Transaction &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/reverse-a-transaction-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="f1518-138">См. также</span><span class="sxs-lookup"><span data-stu-id="f1518-138">Related Content</span></span>  
  
-   [<span data-ttu-id="f1518-139">Администраторы (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f1518-139">Administrators &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/administrators-master-data-services.md)  
  
-   [<span data-ttu-id="f1518-140">Заметки (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f1518-140">Annotations &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/annotations-master-data-services.md)  
  
  
