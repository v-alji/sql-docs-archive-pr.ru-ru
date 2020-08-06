---
title: Компоненты SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Upgrade Advisor, components
- listing components to analyze
- Upgrade Advisor [SQL Server], components
- component analysis [Upgrade Advisor]
- finding components to analyze
- locating components to analyze
- detecting components to analyze
- server names [Upgrade Advisor]
- analyzing system [Upgrade Advisor], component list
- identifying components to analyze
ms.assetid: 539b9525-ce3f-4950-9146-5527a5a297ee
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 95fe39ce8e616b238cf7c70763e7cf1819341f16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751679"
---
# <a name="sql-server-components"></a><span data-ttu-id="4af9d-102">Компоненты SQL Server</span><span class="sxs-lookup"><span data-stu-id="4af9d-102">SQL Server Components</span></span>
  <span data-ttu-id="4af9d-103">Мастер анализа помощника по обновлению можно запустить на локальном или удаленном компьютере, на котором [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] установлен,, [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] или [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4af9d-103">You can run the Upgrade Advisor Analysis Wizard against a local or remote computer that has [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] installed.</span></span> <span data-ttu-id="4af9d-104">Первый шаг анализа, предшествующего обновлению, — определение компьютера и компонентов, подлежащих анализу.</span><span class="sxs-lookup"><span data-stu-id="4af9d-104">The first step in the pre-upgrade analysis is to identify the computer and components for analysis.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4af9d-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="4af9d-105">Options</span></span>  
 <span data-ttu-id="4af9d-106">**Имя компьютера**</span><span class="sxs-lookup"><span data-stu-id="4af9d-106">**Computer name**</span></span>  
 <span data-ttu-id="4af9d-107">Задает имя компьютера для проведения анализа.</span><span class="sxs-lookup"><span data-stu-id="4af9d-107">Specifies the name of the computer to analyze.</span></span> <span data-ttu-id="4af9d-108">Советник по переходу заполняет поле **имя сервера** именем локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="4af9d-108">Upgrade Advisor populates the **Server name** box with the local computer name.</span></span> <span data-ttu-id="4af9d-109">Для подключения к локальному компьютеру можно также использовать обозначения «.» и «localhost».</span><span class="sxs-lookup"><span data-stu-id="4af9d-109">You can also use "." and "localhost" to connect to the local computer.</span></span>  
  
 <span data-ttu-id="4af9d-110">Для анализа другого компьютера используются следующие правила.</span><span class="sxs-lookup"><span data-stu-id="4af9d-110">To analyze a different computer, use the following guidelines:</span></span>  
  
-   <span data-ttu-id="4af9d-111">Чтобы проверить некластеризованные экземпляры, введите имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="4af9d-111">To scan nonclustered instances, enter the computer name.</span></span>  
  
-   <span data-ttu-id="4af9d-112">Чтобы просмотреть кластеризованные экземпляры, введите имя экземпляра отказоустойчивого кластера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4af9d-112">To scan clustered instances, enter the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster instance.</span></span>  
  
-   <span data-ttu-id="4af9d-113">Чтобы проверить некластеризованные компоненты, установленные на узле кластера, введите имя компьютера для узла отказоустойчивого кластера.</span><span class="sxs-lookup"><span data-stu-id="4af9d-113">To scan nonclustered components that are installed on a node of a cluster, enter the computer name of the failover cluster node.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="4af9d-114">Не включайте в него имя экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4af9d-114">Do not include the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name.</span></span>  
  
 <span data-ttu-id="4af9d-115">Вместо имени компьютера можно указать его IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="4af9d-115">Instead of specifying the computer name, you can specify the IP address.</span></span>  
  
 <span data-ttu-id="4af9d-116">При просмотре служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] следует указать имя локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="4af9d-116">If scanning [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must specify the name of the local computer.</span></span> <span data-ttu-id="4af9d-117">Помощник по обновлению просматривает только локальные серверы отчетов.</span><span class="sxs-lookup"><span data-stu-id="4af9d-117">Upgrade Advisor scans local report servers only.</span></span>  
  
 <span data-ttu-id="4af9d-118">**Detect**</span><span class="sxs-lookup"><span data-stu-id="4af9d-118">**Detect**</span></span>  
 <span data-ttu-id="4af9d-119">Кнопка " **обнаружить** " обращается к указанному компьютеру и обнаруживает анализируемые компоненты:</span><span class="sxs-lookup"><span data-stu-id="4af9d-119">The **Detect** button accesses the specified computer and detects components to analyze:</span></span>  
  
-   <span data-ttu-id="4af9d-120">Если выполняется анализ экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на удаленном компьютере, на этом компьютере необходимо включить службы удаленного реестра.</span><span class="sxs-lookup"><span data-stu-id="4af9d-120">If you are analyzing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance on a remote computer, you must enable the remote registry services on the remote computer.</span></span>  
  
-   <span data-ttu-id="4af9d-121">Экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] будет обнаружен в том случае, если в реестре компьютера найден экземпляр [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] или [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4af9d-121">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is detected if an instance of [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] is found in the computer's registry.</span></span>  
  
-   <span data-ttu-id="4af9d-122">Службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] обнаруживаются по наличию данных экземпляра служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в реестре компьютера.</span><span class="sxs-lookup"><span data-stu-id="4af9d-122">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is detected if an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is found in the computer's registry.</span></span>  
  
-   <span data-ttu-id="4af9d-123">Службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] будут обнаружены, если в реестре компьютера найдены службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4af9d-123">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is detected if [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is found in the computer's registry.</span></span> <span data-ttu-id="4af9d-124">Однако помощник по обновлению просматривает только локальные серверы отчетов.</span><span class="sxs-lookup"><span data-stu-id="4af9d-124">However, Upgrade Advisor scans local report servers only.</span></span>  
  
 <span data-ttu-id="4af9d-125">**Components**</span><span class="sxs-lookup"><span data-stu-id="4af9d-125">**Components**</span></span>  
 <span data-ttu-id="4af9d-126">Выберите компоненты, подлежащие анализу.</span><span class="sxs-lookup"><span data-stu-id="4af9d-126">Select the components to analyze.</span></span> <span data-ttu-id="4af9d-127">Можно нажать кнопку **обнаружения** , чтобы выбрать все компоненты, установленные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4af9d-127">You can click the **Detect** button to select all the components installed on the computer.</span></span> <span data-ttu-id="4af9d-128">Рядом с компонентами, найденными на данном компьютере, будет установлен флажок.</span><span class="sxs-lookup"><span data-stu-id="4af9d-128">A check mark will appear next to the components that are detected as installed on the computer.</span></span> <span data-ttu-id="4af9d-129">Можно также выбрать компоненты вручную, установив или сняв флажок рядом с каждым компонентом.</span><span class="sxs-lookup"><span data-stu-id="4af9d-129">You can also manually select the components to analyze by selecting or clearing the check box next to each component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af9d-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="4af9d-130">See Also</span></span>  
 <span data-ttu-id="4af9d-131">[Работа с советником по переходу](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="4af9d-131">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="4af9d-132">Справочник по пользовательскому интерфейсу помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="4af9d-132">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
