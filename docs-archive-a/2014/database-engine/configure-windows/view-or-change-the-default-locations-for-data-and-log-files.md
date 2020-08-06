---
title: Просмотр или изменение расположения по умолчанию для файлов данных и журналов (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- log files [SQL Server], changing default location
- data files [SQL Server], changing default location
ms.assetid: 70a57fda-fcfe-490f-9cf6-5df620e32b2a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: def6be137aecbab7f2730fa4c2bf210b374a3a7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729789"
---
# <a name="view-or-change-the-default-locations-for-data-and-log-files-sql-server-management-studio"></a><span data-ttu-id="82c84-102">Просмотр или изменение расположения по умолчанию для файлов данных и журнала (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="82c84-102">View or Change the Default Locations for Data and Log Files (SQL Server Management Studio)</span></span>
  <span data-ttu-id="82c84-103">Данный раздел описывает функции просмотра и изменения расположения по умолчанию для новых файлов данных и файлов журнала в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82c84-103">This topic describes how to view and change the default locations of new data and log files in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="82c84-104">Путь по умолчанию берется из реестра.</span><span class="sxs-lookup"><span data-stu-id="82c84-104">The default path is obtained from the registry.</span></span> <span data-ttu-id="82c84-105">После изменения местоположения все новые базы данных, созданные в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , будут использовать это местоположение, если не указано другое местоположение.</span><span class="sxs-lookup"><span data-stu-id="82c84-105">After you change the location all new databases created in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will use that location if a different location is not specified.</span></span>  
  
 <span data-ttu-id="82c84-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="82c84-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="82c84-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="82c84-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="82c84-108">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="82c84-108">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="82c84-109">**Просмотр или изменение местоположения по умолчанию для файлов данных и журналов с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="82c84-109">**To view or change the data and log file default locations, using:**</span></span>  
  
     [<span data-ttu-id="82c84-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="82c84-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   <span data-ttu-id="82c84-111">**Продолжение**  [после изменения расположений по умолчанию](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="82c84-111">**Follow Up:**  [Changing the Default Locations](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="82c84-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="82c84-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="82c84-113">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="82c84-113">Recommendations</span></span>  
 <span data-ttu-id="82c84-114">Рекомендуемым способом защиты файлов данных и журналов является защита с помощью списков управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="82c84-114">The best practice for protecting your data files and log files is to ensure that they are protected by access control lists (ACLs).</span></span> <span data-ttu-id="82c84-115">Списки ACL должны располагаться в корневом каталоге, в котором создаются файлы.</span><span class="sxs-lookup"><span data-stu-id="82c84-115">The ACLs should be set on the directory root under which the files are created.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="82c84-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="82c84-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="82c84-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="82c84-117">Permissions</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="82c84-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="82c84-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-default-locations-for-database-files"></a><span data-ttu-id="82c84-119">Просмотр или изменение расположения по умолчанию для файлов базы данных</span><span class="sxs-lookup"><span data-stu-id="82c84-119">To view or change the default locations for database files</span></span>  
  
1.  <span data-ttu-id="82c84-120">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="82c84-120">In Object Explorer, right-click a server and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="82c84-121">На левой панели щелкните страницу **Параметры базы данных** .</span><span class="sxs-lookup"><span data-stu-id="82c84-121">In the left panel, click the **Database settings** page.</span></span>  
  
3.  <span data-ttu-id="82c84-122">В области **Места хранения, используемые базой данных по умолчанию**можно просмотреть текущие расположения, используемые по умолчанию для новых файлов данных и файлов журнала.</span><span class="sxs-lookup"><span data-stu-id="82c84-122">In **Database default locations**, view the current default locations for new data files and new log files.</span></span> <span data-ttu-id="82c84-123">Чтобы изменить местоположение по умолчанию, введите новый путь по умолчанию в поле **Данные** или **Журнал** или нажмите кнопку обзора, перейдите к нужному пути и выберите его.</span><span class="sxs-lookup"><span data-stu-id="82c84-123">To change a default location, enter a new default pathname in the **Data** or **Log** field, or click the browse button to find and select a pathname.</span></span>  
  
##  <a name="follow-up-after-changing-the-default-locations"></a><a name="FollowUp"></a><span data-ttu-id="82c84-124">Дальнейшие действия. После изменения расположений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="82c84-124">Follow Up: After Changing the Default Locations</span></span>  
 <span data-ttu-id="82c84-125">Необходимо остановить и запустить службу SQL Server для завершения изменения.</span><span class="sxs-lookup"><span data-stu-id="82c84-125">You must stop and start the SQL Server service to complete the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82c84-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="82c84-126">See Also</span></span>  
 <span data-ttu-id="82c84-127">[CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="82c84-127">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="82c84-128">Создание базы данных</span><span class="sxs-lookup"><span data-stu-id="82c84-128">Create a Database</span></span>](../../relational-databases/databases/create-a-database.md)  
  
  
