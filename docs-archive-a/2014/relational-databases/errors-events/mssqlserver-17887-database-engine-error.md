---
title: MSSQLSERVER_17887 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17887 (Database Engine error)
ms.assetid: ad0806e6-3296-4c32-b103-fccf0f8a8d3d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 006e616d80ef7e8d083f60675b02b4e6a4e8dc24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655250"
---
# <a name="mssqlserver_17887"></a><span data-ttu-id="c67c4-102">MSSQLSERVER_17887</span><span class="sxs-lookup"><span data-stu-id="c67c4-102">MSSQLSERVER_17887</span></span>
    
## <a name="details"></a><span data-ttu-id="c67c4-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="c67c4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c67c4-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="c67c4-104">Product Name</span></span>|<span data-ttu-id="c67c4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c67c4-105">SQL Server</span></span>|  
|<span data-ttu-id="c67c4-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="c67c4-106">Event ID</span></span>|<span data-ttu-id="c67c4-107">17887</span><span class="sxs-lookup"><span data-stu-id="c67c4-107">17887</span></span>|  
|<span data-ttu-id="c67c4-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="c67c4-108">Event Source</span></span>|<span data-ttu-id="c67c4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c67c4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c67c4-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="c67c4-110">Component</span></span>|<span data-ttu-id="c67c4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c67c4-111">SQLEngine</span></span>|  
|<span data-ttu-id="c67c4-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="c67c4-112">Symbolic Name</span></span>|<span data-ttu-id="c67c4-113">SRV_IO_COMP_LISTENER_NONYIELDING</span><span class="sxs-lookup"><span data-stu-id="c67c4-113">SRV_IO_COMP_LISTENER_NONYIELDING</span></span>|  
|<span data-ttu-id="c67c4-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="c67c4-114">Message Text</span></span>|<span data-ttu-id="c67c4-115">Прослушиватель завершения операций ввода-вывода (0x%lx) исполнитель 0x%p, по-видимому, не возвращает управление узлу %ld.</span><span class="sxs-lookup"><span data-stu-id="c67c4-115">IO Completion Listener (0x%lx) Worker 0x%p appears to be non-yielding on Node %ld.</span></span> <span data-ttu-id="c67c4-116">Примерная загрузка ЦП: ядро %I64d мс, пользователь %I64d мс, интервал: %I64d.</span><span class="sxs-lookup"><span data-stu-id="c67c4-116">Approx CPU Used: kernel %I64d ms, user %I64d ms, Interval: %I64d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c67c4-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="c67c4-117">Explanation</span></span>  
 <span data-ttu-id="c67c4-118">Указывает на возможную проблему прослушивателя порта завершения операций ввода-вывода на указанном узле при выполнении подпрограммы завершения ввода-вывода для сетевого события чтения или записи.</span><span class="sxs-lookup"><span data-stu-id="c67c4-118">Indicates that there is a possible problem with the I/O Completion Port Listener on the specified node when executing the I/O Completion routine for a network read/write event.</span></span> <span data-ttu-id="c67c4-119">Эта ошибка исчезнет, когда прослушиватель порта завершения операций ввода-вывода на указанном узле вернет управление после выполнения подпрограммы завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="c67c4-119">This error will go away when the I/O Completion Port Listener returns from executing the I/O Completion routine.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c67c4-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="c67c4-120">User Action</span></span>  
 <span data-ttu-id="c67c4-121">Обратитесь в службу поддержки пользователей Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c67c4-121">Contact Microsoft Customer Support Services (CSS).</span></span>  
  
  
