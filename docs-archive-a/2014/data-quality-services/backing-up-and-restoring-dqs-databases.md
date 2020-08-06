---
title: Резервное копирование и восстановление баз данных DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f3091f62-2234-4a80-a615-cf14c2a1da85
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 489664d8c64a99d1ea4dcec79b93e5b01b28f649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655985"
---
# <a name="backing-up-and-restoring-dqs-databases"></a><span data-ttu-id="ee024-102">Резервное копирование и восстановление баз данных DQS</span><span class="sxs-lookup"><span data-stu-id="ee024-102">Backing Up and Restoring DQS Databases</span></span>
  <span data-ttu-id="ee024-103">В этом разделе описывается, как проводить резервное копирование и восстановление баз данных DQS.</span><span class="sxs-lookup"><span data-stu-id="ee024-103">This topic describes how to back up and restore the DQS databases.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ee024-104">Перед началом</span><span class="sxs-lookup"><span data-stu-id="ee024-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="ee024-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="ee024-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="ee024-106">Необходимо знать пароль для главного ключа базы данных, который вы указывали при установке сервера DQS.</span><span class="sxs-lookup"><span data-stu-id="ee024-106">You must know or remember the password for the database master key that you provided during the DQS server installation.</span></span>  
  
-   <span data-ttu-id="ee024-107">Убедитесь, что не существует текущих операций или процессов в DQS.</span><span class="sxs-lookup"><span data-stu-id="ee024-107">Ensure that there are no running activities or processes in DQS.</span></span> <span data-ttu-id="ee024-108">Это можно проверить с помощью экрана **Мониторинг активности** .</span><span class="sxs-lookup"><span data-stu-id="ee024-108">This can be verified using the **Activity Monitoring** screen.</span></span> <span data-ttu-id="ee024-109">Дополнительные сведения о работе с этим экраном см. в разделе [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span><span class="sxs-lookup"><span data-stu-id="ee024-109">For detailed information about working in this screen, see [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span></span>  
  
-   <span data-ttu-id="ee024-110">Убедитесь, что на сервере DQS нет подключенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="ee024-110">Ensure that there are no users logged on the DQS server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ee024-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="ee024-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ee024-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="ee024-112">Permissions</span></span>  
  
-   <span data-ttu-id="ee024-113">Для выполнения операций резервного копирования и восстановления учетная запись Windows должна быть членом предопределенной роли сервера sysadmin на этом экземпляре SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ee024-113">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance to perform the backup and restore operations.</span></span>  
  
-   <span data-ttu-id="ee024-114">Для завершения любых выполняемых операций или остановки каких-либо процессов в службах DQS необходимо быть членом роли dqs_administrator в базе данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="ee024-114">You must have the dqs_administrator role on the DQS_MAIN database to terminate any running activities or stop any running processes in DQS.</span></span>  
  
##  <a name="backup-and-restore-dqs-databases"></a><a name="BackupRestore"></a><span data-ttu-id="ee024-115">Резервное копирование и восстановление баз данных DQS</span><span class="sxs-lookup"><span data-stu-id="ee024-115">Backup and Restore DQS Databases</span></span>  
  
1.  <span data-ttu-id="ee024-116">Запустите среду Microsoft SQL Server Management Studio и подключитесь к соответствующему экземпляру SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ee024-116">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="ee024-117">В обозревателе объектов разверните узел **Базы данных** .</span><span class="sxs-lookup"><span data-stu-id="ee024-117">In Object Explorer, expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="ee024-118">Создайте резервную копию базы данных DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="ee024-118">Back up the DQS_STAGING_DATA database.</span></span> <span data-ttu-id="ee024-119">Пошаговые инструкции по резервному копированию базы данных SQL Server см. в разделе [Создание полной резервной копии базы данных &#40;SQL Server&#41;](../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ee024-119">For step-by-step instructions for backing a SQL Server database, see [Create a Full Database Backup &#40;SQL Server&#41;](../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="ee024-120">Создайте резервную копию базы данных DQS_PROJECTS.</span><span class="sxs-lookup"><span data-stu-id="ee024-120">Back up the DQS_PROJECTS database.</span></span>  
  
5.  <span data-ttu-id="ee024-121">Создайте резервную копию базы данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="ee024-121">Back up the DQS_MAIN database.</span></span>  
  
6.  <span data-ttu-id="ee024-122">Отключитесь от текущего экземпляра SQL Server и подключитесь к экземпляру SQL Server, на котором нужно восстановить эти базы данных.</span><span class="sxs-lookup"><span data-stu-id="ee024-122">Disconnect from the current instance of SQL Server, and connect to the SQL Server instance where you want to restore these databases.</span></span>  
  
7.  <span data-ttu-id="ee024-123">Восстановите базу данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="ee024-123">Restore DQS_MAIN database.</span></span> <span data-ttu-id="ee024-124">Пошаговые инструкции по восстановлению базы данных SQL Server см. в разделе [Восстановление резервной копии базы данных &#40;SQL Server Management Studio&#41;](../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="ee024-124">For step-by-step instructions to restore a SQL Server database, see [Restore a Database Backup &#40;SQL Server Management Studio&#41;](../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md).</span></span>  
  
8.  <span data-ttu-id="ee024-125">Восстановите базу данных DQS_PROJECTS.</span><span class="sxs-lookup"><span data-stu-id="ee024-125">Restore the DQS_PROJECTS database.</span></span>  
  
9. <span data-ttu-id="ee024-126">Восстановите базу данных DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="ee024-126">Restore the DQS_STAGING_DATA database.</span></span>  
  
10. <span data-ttu-id="ee024-127">В обозревателе объектов щелкните сервер правой кнопкой мыши и выберите команду **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="ee024-127">In Object Explorer, right-click the server, and then click **New Query**.</span></span>  
  
11. <span data-ttu-id="ee024-128">В окне редактора запросов скопируйте следующие инструкции SQL и замените *\<PASSWORD>* паролем, который вы указали при установке служб DQS для главного ключа базы данных:</span><span class="sxs-lookup"><span data-stu-id="ee024-128">In the Query Editor window, copy the following SQL statements, and replace *\<PASSWORD>* with the password that you provided during the DQS installation for the database master key:</span></span>  
  
    ```sql  
    USE [DQS_MAIN]  
    GO  
    EXECUTE [internal_core].[RestoreDQDatabases] '<PASSWORD>'  
    GO  
    ```  
  
12. <span data-ttu-id="ee024-129">Нажмите клавишу F5, чтобы выполнить инструкции.</span><span class="sxs-lookup"><span data-stu-id="ee024-129">Press F5 to execute the statements.</span></span> <span data-ttu-id="ee024-130">Откройте область **Результаты** , чтобы удостовериться в успешном выполнении инструкций.</span><span class="sxs-lookup"><span data-stu-id="ee024-130">Check the **Results** pane to verify that the statements have executed successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee024-131">См. также</span><span class="sxs-lookup"><span data-stu-id="ee024-131">See Also</span></span>  
 [<span data-ttu-id="ee024-132">Manage DQS Databases</span><span class="sxs-lookup"><span data-stu-id="ee024-132">Manage DQS Databases</span></span>](../../2014/data-quality-services/manage-dqs-databases.md)  
  
  
