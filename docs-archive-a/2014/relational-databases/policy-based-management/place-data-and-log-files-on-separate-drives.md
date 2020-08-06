---
title: Размещение файлов данных и файлов журнала на различных дисках | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 6cbedc27-4d77-44ad-bed2-c23b628475a7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d3f972ea29322a046c09657e2ed2499655c82aed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665987"
---
# <a name="place-data-and-log-files-on-separate-drives"></a><span data-ttu-id="4477e-102">Размещение файлов данных и файлов журнала на различных дисках</span><span class="sxs-lookup"><span data-stu-id="4477e-102">Place Data and Log Files on Separate Drives</span></span>
  <span data-ttu-id="4477e-103">Это правило проверяет, размещаются ли файлы данных и файлы журнала на разных логических дисках.</span><span class="sxs-lookup"><span data-stu-id="4477e-103">This rule checks whether data and log files are placed on separate logical drives.</span></span> <span data-ttu-id="4477e-104">Размещение файлов данных и файлов журнала на одном устройстве может привести к состязанию, что вызовет снижение производительности.</span><span class="sxs-lookup"><span data-stu-id="4477e-104">Placing both data and log files on the same device can cause contention for that device and result in poor performance.</span></span> <span data-ttu-id="4477e-105">Размещение файлов на разных дисках позволяет выполнять операции ввода-вывода для файлов данных и файлов журнала параллельно.</span><span class="sxs-lookup"><span data-stu-id="4477e-105">Placing the files on separate drives allows the I/O activity to occur at the same time for both the data and log files.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="4477e-106">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="4477e-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="4477e-107">При создании новой базы данных укажите разные диски для данных и журналов.</span><span class="sxs-lookup"><span data-stu-id="4477e-107">When you create a new database, specify separate drives for the data and log.</span></span> <span data-ttu-id="4477e-108">Чтобы переместить файлы после создания базы данных, ее необходимо перевести в режим «вне сети».</span><span class="sxs-lookup"><span data-stu-id="4477e-108">To move files after the database is created, the database must be taken offline.</span></span> <span data-ttu-id="4477e-109">Переместите файлы одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="4477e-109">Move the files by using one of the following methods:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4477e-110">Эта политика не может обнаружить отдельные физические устройства посредством точек подключения</span><span class="sxs-lookup"><span data-stu-id="4477e-110">This policy cannot detect separate physical devices through mount points</span></span>  
  
-   <span data-ttu-id="4477e-111">Восстановите базу данных из резервной копии, выполнив инструкцию RESTORE DATABASE с параметром WITH MOVE.</span><span class="sxs-lookup"><span data-stu-id="4477e-111">Restore the database from backup by using the RESTORE DATABASE statement with the WITH MOVE option.</span></span>  
  
-   <span data-ttu-id="4477e-112">Отсоедините и заново присоедините базу данных, указав различные расположения для хранения данных и журнала.</span><span class="sxs-lookup"><span data-stu-id="4477e-112">Detach and then attach the database specifying separate locations for the data and log devices.</span></span>  
  
-   <span data-ttu-id="4477e-113">Укажите новое расположение, выполнив инструкцию ALTER DATABASE с параметром MODIFY FILE, а затем перезапустив экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4477e-113">Specify a new location by running the ALTER DATABASE statement with the MODIFY FILE option, and then restarting the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="4477e-114">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="4477e-114">For More Information</span></span>  
 [<span data-ttu-id="4477e-115">Перемещение файлов базы данных</span><span class="sxs-lookup"><span data-stu-id="4477e-115">Move Database Files</span></span>](../databases/move-database-files.md)  
  
 [<span data-ttu-id="4477e-116">Перемещение пользовательских баз данных</span><span class="sxs-lookup"><span data-stu-id="4477e-116">Move User Databases</span></span>](../databases/move-user-databases.md)  
  
 [<span data-ttu-id="4477e-117">Присоединение и отсоединение базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4477e-117">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../databases/database-detach-and-attach-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="4477e-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="4477e-118">See Also</span></span>  
 [<span data-ttu-id="4477e-119">Наблюдение с помощью управления на основе политик и принудительное применение рекомендаций с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="4477e-119">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
