---
title: LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: a7c5ce08-8841-49a3-b252-116807ba469a
author: stevestein
ms.author: sstein
ms.openlocfilehash: aa6db2af138bb2aeefb1a922e55db56c4ea821f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752187"
---
# <a name="localdb_error_instance_exists_with_lower_version"></a><span data-ttu-id="d2ac9-102">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span><span class="sxs-lookup"><span data-stu-id="d2ac9-102">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span></span>
    
## <a name="details"></a><span data-ttu-id="d2ac9-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="d2ac9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d2ac9-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="d2ac9-104">Product Name</span></span>|<span data-ttu-id="d2ac9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d2ac9-105">SQL Server</span></span>|  
|<span data-ttu-id="d2ac9-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="d2ac9-106">Event ID</span></span>|<span data-ttu-id="d2ac9-107">258</span><span class="sxs-lookup"><span data-stu-id="d2ac9-107">258</span></span>|  
|<span data-ttu-id="d2ac9-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="d2ac9-108">Event Source</span></span>|<span data-ttu-id="d2ac9-109">Среда выполнения локальной базы данных SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="d2ac9-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="d2ac9-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="d2ac9-110">Component</span></span>|<span data-ttu-id="d2ac9-111">API среды выполнения локальной базы данных</span><span class="sxs-lookup"><span data-stu-id="d2ac9-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="d2ac9-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="d2ac9-112">Message Text</span></span>|<span data-ttu-id="d2ac9-113">Не удалось создать экземпляр локальной базы данных с указанной версией.</span><span class="sxs-lookup"><span data-stu-id="d2ac9-113">Unable to create the Local Database instance with specified version.</span></span> <span data-ttu-id="d2ac9-114">Экземпляр с таким именем уже существует, но его версия более ранняя.</span><span class="sxs-lookup"><span data-stu-id="d2ac9-114">An instance with the same name already exists, but it has lower version than the specified version.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d2ac9-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="d2ac9-115">Explanation</span></span>  
 <span data-ttu-id="d2ac9-116">Указанный экземпляр уже существует, но его версия ниже запрошенной.</span><span class="sxs-lookup"><span data-stu-id="d2ac9-116">The specified instance already exists but its version is lower than requested.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d2ac9-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="d2ac9-117">User Action</span></span>  
 <span data-ttu-id="d2ac9-118">Удалите существующий экземпляр и повторите операцию.</span><span class="sxs-lookup"><span data-stu-id="d2ac9-118">Delete the existing instance and retry the operation.</span></span>  
  
  
