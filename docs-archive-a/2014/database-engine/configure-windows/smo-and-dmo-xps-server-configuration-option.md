---
title: Параметр конфигурации сервера "SMO and DMO XPs" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: bcd945ba-5d81-4124-9a2b-d87491c2a369
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f18fc6fafcf033113c983f990700158a10aec92a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740409"
---
# <a name="smo-and-dmo-xps-server-configuration-option"></a><span data-ttu-id="93791-102">Параметр конфигурации сервера «SMO and DMO XPs»</span><span class="sxs-lookup"><span data-stu-id="93791-102">SMO and DMO XPs Server Configuration Option</span></span>
  <span data-ttu-id="93791-103">С помощью параметра «SMO and DMO XPs» включите расширенные хранимые процедуры управляющих объектов (SMO) [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="93791-103">Use the SMO and DMO XPs option to enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Object (SMO) extended stored procedures on this server.</span></span>  
  
 <span data-ttu-id="93791-104">Обратите внимание, что, начиная с версии [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], объекты DMO были удалены из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93791-104">Note than beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], DMO has been removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="93791-105">Возможные значения описаны в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="93791-105">The possible values are described in the following table:</span></span>  
  
|<span data-ttu-id="93791-106">Значение</span><span class="sxs-lookup"><span data-stu-id="93791-106">Value</span></span>|<span data-ttu-id="93791-107">Значение</span><span class="sxs-lookup"><span data-stu-id="93791-107">Meaning</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="93791-108">0</span><span class="sxs-lookup"><span data-stu-id="93791-108">0</span></span>|<span data-ttu-id="93791-109">Расширенные хранимые процедуры объектов SMO недоступны.</span><span class="sxs-lookup"><span data-stu-id="93791-109">SMO XPs are not available.</span></span>|  
|<span data-ttu-id="93791-110">1</span><span class="sxs-lookup"><span data-stu-id="93791-110">1</span></span>|<span data-ttu-id="93791-111">Расширенные хранимые процедуры объектов SMO доступны.</span><span class="sxs-lookup"><span data-stu-id="93791-111">SMO XPs are available.</span></span> <span data-ttu-id="93791-112">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="93791-112">This is the default.</span></span>|  
  
 <span data-ttu-id="93791-113">Изменение параметров вступает в силу немедленно.</span><span class="sxs-lookup"><span data-stu-id="93791-113">The setting takes effect immediately.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="93791-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="93791-114">Examples</span></span>  
 <span data-ttu-id="93791-115">В следующем примере активируются расширенные хранимые процедуры объектов SMO.</span><span class="sxs-lookup"><span data-stu-id="93791-115">The following example enables SMO extended stored procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'SMO and DMO XPs', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="93791-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="93791-116">See Also</span></span>  
 [<span data-ttu-id="93791-117">Учебник по программированию управляющих объектов SQL Server (SMO)</span><span class="sxs-lookup"><span data-stu-id="93791-117">SQL Server Management Objects &#40;SMO&#41; Programming Guide</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
  
