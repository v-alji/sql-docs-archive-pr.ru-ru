---
title: Развертывание решений PowerPivot в SharePoint | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f202a2b7-34e0-43aa-90d5-c9a085a37c32
author: minewiskan
ms.author: owend
ms.openlocfilehash: 043647988598f932b70cc06e6bb5492d66864372
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666231"
---
# <a name="deploy-powerpivot-solutions-to-sharepoint"></a><span data-ttu-id="9188c-102">Развертывание решений PowerPivot в SharePoint</span><span class="sxs-lookup"><span data-stu-id="9188c-102">Deploy PowerPivot Solutions to SharePoint</span></span>
  <span data-ttu-id="9188c-103">Используйте следующие инструкции для выполнения вручную развертывания двух пакетов решений, добавляющих функции PowerPivot в среде SharePoint Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9188c-103">Use the following instructions to manually deploy two solution packages that add PowerPivot features to a SharePoint Server 2010 environment.</span></span> <span data-ttu-id="9188c-104">Развертывание решений — это обязательный шаг настройки PowerPivot для SharePoint на сервере SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="9188c-104">Deploying the solutions is a required step for configuring PowerPivot for SharePoint on a SharePoint 2010 server.</span></span> <span data-ttu-id="9188c-105">Полный список необходимых шагов см. [в разделе Администрирование и настройка сервера PowerPivot в центре администрирования](power-pivot-server-administration-and-configuration-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="9188c-105">To view the complete list of required steps, see [PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md).</span></span>  
  
 <span data-ttu-id="9188c-106">Кроме того, для развертывания решений можно использовать средство настройки PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9188c-106">Alternatively, you can use the PowerPivot Configuration Tool to deploy the solutions.</span></span> <span data-ttu-id="9188c-107">При установке одиночного сервера проще и удобнее использовать средство настройки, однако если вы предпочитаете знакомое средство или если требуется настроить несколько компонентов одновременно, то лучше пользоваться центром администрирования и PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9188c-107">Using the configuration tool is easier and more efficient for a single server installation, but you might want to use Central Administration and PowerShell if you prefer using a familiar tool or if you are configuring multiple features at the same time.</span></span> <span data-ttu-id="9188c-108">Дополнительные сведения об использовании средства настройки см. в разделе [PowerPivot средства настройки](power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9188c-108">For more information about using the configuration tool, see [PowerPivot Configuration Tools](power-pivot-configuration-tools.md).</span></span>  
  
 <span data-ttu-id="9188c-109">Перед развертыванием решения необходимо установить PowerPivot для SharePoint с установочного носителя SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="9188c-109">Before deploying the solutions, you must first install PowerPivot for SharePoint using the SQL Server 2012 installation media.</span></span> <span data-ttu-id="9188c-110">Программа установки SQL Server устанавливает пакеты решения, которое вы собираетесь развертывать.</span><span class="sxs-lookup"><span data-stu-id="9188c-110">SQL Server Setup installs the solution packages that you are about to deploy.</span></span>  
  
 <span data-ttu-id="9188c-111">Этот раздел состоит из следующих подразделов.</span><span class="sxs-lookup"><span data-stu-id="9188c-111">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="9188c-112">Необходимое условие: Убедитесь, что веб-приложение использует классический режим проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="9188c-112">Prerequisite: Verify the Web Application uses Classic Mode Authentication</span></span>](#bkmk_classic)  
  
 [<span data-ttu-id="9188c-113">Шаг 1. Развертывание решения фермы</span><span class="sxs-lookup"><span data-stu-id="9188c-113">Step 1: Deploy the Farm Solution</span></span>](#bkmk_farm)  
  
 [<span data-ttu-id="9188c-114">Шаг 2. Развертывание решения веб-приложения PowerPivot в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="9188c-114">Step 2: Deploy the PowerPivot Web Application Solution to Central Administration</span></span>](#deployCA)  
  
 [<span data-ttu-id="9188c-115">Шаг 3. Развертывание решения веб-приложения PowerPivot для других веб-приложений</span><span class="sxs-lookup"><span data-stu-id="9188c-115">Step 3: Deploy the PowerPivot Web Application Solution to Other Web Applications</span></span>](#deployUI)  
  
 [<span data-ttu-id="9188c-116">Повторное развертывание или отзыв решения</span><span class="sxs-lookup"><span data-stu-id="9188c-116">Redeploy or retract the Solution</span></span>](#retract)  
  
 [<span data-ttu-id="9188c-117">О решениях PowerPivot</span><span class="sxs-lookup"><span data-stu-id="9188c-117">About the PowerPivot Solutions</span></span>](#intro)  
  
##  <a name="prerequisite-verify-the-web-application-uses-classic-mode-authentication"></a><a name="bkmk_classic"></a> <span data-ttu-id="9188c-118">Обязательное условие: убедитесь, что в веб-приложении используется классический режим проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="9188c-118">Prerequisite: Verify the Web Application uses Classic Mode Authentication</span></span>  
 <span data-ttu-id="9188c-119">PowerPivot для SharePoint поддерживается только в тех веб-приложениях, которые используют классическую проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="9188c-119">PowerPivot for SharePoint is only supported for web applications that use Windows-classic mode authentication.</span></span> <span data-ttu-id="9188c-120">Чтобы проверить, использует ли приложение классический режим, выполните следующий командлет PowerShell из **командной консоли sharepoint 2010**, заменив `http://<top-level site name>` именем своего сайта SharePoint:</span><span class="sxs-lookup"><span data-stu-id="9188c-120">To check whether the application uses Classic mode, run the following PowerShell cmdlet from the **SharePoint 2010 Management Shell**, replacing `http://<top-level site name>` with the name of your SharePoint site:</span></span>  
  
```powershell
Get-SPWebApplication http://<top-level site name> | Format-List UseClaimsAuthentication  
```  
  
 <span data-ttu-id="9188c-121">Должно быть возвращено значение **false**.</span><span class="sxs-lookup"><span data-stu-id="9188c-121">The return value should be **false**.</span></span> <span data-ttu-id="9188c-122">Если **это так, вы**не сможете получить доступ к данным PowerPivot с помощью этого веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="9188c-122">If it is **true**, you cannot access PowerPivot data with this web application.</span></span>  
  
##  <a name="step-1-deploy-the-farm-solution"></a><a name="bkmk_farm"></a><span data-ttu-id="9188c-123">Шаг 1. Развертывание решения фермы</span><span class="sxs-lookup"><span data-stu-id="9188c-123">Step 1: Deploy the Farm Solution</span></span>  
 <span data-ttu-id="9188c-124">В этом разделе показано, как развертывать решения с помощью PowerShell, но для этой задачи можно использовать и средство PowerPivot Configuration Tool.</span><span class="sxs-lookup"><span data-stu-id="9188c-124">This section shows you how to deploy solutions using PowerShell, but you can also use the PowerPivot Configuration Tool to complete this task.</span></span> <span data-ttu-id="9188c-125">Дополнительные сведения см. в разделе [Настройка или восстановление PowerPivot для SharePoint 2010 &#40;средства настройки PowerPivot&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="9188c-125">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span></span>  
  
 <span data-ttu-id="9188c-126">Эта задача выполняется один раз после установки PowerPivot для SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9188c-126">This task only needs to be performed once, after you install PowerPivot for SharePoint.</span></span>  
  
1.  <span data-ttu-id="9188c-127">На сервере с установленным PowerPivot для SharePoint откройте консоль управления SharePoint 2010 с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="9188c-127">On a server that has an installation of PowerPivot for SharePoint, open a SharePoint 2010 Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="9188c-128">Для добавления решения фермы выполните следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="9188c-128">Run the following cmdlet to add the farm solution.</span></span>  
  
    ```powershell
    Add-SPSolution -LiteralPath "C:\Program Files\Microsoft SQL Server\110\Tools\PowerPivotTools\ConfigurationTool\Resources\PowerPivotFarm.wsp"  
    ```  
  
     <span data-ttu-id="9188c-129">Командлет возвратит имя решения, его идентификатор, а также атрибут Deployed=False.</span><span class="sxs-lookup"><span data-stu-id="9188c-129">The cmdlet returns the name of the solution, its solution ID, and Deployed=False.</span></span> <span data-ttu-id="9188c-130">На следующем шаге будет выполнено развертывание решения.</span><span class="sxs-lookup"><span data-stu-id="9188c-130">In the next step, you will deploy the solution.</span></span>  
  
3.  <span data-ttu-id="9188c-131">Выполните следующий командлет, чтобы развернуть решение фермы.</span><span class="sxs-lookup"><span data-stu-id="9188c-131">Run the next cmdlet to deploy the farm solution:</span></span>  
  
    ```powershell
    Install-SPSolution -Identity PowerPivotFarm.wsp -GACDeployment -Force  
    ```  
  
##  <a name="step-2-deploy-the-powerpivot-web-application-solution-to-central-administration"></a><a name="deployCA"></a><span data-ttu-id="9188c-132">Шаг 2. Развертывание решения веб-приложения PowerPivot в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="9188c-132">Step 2: Deploy the PowerPivot Web Application Solution to Central Administration</span></span>  
 <span data-ttu-id="9188c-133">После развертывания решения фермы следует развернуть решение веб-приложения для центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="9188c-133">After you deploy the farm solution, you must deploy the Web application solution to Central Administration.</span></span> <span data-ttu-id="9188c-134">Этот шаг добавляет в центр администрирования панель управления PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9188c-134">This step adds the PowerPivot Management Dashboard to Central Administration.</span></span>  
  
1.  <span data-ttu-id="9188c-135">Откройте консоль управления SharePoint 2010, выбрав команду **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="9188c-135">Open a SharePoint 2010 Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="9188c-136">Выполните следующий командлет, чтобы создать ссылку на центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="9188c-136">Run the following cmdlet to create a reference to Central Administration:</span></span>  
  
    ```powershell
    $centralAdmin = $(Get-SPWebApplication -IncludeCentralAdministration | Where { $_.IsAdministrationWebApplication -eq $TRUE})  
    ```  
  
3.  <span data-ttu-id="9188c-137">Для добавления решения фермы выполните следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="9188c-137">Run the following cmdlet to add the farm solution.</span></span>  
  
    ```powershell
    Add-SPSolution -LiteralPath "C:\Program Files\Microsoft SQL Server\110\Tools\PowerPivotTools\ConfigurationTool\Resources\PowerPivotWebApp.wsp"  
    ```  
  
     <span data-ttu-id="9188c-138">Командлет возвратит имя решения, его идентификатор, а также атрибут Deployed=False.</span><span class="sxs-lookup"><span data-stu-id="9188c-138">The cmdlet returns the name of the solution, its solution ID, and Deployed=False.</span></span> <span data-ttu-id="9188c-139">На следующем шаге будет выполнено развертывание решения.</span><span class="sxs-lookup"><span data-stu-id="9188c-139">In the next step, you will deploy the solution.</span></span>  
  
4.  <span data-ttu-id="9188c-140">Выполните следующий командлет для установки решения веб-приложения в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="9188c-140">Run the next cmdlet to install the web application solution to Central Administration.</span></span>  
  
    ```powershell
    Install-SPSolution -Identity PowerPivotWebApp.wsp -GACDeployment -Force -WebApplication $centralAdmin  
    ```  
  
 <span data-ttu-id="9188c-141">Теперь, когда решение веб-приложения развернуто в центре администрирования, оставшиеся шаги конфигурации можно выполнить с помощью центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="9188c-141">Now that the web application solution is deployed to Central Administration, you can use Central Administration to complete all remaining configuration steps.</span></span>  
  
##  <a name="step-3-deploy-the-powerpivot-web-application-solution-to-other-web-applications"></a><a name="deployUI"></a><span data-ttu-id="9188c-142">Шаг 3. Развертывание решения веб-приложения PowerPivot для других веб-приложений</span><span class="sxs-lookup"><span data-stu-id="9188c-142">Step 3: Deploy the PowerPivot Web Application Solution to Other Web Applications</span></span>  
 <span data-ttu-id="9188c-143">В предыдущей задаче решение powerpivotwebapp.wsp было развернуто в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="9188c-143">In the previous task, you deployed Powerpivotwebapp.wsp to Central Administration.</span></span> <span data-ttu-id="9188c-144">В этом разделе описано развертывание решения powerpivotwebapp.wsp для каждого веб-приложения, поддерживающего доступ к данным PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9188c-144">In this section, you deploy the powerpivotwebapp.wsp on each existing web application that supports PowerPivot data access.</span></span> <span data-ttu-id="9188c-145">При добавлении других веб-приложений в дальнейшем необходимо будет повторить для них этот шаг.</span><span class="sxs-lookup"><span data-stu-id="9188c-145">If you add more web applications later, be sure to repeat this step for those additional web applications.</span></span>  
  
1.  <span data-ttu-id="9188c-146">В разделе «Системные параметры» центра администрирования выберите **Управление решениями фермы**.</span><span class="sxs-lookup"><span data-stu-id="9188c-146">In Central Administration, in System Settings, click **Manage farm solutions**.</span></span>  
  
2.  <span data-ttu-id="9188c-147">Щелкните **powerpivotwebapp. wsp**.</span><span class="sxs-lookup"><span data-stu-id="9188c-147">Click **powerpivotwebapp.wsp**.</span></span>  
  
3.  <span data-ttu-id="9188c-148">Нажмите **Развернуть решение**.</span><span class="sxs-lookup"><span data-stu-id="9188c-148">Click **Deploy Solution**.</span></span>  
  
4.  <span data-ttu-id="9188c-149">В разделе **Deploy to? (развертывание в**) выберите веб-приложение SharePoint, для которого требуется добавить поддержку функций PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9188c-149">In **Deploy To?**, select the SharePoint web application for which you want to add PowerPivot feature support.</span></span>  
  
5.  <span data-ttu-id="9188c-150">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9188c-150">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="9188c-151">Повторите процедуру для других веб-приложений SharePoint, которые тоже будут поддерживать доступ к данным PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9188c-151">Repeat for other SharePoint web applications that will also support PowerPivot data access.</span></span>  
  
##  <a name="redeploy-or-retract-the-solution"></a><a name="retract"></a><span data-ttu-id="9188c-152">Повторное развертывание или отзыв решения</span><span class="sxs-lookup"><span data-stu-id="9188c-152">Redeploy or retract the Solution</span></span>  
 <span data-ttu-id="9188c-153">Хотя центр администрирования SharePoint позволяет отзывать решения, для файла powerpivotwebapp.wsp это следует делать только тогда, когда систематически проводится диагностика проблем установки или развертывания обновлений.</span><span class="sxs-lookup"><span data-stu-id="9188c-153">Although SharePoint Central Administration provides solution retraction, you do not need to retract the powerpivotwebapp.wsp file unless you are systematically troubleshooting an installation or patch deployment problem.</span></span>  
  
1.  <span data-ttu-id="9188c-154">В разделе «Системные параметры» центра администрирования SharePoint 2010 выберите **Управление решениями фермы**.</span><span class="sxs-lookup"><span data-stu-id="9188c-154">In SharePoint 2010 Central Administration, in System Settings, click **Manage farm solutions**.</span></span>  
  
2.  <span data-ttu-id="9188c-155">Щелкните **Powerpivotwebapp.wsp**.</span><span class="sxs-lookup"><span data-stu-id="9188c-155">Click **Powerpivotwebapp.wsp**.</span></span>  
  
3.  <span data-ttu-id="9188c-156">Нажмите **Отозвать решение**.</span><span class="sxs-lookup"><span data-stu-id="9188c-156">Click **Retract Solution**.</span></span>  
  
 <span data-ttu-id="9188c-157">При возникновении проблем с развертыванием сервера, которые можно перевернуть в решение фермы, можно повторно развернуть его, запустив параметр **восстановления** в средстве настройки PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9188c-157">If you encounter server deployment issues that you trace back to the farm solution, you can redeploy it by running the **Repair** option in the PowerPivot Configuration Tool.</span></span> <span data-ttu-id="9188c-158">Предпочтительнее выполнять операции восстановления с помощью PowerPivot Configuration Tool, так как они включают меньше шагов.</span><span class="sxs-lookup"><span data-stu-id="9188c-158">Repair operations via the tool is preferred because it requires fewer steps on your part.</span></span> <span data-ttu-id="9188c-159">Дополнительные сведения см. в разделе [Настройка или восстановление PowerPivot для SharePoint 2010 &#40;средства настройки PowerPivot&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="9188c-159">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span></span>  
  
 <span data-ttu-id="9188c-160">Если же необходимо повторное развертывание всех решений, обязательно выполните его в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="9188c-160">If you still want to re-deploy all solutions, be sure to do so in this order:</span></span>  
  
1.  <span data-ttu-id="9188c-161">Отзыв решения для веб-приложений PowerPivot из всех веб-приложений SharePoint, которые его используют.</span><span class="sxs-lookup"><span data-stu-id="9188c-161">Retract the PowerPivot Web application solution from all SharePoint web applications that use it.</span></span>  
  
2.  <span data-ttu-id="9188c-162">Отзыв решения для фермы PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9188c-162">Retract the PowerPivot farm solution.</span></span>  
  
3.  <span data-ttu-id="9188c-163">Повторное развертывание решения для фермы PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9188c-163">Redeploy the PowerPivot farm solution.</span></span>  
  
4.  <span data-ttu-id="9188c-164">Повторное развертывание решения для веб-приложений PowerPivot для всех веб-приложений SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9188c-164">Redeploy the PowerPivot Web application solution to all SharePoint web applications.</span></span>  
  
##  <a name="about-the-powerpivot-solutions"></a><a name="intro"></a><span data-ttu-id="9188c-165">О решениях PowerPivot</span><span class="sxs-lookup"><span data-stu-id="9188c-165">About the PowerPivot Solutions</span></span>  
 <span data-ttu-id="9188c-166">PowerPivot для SharePoint использует два пакета решений для развертывания страниц своего приложения и программных файлов в ферме и в отдельных веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="9188c-166">PowerPivot for SharePoint uses two solution packages to deploy its application pages and program files to the farm and to individual web applications.</span></span>  
  
-   <span data-ttu-id="9188c-167">Решение фермы является глобальным.</span><span class="sxs-lookup"><span data-stu-id="9188c-167">The farm solution is global.</span></span> <span data-ttu-id="9188c-168">Оно развертывается один раз и автоматически становится доступным для любого нового сервера PowerPivot для SharePoint, который будет добавлен в ферму в будущем.</span><span class="sxs-lookup"><span data-stu-id="9188c-168">It is deployed once and then becomes automatically available to any new PowerPivot for SharePoint servers that you add to the farm later.</span></span>  
  
-   <span data-ttu-id="9188c-169">Решение веб-приложения для каждого приложения свое и должно развертываться для каждого приложения на ферме, включая веб-приложение центра администрирования (Central Administration).</span><span class="sxs-lookup"><span data-stu-id="9188c-169">The web application solution is application-specific and must be deployed to each web application in the farm, including the Central Administration web application.</span></span>  
  
 <span data-ttu-id="9188c-170">Каждое решение развертывается индивидуально.</span><span class="sxs-lookup"><span data-stu-id="9188c-170">Each solution is deployed differently.</span></span>  <span data-ttu-id="9188c-171">Решение фермы развертывается один раз после установки первого экземпляра PowerPivot для SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9188c-171">The farm solution is deployed once, after the first PowerPivot for SharePoint instance is installed.</span></span> <span data-ttu-id="9188c-172">Для развертывания решения фермы используется средство PowerPivot Configuration Tool или командлеты PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9188c-172">To deploy the farm solution, you use the PowerPivot Configuration Tool or PowerShell cmdlets.</span></span>  
  
 <span data-ttu-id="9188c-173">Решение веб-приложения сначала развертывается для центра администрирования, а затем для любых дополнительных веб-приложений, поддерживающих запросы к данным PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9188c-173">The web application solution is initially deployed to Central Administration, followed by subsequent solution deployments to any additional web applications that will support requests for PowerPivot data.</span></span> <span data-ttu-id="9188c-174">Чтобы развернуть решение веб-приложения для центра администрирования, необходимо использовать средство настройки PowerPivot или командлет PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9188c-174">To deploy the web application solution to Central Administration, you must use the PowerPivot Configuration Tool or PowerShell cmdlet.</span></span> <span data-ttu-id="9188c-175">Решение веб-приложения для других веб-приложений можно развернуть вручную с помощью центра администрирования или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9188c-175">For all other web applications, you can deploy the web application solution manually using Central Administration or PowerShell.</span></span>  
  
|<span data-ttu-id="9188c-176">Решение</span><span class="sxs-lookup"><span data-stu-id="9188c-176">Solution</span></span>|<span data-ttu-id="9188c-177">Описание</span><span class="sxs-lookup"><span data-stu-id="9188c-177">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="9188c-178">Powerpivotfarm.wsp</span><span class="sxs-lookup"><span data-stu-id="9188c-178">Powerpivotfarm.wsp</span></span>|<span data-ttu-id="9188c-179">Добавляет файл Microsoft.AnalysisServices.SharePoint.Integration.dll к глобальной сборке.</span><span class="sxs-lookup"><span data-stu-id="9188c-179">Adds Microsoft.AnalysisServices.SharePoint.Integration.dll to the global assembly.</span></span><br /><br /> <span data-ttu-id="9188c-180">Добавляет файл Microsoft.AnalysisServices.ChannelTransport.dll к глобальной сборке.</span><span class="sxs-lookup"><span data-stu-id="9188c-180">Adds Microsoft.AnalysisServices.ChannelTransport.dll to the global assembly.</span></span><br /><br /> <span data-ttu-id="9188c-181">Устанавливает функции и файлы ресурсов, а также регистрирует типы содержимого.</span><span class="sxs-lookup"><span data-stu-id="9188c-181">Installs features and resources files, and registers content types.</span></span><br /><br /> <span data-ttu-id="9188c-182">Добавляет шаблоны библиотек PowerPivot Gallery и Data Feed.</span><span class="sxs-lookup"><span data-stu-id="9188c-182">Adds library templates for PowerPivot Gallery and Data Feed libraries.</span></span><br /><br /> <span data-ttu-id="9188c-183">Добавляет страницы приложений для настройки приложений службы, панели управления PowerPivot, обновления данных и галереи PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9188c-183">Adds application pages for service application configuration, PowerPivot Management Dashboard, data refresh, and PowerPivot Gallery.</span></span>|  
|<span data-ttu-id="9188c-184">powerpivotwebapp.wsp</span><span class="sxs-lookup"><span data-stu-id="9188c-184">Powerpivotwebapp.wsp</span></span>|<span data-ttu-id="9188c-185">Добавляет файлы ресурсов Microsoft.AnalysisServices.SharePoint.Integration.dll в папку расширений веб-сервера на сервере клиентского веб-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9188c-185">Adds Microsoft.AnalysisServices.SharePoint.Integration.dll resources files to the web server extensions folder on the Web front-end.</span></span><br /><br /> <span data-ttu-id="9188c-186">Добавляет веб-службу PowerPivot к серверу клиентского веб-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9188c-186">Adds PowerPivot Web service to the Web-front end.</span></span><br /><br /> <span data-ttu-id="9188c-187">Добавляет возможность формирования эскизов для галереи PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9188c-187">Adds thumbnail image generation for PowerPivot Gallery.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9188c-188">См. также:</span><span class="sxs-lookup"><span data-stu-id="9188c-188">See Also</span></span>  
 <span data-ttu-id="9188c-189">[PowerPivot для SharePoint обновления](../../database-engine/install-windows/upgrade-power-pivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="9188c-189">[Upgrade PowerPivot for SharePoint](../../database-engine/install-windows/upgrade-power-pivot-for-sharepoint.md) </span></span>  
 <span data-ttu-id="9188c-190">[Администрирование и настройка сервера PowerPivot в центре администрирования](power-pivot-server-administration-and-configuration-in-central-administration.md) </span><span class="sxs-lookup"><span data-stu-id="9188c-190">[PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) </span></span>  
 [<span data-ttu-id="9188c-191">Настройка PowerPivot с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9188c-191">PowerPivot Configuration using Windows PowerShell</span></span>](power-pivot-configuration-using-windows-powershell.md)  
