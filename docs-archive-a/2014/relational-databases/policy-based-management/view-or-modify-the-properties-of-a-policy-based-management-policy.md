---
title: Просмотр или изменение свойств политики управления на основе политик | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, modify policies
- Policy-Based Management, view policies
ms.assetid: ba805504-5db5-4731-a8da-a0e89cb20c37
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: da2226d3049a84098eb8e561635161f73b71ab10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657696"
---
# <a name="view-or-modify-the-properties-of-a-policy-based-management-policy"></a><span data-ttu-id="4bfe1-102">Просмотр или изменение свойств политики управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="4bfe1-102">View or Modify the Properties of a Policy-Based Management Policy</span></span>
  <span data-ttu-id="4bfe1-103">В этом разделе описывается просмотр и изменение свойств политики управления на основе политик в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bfe1-103">This topic describes how to view or modify a Policy-Based Management policy's properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4bfe1-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="4bfe1-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4bfe1-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="4bfe1-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4bfe1-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="4bfe1-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4bfe1-107">**Просмотр или изменение свойств политики с помощью:**</span><span class="sxs-lookup"><span data-stu-id="4bfe1-107">**To view or modify a policy's properties, using:**</span></span>  
  
     [<span data-ttu-id="4bfe1-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4bfe1-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4bfe1-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4bfe1-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4bfe1-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="4bfe1-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4bfe1-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="4bfe1-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4bfe1-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="4bfe1-112">Permissions</span></span>  
 <span data-ttu-id="4bfe1-113">Требуется членство в роли PolicyAdministratorRole базы данных msdb.</span><span class="sxs-lookup"><span data-stu-id="4bfe1-113">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4bfe1-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4bfe1-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-of-all-policies-on-an-object"></a><span data-ttu-id="4bfe1-115">Просмотр свойств всех политик в объекте</span><span class="sxs-lookup"><span data-stu-id="4bfe1-115">To view the properties of all policies on an object</span></span>  
  
1.  <span data-ttu-id="4bfe1-116">В обозревателе объектов щелкните правой кнопкой мыши сервер, базу данных или объект базы данных, укажите пункт **Политики** и выберите пункт **Просмотреть**.</span><span class="sxs-lookup"><span data-stu-id="4bfe1-116">In Object Explorer, right-click a server, server object, database, or database object, point to **Policies** and select **View**.</span></span> <span data-ttu-id="4bfe1-117">Дополнительные сведения о параметрах, доступных в диалоговом окне **Просмотр политик —**_имя_объекта_, см. в статье [Диалоговое окно "Просмотр политик"](view-policies-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="4bfe1-117">For more information on the available options in the **View Policies -**_object_name_ dialog box, see [View Policies Dialog Box](view-policies-dialog-box.md).</span></span>  
  
2.  <span data-ttu-id="4bfe1-118">После завершения нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="4bfe1-118">When finished, click **Close**.</span></span>  
  
#### <a name="to-view-or-modify-a-specific-policys-properties"></a><span data-ttu-id="4bfe1-119">Просмотр или изменение свойств отдельной политики</span><span class="sxs-lookup"><span data-stu-id="4bfe1-119">To view or modify a specific policy's properties</span></span>  
  
1.  <span data-ttu-id="4bfe1-120">В **обозревателе объектов**щелкните знак "плюс", чтобы развернуть сервер, содержащий политику управления на основе политик, которую необходимо просмотреть или изменить.</span><span class="sxs-lookup"><span data-stu-id="4bfe1-120">In **Object Explorer**, click the plus sign to expand the server that contains the Policy-Based Management policy that you want to view or modify.</span></span>  
  
2.  <span data-ttu-id="4bfe1-121">Щелкните знак «плюс», чтобы развернуть папку **Управление** .</span><span class="sxs-lookup"><span data-stu-id="4bfe1-121">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="4bfe1-122">Щелкните знак «плюс», чтобы развернуть папку **Управление политиками**.</span><span class="sxs-lookup"><span data-stu-id="4bfe1-122">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="4bfe1-123">Щелкните знак «плюс», чтобы развернуть папку **Политики** .</span><span class="sxs-lookup"><span data-stu-id="4bfe1-123">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="4bfe1-124">Щелкните правой кнопкой политику, свойства которой необходимо просмотреть или изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="4bfe1-124">Right-click the policy that you want to view or modify and select **Properties**.</span></span> <span data-ttu-id="4bfe1-125">Дополнительные сведения о параметрах, доступных в диалоговом окне **Открытие политики —**_имя_политики_, см. в статьях [Диалоговое окно "Создание новой политики" или "Открытие политики", страница "Общее"](../../integration-services/general-page-of-integration-services-designers-options.md) и [Диалоговое окно "Создание новой политики" или "Открытие политики", страница "Описание"](create-new-policy-or-open-policy-dialog-box-description-page.md).</span><span class="sxs-lookup"><span data-stu-id="4bfe1-125">For more information on the available options in the **Open Policy -**_policy_name_ dialog box, see [Create New Policy or Open Policy Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md) and [Create New Policy or Open Policy Dialog Box, Description Page](create-new-policy-or-open-policy-dialog-box-description-page.md).</span></span>  
  
6.  <span data-ttu-id="4bfe1-126">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4bfe1-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4bfe1-127">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4bfe1-127">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-policys-properties"></a><span data-ttu-id="4bfe1-128">Просмотр свойств политики</span><span class="sxs-lookup"><span data-stu-id="4bfe1-128">To view a policy's properties</span></span>  
  
1.  <span data-ttu-id="4bfe1-129">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bfe1-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4bfe1-130">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="4bfe1-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4bfe1-131">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="4bfe1-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    SELECT name,  
       execution_mode,  
       description,  
       is_enabled,  
       job_id  
    FROM syspolicy_policies;  
    GO  
    ```  
  
 <span data-ttu-id="4bfe1-132">Дополнительные сведения см. в статье [syspolicy_policies (Transact-SQL)](/sql/relational-databases/system-catalog-views/syspolicy-policies-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4bfe1-132">For more information, see [syspolicy_policies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-policies-transact-sql).</span></span>  
  
  
