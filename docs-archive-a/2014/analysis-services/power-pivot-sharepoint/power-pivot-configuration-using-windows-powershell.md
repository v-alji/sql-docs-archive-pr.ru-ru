---
title: Настройка PowerPivot с помощью Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 4d83e53e-04f1-417d-9039-d9e81ae0483d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 83b42da3e676a291bb021c02ee52e9a810207397
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667418"
---
# <a name="powerpivot-configuration-using-windows-powershell"></a><span data-ttu-id="71200-102">Настройка PowerPivot с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="71200-102">PowerPivot Configuration using Windows PowerShell</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="71200-103">включает в себя командлеты Windows PowerShell, которые можно использовать для настройки установки [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71200-103">includes Windows PowerShell cmdlets that you can use to configure an installation of [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)].</span></span> <span data-ttu-id="71200-104">Для полной настройки установки требуются командлеты и SharePoint, и PowerPivot для SharePoint.</span><span class="sxs-lookup"><span data-stu-id="71200-104">To fully configure an installation with PowerShell requires the use of both SharePoint cmdlets and PowerPivot for SharePoint cmdlets.</span></span> <span data-ttu-id="71200-105">Большую часть настройки можно выполнить с помощью одного из средств [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71200-105">A majority of configuration can be completed using one of the [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] tools.</span></span> <span data-ttu-id="71200-106">Дополнительные сведения об этих средствах см. в разделе [PowerPivot Configuration Tools](power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="71200-106">For more information on the tools, see [PowerPivot Configuration Tools](power-pivot-configuration-tools.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="71200-107">При работе с фермой SharePoint 2010 необходимо установить SharePoint 2010 с пакетом обновления 1 (SP1), чтобы иметь возможность настроить PowerPivot для SharePoint или ферму SharePoint 2010, в которой используется сервер базы данных [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71200-107">For a SharePoint 2010 farm, SharePoint 2010 SP1 must be installed before you can configure either PowerPivot for SharePoint, or a SharePoint farm that uses a [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] database server.</span></span> <span data-ttu-id="71200-108">Если пакет обновления еще не установлен, установите его, прежде чем начать настройку сервера.</span><span class="sxs-lookup"><span data-stu-id="71200-108">If you have not yet installed the service pack, install it before you begin configuring the server.</span></span>  
  
## <a name="benefits-of-configuring-powerpivot-for-sharepoint-using-powershell"></a><span data-ttu-id="71200-109">Преимущества настройки PowerPivot для SharePoint с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="71200-109">Benefits of Configuring PowerPivot for SharePoint Using PowerShell</span></span>  
 <span data-ttu-id="71200-110">Для автоматизации задач настройки можно построить файлы скриптов Windows PowerShell (PS1).</span><span class="sxs-lookup"><span data-stu-id="71200-110">You can build Windows PowerShell script (.ps1) files to automate configuration tasks.</span></span> <span data-ttu-id="71200-111">Этот подход рекомендуется, если необходимо обеспечить установку и настройку с помощью скриптов, которые можно выполнить на любом сервере.</span><span class="sxs-lookup"><span data-stu-id="71200-111">This approach is recommended if you require scripted installation and configuration steps that you can run on any server.</span></span> <span data-ttu-id="71200-112">В случае отказа аппаратной части подобный скрипт может потребоваться как часть плана аварийного восстановления сервера.</span><span class="sxs-lookup"><span data-stu-id="71200-112">You might require such a script as part of a disaster recovery plan for rebuilding a server in the event of a hardware failure.</span></span>  
  
## <a name="view-a-list-of-the-powerpivot-cmdlets-on-a-server"></a><span data-ttu-id="71200-113">Просмотр списка командлетов PowerPivot на сервере</span><span class="sxs-lookup"><span data-stu-id="71200-113">View a list of the PowerPivot Cmdlets on a Server</span></span>  
 <span data-ttu-id="71200-114">Чтобы просмотреть содержимое и примеры [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] командлетов, см. [Справочник по PowerShell для PowerPivot для SharePoint](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint).</span><span class="sxs-lookup"><span data-stu-id="71200-114">To see content and examples of the [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] cmdlets, see [PowerShell Reference for PowerPivot for SharePoint](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint).</span></span>  
  
 <span data-ttu-id="71200-115">Использование PowerShell для просмотра списка командлетов PowerPivot</span><span class="sxs-lookup"><span data-stu-id="71200-115">To use PowerShell to view a list of the PowerPivot cmdlets:</span></span>  
  
1.  <span data-ttu-id="71200-116">Откройте консоль управления SharePoint с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="71200-116">Open SharePoint Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="71200-117">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="71200-117">Enter the following command:</span></span>  
  
    ```powershell
    Get-Help *powerpivot*  
    ```  
  
     <span data-ttu-id="71200-118">Появится список командлетов, содержащих в имени «PowerPivot».</span><span class="sxs-lookup"><span data-stu-id="71200-118">You should see a list of cmdlets that include PowerPivot in the cmdlet name.</span></span> <span data-ttu-id="71200-119">Например, `Get-PowerPivotServiceApplication`.</span><span class="sxs-lookup"><span data-stu-id="71200-119">For example `Get-PowerPivotServiceApplication`.</span></span> <span data-ttu-id="71200-120">Число доступных командлетов зависит от используемой версии служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="71200-120">The number of cmdlets available depends on the version of Analysis Services you are using.</span></span>  
  
    -   <span data-ttu-id="71200-121">10 командлетов на сервере служб SQL Server 2012 Analysis Services с пакетом обновления 1 (SP1), работающим в режиме интеграции с SharePoint и SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="71200-121">10 cmdlets with SQL Server 2012 SP1 Analysis Services server configured in SharePoint mode, and SharePoint 2013.</span></span> <span data-ttu-id="71200-122">Версия 2012 с пакетом обновления 1 (SP1) использует новую архитектуру, которая позволяет серверу анализа данных работать за пределами фермы SharePoint и требует меньше командлетов управления Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71200-122">The 2012 SP1 version utilizes a new architecture that allows the Analysis Server to run outside the SharePoint farm and requires fewer management Windows PowerShell cmdlets.</span></span>  
  
    -   <span data-ttu-id="71200-123">17 командлетов на сервере служб Analysis Services SQL Server 2012, работающем в режиме интеграции с SharePoint и SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="71200-123">17 cmdlets with SQL Server 2012 Analysis Services server configured in SharePoint mode, and SharePoint 2010.</span></span>  
  
     <span data-ttu-id="71200-124">Если в списке не возвращено ни одной команды или появляется сообщение об ошибке, похожее на " `get-help could not find *powerpivot* in a help file in this session.` ", см. сведения о том, как включить командлеты PowerPivot на сервере в следующем разделе этого раздела.</span><span class="sxs-lookup"><span data-stu-id="71200-124">If no commands are returned in the list or you see an error message similar to "`get-help could not find *powerpivot* in a help file in this session.`", see the next section in this topic for instructions on how to enable the PowerPivot cmdlets on the server.</span></span>  
  
     <span data-ttu-id="71200-125">Для всех командлетов имеется справка в Интернете.</span><span class="sxs-lookup"><span data-stu-id="71200-125">All cmdlets have online help.</span></span> <span data-ttu-id="71200-126">В следующем примере показано, как посмотреть справку в Интернете для командлета `New-PowerPivotServiceApplication`.</span><span class="sxs-lookup"><span data-stu-id="71200-126">The following example shows how to view the online help for the `New-PowerPivotServiceApplication` cmdlet:</span></span>  
  
    ```powershell
    Get-Help new-powerpivotserviceapplication -Full  
    ```  
  
     <span data-ttu-id="71200-127">Кроме того, чтобы просмотреть только примеры, используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="71200-127">Alternatively, to view just the examples, use the following syntax:</span></span>  
  
    ```powershell
    Get-Help new-powerpivotserviceapplication -Example  
    ```  
  
## <a name="enable-powerpivot-cmdlets-on-a-server"></a><span data-ttu-id="71200-128">Включение командлетов PowerPivot на сервере</span><span class="sxs-lookup"><span data-stu-id="71200-128">Enable PowerPivot Cmdlets on a Server</span></span>  
 <span data-ttu-id="71200-129">Командлеты PowerPivot доступны после установки PowerPivot для SharePoint и развертывания решения фермы.</span><span class="sxs-lookup"><span data-stu-id="71200-129">PowerPivot cmdlets are available after you install PowerPivot for SharePoint and deploy the farm solution.</span></span> <span data-ttu-id="71200-130">Решения развертываются при запуске средства настройки PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="71200-130">The solutions are deployed when you ran the PowerPivot Configuration tool.</span></span> <span data-ttu-id="71200-131">Выполните следующие действия, чтобы включить использование командлетов.</span><span class="sxs-lookup"><span data-stu-id="71200-131">Follow these steps to enable the use of cmdlets:</span></span>  
  
1.  <span data-ttu-id="71200-132">Откройте консоль управления SharePoint с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="71200-132">Open SharePoint Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="71200-133">Запустите первый командлет.</span><span class="sxs-lookup"><span data-stu-id="71200-133">Run the first cmdlet:</span></span>  
  
    ```powershell
    Add-SPSolution -LiteralPath "C:\Program Files\Microsoft SQL Server\110\Tools\PowerPivotTools\ConfigurationTool\Resources\PowerPivotFarm.wsp"  
    ```  
  
     <span data-ttu-id="71200-134">Командлет возвратит имя решения, его идентификатор, а также атрибут Deployed=False.</span><span class="sxs-lookup"><span data-stu-id="71200-134">The cmdlet returns the name of the solution, its solution ID, and Deployed=False.</span></span> <span data-ttu-id="71200-135">На следующем шаге будет выполнено развертывание решения.</span><span class="sxs-lookup"><span data-stu-id="71200-135">In the next step, you deploy the solution.</span></span>  
  
3.  <span data-ttu-id="71200-136">Выполните второй командлет, чтобы развернуть решение.</span><span class="sxs-lookup"><span data-stu-id="71200-136">Run the second cmdlet to deploy the solution:</span></span>  
  
    ```powershell
    Install-SPSolution -Identity PowerPivotFarm.wsp -GACDeployment -Force  
    ```  
  
4.  <span data-ttu-id="71200-137">Закройте окно.</span><span class="sxs-lookup"><span data-stu-id="71200-137">Close the window.</span></span> <span data-ttu-id="71200-138">Откройте его снова с помощью варианта **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="71200-138">Reopen it, again using the **Run as Administrator** option.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="71200-139">См. также</span><span class="sxs-lookup"><span data-stu-id="71200-139">Related Content</span></span>  
 [<span data-ttu-id="71200-140">Настройка и администрирование сервера PowerPivot в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="71200-140">PowerPivot Server Administration and Configuration in Central Administration</span></span>](power-pivot-server-administration-and-configuration-in-central-administration.md)  
  
 [<span data-ttu-id="71200-141">PowerPivot Configuration Tools</span><span class="sxs-lookup"><span data-stu-id="71200-141">PowerPivot Configuration Tools</span></span>](power-pivot-configuration-tools.md)  
  
 [<span data-ttu-id="71200-142">Справочник по PowerShell для PowerPivot для SharePoint</span><span class="sxs-lookup"><span data-stu-id="71200-142">PowerShell Reference for PowerPivot for SharePoint</span></span>](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint)  
