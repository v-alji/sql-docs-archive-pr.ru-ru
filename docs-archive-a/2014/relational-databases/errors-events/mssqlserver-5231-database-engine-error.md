---
title: MSSQLSERVER_5231 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5231 (Database Engine error)
ms.assetid: 6954ae84-ed0b-4f4c-9d0a-e73f3d71476c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 68f40ac3a566280526757bd8b83c784954ba3dde
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729502"
---
# <a name="mssqlserver_5231"></a><span data-ttu-id="1ff85-102">MSSQLSERVER_5231</span><span class="sxs-lookup"><span data-stu-id="1ff85-102">MSSQLSERVER_5231</span></span>
    
## <a name="details"></a><span data-ttu-id="1ff85-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="1ff85-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ff85-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="1ff85-104">Product Name</span></span>|<span data-ttu-id="1ff85-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1ff85-105">SQL Server</span></span>|  
|<span data-ttu-id="1ff85-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="1ff85-106">Event ID</span></span>|<span data-ttu-id="1ff85-107">5231</span><span class="sxs-lookup"><span data-stu-id="1ff85-107">5231</span></span>|  
|<span data-ttu-id="1ff85-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="1ff85-108">Event Source</span></span>|<span data-ttu-id="1ff85-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1ff85-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1ff85-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="1ff85-110">Component</span></span>|<span data-ttu-id="1ff85-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1ff85-111">SQLEngine</span></span>|  
|<span data-ttu-id="1ff85-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="1ff85-112">Symbolic Name</span></span>|<span data-ttu-id="1ff85-113">DBCC4_DEADLOCK_SKIPPED_OBJECT</span><span class="sxs-lookup"><span data-stu-id="1ff85-113">DBCC4_DEADLOCK_SKIPPED_OBJECT</span></span>|  
|<span data-ttu-id="1ff85-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="1ff85-114">Message Text</span></span>|<span data-ttu-id="1ff85-115">Объект с идентификатором O_ID (объект "имя_объекта"): произошла взаимоблокировка при попытке заблокировать данный объект для проверки.</span><span class="sxs-lookup"><span data-stu-id="1ff85-115">Object ID O_ID (object 'NAME'): A deadlock occurred while trying to lock this object for checking.</span></span> <span data-ttu-id="1ff85-116">Этот объект пропущен и останется необработанным.</span><span class="sxs-lookup"><span data-stu-id="1ff85-116">This object has been skipped and will not be processed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1ff85-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="1ff85-117">Explanation</span></span>  
 <span data-ttu-id="1ff85-118">Произошла взаимоблокировка при попытке команды DBCC заблокировать объект, команда DBCC была выбрана жертвой взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="1ff85-118">A deadlock occurred when DBCC was trying to lock the object, and DBCC was chosen as the deadlock victim.</span></span> <span data-ttu-id="1ff85-119">Объект не будет обработан.</span><span class="sxs-lookup"><span data-stu-id="1ff85-119">The object will not be processed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1ff85-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="1ff85-120">User Action</span></span>  
 <span data-ttu-id="1ff85-121">None</span><span class="sxs-lookup"><span data-stu-id="1ff85-121">None</span></span>  
  
  
