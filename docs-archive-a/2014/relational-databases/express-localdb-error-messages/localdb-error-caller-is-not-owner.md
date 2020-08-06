---
title: LOCALDB_ERROR_CALLER_IS_NOT_OWNER | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: f3303072-2b44-4443-936c-f024b0b2a8c5
author: stevestein
ms.author: sstein
ms.openlocfilehash: ce4fd6d84929ce7d1338f5fd688d3c24f1e1858a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668363"
---
# <a name="localdb_error_caller_is_not_owner"></a><span data-ttu-id="3b429-102">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3b429-102">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span></span>
    
## <a name="details"></a><span data-ttu-id="3b429-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="3b429-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3b429-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="3b429-104">Product Name</span></span>|<span data-ttu-id="3b429-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3b429-105">SQL Server</span></span>|  
|<span data-ttu-id="3b429-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="3b429-106">Event ID</span></span>|<span data-ttu-id="3b429-107">282</span><span class="sxs-lookup"><span data-stu-id="3b429-107">282</span></span>|  
|<span data-ttu-id="3b429-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="3b429-108">Event Source</span></span>|<span data-ttu-id="3b429-109">Среда выполнения локальной базы данных SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="3b429-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="3b429-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="3b429-110">Component</span></span>|<span data-ttu-id="3b429-111">API среды выполнения локальной базы данных</span><span class="sxs-lookup"><span data-stu-id="3b429-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="3b429-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="3b429-112">Message Text</span></span>|<span data-ttu-id="3b429-113">Вызывающий API не является владельцем экземпляра локальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="3b429-113">API caller is not Local Database instance owner.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3b429-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="3b429-114">Explanation</span></span>  
 <span data-ttu-id="3b429-115">Пользователю необходимо быть владельцем экземпляра, чтобы иметь возможность выполнить запрошенную операцию.</span><span class="sxs-lookup"><span data-stu-id="3b429-115">User needs to be the instance owner to be able to execute the requested operation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3b429-116">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="3b429-116">User Action</span></span>  
 <span data-ttu-id="3b429-117">Обратитесь к владельцу экземпляра за помощью.</span><span class="sxs-lookup"><span data-stu-id="3b429-117">Contact the instance owner for help.</span></span>  
  
  
