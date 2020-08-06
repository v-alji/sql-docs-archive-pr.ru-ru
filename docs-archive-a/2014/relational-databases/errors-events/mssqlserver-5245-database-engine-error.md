---
title: MSSQLSERVER_ 5245 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5245 (Database Engine error)
ms.assetid: 6005c9ec-ccdd-4def-9eb4-37cdb599ddb3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f98c831642580587552bf60c604d84c38fffca8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667102"
---
# <a name="mssqlserver_5245"></a><span data-ttu-id="6c241-102">MSSQLSERVER_5245</span><span class="sxs-lookup"><span data-stu-id="6c241-102">MSSQLSERVER_5245</span></span>
    
## <a name="details"></a><span data-ttu-id="6c241-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="6c241-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6c241-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="6c241-104">Product Name</span></span>|<span data-ttu-id="6c241-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6c241-105">SQL Server</span></span>|  
|<span data-ttu-id="6c241-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6c241-106">Event ID</span></span>|<span data-ttu-id="6c241-107">5245</span><span class="sxs-lookup"><span data-stu-id="6c241-107">5245</span></span>|  
|<span data-ttu-id="6c241-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="6c241-108">Event Source</span></span>|<span data-ttu-id="6c241-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6c241-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6c241-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="6c241-110">Component</span></span>|<span data-ttu-id="6c241-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6c241-111">SQLEngine</span></span>|  
|<span data-ttu-id="6c241-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="6c241-112">Symbolic Name</span></span>|<span data-ttu-id="6c241-113">DBCC4_TABLE_LOCK_TIMEOUT_EXCEEDED</span><span class="sxs-lookup"><span data-stu-id="6c241-113">DBCC4_TABLE_LOCK_TIMEOUT_EXCEEDED</span></span>|  
|<span data-ttu-id="6c241-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="6c241-114">Message Text</span></span>|<span data-ttu-id="6c241-115">Объект с идентификатором O_ID (объект "имя_объекта"): команде DBCC не удалось заблокировать этот объект из-за превышения времени ожидания запроса на блокировку.</span><span class="sxs-lookup"><span data-stu-id="6c241-115">Object ID O_ID (object 'NAME'): DBCC could not obtain a lock on this object because the lock request time-out period was exceeded.</span></span> <span data-ttu-id="6c241-116">Этот объект пропущен и останется необработанным.</span><span class="sxs-lookup"><span data-stu-id="6c241-116">This object has been skipped and will not be processed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6c241-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="6c241-117">Explanation</span></span>  
 <span data-ttu-id="6c241-118">Истекло время ожидания командой DBCC блокировки таблицы для заданного объекта.</span><span class="sxs-lookup"><span data-stu-id="6c241-118">A lock time-out occurred while DBCC was waiting on a table lock for the specified object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6c241-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="6c241-119">User Action</span></span>  
 <span data-ttu-id="6c241-120">Повторно выполните команду DBCC.</span><span class="sxs-lookup"><span data-stu-id="6c241-120">Rerun the DBCC command.</span></span>  
  
  
