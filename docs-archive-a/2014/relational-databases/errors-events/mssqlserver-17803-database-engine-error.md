---
title: MSSQLSERVER_17803 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17803 (Database Engine error)
ms.assetid: 28591a19-258d-4891-b78a-4686789bb2d7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8be63b3d05bff2ebf90122f66af4297d77376fce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667148"
---
# <a name="mssqlserver_17803"></a><span data-ttu-id="9b431-102">MSSQLSERVER_17803</span><span class="sxs-lookup"><span data-stu-id="9b431-102">MSSQLSERVER_17803</span></span>
    
## <a name="details"></a><span data-ttu-id="9b431-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="9b431-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9b431-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="9b431-104">Product Name</span></span>|<span data-ttu-id="9b431-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9b431-105">SQL Server</span></span>|  
|<span data-ttu-id="9b431-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="9b431-106">Event ID</span></span>|<span data-ttu-id="9b431-107">17803</span><span class="sxs-lookup"><span data-stu-id="9b431-107">17803</span></span>|  
|<span data-ttu-id="9b431-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="9b431-108">Event Source</span></span>|<span data-ttu-id="9b431-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9b431-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9b431-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="9b431-110">Component</span></span>|<span data-ttu-id="9b431-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9b431-111">SQLEngine</span></span>|  
|<span data-ttu-id="9b431-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="9b431-112">Symbolic Name</span></span>|<span data-ttu-id="9b431-113">SRV_NOMEMORY</span><span class="sxs-lookup"><span data-stu-id="9b431-113">SRV_NOMEMORY</span></span>|  
|<span data-ttu-id="9b431-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="9b431-114">Message Text</span></span>|<span data-ttu-id="9b431-115">Во время установления соединения произошла ошибка выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="9b431-115">There was a memory allocation failure during connection establishment.</span></span> <span data-ttu-id="9b431-116">Сократите необязательный расход памяти или увеличьте объем системной памяти.</span><span class="sxs-lookup"><span data-stu-id="9b431-116">Reduce nonessential memory load, or increase system memory.</span></span> <span data-ttu-id="9b431-117">Соединение было закрыто.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="9b431-117">The connection has been closed.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9b431-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="9b431-118">Explanation</span></span>  
 <span data-ttu-id="9b431-119">Серверу не хватает памяти.</span><span class="sxs-lookup"><span data-stu-id="9b431-119">Server is running out of memory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9b431-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="9b431-120">User Action</span></span>  
 <span data-ttu-id="9b431-121">Определите причину нехватки памяти на сервере.</span><span class="sxs-lookup"><span data-stu-id="9b431-121">Determine the cause for server running out of memory.</span></span> <span data-ttu-id="9b431-122">Возможно, окажутся полезными общие шаги по устранению неполадок с памятью.</span><span class="sxs-lookup"><span data-stu-id="9b431-122">Generic memory troubleshooting steps may be useful</span></span>  
  
  
