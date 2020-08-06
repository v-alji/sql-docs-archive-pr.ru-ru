---
title: MSSQLSERVER_3452 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3452 (Database Engine error)
ms.assetid: bf838f02-7186-4b33-b01e-361b0c02de1f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 662d342064e8094400a6b672e21704877b4d0448
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654314"
---
# <a name="mssqlserver_3452"></a><span data-ttu-id="187cf-102">MSSQLSERVER_3452</span><span class="sxs-lookup"><span data-stu-id="187cf-102">MSSQLSERVER_3452</span></span>
    
## <a name="details"></a><span data-ttu-id="187cf-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="187cf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="187cf-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="187cf-104">Product Name</span></span>|<span data-ttu-id="187cf-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="187cf-105">SQL Server</span></span>|  
|<span data-ttu-id="187cf-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="187cf-106">Event ID</span></span>|<span data-ttu-id="187cf-107">3452</span><span class="sxs-lookup"><span data-stu-id="187cf-107">3452</span></span>|  
|<span data-ttu-id="187cf-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="187cf-108">Event Source</span></span>|<span data-ttu-id="187cf-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="187cf-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="187cf-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="187cf-110">Component</span></span>|<span data-ttu-id="187cf-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="187cf-111">SQLEngine</span></span>|  
|<span data-ttu-id="187cf-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="187cf-112">Symbolic Name</span></span>|<span data-ttu-id="187cf-113">REC_CHECKIDENTITY</span><span class="sxs-lookup"><span data-stu-id="187cf-113">REC_CHECKIDENTITY</span></span>|  
|<span data-ttu-id="187cf-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="187cf-114">Message Text</span></span>|<span data-ttu-id="187cf-115">Процедура восстановления базы данных «%.\*ls» (%d) обнаружила возможное несовпадение тождественных значений в таблице со значением идентификатора %d.</span><span class="sxs-lookup"><span data-stu-id="187cf-115">Recovery of database '%.\*ls' (%d) detected possible identity value inconsistency in table ID %d.</span></span> <span data-ttu-id="187cf-116">Запустите процедуру DBCC CHECKIDENT ("%.\*ls").</span><span class="sxs-lookup"><span data-stu-id="187cf-116">Run DBCC CHECKIDENT ('%.\*ls').</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="187cf-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="187cf-117">Explanation</span></span>  
 <span data-ttu-id="187cf-118">Во время обновления сервера до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] процесс восстановления значений идентификаторов в базе данных обнаружил несогласованность в метаданных.</span><span class="sxs-lookup"><span data-stu-id="187cf-118">During the upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the process to recover the identity values in the database found an inconsistency in the metadata.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="187cf-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="187cf-119">User Action</span></span>  
 <span data-ttu-id="187cf-120">Выполнить команду DBCC CHECKIDENT.</span><span class="sxs-lookup"><span data-stu-id="187cf-120">Run DBCC CHECKIDENT.</span></span>  
  
  
