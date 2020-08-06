---
title: MSSQLSERVER_17132 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17132 (Database Engine error)
ms.assetid: d1d198bd-6730-4394-bd5f-28f320c01a38
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 609b9cea138db15cefd002f494620b5a1da7b208
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731673"
---
# <a name="mssqlserver_17132"></a><span data-ttu-id="07b3a-102">MSSQLSERVER_17132</span><span class="sxs-lookup"><span data-stu-id="07b3a-102">MSSQLSERVER_17132</span></span>
    
## <a name="details"></a><span data-ttu-id="07b3a-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="07b3a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07b3a-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="07b3a-104">Product Name</span></span>|<span data-ttu-id="07b3a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="07b3a-105">SQL Server</span></span>|  
|<span data-ttu-id="07b3a-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="07b3a-106">Event ID</span></span>|<span data-ttu-id="07b3a-107">17132</span><span class="sxs-lookup"><span data-stu-id="07b3a-107">17132</span></span>|  
|<span data-ttu-id="07b3a-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="07b3a-108">Event Source</span></span>|<span data-ttu-id="07b3a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="07b3a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="07b3a-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="07b3a-110">Component</span></span>|<span data-ttu-id="07b3a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="07b3a-111">SQLEngine</span></span>|  
|<span data-ttu-id="07b3a-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="07b3a-112">Symbolic Name</span></span>|<span data-ttu-id="07b3a-113">INIT_NODESSPACE</span><span class="sxs-lookup"><span data-stu-id="07b3a-113">INIT_NODESSPACE</span></span>|  
|<span data-ttu-id="07b3a-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="07b3a-114">Message Text</span></span>|<span data-ttu-id="07b3a-115">Не удалось запустить сервер из-за нехватки памяти для дескриптора.</span><span class="sxs-lookup"><span data-stu-id="07b3a-115">Server startup failed due to insufficient memory for descriptor.</span></span> <span data-ttu-id="07b3a-116">Отмените необязательные операции с памятью или увеличьте объем системной памяти.</span><span class="sxs-lookup"><span data-stu-id="07b3a-116">Reduce non-essential memory load or increase system memory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="07b3a-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="07b3a-117">Explanation</span></span>  
 <span data-ttu-id="07b3a-118">Не удалось выделить достаточный объем памяти для хранения внутреннего дескриптора сервера.</span><span class="sxs-lookup"><span data-stu-id="07b3a-118">Failed to allocate enough memory to store server internal descriptor.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="07b3a-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="07b3a-119">User Action</span></span>  
 <span data-ttu-id="07b3a-120">Увеличьте объем памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="07b3a-120">Add more memory to the machine.</span></span> <span data-ttu-id="07b3a-121">Возможно, окажутся полезными общие шаги по устранению неполадок с памятью.</span><span class="sxs-lookup"><span data-stu-id="07b3a-121">Generic memory troubleshooting steps may be useful.</span></span>  
  
  
