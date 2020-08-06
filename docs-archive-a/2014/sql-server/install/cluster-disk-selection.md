---
title: Выбор диска кластера | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- cluster disk selection
ms.assetid: 0d6b863d-5972-4a20-9990-64ee8016fea6
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0f53d6d3f623254d2b17996be7fd5b8235dca223
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659219"
---
# <a name="cluster-disk-selection"></a><span data-ttu-id="8468b-102">Выбор диска кластера</span><span class="sxs-lookup"><span data-stu-id="8468b-102">Cluster Disk Selection</span></span>
  <span data-ttu-id="8468b-103">Страница **Выбор диска кластера** мастера установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используется для выбора диска кластера как общего ресурса для отказоустойчивого кластера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8468b-103">Use the **Cluster Disk Selection** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to select the shared cluster disk resource for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span> <span data-ttu-id="8468b-104">Данные [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] будут размещены на этом диске кластера.</span><span class="sxs-lookup"><span data-stu-id="8468b-104">The cluster disk is where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data will be placed.</span></span>  
  
 <span data-ttu-id="8468b-105">Общий диск кластера не является обязательным для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] установки кластера.</span><span class="sxs-lookup"><span data-stu-id="8468b-105">A shared cluster disk is not a requirement for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] cluster installations.</span></span> <span data-ttu-id="8468b-106">Файловый сервер SMB является поддерживаемым хранилищем для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] установок отказоустойчивого кластера, и его можно указать с помощью страницы **ядро СУБД-Data Directories** перед завершением установки.</span><span class="sxs-lookup"><span data-stu-id="8468b-106">An SMB file server is a supported storage for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] failover cluster installations, and can be specified by using the **Database Engine - Data Directories** page before completing the installation.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="8468b-107">Если для установки были выбраны службы Analysis Services, необходимо указать общий диск кластера.</span><span class="sxs-lookup"><span data-stu-id="8468b-107">If you have selected Analysis Services to be installed, you must specify a shared cluster disk.</span></span>  
>   
>  <span data-ttu-id="8468b-108">Если на этом экземпляре отказоустойчивого кластера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] планируется включить параметр FILESTREAM, необходимо указать общий диск кластера.</span><span class="sxs-lookup"><span data-stu-id="8468b-108">If you plan to enable FILESTREAM on this [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster instance, you must specify a shared cluster disk.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8468b-109">Варианты</span><span class="sxs-lookup"><span data-stu-id="8468b-109">Options</span></span>  
 <span data-ttu-id="8468b-110">**Общие диски**</span><span class="sxs-lookup"><span data-stu-id="8468b-110">**Shared Disks**</span></span>  
 <span data-ttu-id="8468b-111">Выбирает диск из списка.</span><span class="sxs-lookup"><span data-stu-id="8468b-111">Select a single disk from the list.</span></span> <span data-ttu-id="8468b-112">Данные [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] будут размещены на этом диске кластера.</span><span class="sxs-lookup"><span data-stu-id="8468b-112">The cluster disk is where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data will be placed.</span></span>  
  
 <span data-ttu-id="8468b-113">Можно указать только один диск.</span><span class="sxs-lookup"><span data-stu-id="8468b-113">Only one disk can be specified.</span></span> <span data-ttu-id="8468b-114">Если выбрать группу, содержащую ресурс кластерного кворума, выводится предупреждение.</span><span class="sxs-lookup"><span data-stu-id="8468b-114">If you select the group containing the cluster quorum resource, a warning will be displayed.</span></span> <span data-ttu-id="8468b-115">Рекомендуется не выполнять установку на ресурс кластерного кворума.</span><span class="sxs-lookup"><span data-stu-id="8468b-115">We recommend that you do not install to the cluster quorum resource.</span></span>  
  
 <span data-ttu-id="8468b-116">**Доступные общие диски**</span><span class="sxs-lookup"><span data-stu-id="8468b-116">**Available Shared Disks**</span></span>  
 <span data-ttu-id="8468b-117">Отображает список доступных дисков, указывает, определен ли отдельный диск как общий, и выводит описание дискового ресурса.</span><span class="sxs-lookup"><span data-stu-id="8468b-117">Displays a list of available disks, whether each is qualified as a shared disk, and a description of each disk resource.</span></span>  
  
  
