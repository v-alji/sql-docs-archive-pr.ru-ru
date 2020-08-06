---
title: MSSQLSERVER_15517 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15517 (Database Engine error)
ms.assetid: f94287f5-129f-4c52-9d34-62b996088001
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b8e66e211faf03e1457953d0292e711cde1798ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667165"
---
# <a name="mssqlserver_15517"></a><span data-ttu-id="a275d-102">MSSQLSERVER_15517</span><span class="sxs-lookup"><span data-stu-id="a275d-102">MSSQLSERVER_15517</span></span>
    
## <a name="details"></a><span data-ttu-id="a275d-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="a275d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a275d-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a275d-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="a275d-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a275d-105">Event ID</span></span>|<span data-ttu-id="a275d-106">15517</span><span class="sxs-lookup"><span data-stu-id="a275d-106">15517</span></span>|  
|<span data-ttu-id="a275d-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="a275d-107">Event Source</span></span>|<span data-ttu-id="a275d-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a275d-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a275d-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="a275d-109">Component</span></span>|<span data-ttu-id="a275d-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a275d-110">SQLEngine</span></span>|  
|<span data-ttu-id="a275d-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="a275d-111">Symbolic Name</span></span>|<span data-ttu-id="a275d-112">SEC_CANNOTEXECUTEASUSER</span><span class="sxs-lookup"><span data-stu-id="a275d-112">SEC_CANNOTEXECUTEASUSER</span></span>|  
|<span data-ttu-id="a275d-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a275d-113">Message Text</span></span>|<span data-ttu-id="a275d-114">Невозможно выполнить в качестве участника базы данных, поскольку участник "*участник*" не существует, этот тип участника не может проходить олицетворение или отсутствует разрешение.</span><span class="sxs-lookup"><span data-stu-id="a275d-114">Cannot execute as the database principal because the principal "*principal*" does not exist, this type of principal cannot be impersonated, or you do not have permission.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="a275d-115">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a275d-115">User Action</span></span>  
 <span data-ttu-id="a275d-116">Используйте имя существующего участника или получите разрешение IMPERSONATE для этого участника.</span><span class="sxs-lookup"><span data-stu-id="a275d-116">Use the name of an existing principal or get the IMPERSONATE permission on that principal.</span></span>  
  
 <span data-ttu-id="a275d-117">15517 может также возникнуть после присоединения и восстановления базы данных пользователем, который не является ее изначальным владельцем.</span><span class="sxs-lookup"><span data-stu-id="a275d-117">15517 can also occur after performing an attach and restore of a database by someone other than the original database owner.</span></span> <span data-ttu-id="a275d-118">Чтобы устранить эту ошибку, измените db_owner на имя входа на сервере с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="a275d-118">To resolve this error, change the db_owner to a login on your server, by running the following command:</span></span>  
  
```  
ALTER AUTHORIZATION ON DATABASE:: DBName TO [NewLogin]  
```  
  
## <a name="see-also"></a><span data-ttu-id="a275d-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="a275d-119">See Also</span></span>  
 [<span data-ttu-id="a275d-120">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="a275d-120">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
