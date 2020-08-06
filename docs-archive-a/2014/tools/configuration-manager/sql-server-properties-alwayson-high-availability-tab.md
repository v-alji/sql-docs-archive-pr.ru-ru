---
title: Свойства SQL Server (вкладка "высокий уровень доступности AlwaysOn") | Документация Майкрософт
description: Сведения о включении или отключении группы доступности AlwaysOn компонента в SQL Server 2014. Просмотрите предварительные требования, которые должны соответствовать экземпляру сервера для этой функции.
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: d8630923-a600-4f1c-aca1-027453a3ec82
author: mikeraymsft
ms.author: mikeray
ms.openlocfilehash: 3939b40a334746e9ee96441338e2e50791987103
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734826"
---
# <a name="sql-server-properties-alwayson-high-availability-tab"></a><span data-ttu-id="f46d7-104">Свойства SQL Server (вкладка «Высокий уровень доступности AlwaysOn»)</span><span class="sxs-lookup"><span data-stu-id="f46d7-104">SQL Server Properties (AlwaysOn High Availability Tab)</span></span>
  <span data-ttu-id="f46d7-105">На вкладке **Высокий уровень доступности AlwaysOn** в диалоговом окне **Свойства SQL Server** в диспетчере конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно включить или отключить функцию «Группы доступности AlwaysOn» в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f46d7-105">Use the **AlwaysOn High Availability** tab of the **SQL Server Properties** dialog box in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to enable or disable the AlwaysOn Availability Groups feature in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="f46d7-106">Включение функции «Группы доступности AlwaysOn» является предварительным требованием для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , чтобы группы доступности использовались в качестве решения высокого уровня доступности и аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="f46d7-106">Enabling AlwaysOn Availability Groups is a prerequisite for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use availability groups as a high availability and disaster recovery solution.</span></span>  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="f46d7-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f46d7-107">Prerequisites</span></span>  
 <span data-ttu-id="f46d7-108">Для включения функции «Группы доступности AlwaysOn» экземпляр должен соответствовать следующим предварительным условиям.</span><span class="sxs-lookup"><span data-stu-id="f46d7-108">To be enabled for AlwaysOn Availability Groups, a server instance must meet the following prerequisites:</span></span>  
  
-   <span data-ttu-id="f46d7-109">Экземпляр сервера должен находиться на узле отказоустойчивой кластеризации Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="f46d7-109">The server instance must reside on a Windows Server Failover Clustering (WSFC) node.</span></span>  
  
-   <span data-ttu-id="f46d7-110">Чтобы оказаться в одной и той же группе доступности, экземпляры должны входить в один и тот же кластер WSFC.</span><span class="sxs-lookup"><span data-stu-id="f46d7-110">To be in the same availability group, instances must be in the same WSFC cluster.</span></span> <span data-ttu-id="f46d7-111">Группа доступности не может пересекать границы кластера WSFC.</span><span class="sxs-lookup"><span data-stu-id="f46d7-111">An availability group cannot span WSFC clusters.</span></span>  
  
-   <span data-ttu-id="f46d7-112">Экземпляр сервера должен работать на выпуске [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который поддерживает [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f46d7-112">The server instance must be running an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that supports [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span></span>  
  
-   <span data-ttu-id="f46d7-113">Включайте функцию «Группы доступности AlwaysOn» только для одного экземпляра сервера в один момент времени.</span><span class="sxs-lookup"><span data-stu-id="f46d7-113">Enable AlwaysOn Availability Groups for only one server instance at a time.</span></span> <span data-ttu-id="f46d7-114">После включения функции «Группы доступности AlwaysOn» подождите, пока служба [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не перезапустится, и только после этого включайте следующий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="f46d7-114">After enabling AlwaysOn Availability Groups, wait until the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service has restarted before you enable the next server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f46d7-115">Сведения о поддержке компонентов и о других предварительных условиях, ограничениях и рекомендациях по [!INCLUDE[ssHADR](../../includes/sshadr-md.md)]см. в электронной документации по [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f46d7-115">For information about feature support and for information about additional prerequisites, restrictions, and recommendations for [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Books Online.</span></span>  
  
## <a name="dialog-options"></a><span data-ttu-id="f46d7-116">Параметры диалогового окна</span><span class="sxs-lookup"><span data-stu-id="f46d7-116">Dialog Options</span></span>  
 <span data-ttu-id="f46d7-117">**Имя отказоустойчивого кластера Windows**</span><span class="sxs-lookup"><span data-stu-id="f46d7-117">**Windows failover cluster name**</span></span>  
 <span data-ttu-id="f46d7-118">Отображает имя кластера WSFC, в котором локальный компьютер является узлом.</span><span class="sxs-lookup"><span data-stu-id="f46d7-118">Displays the name of the WSFC cluster in which the local computer is a node.</span></span>  
  
 <span data-ttu-id="f46d7-119">**Включить группы доступности AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="f46d7-119">**Enable AlwaysOn Availability Groups**</span></span>  
 <span data-ttu-id="f46d7-120">Этот флажок позволяет включить или выключить функцию «Группы доступности AlwaysOn» на данном экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f46d7-120">Use this check box to enable or disable AlwaysOn Availability Groups on this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], as follows:</span></span>  
  
-   <span data-ttu-id="f46d7-121">Если этот флажок пуст, то функция «Группы доступности AlwaysOn» в настоящее время отключена.</span><span class="sxs-lookup"><span data-stu-id="f46d7-121">If this check box is empty, AlwaysOn Availability Groups is currently disabled.</span></span> <span data-ttu-id="f46d7-122">Чтобы включить «Группы доступности AlwaysOn», выберите флажок, нажмите кнопку **ОК**и вручную перезапустите службу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f46d7-122">To enable AlwaysOn Availability Groups, select this check box, click **OK**, and manually restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
-   <span data-ttu-id="f46d7-123">Если этот флажок уже выбран, то функция «Группы доступности AlwaysOn» в настоящее время включена.</span><span class="sxs-lookup"><span data-stu-id="f46d7-123">If this check box is already selected, AlwaysOn Availability Groups is currently enabled.</span></span> <span data-ttu-id="f46d7-124">Чтобы отключить «Группы доступности AlwaysOn», снимите этот флажок и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f46d7-124">To disable AlwaysOn Availability Groups, uncheck the check box and click **OK**.</span></span> <span data-ttu-id="f46d7-125">Экземпляр сервера будет перезапущен автоматически.</span><span class="sxs-lookup"><span data-stu-id="f46d7-125">This causes the server instance to restart.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="f46d7-126">После отключения функции «Группы доступности AlwaysOn» необходимо удалить все локальные реплики доступности с экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="f46d7-126">After disabling AlwaysOn Availability Groups, you should remove any local availability replicas from the server instance.</span></span> <span data-ttu-id="f46d7-127">При удалении последней реплики для данной группы доступности будет также удалена и сама группа.</span><span class="sxs-lookup"><span data-stu-id="f46d7-127">If you remove the last replica of a given availability group, you should also remove the group.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="f46d7-128">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="f46d7-128">UI element list</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f46d7-129">Дополнительные сведения о действиях после отключения функции «Группы доступности AlwaysOn» и о том, как создать и настроить группы доступности, см. в электронной документации по [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f46d7-129">For more information about follow up after you disable AlwaysOn Availability Groups and for information about how to create and configure availability groups, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Books Online.</span></span>  
  
  
