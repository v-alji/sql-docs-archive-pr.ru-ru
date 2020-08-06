---
title: MSSQLSERVER_12304 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 12304 (Database Engine error)
ms.assetid: a2c252c2-e815-4ac8-a101-7af5b32e3233
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c2347fc46fe5ab83ef2ff46b81500cd737ed02d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665378"
---
# <a name="mssqlserver_12304"></a><span data-ttu-id="1fcc2-102">MSSQLSERVER_12304</span><span class="sxs-lookup"><span data-stu-id="1fcc2-102">MSSQLSERVER_12304</span></span>
    
## <a name="details"></a><span data-ttu-id="1fcc2-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="1fcc2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1fcc2-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="1fcc2-104">Product Name</span></span>|<span data-ttu-id="1fcc2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1fcc2-105">SQL Server</span></span>|  
|<span data-ttu-id="1fcc2-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="1fcc2-106">Event ID</span></span>|<span data-ttu-id="1fcc2-107">12304</span><span class="sxs-lookup"><span data-stu-id="1fcc2-107">12304</span></span>|  
|<span data-ttu-id="1fcc2-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="1fcc2-108">Event Source</span></span>|<span data-ttu-id="1fcc2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1fcc2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1fcc2-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="1fcc2-110">Component</span></span>|<span data-ttu-id="1fcc2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1fcc2-111">SQLEngine</span></span>|  
|<span data-ttu-id="1fcc2-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="1fcc2-112">Symbolic Name</span></span>|<span data-ttu-id="1fcc2-113">HK_UNSUPPORTED_IDENTITY_TABLE_VAR</span><span class="sxs-lookup"><span data-stu-id="1fcc2-113">HK_UNSUPPORTED_IDENTITY_TABLE_VAR</span></span>|  
|<span data-ttu-id="1fcc2-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="1fcc2-114">Message Text</span></span>|<span data-ttu-id="1fcc2-115">Использование табличного типа, оптимизированного для памяти, который использует свойство IDENTITY не поддерживается с любым из его столбцов при использовании типа вне контекста изначально компилированной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="1fcc2-115">Using a memory optimized table type that uses the IDENTITY property with any of its columns is not supported when using the type outside the context of a natively compiled stored procedure.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="1fcc2-116">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="1fcc2-116">User Action</span></span>  
 <span data-ttu-id="1fcc2-117">Не используйте тип памяти, оптимизированный для памяти, который использует свойство IDENTITY с любым из его столбцов.</span><span class="sxs-lookup"><span data-stu-id="1fcc2-117">Do not use a memory-optimized table type that uses the identity property with any of its columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fcc2-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="1fcc2-118">See Also</span></span>  
 [<span data-ttu-id="1fcc2-119">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="1fcc2-119">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
