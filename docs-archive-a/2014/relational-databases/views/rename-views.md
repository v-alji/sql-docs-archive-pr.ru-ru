---
title: Переименование представлений | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], renaming
- renaming views
ms.assetid: 5eed0488-81d2-40e8-8fdf-b0a640a591d0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5cc76ced033a69788270c3fa9277bcca6972e080
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729321"
---
# <a name="rename-views"></a><span data-ttu-id="5ec9f-102">Переименование представлений</span><span class="sxs-lookup"><span data-stu-id="5ec9f-102">Rename Views</span></span>
  <span data-ttu-id="5ec9f-103">Представление в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно переименовать, используя [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ec9f-103">You can rename a view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="5ec9f-104">При переименовании представления фрагменты кода и приложения, использующие это представление, могут привести к сбою.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-104">If you rename a view, code and applications that depend on the view may fail.</span></span> <span data-ttu-id="5ec9f-105">Это касается других представлений, запросов, хранимых процедур, определяемых пользователем функций и клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-105">These include other views, queries, stored procedures, user-defined functions, and client applications.</span></span> <span data-ttu-id="5ec9f-106">Следует иметь в виду, что возникновение ошибок происходит каскадом.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-106">Note that these failures will cascade.</span></span>  
  
 <span data-ttu-id="5ec9f-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="5ec9f-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5ec9f-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="5ec9f-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5ec9f-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="5ec9f-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="5ec9f-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="5ec9f-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5ec9f-111">**Переименование представления с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="5ec9f-111">**To rename a view, using:**</span></span>  
  
     [<span data-ttu-id="5ec9f-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5ec9f-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5ec9f-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5ec9f-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="5ec9f-114">**Дальнейшие действия.**  [После переименования представления](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="5ec9f-114">**Follow Up:**  [After renaming a view](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5ec9f-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="5ec9f-115">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="5ec9f-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="5ec9f-116">Prerequisites</span></span>  
 <span data-ttu-id="5ec9f-117">Получение списка всех зависимостей в представлении.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-117">Obtain a list of all dependencies on the view.</span></span> <span data-ttu-id="5ec9f-118">Все объекты, скрипты или приложения, которые ссылаются на представление, необходимо изменить в соответствии с новым именем представления.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-118">Any objects, scripts or applications that reference the view must be modified to reflect the new name of the view.</span></span> <span data-ttu-id="5ec9f-119">Дополнительные сведения см. в статье [Get Information About a View](get-information-about-a-view.md).</span><span class="sxs-lookup"><span data-stu-id="5ec9f-119">For more information, see [Get Information About a View](get-information-about-a-view.md).</span></span> <span data-ttu-id="5ec9f-120">Рекомендуется удалить представление и создать его повторно с новым именем вместо переименования.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-120">We recommend that you drop the view and recreate it with a new name instead of renaming the view.</span></span> <span data-ttu-id="5ec9f-121">При повторном создании представления выполняется обновление сведений о зависимостях для объектов, на которые имеются ссылки в представлении.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-121">By recreating the view, you update the dependency information for the objects that are referenced in the view.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5ec9f-122">безопасность</span><span class="sxs-lookup"><span data-stu-id="5ec9f-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5ec9f-123">Permissions</span><span class="sxs-lookup"><span data-stu-id="5ec9f-123">Permissions</span></span>  
 <span data-ttu-id="5ec9f-124">Требуется разрешение ALTER для SCHEMA или разрешение CONTROL для OBJECT, а также разрешение CREATE VIEW в базе данных.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-124">Requires ALTER permission on SCHEMA or CONTROL permission on OBJECT is required, and CREATE VIEW permission in the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5ec9f-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5ec9f-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-view"></a><span data-ttu-id="5ec9f-126">Переименование представления</span><span class="sxs-lookup"><span data-stu-id="5ec9f-126">To rename a view</span></span>  
  
1.  <span data-ttu-id="5ec9f-127">В **обозревателе объектов**разверните базу данных, содержащую представление, которое необходимо переименовать, а затем разверните папку **Представление** .</span><span class="sxs-lookup"><span data-stu-id="5ec9f-127">In **Object Explorer**, expand the database that contains the view you wish to rename and then expand the **View** folder.</span></span>  
  
2.  <span data-ttu-id="5ec9f-128">Щелкните правой кнопкой мыши представление, которое нужно переименовать, и выберите пункт **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-128">Right-click the view you wish to rename and select **Rename**.</span></span>  
  
3.  <span data-ttu-id="5ec9f-129">Введите новое имя представления.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-129">Enter the view's new name.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5ec9f-130">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5ec9f-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="5ec9f-131">**Переименование представления**</span><span class="sxs-lookup"><span data-stu-id="5ec9f-131">**To rename a view**</span></span>  
  
 <span data-ttu-id="5ec9f-132">Хотя можно использовать **sp_rename** для изменения имени представления, рекомендуется удалить существующее представление, а затем повторно создать его с новым именем.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-132">While you can use **sp_rename** to change the name of the view, we recommend that you delete the existing view and then re-create it with the new name.</span></span>  
  
 <span data-ttu-id="5ec9f-133">Дополнительные сведения см. в разделах [CREATE VIEW (Transact-SQL)](/sql/t-sql/statements/create-view-transact-sql) и [DROP VIEW (Transact-SQL)](/sql/t-sql/statements/drop-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5ec9f-133">For more information, see [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) and [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span></span>  
  
##  <a name="follow-up-after-renaming-a-view"></a><a name="FollowUp"></a> <span data-ttu-id="5ec9f-134">Дальнейшие действия. После переименования представления</span><span class="sxs-lookup"><span data-stu-id="5ec9f-134">Follow Up: After Renaming a View</span></span>  
 <span data-ttu-id="5ec9f-135">Убедитесь, что все объекты, скрипты и приложения, ссылающиеся на предыдущее имя представления, теперь используют новое имя.</span><span class="sxs-lookup"><span data-stu-id="5ec9f-135">Ensure that all objects, scripts, and applications that reference the view's old name now use the new name.</span></span>  
  
  
