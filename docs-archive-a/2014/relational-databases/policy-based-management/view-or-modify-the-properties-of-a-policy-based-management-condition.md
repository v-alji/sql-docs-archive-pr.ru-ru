---
title: Просмотр или изменение свойств условия управления на основе политик | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view policy conditions
- Policy-Based Management, modify policy conditions
ms.assetid: 890d7384-8444-4767-bb6f-f5debb155747
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 08baec48bd13445ef56ea6a29520d23ebaf683b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657695"
---
# <a name="view-or-modify-the-properties-of-a-policy-based-management-condition"></a><span data-ttu-id="59f35-102">Просмотр или изменение свойств условия управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="59f35-102">View or Modify the Properties of a Policy-Based Management Condition</span></span>
  <span data-ttu-id="59f35-103">В этом разделе описывается просмотр и изменение свойств условия управления на основе политик в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59f35-103">This topic describes how to view or modify the properties of a Policy-Based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="59f35-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="59f35-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="59f35-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="59f35-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="59f35-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="59f35-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="59f35-107">**Просмотр или изменение свойств условия с помощью:**</span><span class="sxs-lookup"><span data-stu-id="59f35-107">**To view or modify a condition's properties, using:**</span></span>  
  
     [<span data-ttu-id="59f35-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="59f35-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="59f35-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="59f35-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="59f35-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="59f35-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="59f35-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="59f35-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="59f35-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="59f35-112">Permissions</span></span>  
 <span data-ttu-id="59f35-113">Требуется членство в роли PolicyAdministratorRole базы данных msdb.</span><span class="sxs-lookup"><span data-stu-id="59f35-113">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="59f35-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="59f35-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-modify-a-conditions-properties"></a><span data-ttu-id="59f35-115">Просмотр или изменение свойств условия</span><span class="sxs-lookup"><span data-stu-id="59f35-115">To view or modify a condition's properties</span></span>  
  
1.  <span data-ttu-id="59f35-116">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть сервер, содержащий условие, которое нужно просмотреть или изменить.</span><span class="sxs-lookup"><span data-stu-id="59f35-116">In **Object Explorer**, click the plus sign to expand the server that contains the condition that you want to view or modify.</span></span>  
  
2.  <span data-ttu-id="59f35-117">Щелкните знак «плюс», чтобы развернуть папку **Управление** .</span><span class="sxs-lookup"><span data-stu-id="59f35-117">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="59f35-118">Щелкните знак «плюс», чтобы развернуть папку **Управление политиками**.</span><span class="sxs-lookup"><span data-stu-id="59f35-118">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="59f35-119">Щелкните знак «плюс», чтобы развернуть папку **Условия** .</span><span class="sxs-lookup"><span data-stu-id="59f35-119">Click the plus sign to expand the **Conditions** folder.</span></span>  
  
5.  <span data-ttu-id="59f35-120">Щелкните правой кнопкой мыши условие, свойства которого необходимо просмотреть или изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="59f35-120">Right-click the condition that you want to view or edit and select **Properties**.</span></span> <span data-ttu-id="59f35-121">Дополнительные сведения о параметрах, доступных в диалоговом окне **Открытие условия —**_имя_условия_, см. в статьях [Диалоговое окно "Создание нового условия" или "Открытие условия", страница "Общее"](../../integration-services/general-page-of-integration-services-designers-options.md), [Диалоговое окно "Открытие условия", вкладка "Зависимые политики"](open-condition-dialog-box-dependent-policies-page.md), [Диалоговое окно "Создание нового условия" или "Открытие условия", страница "Описание"](create-new-condition-or-open-condition-dialog-box-description-page.md) и [Диалоговое окно "Расширенное редактирование" (условие)](advanced-edit-condition-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="59f35-121">For more information on the available options in the **Open Condition -**_condition_name_ dialog box, see [Create New Condition or Open Condition Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md), [Open Condition Dialog Box, Dependent Policies Page](open-condition-dialog-box-dependent-policies-page.md), [Create New Condition or Open Condition Dialog Box, Description Page](create-new-condition-or-open-condition-dialog-box-description-page.md), and [Advanced Edit &#40;Condition&#41; Dialog Box](advanced-edit-condition-dialog-box.md).</span></span>  
  
6.  <span data-ttu-id="59f35-122">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="59f35-122">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="59f35-123">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="59f35-123">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-conditions-properties"></a><span data-ttu-id="59f35-124">Просмотр свойств условия</span><span class="sxs-lookup"><span data-stu-id="59f35-124">To view a condition's properties</span></span>  
  
1.  <span data-ttu-id="59f35-125">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59f35-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="59f35-126">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="59f35-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="59f35-127">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="59f35-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    SELECT name,  
       description,  
       facet,  
       expression,  
       is_name_condition,  
       obj_name  
    FROM syspolicy_conditions;  
    GO  
  
    ```  
  
 <span data-ttu-id="59f35-128">Дополнительные сведения см. в статье [syspolicy_conditions (Transact-SQL)](/sql/relational-databases/system-catalog-views/syspolicy-conditions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="59f35-128">For more information, see [syspolicy_conditions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-conditions-transact-sql).</span></span>  
  
  
