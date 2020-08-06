---
title: MSSQLSERVER_33028 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33028 (Database Engine error)
ms.assetid: c5cec0e4-0bcd-4907-826f-e7d835cfcb37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 555dcf0220793abc0e8af81b3f56867f9960c5f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658774"
---
# <a name="mssqlserver_33028"></a><span data-ttu-id="507e7-102">MSSQLSERVER_33028</span><span class="sxs-lookup"><span data-stu-id="507e7-102">MSSQLSERVER_33028</span></span>
    
## <a name="details"></a><span data-ttu-id="507e7-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="507e7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="507e7-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="507e7-104">Product Name</span></span>|<span data-ttu-id="507e7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="507e7-105">SQL Server</span></span>|  
|<span data-ttu-id="507e7-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="507e7-106">Event ID</span></span>|<span data-ttu-id="507e7-107">33028</span><span class="sxs-lookup"><span data-stu-id="507e7-107">33028</span></span>|  
|<span data-ttu-id="507e7-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="507e7-108">Event Source</span></span>|<span data-ttu-id="507e7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="507e7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="507e7-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="507e7-110">Component</span></span>|<span data-ttu-id="507e7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="507e7-111">SQLEngine</span></span>|  
|<span data-ttu-id="507e7-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="507e7-112">Symbolic Name</span></span>|<span data-ttu-id="507e7-113">SEC_CRYPTOPROV_CANTOPENSESSION</span><span class="sxs-lookup"><span data-stu-id="507e7-113">SEC_CRYPTOPROV_CANTOPENSESSION</span></span>|  
|<span data-ttu-id="507e7-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="507e7-114">Message Text</span></span>|<span data-ttu-id="507e7-115">Не удается открыть сеанс для %S_MSG '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="507e7-115">Cannot open session for %S_MSG '%.\*ls'.</span></span> <span data-ttu-id="507e7-116">Код ошибки поставщика: %d.</span><span class="sxs-lookup"><span data-stu-id="507e7-116">Provider error code: %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="507e7-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="507e7-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="507e7-118">не смог открыть поставщик служб шифрования, указанный в сообщении об ошибке.</span><span class="sxs-lookup"><span data-stu-id="507e7-118">was unable to open the cryptographic provider listed in the error message.</span></span> <span data-ttu-id="507e7-119">Поставщик служб шифрования предоставляет указанный код ошибки.</span><span class="sxs-lookup"><span data-stu-id="507e7-119">The cryptographic provider supplied the error code listed.</span></span> <span data-ttu-id="507e7-120">Возможно, придется обратиться к поставщику служб шифрования за дополнительными сведениями об ошибке.</span><span class="sxs-lookup"><span data-stu-id="507e7-120">You may need to contact your cryptographic provider for more information about the error.</span></span>  
  
|<span data-ttu-id="507e7-121">Код ошибки</span><span class="sxs-lookup"><span data-stu-id="507e7-121">Error code</span></span>|<span data-ttu-id="507e7-122">Описание</span><span class="sxs-lookup"><span data-stu-id="507e7-122">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="507e7-123">0</span><span class="sxs-lookup"><span data-stu-id="507e7-123">0</span></span>|<span data-ttu-id="507e7-124">Успешно.</span><span class="sxs-lookup"><span data-stu-id="507e7-124">Success.</span></span> <span data-ttu-id="507e7-125">Нет ошибки.</span><span class="sxs-lookup"><span data-stu-id="507e7-125">No error.</span></span>|  
|<span data-ttu-id="507e7-126">1</span><span class="sxs-lookup"><span data-stu-id="507e7-126">1</span></span>|<span data-ttu-id="507e7-127">Ошибка.</span><span class="sxs-lookup"><span data-stu-id="507e7-127">Failure.</span></span> <span data-ttu-id="507e7-128">Произошла неуказанная или непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="507e7-128">An unspecified or unexpected error occurred.</span></span> <span data-ttu-id="507e7-129">Дополнительные сведения об ошибке недоступны.</span><span class="sxs-lookup"><span data-stu-id="507e7-129">Additional information is not available.</span></span>|  
|<span data-ttu-id="507e7-130">2</span><span class="sxs-lookup"><span data-stu-id="507e7-130">2</span></span>|<span data-ttu-id="507e7-131">Недостаточно места в буфере.</span><span class="sxs-lookup"><span data-stu-id="507e7-131">Insufficient Buffer.</span></span> <span data-ttu-id="507e7-132">Нельзя выделить пространство для поставщика служб шифрования.</span><span class="sxs-lookup"><span data-stu-id="507e7-132">Space could not be allocated for the cryptographic provider.</span></span>|  
|<span data-ttu-id="507e7-133">3</span><span class="sxs-lookup"><span data-stu-id="507e7-133">3</span></span>|<span data-ttu-id="507e7-134">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="507e7-134">Not Supported.</span></span> <span data-ttu-id="507e7-135">Этот поставщик служб шифрования не поддерживается данным выпуском.</span><span class="sxs-lookup"><span data-stu-id="507e7-135">The cryptographic provider is not supported by this release.</span></span> <span data-ttu-id="507e7-136">Выберите другой поставщик служб шифрования.</span><span class="sxs-lookup"><span data-stu-id="507e7-136">Select another cryptographic provider.</span></span>|  
|<span data-ttu-id="507e7-137">4</span><span class="sxs-lookup"><span data-stu-id="507e7-137">4</span></span>|<span data-ttu-id="507e7-138">Не найден.</span><span class="sxs-lookup"><span data-stu-id="507e7-138">Not Found.</span></span> <span data-ttu-id="507e7-139">Указанный поставщик служб шифрования отсутствует, или пользователь не авторизован для доступа к файлам.</span><span class="sxs-lookup"><span data-stu-id="507e7-139">The specified cryptographic provider is not present or you do not have authorization to access the files.</span></span>|  
|<span data-ttu-id="507e7-140">5</span><span class="sxs-lookup"><span data-stu-id="507e7-140">5</span></span>|<span data-ttu-id="507e7-141">Ошибка авторизации.</span><span class="sxs-lookup"><span data-stu-id="507e7-141">Authorization Failure.</span></span> <span data-ttu-id="507e7-142">Причиной может быть неверный пароль или имя пользователя при создании учетных данных.</span><span class="sxs-lookup"><span data-stu-id="507e7-142">Can result from providing an incorrect password or username when creating the credential.</span></span> <span data-ttu-id="507e7-143">Может произойти, если учетные данные не существуют.</span><span class="sxs-lookup"><span data-stu-id="507e7-143">Can result if the credential does not exist.</span></span>|  
|<span data-ttu-id="507e7-144">6</span><span class="sxs-lookup"><span data-stu-id="507e7-144">6</span></span>|<span data-ttu-id="507e7-145">Недопустимый аргумент.</span><span class="sxs-lookup"><span data-stu-id="507e7-145">Invalid Argument.</span></span> <span data-ttu-id="507e7-146">Поставщику служб шифрования передан неправильный аргумент.</span><span class="sxs-lookup"><span data-stu-id="507e7-146">An invalid argument was passed to the cryptographic provider.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="507e7-147">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="507e7-147">User Action</span></span>  
 <span data-ttu-id="507e7-148">Устраните ошибку или обратитесь к поставщику служб шифрования за дополнительными сведениями.</span><span class="sxs-lookup"><span data-stu-id="507e7-148">Resolve the error, or contact the cryptographic provider for more information.</span></span>  
  
  
