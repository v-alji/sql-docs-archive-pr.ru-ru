---
title: MSSQLSERVER_33081 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33081 (Database Engine error)
ms.assetid: 839705e7-fa37-4c0d-9f3f-95a9eab98bcf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0752220cc20641d9b51a3a66fecc86f9efd63433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658773"
---
# <a name="mssqlserver_33081"></a><span data-ttu-id="030a2-102">MSSQLSERVER_33081</span><span class="sxs-lookup"><span data-stu-id="030a2-102">MSSQLSERVER_33081</span></span>
    
## <a name="details"></a><span data-ttu-id="030a2-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="030a2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="030a2-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="030a2-104">Product Name</span></span>|<span data-ttu-id="030a2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="030a2-105">SQL Server</span></span>|  
|<span data-ttu-id="030a2-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="030a2-106">Event ID</span></span>|<span data-ttu-id="030a2-107">33081</span><span class="sxs-lookup"><span data-stu-id="030a2-107">33081</span></span>|  
|<span data-ttu-id="030a2-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="030a2-108">Event Source</span></span>|<span data-ttu-id="030a2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="030a2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="030a2-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="030a2-110">Component</span></span>|<span data-ttu-id="030a2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="030a2-111">SQLEngine</span></span>|  
|<span data-ttu-id="030a2-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="030a2-112">Symbolic Name</span></span>|<span data-ttu-id="030a2-113">SEC_DLL_TRUST_VERIFICATION_FAILED</span><span class="sxs-lookup"><span data-stu-id="030a2-113">SEC_DLL_TRUST_VERIFICATION_FAILED</span></span>|  
|<span data-ttu-id="030a2-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="030a2-114">Message Text</span></span>|<span data-ttu-id="030a2-115">Не удалось загрузить поставщик служб шифрования "%.\*ls" из-за недействительной подписи Authenticode или недействительного пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="030a2-115">Failed to load cryptographic provider '%.\*ls' due to an invalid Authenticode signature or invalid file path.</span></span>  <span data-ttu-id="030a2-116">Проверьте наличие других ошибок в предыдущих сообщениях.</span><span class="sxs-lookup"><span data-stu-id="030a2-116">Check previous messages for other failures.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="030a2-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="030a2-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="030a2-118">не смог загрузить поставщик служб шифрования, указанный в сообщении об ошибке.</span><span class="sxs-lookup"><span data-stu-id="030a2-118">was unable to load the cryptographic provider listed in the error message.</span></span> <span data-ttu-id="030a2-119">Существует несколько ошибок Win API, которые могут вызвать эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="030a2-119">There are several Win API failures which might cause this error.</span></span> <span data-ttu-id="030a2-120">Кольцевой буфер содержит имя ошибочного API и код ошибки Windows, возвращенный API.</span><span class="sxs-lookup"><span data-stu-id="030a2-120">The ring buffer contains the name of the failed API and the Windows error code returned by the API.</span></span> <span data-ttu-id="030a2-121">Чтобы получить дополнительные сведения, выполните следующий запрос к представлению sys.dm_os_ring_buffers.</span><span class="sxs-lookup"><span data-stu-id="030a2-121">To get more information, query the sys.dm_os_ring_buffers view using the following query.</span></span>  
  
```  
SELECT * FROM sys.dm_os_ring_buffers   
WHERE ring_buffer_type = 'RING_BUFFER_SECURITY_ERROR';  
```  
  
## <a name="user-action"></a><span data-ttu-id="030a2-122">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="030a2-122">User Action</span></span>  
 <span data-ttu-id="030a2-123">Чтобы исследовать эту проблему, выполните поиск кода ошибки Windows в MSDN (https://msdn.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="030a2-123">To investigate the problem, search for the Windows error code in MSDN (https://msdn.microsoft.com/).</span></span> <span data-ttu-id="030a2-124">Устраните ошибку или обратитесь к службу поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] за дополнительными сведениями.</span><span class="sxs-lookup"><span data-stu-id="030a2-124">Resolve the error, or contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] CSS for more information.</span></span> <span data-ttu-id="030a2-125">Перед обращением в службу поддержки пользователей соберите следующие данные.</span><span class="sxs-lookup"><span data-stu-id="030a2-125">If you need to contact CSS, collect the following information for our support staff.</span></span>  
  
-   <span data-ttu-id="030a2-126">Журнал ошибок, отображающий ошибку загрузки поставщика служб шифрования.</span><span class="sxs-lookup"><span data-stu-id="030a2-126">The error log showing the failed to load cryptographic provider error.</span></span>  
  
-   <span data-ttu-id="030a2-127">Выход из следующей инструкции:</span><span class="sxs-lookup"><span data-stu-id="030a2-127">The output from the following statement:</span></span>  
  
    ```  
    SELECT * FROM sys.dm_os_ring_buffers   
    WHERE ring_buffer_type = 'RING_BUFFER_SECURITY_ERROR';  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="030a2-128">Попробуйте сразу собрать данные кольцевого буфера, поскольку они могут быть потеряны при перезагрузке.</span><span class="sxs-lookup"><span data-stu-id="030a2-128">Try to collect the ring buffer information promptly as ring buffer information can be lost during a restart.</span></span>  
  
  
