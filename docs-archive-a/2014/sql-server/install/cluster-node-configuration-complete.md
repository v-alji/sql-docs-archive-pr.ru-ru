---
title: Конфигурация узла кластера (полная) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 64174d54-edee-49b8-9b43-039574bf2ca1
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cc1f8ce4574580746e20c478b23e40485c3e6ecc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659215"
---
# <a name="cluster-node-configuration-complete"></a><span data-ttu-id="d1e87-102">Настройка узла кластера (Полная)</span><span class="sxs-lookup"><span data-stu-id="d1e87-102">Cluster Node Configuration (Complete)</span></span>
  <span data-ttu-id="d1e87-103">Воспользуйтесь страницей «Настройка узла кластера (полная)», чтобы указать существующий экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который подготовлен для работы в кластере. Чтобы установить или обновить отказоустойчивый кластер [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , необходимо запустить программу установки на каждом узле кластера.</span><span class="sxs-lookup"><span data-stu-id="d1e87-103">Use the Cluster Node Configuration (Complete) page to specify an existing instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that has been prepared for clustering.To install or upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you must run the Setup program on each node of the failover cluster.</span></span> <span data-ttu-id="d1e87-104">Чтобы добавить узел в существующий отказоустойчивый кластер [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , необходимо запустить программу установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на узле, который добавляется в экземпляр отказоустойчивого кластера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d1e87-104">To add a node to an existing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you must run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup on the node that is to be added to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster instance.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d1e87-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="d1e87-105">Options</span></span>  
 <span data-ttu-id="d1e87-106">Из раскрывающегося списка:</span><span class="sxs-lookup"><span data-stu-id="d1e87-106">From the drop-down boxes:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="d1e87-107">имя экземпляра. Выберите имя экземпляра для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отказоустойчивого кластера.</span><span class="sxs-lookup"><span data-stu-id="d1e87-107">instance name - Select the instance name for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span>  
  
-   <span data-ttu-id="d1e87-108">Имя этого узла. это поле заполняется именем компьютера, на котором [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] запущена программа установки.</span><span class="sxs-lookup"><span data-stu-id="d1e87-108">Name of this node - This field is pre-populated with the computer name where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="d1e87-109">Сетевое имя отказоустойчивого кластера — это поле не заполняется заранее.</span><span class="sxs-lookup"><span data-stu-id="d1e87-109">Failover Cluster Network Name - This field is not pre-populated.</span></span> <span data-ttu-id="d1e87-110">Укажите сетевое имя для нового экземпляра отказоустойчивого кластера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d1e87-110">Specify the network name for the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster instance.</span></span> <span data-ttu-id="d1e87-111">Это имя, которое идентифицирует отказоустойчивый кластер в сети.</span><span class="sxs-lookup"><span data-stu-id="d1e87-111">This is the name that identifies the failover cluster instance on the network.</span></span>  
  
  
