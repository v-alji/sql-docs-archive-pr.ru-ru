---
title: Устаревшие функции средств управления в SQL Server 2014 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: a08d1354-cc91-4ab7-a73f-3ad815af3d5a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 484e4078e25249e17a1d8b87426a395c3cfa1725
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657268"
---
# <a name="deprecated-management-tools-features-in-sql-server-2014"></a><span data-ttu-id="94ac4-102">Устаревшие возможности средств управления в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="94ac4-102">Deprecated Management Tools Features in SQL Server 2014</span></span>
  <span data-ttu-id="94ac4-103">В этом разделе описаны устаревшие возможности средств управления, которые все еще доступны в [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94ac4-103">This topic describes the deprecated Management Tools features that are still available in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="94ac4-104">Эти функции будут удалены в следующем выпуске [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94ac4-104">These features are scheduled to be removed in a future release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="94ac4-105">Не следует использовать устаревшие функции в новых приложениях.</span><span class="sxs-lookup"><span data-stu-id="94ac4-105">Deprecated features should not be used in new applications.</span></span>  
  
|<span data-ttu-id="94ac4-106">Признак</span><span class="sxs-lookup"><span data-stu-id="94ac4-106">Feature</span></span>|<span data-ttu-id="94ac4-107">Этап устаревания</span><span class="sxs-lookup"><span data-stu-id="94ac4-107">Deprecation stage</span></span>|  
|-------------|-----------------------|  
|[!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]<span data-ttu-id="94ac4-108">API зарегистрированного сервера</span><span class="sxs-lookup"><span data-stu-id="94ac4-108">Registered Server API</span></span>|<span data-ttu-id="94ac4-109">Объявление</span><span class="sxs-lookup"><span data-stu-id="94ac4-109">Announcement</span></span>|  
|<span data-ttu-id="94ac4-110">sqlps.exe</span><span class="sxs-lookup"><span data-stu-id="94ac4-110">sqlps.exe</span></span>|<span data-ttu-id="94ac4-111">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="94ac4-111">Warning</span></span>|  
|<span data-ttu-id="94ac4-112">osql.exe</span><span class="sxs-lookup"><span data-stu-id="94ac4-112">osql.exe</span></span>|<span data-ttu-id="94ac4-113">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="94ac4-113">Warning</span></span>|  
|<span data-ttu-id="94ac4-114">SQLMail</span><span class="sxs-lookup"><span data-stu-id="94ac4-114">SQLMail</span></span>|<span data-ttu-id="94ac4-115">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="94ac4-115">Warning</span></span>|  
|<span data-ttu-id="94ac4-116">Класс SMO: класс Microsoft.SQLServer.Management.Smo.Information</span><span class="sxs-lookup"><span data-stu-id="94ac4-116">SMO class: Microsoft.SQLServer.Management.Smo.Information class</span></span>|<span data-ttu-id="94ac4-117">Объявление</span><span class="sxs-lookup"><span data-stu-id="94ac4-117">Announcement</span></span>|  
|<span data-ttu-id="94ac4-118">Класс SMO: класс Microsoft.SQLServer.Management.Smo.Settings</span><span class="sxs-lookup"><span data-stu-id="94ac4-118">SMO class: Microsoft.SQLServer.Management.Smo.Settings class</span></span>|<span data-ttu-id="94ac4-119">Объявление</span><span class="sxs-lookup"><span data-stu-id="94ac4-119">Announcement</span></span>|  
|<span data-ttu-id="94ac4-120">Класс SMO: класс Microsoft.SQLServer.Management.Smo.DatabaseOptions</span><span class="sxs-lookup"><span data-stu-id="94ac4-120">SMO Class: Microsoft.SQLServer.Management.Smo.DatabaseOptions class</span></span>|<span data-ttu-id="94ac4-121">Объявление</span><span class="sxs-lookup"><span data-stu-id="94ac4-121">Announcement</span></span>|  
|<span data-ttu-id="94ac4-122">Класс SMO: свойство Microsoft.SqlServer.Management.Smo.DatabaseDdlTrigger.NotForReplication</span><span class="sxs-lookup"><span data-stu-id="94ac4-122">SMO Class: Microsoft.SqlServer.Management.Smo.DatabaseDdlTrigger.NotForReplication property</span></span>|<span data-ttu-id="94ac4-123">Объявление</span><span class="sxs-lookup"><span data-stu-id="94ac4-123">Announcement</span></span>|  
|<span data-ttu-id="94ac4-124">Система проекта базы данных в среде SSMS, включая интеграцию системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="94ac4-124">The Database Project System, including source-control integration, in SSMS</span></span>|<span data-ttu-id="94ac4-125">Объявление</span><span class="sxs-lookup"><span data-stu-id="94ac4-125">Announcement</span></span>|  
|<span data-ttu-id="94ac4-126">Уведомления net send (агент[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="94ac4-126">Net send notifications ([!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent)</span></span>|<span data-ttu-id="94ac4-127">Объявление</span><span class="sxs-lookup"><span data-stu-id="94ac4-127">Announcement</span></span>|  
|<span data-ttu-id="94ac4-128">Уведомления по пейджинговой связи (агент[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="94ac4-128">Pager notifications ([!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent)</span></span>|<span data-ttu-id="94ac4-129">Объявление</span><span class="sxs-lookup"><span data-stu-id="94ac4-129">Announcement</span></span>|  
|<span data-ttu-id="94ac4-130">Подсистема ActiveX (агент[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="94ac4-130">The ActiveX subsystem ([!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent)</span></span>|<span data-ttu-id="94ac4-131">Объявление</span><span class="sxs-lookup"><span data-stu-id="94ac4-131">Announcement</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94ac4-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="94ac4-132">See Also</span></span>  
 [<span data-ttu-id="94ac4-133">Обратная совместимость</span><span class="sxs-lookup"><span data-stu-id="94ac4-133">Backward Compatibility</span></span>](../../2014/getting-started/backward-compatibility.md)  
  
  
