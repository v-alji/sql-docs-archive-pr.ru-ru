---
title: LOCALDB_ERROR_TOO_MANY_SHARED_INSTANCES | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: c1595263-6264-4a43-9535-5eb76ece3a57
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0896f3e70e6c65a1fcd0de4169249fb622e6b5f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655188"
---
# <a name="localdb_error_too_many_shared_instances"></a><span data-ttu-id="eb5b7-102">LOCALDB_ERROR_TOO_MANY_SHARED_INSTANCES</span><span class="sxs-lookup"><span data-stu-id="eb5b7-102">LOCALDB_ERROR_TOO_MANY_SHARED_INSTANCES</span></span>
    
## <a name="details"></a><span data-ttu-id="eb5b7-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="eb5b7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eb5b7-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="eb5b7-104">Product Name</span></span>|<span data-ttu-id="eb5b7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="eb5b7-105">SQL Server</span></span>|  
|<span data-ttu-id="eb5b7-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="eb5b7-106">Event ID</span></span>|<span data-ttu-id="eb5b7-107">287</span><span class="sxs-lookup"><span data-stu-id="eb5b7-107">287</span></span>|  
|<span data-ttu-id="eb5b7-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="eb5b7-108">Event Source</span></span>|<span data-ttu-id="eb5b7-109">Среда выполнения локальной базы данных SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="eb5b7-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="eb5b7-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="eb5b7-110">Component</span></span>|<span data-ttu-id="eb5b7-111">API среды выполнения локальной базы данных</span><span class="sxs-lookup"><span data-stu-id="eb5b7-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="eb5b7-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="eb5b7-112">Message Text</span></span>|<span data-ttu-id="eb5b7-113">Общих экземпляров слишком много, и создать уникальное имя пользовательского экземпляра не удается.</span><span class="sxs-lookup"><span data-stu-id="eb5b7-113">There are too many shared instance and we cannot generate unique User Instance Name.</span></span> <span data-ttu-id="eb5b7-114">Отключите совместный доступ к некоторым из существующих общих экземпляров.</span><span class="sxs-lookup"><span data-stu-id="eb5b7-114">Unshare some of the existing shared instances.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="eb5b7-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="eb5b7-115">Explanation</span></span>  
 <span data-ttu-id="eb5b7-116">Общих экземпляров слишком много, и создать уникальное имя пользовательского экземпляра не удается.</span><span class="sxs-lookup"><span data-stu-id="eb5b7-116">There are too many shared instance and we cannot generate unique User Instance Name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eb5b7-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="eb5b7-117">User Action</span></span>  
 <span data-ttu-id="eb5b7-118">Отключите совместный доступ к одному или нескольким общим экземплярам среды выполнения локальной базы данных и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="eb5b7-118">Unshare one or more of the shared Local Database Runtime instances and try again.</span></span>  
  
  
