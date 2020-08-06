---
title: MSSQLSERVER_15599 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15599 (Database Engine error)
ms.assetid: 97e427a9-8587-46ea-954b-974b5df9c223
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 15f1b3eb6d97837f1c1c4a9944535cade5b31300
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667163"
---
# <a name="mssqlserver_15599"></a><span data-ttu-id="5edea-102">MSSQLSERVER_15599</span><span class="sxs-lookup"><span data-stu-id="5edea-102">MSSQLSERVER_15599</span></span>
    
## <a name="details"></a><span data-ttu-id="5edea-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="5edea-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5edea-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="5edea-104">Product Name</span></span>|<span data-ttu-id="5edea-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5edea-105">SQL Server</span></span>|  
|<span data-ttu-id="5edea-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="5edea-106">Event ID</span></span>|<span data-ttu-id="5edea-107">15599</span><span class="sxs-lookup"><span data-stu-id="5edea-107">15599</span></span>|  
|<span data-ttu-id="5edea-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="5edea-108">Event Source</span></span>|<span data-ttu-id="5edea-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5edea-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5edea-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="5edea-110">Component</span></span>|<span data-ttu-id="5edea-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5edea-111">SQLEngine</span></span>|  
|<span data-ttu-id="5edea-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="5edea-112">Symbolic Name</span></span>|<span data-ttu-id="5edea-113">SEC_LOCAL_TEMP_AUDIT_PERMISSIONS</span><span class="sxs-lookup"><span data-stu-id="5edea-113">SEC_LOCAL_TEMP_AUDIT_PERMISSIONS</span></span>|  
|<span data-ttu-id="5edea-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="5edea-114">Message Text</span></span>|<span data-ttu-id="5edea-115">Аудит и разрешения нельзя задать для локальных временных объектов.</span><span class="sxs-lookup"><span data-stu-id="5edea-115">Auditing and permissions can't be set on local temporary objects.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5edea-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="5edea-116">Explanation</span></span>  
 <span data-ttu-id="5edea-117">Аудит и разрешения не работают при установке для локальных или глобальных временных объектов.</span><span class="sxs-lookup"><span data-stu-id="5edea-117">Auditing and permissions do not have any effect when set for local or global temp objects.</span></span> <span data-ttu-id="5edea-118">Инструкция не завершилась ошибкой (возвращен успешный код), но не имела никакого эффекта.</span><span class="sxs-lookup"><span data-stu-id="5edea-118">The statements do not result in an error (the operations will return success), but have no effect.</span></span>  
  
 <span data-ttu-id="5edea-119">Это поведение не изменилось, хотя, начиная с [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], это информационное сообщение предупреждает пользователя.</span><span class="sxs-lookup"><span data-stu-id="5edea-119">This behavior has not changed, however beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], this informational message alerts the user.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5edea-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="5edea-120">User Action</span></span>  
 <span data-ttu-id="5edea-121">Действия не требуются, но подумайте над удалением инструкций, которые пытаются установить аудит или разрешения на локальных или глобальных временных объектах.</span><span class="sxs-lookup"><span data-stu-id="5edea-121">No action is necessary, but consider removing statements that attempt to set auditing or permissions on local or global temp objects.</span></span>  
  
  
