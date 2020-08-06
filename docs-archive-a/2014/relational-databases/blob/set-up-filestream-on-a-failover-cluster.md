---
title: Настойка FILESTREAM в отказоустойчивом кластере | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], setting up on a failover cluster
ms.assetid: 6721f780-20b7-4109-8ddb-ac327310699e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 29541bbcfd323a85a3fa751f60904fd1a26e1199
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728362"
---
# <a name="set-up-filestream-on-a-failover-cluster"></a><span data-ttu-id="49f2a-102">Установка FILESTREAM в отказоустойчивом кластере</span><span class="sxs-lookup"><span data-stu-id="49f2a-102">Set Up FILESTREAM on a Failover Cluster</span></span>
  <span data-ttu-id="49f2a-103">В этом разделе описано включение FILESTREAM в отказоустойчивом кластере.</span><span class="sxs-lookup"><span data-stu-id="49f2a-103">This topic describes how to enable FILESTREAM on a failover cluster.</span></span> <span data-ttu-id="49f2a-104">Перед началом этой процедуры необходимо ознакомиться с принципами работы [отказоустойчивой кластеризации](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md) и включить FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="49f2a-104">Before you try this procedure, you should understand [failover clustering](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md) and have FILESTREAM enabled.</span></span> <span data-ttu-id="49f2a-105">Сведения о включении FILESTREAM см. в разделе [Включение и настройка FILESTREAM](enable-and-configure-filestream.md).</span><span class="sxs-lookup"><span data-stu-id="49f2a-105">For information about how to enable FILESTREAM, see [Enable and Configure FILESTREAM](enable-and-configure-filestream.md).</span></span>  
  
### <a name="to-set-up-filestream-on-a-failover-cluster"></a><span data-ttu-id="49f2a-106">Установка FILESTREAM в отказоустойчивом кластере</span><span class="sxs-lookup"><span data-stu-id="49f2a-106">To set up FILESTREAM on a failover cluster</span></span>  
  
1.  <span data-ttu-id="49f2a-107">Установите основной узел отказоустойчивого кластера.</span><span class="sxs-lookup"><span data-stu-id="49f2a-107">Set up the primary node for the failover cluster.</span></span>  
  
     <span data-ttu-id="49f2a-108">После завершения программы установки включите FILESTREAM на основном узле с помощью **диспетчера конфигурации SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="49f2a-108">After the setup finishes, enable FILESTREAM on the primary node by using **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="49f2a-109">Тем самым включаются параметры, требующие права доступа администратора Windows.</span><span class="sxs-lookup"><span data-stu-id="49f2a-109">This enables the settings that require Windows Admin privileges.</span></span> <span data-ttu-id="49f2a-110">Если нужен удаленный доступ, установите флажок **Разрешить удаленным клиентам потоковый доступ к данным FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="49f2a-110">If remote access is required, select **Allow remote clients to have streaming access to FILESTREAM data**.</span></span> <span data-ttu-id="49f2a-111">Этим создается кластерный ресурс общей папки.</span><span class="sxs-lookup"><span data-stu-id="49f2a-111">This will create a file-share cluster resource.</span></span>  
  
2.  <span data-ttu-id="49f2a-112">Установите пассивный узел.</span><span class="sxs-lookup"><span data-stu-id="49f2a-112">Set up a passive node.</span></span>  
  
     <span data-ttu-id="49f2a-113">После завершения программы установки включите FILESTREAM на пассивном узле с помощью **диспетчера конфигурации SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="49f2a-113">After the setup finishes, enable FILESTREAM on the passive node by using **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="49f2a-114">Имя указываемого **общего ресурса Windows** должно быть одинаковым для всех узлов кластера.</span><span class="sxs-lookup"><span data-stu-id="49f2a-114">The name that you specify for **Windows Share Name** must be the same across all nodes in the cluster.</span></span>  
  
3.  <span data-ttu-id="49f2a-115">Чтобы установить дополнительные пассивные узлы, повторите шаг 2.</span><span class="sxs-lookup"><span data-stu-id="49f2a-115">To add more passive nodes, repeat step 2.</span></span>  
  
4.  <span data-ttu-id="49f2a-116">После добавления всех узлов завершите процесс, выполнив хранимую процедуру sp_configure на каждом экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49f2a-116">After all the nodes are added, complete the process by executing the sp_configure stored procedure on each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="49f2a-117">Чтобы в любое время добавить и задействовать дополнительные узлы кластера, можно повторить шаги 2, 3 и 4.</span><span class="sxs-lookup"><span data-stu-id="49f2a-117">To add and enable additional nodes to the cluster at any time, you can repeat steps 2, 3, and 4.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49f2a-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="49f2a-118">See Also</span></span>  
 <span data-ttu-id="49f2a-119">[Параметры конфигурации сервера (SQL Server)](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="49f2a-119">[Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="49f2a-120">[Создание отказоустойчивого кластера SQL Server (программа установки)](../../sql-server/failover-clusters/install/create-a-new-sql-server-failover-cluster-setup.md) </span><span class="sxs-lookup"><span data-stu-id="49f2a-120">[Create a New SQL Server Failover Cluster &#40;Setup&#41;](../../sql-server/failover-clusters/install/create-a-new-sql-server-failover-cluster-setup.md) </span></span>  
 <span data-ttu-id="49f2a-121">[Удаление экземпляра отказоустойчивого кластера SQL Server (программа установки)](../../sql-server/failover-clusters/install/remove-a-sql-server-failover-cluster-instance-setup.md) </span><span class="sxs-lookup"><span data-stu-id="49f2a-121">[Remove a SQL Server Failover Cluster Instance &#40;Setup&#41;](../../sql-server/failover-clusters/install/remove-a-sql-server-failover-cluster-instance-setup.md) </span></span>  
 [<span data-ttu-id="49f2a-122">Добавление или удаление узлов отказоустойчивого кластера SQL Server (программа установки)</span><span class="sxs-lookup"><span data-stu-id="49f2a-122">Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;</span></span>](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md)  
  
  
