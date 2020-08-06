---
title: Настройка сжатия резервных копий (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 430905eb-d218-458c-bd48-aeee6fbb7446
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f70994eb64cb6a50b538fd87f03ce7ea2fafe857
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668936"
---
# <a name="configure-backup-compression-sql-server"></a><span data-ttu-id="b92cc-102">Настройка сжатия резервных копий (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b92cc-102">Configure Backup Compression (SQL Server)</span></span>
  <span data-ttu-id="b92cc-103">При установке сжатие резервных копий по умолчанию отключено.</span><span class="sxs-lookup"><span data-stu-id="b92cc-103">At installation, backup compression is off by default.</span></span> <span data-ttu-id="b92cc-104">По умолчанию способ сжатия резервных копий определяется параметром конфигурации **backup compression default** уровня сервера.</span><span class="sxs-lookup"><span data-stu-id="b92cc-104">The default behavior for backup compression is defined by the **backup compression default** Option server-level configuration option.</span></span> <span data-ttu-id="b92cc-105">Однако настройку по умолчанию на уровне сервера можно переопределить при создании отдельной резервной копии или во время планирования ряда регулярных операций резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="b92cc-105">However, you can override the server-level default when creating a single backup or scheduling a series of routine backups.</span></span> <span data-ttu-id="b92cc-106">Чтобы изменить это параметр, см. раздел [Параметр конфигурации сервера "Просмотр или настройка параметра сжатия резервных копий по умолчанию"](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="b92cc-106">To change the server-level default, see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>  
  
## <a name="override-the-backup-compression-default"></a><span data-ttu-id="b92cc-107">Переопределение сжатия резервных копий по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b92cc-107">Override the Backup Compression Default</span></span>  
 <span data-ttu-id="b92cc-108">Способ сжатия резервных копий вы можете изменить для отдельной резервной копии, задания резервного копирования или для конфигурации доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="b92cc-108">You can change the backup compression behavior for an individual backup, backup job, or log shipping configuration.</span></span>  
  
-   **[!INCLUDE[tsql](../../includes/tsql-md.md)]**  
  
     <span data-ttu-id="b92cc-109">Для переопределения сжатия резервных копий по умолчанию используйте параметр WITH NO_COMPRESSION или WITH COMPRESSION в инструкции [BACKUP](/sql/t-sql/statements/backup-transact-sql) в процессе создания резервной копии.</span><span class="sxs-lookup"><span data-stu-id="b92cc-109">To override the server backup-compression default when creating a backup, use either WITH NO_COMPRESSION or WITH COMPRESSION in you [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement.</span></span>  
  
     <span data-ttu-id="b92cc-110">Для конфигурации доставки журналов поведение сжатия резервных копий можно контролировать с помощью хранимой процедуры [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql)[sp_change_log_shipping_primary_database (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-change-log-shipping-primary-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b92cc-110">For a log shipping configuration, you can control the backup compression behavior of log backups by using [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql)[sp_change_log_shipping_primary_database &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-log-shipping-primary-database-transact-sql).</span></span>  
  
-   **[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**  
  
     <span data-ttu-id="b92cc-111">Сведения о просмотре или настройке параметра сжатия резервных копий по умолчанию для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в разделе [Параметр конфигурации сервера "Просмотр или настройка параметра сжатия резервных копий по умолчанию"](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="b92cc-111">For information about how to view or configure the backup compression default option for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>  
  
     <span data-ttu-id="b92cc-112">Можно переопределить сжатие резервных копий по умолчанию для сервера, выбрав **Сжимать резервные копии** или **Не сжимать резервные копии** в одном из следующих диалоговых окон:</span><span class="sxs-lookup"><span data-stu-id="b92cc-112">You can override the server backup-compression default when creating a backup by specifying **Compress backup** or **Do not compress backup** in any of the following dialog boxes:</span></span>  
  
    -   [<span data-ttu-id="b92cc-113">Резервное копирование базы данных (страница «Параметры»)</span><span class="sxs-lookup"><span data-stu-id="b92cc-113">Back Up Database (Options Page)</span></span>](back-up-database-backup-options-page.md)  
  
         <span data-ttu-id="b92cc-114">При резервном копировании базы данных можно управлять сжатием резервной копии для отдельной базы данных, файла или журнала.</span><span class="sxs-lookup"><span data-stu-id="b92cc-114">When backing up a database, you can control backup compression for an individual database, file, or log backup.</span></span>  
  
    -   [<span data-ttu-id="b92cc-115">Использование мастера планов обслуживания</span><span class="sxs-lookup"><span data-stu-id="b92cc-115">Use the Maintenance Plan Wizard</span></span>](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
         <span data-ttu-id="b92cc-116">Мастер планов обслуживания позволяет управлять сжатием резервных копий для каждого запланированного набора полных или разностных резервных копий базы данных или журнала.</span><span class="sxs-lookup"><span data-stu-id="b92cc-116">The Maintenance Plan Wizard enables you to control backup compression for each set full or differential database backups or log backups that you schedule.</span></span>  
  
    -   <span data-ttu-id="b92cc-117">Integration Services (SSIS) [Задача "Резервное копирование базы данных"](../../integration-services/control-flow/back-up-database-task.md)</span><span class="sxs-lookup"><span data-stu-id="b92cc-117">Integration Services (SSIS) [Back Up Database task](../../integration-services/control-flow/back-up-database-task.md)</span></span>  
  
         <span data-ttu-id="b92cc-118">Сжатием резервных копий можно управлять при создании пакета для резервного копирования отдельной базы данных или нескольких баз данных.</span><span class="sxs-lookup"><span data-stu-id="b92cc-118">You can control the backup compression behavior when creating a package for backing up a single database or multiple databases.</span></span>  
  
    -   [<span data-ttu-id="b92cc-119">Настройки резервного копирования журналов транзакций для доставки журналов</span><span class="sxs-lookup"><span data-stu-id="b92cc-119">Log Shipping Transaction Log Backup Settings</span></span>](../databases/log-shipping-transaction-log-backup-settings.md)  
  
         <span data-ttu-id="b92cc-120">Можно управлять поведением сжатия резервных копий журналов.</span><span class="sxs-lookup"><span data-stu-id="b92cc-120">You can control the backup compression behavior of log backups.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="b92cc-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="b92cc-121">See Also</span></span>  
 [<span data-ttu-id="b92cc-122">Сжатие резервных копий (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b92cc-122">Backup Compression &#40;SQL Server&#41;</span></span>](backup-compression-sql-server.md)  
  
  
