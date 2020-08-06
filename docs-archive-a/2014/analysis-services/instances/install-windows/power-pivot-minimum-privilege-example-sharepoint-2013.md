---
title: Пример конфигурации с минимальными правами для PowerPivot для SharePoint 2013 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c1e09e6c-52d3-48ab-8c70-818d5d775087
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0188f314e4c354b33d03e6e7948aed1ba4cf8be2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729917"
---
# <a name="example-of-a-minimum-privilege-configuration-for-powerpivot-for-sharepoint-2013"></a><span data-ttu-id="9ad10-102">Пример конфигурации PowerPivot для SharePoint 2013 с минимальными правами</span><span class="sxs-lookup"><span data-stu-id="9ad10-102">Example of a Minimum-Privilege Configuration for PowerPivot for SharePoint 2013</span></span>
  <span data-ttu-id="9ad10-103">В этом разделе описывается пример настройки PowerPivot для SharePoint 2013 с минимальными правами доступа.</span><span class="sxs-lookup"><span data-stu-id="9ad10-103">This topic describes an example PowerPivot for SharePoint 2013 configuration with minimum privileges.</span></span> <span data-ttu-id="9ad10-104">В конфигурации используется отдельная учетная запись для каждого из трех компонентов и каждая учетная запись имеет минимальный уровень прав доступа.</span><span class="sxs-lookup"><span data-stu-id="9ad10-104">The configuration utilizes a different account for each of the three components and each account has the minimum level of privileges.</span></span>  
  
## <a name="summary-of-accounts"></a><span data-ttu-id="9ad10-105">Сводка учетных записей</span><span class="sxs-lookup"><span data-stu-id="9ad10-105">Summary of Accounts</span></span>  
 <span data-ttu-id="9ad10-106">PowerPivot для SharePoint 2013 позволяет использовать учетную запись сетевой службы для учетной записи служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="9ad10-106">PowerPivot for SharePoint 2013 supports the use of the Network Service account for the Analysis Services service account.</span></span> <span data-ttu-id="9ad10-107">Учетная запись сетевой службы не поддерживается в SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="9ad10-107">The Network Service account is not a supported scenario with SharePoint 2010.</span></span> <span data-ttu-id="9ad10-108">Дополнительные сведения об учетных записях служб см. в разделе [Configure Windows Service Accounts and Permissions](../../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md) ( https://msdn.microsoft.com/library/ms143504.aspx) .</span><span class="sxs-lookup"><span data-stu-id="9ad10-108">For more information on Service accounts, see [Configure Windows Service Accounts and Permissions](../../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md) (https://msdn.microsoft.com/library/ms143504.aspx).</span></span>  
  
 <span data-ttu-id="9ad10-109">В следующей таблице представлены три учетные записи, используемые в данном примере конфигурации с минимальными правами доступа.</span><span class="sxs-lookup"><span data-stu-id="9ad10-109">The following table summarizes the three accounts used in this example of a minimum privileged configuration.</span></span>  
  
|<span data-ttu-id="9ad10-110">Область</span><span class="sxs-lookup"><span data-stu-id="9ad10-110">Scope</span></span>|<span data-ttu-id="9ad10-111">Имя</span><span class="sxs-lookup"><span data-stu-id="9ad10-111">Name</span></span>|  
|-----------|----------|  
|<span data-ttu-id="9ad10-112">Учетная запись администратора SharePoint</span><span class="sxs-lookup"><span data-stu-id="9ad10-112">SharePoint Administrator account</span></span>|<span data-ttu-id="9ad10-113">**SPAdmin**</span><span class="sxs-lookup"><span data-stu-id="9ad10-113">**SPAdmin**</span></span>|  
|<span data-ttu-id="9ad10-114">Учетная запись фермы SharePoint</span><span class="sxs-lookup"><span data-stu-id="9ad10-114">SharePoint Farm account</span></span>|<span data-ttu-id="9ad10-115">**SPFarm**</span><span class="sxs-lookup"><span data-stu-id="9ad10-115">**SPFarm**</span></span>|  
|<span data-ttu-id="9ad10-116">Учетная запись службы Analysis Services</span><span class="sxs-lookup"><span data-stu-id="9ad10-116">Analysis Services service account</span></span>|<span data-ttu-id="9ad10-117">**SPsvc**</span><span class="sxs-lookup"><span data-stu-id="9ad10-117">**SPsvc**</span></span>|  
  
### <a name="the-sharepoint-administrator-account-spadmin"></a><span data-ttu-id="9ad10-118">Учетная запись администратора SharePoint (SpAdmin)</span><span class="sxs-lookup"><span data-stu-id="9ad10-118">The SharePoint Administrator account (SpAdmin)</span></span>  
 <span data-ttu-id="9ad10-119">**SPAdmin** — учетная запись домена, используемая для установки и настройки фермы.</span><span class="sxs-lookup"><span data-stu-id="9ad10-119">**SPAdmin** is a domain account you use to install and configure the farm.</span></span> <span data-ttu-id="9ad10-120">Это учетная запись, используемая для запуска мастера настройки SharePoint и средства настройки PowerPivot для SharePoint 2013. учетная запись **администратора** — это единственная учетная запись, для которой требуются права локального администратора.</span><span class="sxs-lookup"><span data-stu-id="9ad10-120">It is the account used to run the SharePoint Configuration Wizard and the PowerPivot Configuration Tool for SharePoint 2013.The **SPAdmin** account is the only account that requires local Administrator rights.</span></span> <span data-ttu-id="9ad10-121">Перед запуском средства настройки PowerPivot предоставьте учетной записи **администратора** доступ к экземпляру базы данных SQL Server, где SharePoint создает базы данных содержимого и конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9ad10-121">Before running the PowerPivot Configuration tool, grant the **SPAdmin** account privileges to the SQL Server database instance where SharePoint creates content and configuration databases.</span></span> <span data-ttu-id="9ad10-122">Чтобы можно было настроить учетную запись SPAdmin с минимальными правами доступа, она должна быть членом ролей **securityadmin** и **dbcreator**.</span><span class="sxs-lookup"><span data-stu-id="9ad10-122">To configure the SPAdmin account in a minimum privilege scenario, it should be a member of the roles **securityadmin** and **dbcreator**.</span></span>  
  
### <a name="the-farm-account-spfarm"></a><span data-ttu-id="9ad10-123">Учетная запись фермы (SPFarm)</span><span class="sxs-lookup"><span data-stu-id="9ad10-123">The Farm account (SPFarm)</span></span>  
 <span data-ttu-id="9ad10-124">**SPFarm** — учетная запись домена, используемая службой таймера SharePoint и веб-приложением для центра администрирования служб, чтобы получить доступ к базе данных содержимого SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9ad10-124">**SPFarm** is a domain account that the SharePoint Timer service and the web application for Central Administration use to access the SharePoint content database.</span></span> <span data-ttu-id="9ad10-125">Эта учетная запись не обязательно должна быть локальным администратором.</span><span class="sxs-lookup"><span data-stu-id="9ad10-125">This account does not need to be a local administrator.</span></span> <span data-ttu-id="9ad10-126">Мастер настройки SharePoint предоставляет необходимые минимальные права доступа к внутренней базе данных SQL Server. Конфигурация SQL Server с минимальными правами доступа — членство в ролях **securityadmin** и **dbcreator**.</span><span class="sxs-lookup"><span data-stu-id="9ad10-126">The SharePoint configuration wizard grants the proper minimal privilege in the back-end SQL Server database.The minimum SQL Server privilege configuration is membership in the roles **securityadmin** and **dbcreator**.</span></span>  
  
### <a name="the-service-account-for-powerpivot-service-spsvc"></a><span data-ttu-id="9ad10-127">Учетная запись службы для службы PowerPivot (SPsvc)</span><span class="sxs-lookup"><span data-stu-id="9ad10-127">The Service Account for PowerPivot Service (SPsvc)</span></span>  
 <span data-ttu-id="9ad10-128">Если новая ферма SharePoint не настроена перед запуском средства настройки PowerPivot, то по умолчанию средство настройки PowerPivot создает:</span><span class="sxs-lookup"><span data-stu-id="9ad10-128">If a new SharePoint farm is not configured before you run the PowerPivot Configuration tool, then by default the PowerPivot Configuration tool will create the following:</span></span>  
  
-   <span data-ttu-id="9ad10-129">Приложение службы PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9ad10-129">PowerPivot Service application.</span></span>  
  
-   <span data-ttu-id="9ad10-130">Приложение службы Excel.</span><span class="sxs-lookup"><span data-stu-id="9ad10-130">Excel Services application.</span></span>  
  
-   <span data-ttu-id="9ad10-131">Приложение безопасного хранения.</span><span class="sxs-lookup"><span data-stu-id="9ad10-131">Secure Store application.</span></span>  
  
 <span data-ttu-id="9ad10-132">Средство настройки PowerPivot настраивает все три приложения службы в пуле приложений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9ad10-132">The PowerPivot configuration tool configures all three of the service applications in the default application pool.</span></span> <span data-ttu-id="9ad10-133">Этот пул приложений обычно настроен для запуска с учетной записью SPFarm, которая имеет доступ ко многим ресурсам, ненужным учетной записи службы. Чтобы наделить среду минимальными правами, настройте новую учетную запись домена, которая будет использоваться соответствующим пулом приложений и веб-приложением.</span><span class="sxs-lookup"><span data-stu-id="9ad10-133">That application pool is typically configured to run as the SPFarm account, which has access to many resources that a service account does not require.To make the environment a minimum-privileged environment, configure a new domain account to be use by the appropriate application pool and web application.</span></span>  
  
 <span data-ttu-id="9ad10-134">**Чтобы создать новую учетную запись домена SPsvc, которая будет использоваться в качестве учетной записи службы SharePoint:**</span><span class="sxs-lookup"><span data-stu-id="9ad10-134">**To create a new domain account SPsvc to be used as a SharePoint Service account:**</span></span>  
  
1.  <span data-ttu-id="9ad10-135">В центре администрирования SharePoint щелкните **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="9ad10-135">In SharePoint Central Administration, click **Security**.</span></span>  
  
2.  <span data-ttu-id="9ad10-136">Щелкните " **настроить учетные записи служб** ".</span><span class="sxs-lookup"><span data-stu-id="9ad10-136">Click **Configure Service Accounts**</span></span>  
  
3.  <span data-ttu-id="9ad10-137">Щелкните **зарегистрировать новую управляемую учетную запись**.</span><span class="sxs-lookup"><span data-stu-id="9ad10-137">Click **Register new managed account**.</span></span>  
  
 <span data-ttu-id="9ad10-138">Учетная запись **SPSvc** не имеет прав доступа локального администратора, и SPsvc не будет иметь никаких прав в базе данных SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9ad10-138">The **SPSvc** account has no local administrator privileges and SPsvc will not have any privileges in the SharePoint database.</span></span> <span data-ttu-id="9ad10-139">Единственные права доступа, необходимые SPsvc, — права администратора для экземпляра PowerPivot служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="9ad10-139">The only privileges SPsvc requires is administrative rights to the PowerPivot Instance of the Analysis Services.</span></span>  
  
 <span data-ttu-id="9ad10-140">**Чтобы настроить соответствующий пул приложений для использования учетной записи SPsvc:**</span><span class="sxs-lookup"><span data-stu-id="9ad10-140">**To configure the appropriate application pool to use the SPsvc account :**</span></span>  
  
1.  <span data-ttu-id="9ad10-141">В центре администрирования SharePoint щелкните **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="9ad10-141">In SharePoint Central Administration, click **Security**.</span></span>  
  
2.  <span data-ttu-id="9ad10-142">Щелкните **Настройка учетных записей служб**.</span><span class="sxs-lookup"><span data-stu-id="9ad10-142">Click **Configure Service Accounts**.</span></span>  
  
3.  <span data-ttu-id="9ad10-143">Выберите пул приложений служб, используемый приложением службы PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9ad10-143">Select the service application pool used by the PowerPivot Service application.</span></span> <span data-ttu-id="9ad10-144">Выберите учетную запись SPSvc.</span><span class="sxs-lookup"><span data-stu-id="9ad10-144">Then select the SPSvc account.</span></span>  
  
 <span data-ttu-id="9ad10-145">**Чтобы предоставить доступ к веб-приложению с PowerShell:**</span><span class="sxs-lookup"><span data-stu-id="9ad10-145">**To Grant access to the web application with PowerShell:**</span></span>  
  
1.  <span data-ttu-id="9ad10-146">Запустите консоль управления SharePoint 2013 с правом доступа администратора.</span><span class="sxs-lookup"><span data-stu-id="9ad10-146">Run the SharePoint 2013 Management Shell with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="9ad10-147">Выполните следующий код PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9ad10-147">Run the following PowerShell code:</span></span>  
  
    ```powershell
    $webApp = Get-SPWebApplication "http://<servername>"  
    $webApp.GrantAccessToProcessIdentity("DOMAIN\<ServiceAccountName>")
    ```  
