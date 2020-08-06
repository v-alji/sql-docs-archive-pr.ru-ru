---
title: LOCALDB_ERROR_INSTANCE_BUSY | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: 0ed9d0f8-3297-4e31-a3e9-4a827f381789
author: stevestein
ms.author: sstein
ms.openlocfilehash: c587ada5f08d3743f4fe7eafccfc923c38a2b7b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658715"
---
# <a name="localdb_error_instance_busy"></a><span data-ttu-id="55343-102">LOCALDB_ERROR_INSTANCE_BUSY</span><span class="sxs-lookup"><span data-stu-id="55343-102">LOCALDB_ERROR_INSTANCE_BUSY</span></span>
    
## <a name="details"></a><span data-ttu-id="55343-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="55343-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="55343-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="55343-104">Product Name</span></span>|<span data-ttu-id="55343-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="55343-105">SQL Server</span></span>|  
|<span data-ttu-id="55343-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="55343-106">Event ID</span></span>|<span data-ttu-id="55343-107">274</span><span class="sxs-lookup"><span data-stu-id="55343-107">274</span></span>|  
|<span data-ttu-id="55343-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="55343-108">Event Source</span></span>|<span data-ttu-id="55343-109">Среда выполнения локальной базы данных SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="55343-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="55343-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="55343-110">Component</span></span>|<span data-ttu-id="55343-111">API среды выполнения локальной базы данных</span><span class="sxs-lookup"><span data-stu-id="55343-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="55343-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="55343-112">Message Text</span></span>|<span data-ttu-id="55343-113">Запрошенную операцию над экземпляром локальной базы данных выполнить нельзя, так как указанный экземпляр в настоящее время используется.</span><span class="sxs-lookup"><span data-stu-id="55343-113">Requested operation on Local Database instance cannot be performed because specified instance is currently in use.</span></span> <span data-ttu-id="55343-114">Остановите экземпляр и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="55343-114">Stop the instance and try again.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="55343-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="55343-115">Explanation</span></span>  
 <span data-ttu-id="55343-116">Указанный экземпляр выполняется.</span><span class="sxs-lookup"><span data-stu-id="55343-116">The specified instance is running.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="55343-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="55343-117">User Action</span></span>  
 <span data-ttu-id="55343-118">Остановите указанный экземпляр среды выполнения локальной базы данных и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="55343-118">Stop the specified Local Database Runtime instance and try again.</span></span>  
  
  
