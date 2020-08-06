---
title: Зашифрованные базы данных с группы доступности AlwaysOn (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Transparent Data Encryption, AlwaysOn Availability Groups
- TDE, AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 09eb6ebc-3051-4fff-86a5-93524507b1fc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 91e717a896634a7df5a96253c51207831f142cff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655961"
---
# <a name="encrypted-databases-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="ced09-102">Зашифрованные базы данных с группами доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ced09-102">Encrypted Databases with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="ced09-103">В этом разделе приведены сведения об использовании зашифрованных или недавно расшифрованных баз данных с использованием [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ced09-103">This topic contains information about the using currently encrypted or recently decrypted databases with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="ced09-104">**В этом разделе.**</span><span class="sxs-lookup"><span data-stu-id="ced09-104">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="ced09-105">Ограничения</span><span class="sxs-lookup"><span data-stu-id="ced09-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="ced09-106">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="ced09-106">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ced09-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="ced09-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ced09-108">Если база данных зашифрована или содержит ключ шифрования базы данных, то нельзя использовать [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] или [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] для добавления базы данных в группу доступности.</span><span class="sxs-lookup"><span data-stu-id="ced09-108">If a database is encrypted or even contains a Database Encryption Key (DEK), you cannot use the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] or [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] to add the database to an availability group.</span></span> <span data-ttu-id="ced09-109">Если зашифрованная база данных была расшифрована, то в резервных копиях ее журналов могут содержаться зашифрованные данные.</span><span class="sxs-lookup"><span data-stu-id="ced09-109">Even if an encrypted database has been decrypted, its log backups might contain encrypted data.</span></span> <span data-ttu-id="ced09-110">В этом случае выполнение полной начальной синхронизации данных в базе данных может завершиться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ced09-110">In this case, full initial data synchronization could fail on the database.</span></span> <span data-ttu-id="ced09-111">Причина этого заключается в том, что операции восстановления журнала может потребоваться сертификат, который был использован ключами шифрования базы данных, который в данный момент недоступен.</span><span class="sxs-lookup"><span data-stu-id="ced09-111">This is because the restore log operation might require the certificate that was used by the database encryption keys (DEKs), and that certificate might be unavailable.</span></span>  
  
     <span data-ttu-id="ced09-112">Чтобы сделать расшифрованную базу данных доступной для добавления в группу доступности с помощью мастера, выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="ced09-112">To make a decrypted database eligible to add to an availability group using the wizard:</span></span>  
  
    1.  <span data-ttu-id="ced09-113">Создайте резервную копию журнала базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="ced09-113">Create a log backup of the primary database.</span></span>  
  
    2.  <span data-ttu-id="ced09-114">Создайте полную резервную копию базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="ced09-114">Create a full database backup of the primary database.</span></span>  
  
    3.  <span data-ttu-id="ced09-115">Восстановите резервную копию базы данных на экземпляре сервера, на котором размещается вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="ced09-115">Restore the database backup on the server instance that hosts the secondary replica.</span></span>  
  
    4.  <span data-ttu-id="ced09-116">Создайте новую резервную копию журнала базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="ced09-116">Create a new log backup from primary database.</span></span>  
  
    5.  <span data-ttu-id="ced09-117">Восстановите эту резервную копию журнала в базе данных-получателе.</span><span class="sxs-lookup"><span data-stu-id="ced09-117">Restore this log backup on the secondary database.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ced09-118">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="ced09-118">Related Tasks</span></span>  
  
-   [<span data-ttu-id="ced09-119">Подготовка базы данных-получателя для присоединения к группе доступности вручную (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ced09-119">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="ced09-120">Использование мастера групп доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ced09-120">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="ced09-121">Использование мастера добавления базы данных в группу доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ced09-121">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="ced09-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="ced09-122">See Also</span></span>  
 <span data-ttu-id="ced09-123">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ced09-123">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="ced09-124">Прозрачное шифрование данных (TDE)</span><span class="sxs-lookup"><span data-stu-id="ced09-124">Transparent Data Encryption &#40;TDE&#41;</span></span>](../../../relational-databases/security/encryption/transparent-data-encryption.md)  
  
  
