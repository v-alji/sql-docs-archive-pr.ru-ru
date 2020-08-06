---
title: LOCALDB_ERROR_INSTANCE_ALREADY_SHARED | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: 35b4d6fa-ebb9-49d3-aaab-d4e37b6f3760
author: stevestein
ms.author: sstein
ms.openlocfilehash: 300f9753b721bc3e0a821a6b77929a9bec09312b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655194"
---
# <a name="localdb_error_instance_already_shared"></a><span data-ttu-id="41d30-102">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span><span class="sxs-lookup"><span data-stu-id="41d30-102">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span></span>
    
## <a name="details"></a><span data-ttu-id="41d30-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="41d30-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="41d30-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="41d30-104">Product Name</span></span>|<span data-ttu-id="41d30-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="41d30-105">SQL Server</span></span>|  
|<span data-ttu-id="41d30-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="41d30-106">Event ID</span></span>|<span data-ttu-id="41d30-107">284</span><span class="sxs-lookup"><span data-stu-id="41d30-107">284</span></span>|  
|<span data-ttu-id="41d30-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="41d30-108">Event Source</span></span>|<span data-ttu-id="41d30-109">Среда выполнения локальной базы данных SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="41d30-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="41d30-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="41d30-110">Component</span></span>|<span data-ttu-id="41d30-111">API среды выполнения локальной базы данных</span><span class="sxs-lookup"><span data-stu-id="41d30-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="41d30-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="41d30-112">Message Text</span></span>|<span data-ttu-id="41d30-113">Указанный экземпляр локальной базы данных уже используется совместно.</span><span class="sxs-lookup"><span data-stu-id="41d30-113">The specified Local Database Instance is already shared.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="41d30-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="41d30-114">Explanation</span></span>  
 <span data-ttu-id="41d30-115">Указанный экземпляр локальной базы данных уже используется совместно под другим общим именем.</span><span class="sxs-lookup"><span data-stu-id="41d30-115">The specified Local Database Instance is already shared with a different shared name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="41d30-116">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="41d30-116">User Action</span></span>  
 <span data-ttu-id="41d30-117">Отключить включенный совместный доступ к экземпляру, прежде чем снова предоставлять его в совместный доступ под другим общим именем.</span><span class="sxs-lookup"><span data-stu-id="41d30-117">Unshare the shared instance before sharing it again with a different shared name.</span></span>  
  
  
