---
title: LOCALDB_ERROR_WAIT_TIMEOUT | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: e5b55efa-daa1-4c39-aa71-eeb7707ed601
author: stevestein
ms.author: sstein
ms.openlocfilehash: e3668b32fb48a3e12c33dc15224467307c696af4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728269"
---
# <a name="localdb_error_wait_timeout"></a><span data-ttu-id="258b1-102">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="258b1-102">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>
    
## <a name="details"></a><span data-ttu-id="258b1-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="258b1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="258b1-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="258b1-104">Product Name</span></span>|<span data-ttu-id="258b1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="258b1-105">SQL Server</span></span>|  
|<span data-ttu-id="258b1-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="258b1-106">Event ID</span></span>|<span data-ttu-id="258b1-107">277</span><span class="sxs-lookup"><span data-stu-id="258b1-107">277</span></span>|  
|<span data-ttu-id="258b1-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="258b1-108">Event Source</span></span>|<span data-ttu-id="258b1-109">Среда выполнения локальной базы данных SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="258b1-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="258b1-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="258b1-110">Component</span></span>|<span data-ttu-id="258b1-111">API среды выполнения локальной базы данных</span><span class="sxs-lookup"><span data-stu-id="258b1-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="258b1-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="258b1-112">Message Text</span></span>|<span data-ttu-id="258b1-113">Истекло время ожидания внутри метода API экземпляра локальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="258b1-113">Timeout occurred inside the Local Database instance API method.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="258b1-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="258b1-114">Explanation</span></span>  
 <span data-ttu-id="258b1-115">При попытке получения блокировок синхронизации истекло время ожидания.</span><span class="sxs-lookup"><span data-stu-id="258b1-115">A time-out occurred while trying to acquire synchronization locks.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="258b1-116">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="258b1-116">User Action</span></span>  
 <span data-ttu-id="258b1-117">Повторить попытку запрошенной операции.</span><span class="sxs-lookup"><span data-stu-id="258b1-117">Retry the requested operation again.</span></span>  
  
  
