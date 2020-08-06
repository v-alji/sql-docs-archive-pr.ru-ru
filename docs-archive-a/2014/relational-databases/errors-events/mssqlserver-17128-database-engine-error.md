---
title: MSSQLSERVER_17128 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17128 (Database Engine error)
ms.assetid: 7b15a5e6-fd41-47ce-ba87-54f72acea4bb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0e08c668acd0a8b2decb14da338b8d1f1e650de5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730721"
---
# <a name="mssqlserver_17128"></a><span data-ttu-id="2ebc2-102">MSSQLSERVER_17128</span><span class="sxs-lookup"><span data-stu-id="2ebc2-102">MSSQLSERVER_17128</span></span>
    
## <a name="details"></a><span data-ttu-id="2ebc2-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="2ebc2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2ebc2-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="2ebc2-104">Product Name</span></span>|<span data-ttu-id="2ebc2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2ebc2-105">SQL Server</span></span>|  
|<span data-ttu-id="2ebc2-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="2ebc2-106">Event ID</span></span>|<span data-ttu-id="2ebc2-107">17128</span><span class="sxs-lookup"><span data-stu-id="2ebc2-107">17128</span></span>|  
|<span data-ttu-id="2ebc2-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="2ebc2-108">Event Source</span></span>|<span data-ttu-id="2ebc2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2ebc2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2ebc2-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="2ebc2-110">Component</span></span>|<span data-ttu-id="2ebc2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2ebc2-111">SQLEngine</span></span>|  
|<span data-ttu-id="2ebc2-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="2ebc2-112">Symbolic Name</span></span>|<span data-ttu-id="2ebc2-113">INIT_NOBUFSPACE</span><span class="sxs-lookup"><span data-stu-id="2ebc2-113">INIT_NOBUFSPACE</span></span>|  
|<span data-ttu-id="2ebc2-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="2ebc2-114">Message Text</span></span>|<span data-ttu-id="2ebc2-115">initdata: недостаточно памяти для буферов ядра.</span><span class="sxs-lookup"><span data-stu-id="2ebc2-115">initdata: No memory for kernel buffers.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2ebc2-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="2ebc2-116">Explanation</span></span>  
 <span data-ttu-id="2ebc2-117">Не удается провести начальное выделение памяти из буферного пула или резервирование памяти. SQL Server завершает работу.</span><span class="sxs-lookup"><span data-stu-id="2ebc2-117">The buffer pool's initial memory allocations or reservations have failed, and SQL Server exits.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2ebc2-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="2ebc2-118">User Action</span></span>  
 <span data-ttu-id="2ebc2-119">Эта обычно случается при запуске SQL Server на очень маломощном компьютере, параметры которого не достигают минимальных требований к системе.</span><span class="sxs-lookup"><span data-stu-id="2ebc2-119">Usually caused by starting SQL Server on an extremely small machine - far smaller than the minimum system requirements.</span></span>  
  
  
