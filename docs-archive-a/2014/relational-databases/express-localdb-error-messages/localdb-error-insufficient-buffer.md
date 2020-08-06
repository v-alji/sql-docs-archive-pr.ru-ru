---
title: LOCALDB_ERROR_INSUFFICIENT_BUFFER | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: ff67bda8-7e5c-4b06-8d7b-9985b6059a98
author: stevestein
ms.author: sstein
ms.openlocfilehash: 934683cfca1a9a9c0596071824c21a0045e6ebab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668348"
---
# <a name="localdb_error_insufficient_buffer"></a><span data-ttu-id="46fa1-102">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="46fa1-102">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>
    
## <a name="details"></a><span data-ttu-id="46fa1-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="46fa1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46fa1-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="46fa1-104">Product Name</span></span>|<span data-ttu-id="46fa1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="46fa1-105">SQL Server</span></span>|  
|<span data-ttu-id="46fa1-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="46fa1-106">Event ID</span></span>|<span data-ttu-id="46fa1-107">276</span><span class="sxs-lookup"><span data-stu-id="46fa1-107">276</span></span>|  
|<span data-ttu-id="46fa1-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="46fa1-108">Event Source</span></span>|<span data-ttu-id="46fa1-109">Среда выполнения локальной базы данных SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="46fa1-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="46fa1-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="46fa1-110">Component</span></span>|<span data-ttu-id="46fa1-111">API среды выполнения локальной базы данных</span><span class="sxs-lookup"><span data-stu-id="46fa1-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="46fa1-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="46fa1-112">Message Text</span></span>|<span data-ttu-id="46fa1-113">Буфер, переданный методу API экземпляра локальной базы данных, имеет недостаточный размер.</span><span class="sxs-lookup"><span data-stu-id="46fa1-113">The buffer passed to the Local Database instance API method has insufficient size.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="46fa1-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="46fa1-114">Explanation</span></span>  
 <span data-ttu-id="46fa1-115">Размер входного буфера является недостаточным, а усечение не было запрошено.</span><span class="sxs-lookup"><span data-stu-id="46fa1-115">The input buffer is too short, and truncation was not requested.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="46fa1-116">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="46fa1-116">User Action</span></span>  
 <span data-ttu-id="46fa1-117">Предоставьте буфер указанного размера.</span><span class="sxs-lookup"><span data-stu-id="46fa1-117">Provide a buffer of the specified size.</span></span>  
  
  
