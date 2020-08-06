---
title: Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- displaying backup content
- viewing backup content
- database backups [SQL Server], viewing content
- backing up databases [SQL Server], viewing content
- backing up databases [SQL Server], properties
- displaying backup properties
- backup devices [SQL Server], viewing information
- viewing backup properties
- database backups [SQL Server], properties
ms.assetid: 3a309074-e816-454d-b6c3-fcfdde0cbf74
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f2bdf41e3dbda079e3627ff7a7c1c3c78103b728
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734165"
---
# <a name="view-the-properties-and-contents-of-a-logical-backup-device-sql-server"></a><span data-ttu-id="5abc5-102">Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5abc5-102">View the Properties and Contents of a Logical Backup Device (SQL Server)</span></span>
  <span data-ttu-id="5abc5-103">В этом разделе описывается просмотр свойств и содержимого логического устройства резервного копирования в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5abc5-103">This topic describes how to view the properties and contents of a logical backup device in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5abc5-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="5abc5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5abc5-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="5abc5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5abc5-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="5abc5-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5abc5-107">**Просмотр свойств и содержимого логического устройства резервного копирования с помощью:**</span><span class="sxs-lookup"><span data-stu-id="5abc5-107">**To view the properties and contents of a logical backup device, using:**</span></span>  
  
     [<span data-ttu-id="5abc5-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5abc5-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5abc5-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5abc5-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5abc5-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="5abc5-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5abc5-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="5abc5-111">Security</span></span>  
 <span data-ttu-id="5abc5-112">Сведения о безопасности см. в статье [RESTORE LABELONLY (Transact-SQL)](/sql/t-sql/statements/restore-statements-labelonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5abc5-112">For information about security, see [RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5abc5-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="5abc5-113">Permissions</span></span>  
 <span data-ttu-id="5abc5-114">В [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] и более поздних версиях для получения сведений о резервном наборе данных или устройстве резервного копирования необходимо разрешение CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="5abc5-114">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, obtaining information about a backup set or backup device requires CREATE DATABASE permission.</span></span> <span data-ttu-id="5abc5-115">Дополнительные сведения см. в разделе [GRANT, предоставление разрешений для базы данных (Transact-SQL)](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5abc5-115">For more information, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5abc5-116">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5abc5-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-and-contents-of-a-logical-backup-device"></a><span data-ttu-id="5abc5-117">Просмотр свойств и содержимого логического устройства резервного копирования</span><span class="sxs-lookup"><span data-stu-id="5abc5-117">To view the properties and contents of a logical backup device</span></span>  
  
1.  <span data-ttu-id="5abc5-118">После подключения к соответствующему экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] в обозревателе объектов разверните дерево сервера, щелкнув его имя.</span><span class="sxs-lookup"><span data-stu-id="5abc5-118">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="5abc5-119">Разверните узел **Объекты сервера**, затем разверните узел **Устройства резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="5abc5-119">Expand **Server Objects**, and expand **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="5abc5-120">Щелкните иконку устройства и правой клавишей мыши щелкните элемент **Свойства**. В результате откроется диалоговое окно **Устройство резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="5abc5-120">Click the device and right-click **Properties**, which opens the **Backup Device** dialog box.</span></span>  
  
4.  <span data-ttu-id="5abc5-121">На странице **Общие** отображается имя устройства и место назначения — ленточное устройство или путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="5abc5-121">The **General** page displays the device name and destination, which is either a tape device or file path.</span></span>  
  
5.  <span data-ttu-id="5abc5-122">На панели **Выбор страницы** щелкните элемент **Содержимое носителя**.</span><span class="sxs-lookup"><span data-stu-id="5abc5-122">In the **Select a Page** pane, click **Media Contents**.</span></span>  
  
6.  <span data-ttu-id="5abc5-123">В правом окне отображаются следующие панели свойств.</span><span class="sxs-lookup"><span data-stu-id="5abc5-123">The right-hand pane displays in the following properties panels:</span></span>  
  
    -   <span data-ttu-id="5abc5-124">**Носитель**</span><span class="sxs-lookup"><span data-stu-id="5abc5-124">**Media**</span></span>  
  
         <span data-ttu-id="5abc5-125">Сведения о порядке носителей (порядковый номер носителя, порядковый номер семейства, идентификатор зеркального сервера, если таковой существует), а также дата и время создания носителя.</span><span class="sxs-lookup"><span data-stu-id="5abc5-125">Media sequence information (the media sequence number, the family sequence number, and the mirror identifier, if any) and the media creation date and time.</span></span>  
  
    -   <span data-ttu-id="5abc5-126">**Набор носителей**</span><span class="sxs-lookup"><span data-stu-id="5abc5-126">**Media set**</span></span>  
  
         <span data-ttu-id="5abc5-127">Сведения о наборе носителей: имя и описание набора носителей (если указано), а также число семейств в наборе носителей.</span><span class="sxs-lookup"><span data-stu-id="5abc5-127">Media set information: the media set name and description, if any, and the number of families in the media set.</span></span>  
  
7.  <span data-ttu-id="5abc5-128">Сетка **Резервные наборы данных** отображает сведения о содержимом данного набора носителей.</span><span class="sxs-lookup"><span data-stu-id="5abc5-128">The **Backup sets** grid displays information about the contents of the media set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5abc5-129">Дополнительные сведения см. в разделе [Страница "Содержимое носителя"](backup-device-media-contents-page.md).</span><span class="sxs-lookup"><span data-stu-id="5abc5-129">For more information, see [Media Contents Page](backup-device-media-contents-page.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5abc5-130">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5abc5-130">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-properties-and-contents-of-a-logical-backup-device"></a><span data-ttu-id="5abc5-131">Просмотр свойств и содержимого логического устройства резервного копирования</span><span class="sxs-lookup"><span data-stu-id="5abc5-131">To view the properties and contents of a logical backup device</span></span>  
  
1.  <span data-ttu-id="5abc5-132">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5abc5-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5abc5-133">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="5abc5-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5abc5-134">Используйте инструкцию [RESTORE LABELONLY](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="5abc5-134">Use the [RESTORE LABELONLY](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) statement.</span></span> <span data-ttu-id="5abc5-135">В этом примере возвращаются сведения о логическом устройстве резервного копирования `AdvWrks2008R2Backup` .</span><span class="sxs-lookup"><span data-stu-id="5abc5-135">This example returns information about the `AdvWrks2008R2Backup` logical backup device.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
RESTORE LABELONLY  
   FROM AdvWrks2008R2Backup ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="5abc5-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="5abc5-136">See Also</span></span>  
 <span data-ttu-id="5abc5-137">[backupfilegroup (Transact-SQL)](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5abc5-137">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="5abc5-138">[backupfile (Transact-SQL)](/sql/relational-databases/system-tables/backupfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5abc5-138">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span></span>  
 <span data-ttu-id="5abc5-139">[backupset (Transact-SQL)](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5abc5-139">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="5abc5-140">[backupmediaset (Transact-SQL)](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5abc5-140">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span></span>  
 <span data-ttu-id="5abc5-141">[backupmediafamily (Transact-SQL)](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5abc5-141">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span></span>  
 <span data-ttu-id="5abc5-142">[sp_addumpdevice (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5abc5-142">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 [<span data-ttu-id="5abc5-143">Устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5abc5-143">Backup Devices &#40;SQL Server&#41;</span></span>](backup-devices-sql-server.md)  
  
  
