---
title: Выполнение скриптов во время синхронизации (программирование репликации на языке Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- synchronization [SQL Server replication], scripts
- scripts [SQL Server replication], synchronization and
- sp_addscriptexec
ms.assetid: b58a0877-4e43-4fab-a281-24e6022d3fb1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4bc217ad160a0238cc4247600d65eb32f156071f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655614"
---
# <a name="execute-scripts-during-synchronization-replication-transact-sql-programming"></a><span data-ttu-id="27acc-102">выполнять скрипты во время синхронизации (программирование репликации на языке Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="27acc-102">Execute Scripts During Synchronization (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="27acc-103">Выполнение скрипта по требованию на подписчике поддерживается для репликации транзакций и публикации слиянием.</span><span class="sxs-lookup"><span data-stu-id="27acc-103">Replication supports on demand script execution for Subscribers to transactional and merge publications.</span></span> <span data-ttu-id="27acc-104">Эта функция осуществляет копирование скрипта в рабочий каталог репликации, а затем командой **sqlcmd** применяет скрипт на подписчике.</span><span class="sxs-lookup"><span data-stu-id="27acc-104">This functionality copies the script to the replication working directory and then uses **sqlcmd** to apply the script at the Subscriber.</span></span> <span data-ttu-id="27acc-105">По умолчанию при возникновении ошибки применения скрипта к подписке на публикацию транзакций работа агента распространителя будет остановлена.</span><span class="sxs-lookup"><span data-stu-id="27acc-105">By default, if there is a failure when applying the script for a subscription to a transactional publication, the Distribution Agent will stop.</span></span> <span data-ttu-id="27acc-106">Программным путем можно задать скрипт [!INCLUDE[tsql](../../includes/tsql-md.md)] , который будет выполняться с помощью хранимых процедур репликации.</span><span class="sxs-lookup"><span data-stu-id="27acc-106">You can specify a [!INCLUDE[tsql](../../includes/tsql-md.md)] script to execute programmatically using replication stored procedures.</span></span>  
  
### <a name="to-specify-a-script-to-run-for-all-subscribers-to-a-snapshot-transactional-or-merge-publication"></a><span data-ttu-id="27acc-107">Настройка скрипта для выполнения всеми подписчиками на публикацию моментальных снимков, транзакций или слиянием</span><span class="sxs-lookup"><span data-stu-id="27acc-107">To specify a script to run for all Subscribers to a snapshot, transactional or merge publication</span></span>  
  
1.  <span data-ttu-id="27acc-108">Создайте и протестируйте скрипт на языке [!INCLUDE[tsql](../../includes/tsql-md.md)] , который будет выполняться по запросу.</span><span class="sxs-lookup"><span data-stu-id="27acc-108">Compose and test the [!INCLUDE[tsql](../../includes/tsql-md.md)] script that will be executed on demand.</span></span>  
  
2.  <span data-ttu-id="27acc-109">Сохраните файл скрипта в папке, доступной для агента моментальных снимков публикации.</span><span class="sxs-lookup"><span data-stu-id="27acc-109">Save the script file to a location where it can be accessed by the Snapshot Agent for the publication.</span></span>  
  
3.  <span data-ttu-id="27acc-110">В издателе в базе данных публикации выполните процедуру [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="27acc-110">At the Publisher on the publication database, execute [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span></span> <span data-ttu-id="27acc-111">Укажите \*\* \@ публикацию**, имя файла скрипта с полным UNC-путем, созданным на шаге 2 для \*\* \@ scriptfile**, и одно из следующих значений для \*\* \@ skiperror\*\*:</span><span class="sxs-lookup"><span data-stu-id="27acc-111">Specify **\@publication**, the name of the script file with full UNC path created in step 2 for **\@scriptfile**, and one of the following values for **\@skiperror**:</span></span>  
  
    -   <span data-ttu-id="27acc-112">**0** — выполнение скрипта агентом в случае ошибки будет остановлено.</span><span class="sxs-lookup"><span data-stu-id="27acc-112">**0** - the agent will stop executing the script if an error is encountered.</span></span>  
  
    -   <span data-ttu-id="27acc-113">**1** — при возникновении ошибки агент делает запись в журнал и продолжает выполнение скрипта.</span><span class="sxs-lookup"><span data-stu-id="27acc-113">**1** - the agent will log errors and continue executing the script when errors are encountered.</span></span>  
  
4.  <span data-ttu-id="27acc-114">Указанный скрипт будет выполнен на всех подписчиках при следующем сеансе синхронизации подписки.</span><span class="sxs-lookup"><span data-stu-id="27acc-114">The specified script will be executed at each Subscriber when the agent next runs to synchronize the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27acc-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="27acc-115">See Also</span></span>  
 [<span data-ttu-id="27acc-116">Синхронизация данных</span><span class="sxs-lookup"><span data-stu-id="27acc-116">Synchronize Data</span></span>](synchronize-data.md)  
  
  
