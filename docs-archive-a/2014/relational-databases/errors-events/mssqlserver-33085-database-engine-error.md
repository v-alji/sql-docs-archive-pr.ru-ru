---
title: MSSQLSERVER_33085 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33085 (Database Engine error)
ms.assetid: c27b8d1d-668a-4ba8-8b61-25a5ebbc5485
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8d774ab115c2d0ddbbd7b35c7e32db17e39fcb2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658772"
---
# <a name="mssqlserver_33085"></a><span data-ttu-id="83499-102">MSSQLSERVER_33085</span><span class="sxs-lookup"><span data-stu-id="83499-102">MSSQLSERVER_33085</span></span>
    
## <a name="details"></a><span data-ttu-id="83499-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="83499-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="83499-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="83499-104">Product Name</span></span>|<span data-ttu-id="83499-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="83499-105">SQL Server</span></span>|  
|<span data-ttu-id="83499-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="83499-106">Event ID</span></span>|<span data-ttu-id="83499-107">33085</span><span class="sxs-lookup"><span data-stu-id="83499-107">33085</span></span>|  
|<span data-ttu-id="83499-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="83499-108">Event Source</span></span>|<span data-ttu-id="83499-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="83499-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="83499-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="83499-110">Component</span></span>|<span data-ttu-id="83499-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="83499-111">SQLEngine</span></span>|  
|<span data-ttu-id="83499-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="83499-112">Symbolic Name</span></span>|<span data-ttu-id="83499-113">SEC_CRYPTOPROVE_METHOD_CANNOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="83499-113">SEC_CRYPTOPROVE_METHOD_CANNOT_FOUND</span></span>|  
|<span data-ttu-id="83499-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="83499-114">Message Text</span></span>|<span data-ttu-id="83499-115">Один или несколько методов не удается найти в библиотеке «%.\*ls» поставщика служб шифрования.</span><span class="sxs-lookup"><span data-stu-id="83499-115">One or more methods cannot be found in cryptographic provider library '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="83499-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="83499-116">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="83499-117">не смог использовать поставщик служб шифрования, указанный в сообщении об ошибке.</span><span class="sxs-lookup"><span data-stu-id="83499-117">was unable to use the cryptographic provider listed in the error message.</span></span> <span data-ttu-id="83499-118">Поставщик служб шифрования не поддерживает необходимый метод.</span><span class="sxs-lookup"><span data-stu-id="83499-118">The cryptographic provider did not support a required method.</span></span> <span data-ttu-id="83499-119">Состояние ошибки указывает, какой метод не обнаружен.</span><span class="sxs-lookup"><span data-stu-id="83499-119">The state of the error indicates which method was not found.</span></span>  
  
|<span data-ttu-id="83499-120">Состояние</span><span class="sxs-lookup"><span data-stu-id="83499-120">State</span></span>|<span data-ttu-id="83499-121">Описание</span><span class="sxs-lookup"><span data-stu-id="83499-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="83499-122">1</span><span class="sxs-lookup"><span data-stu-id="83499-122">1</span></span>|<span data-ttu-id="83499-123">SqlCryptInitializeProvider</span><span class="sxs-lookup"><span data-stu-id="83499-123">SqlCryptInitializeProvider</span></span>|  
|<span data-ttu-id="83499-124">2</span><span class="sxs-lookup"><span data-stu-id="83499-124">2</span></span>|<span data-ttu-id="83499-125">SqlCryptFreeProvider</span><span class="sxs-lookup"><span data-stu-id="83499-125">SqlCryptFreeProvider</span></span>|  
|<span data-ttu-id="83499-126">3</span><span class="sxs-lookup"><span data-stu-id="83499-126">3</span></span>|<span data-ttu-id="83499-127">SqlCryptOpenSession</span><span class="sxs-lookup"><span data-stu-id="83499-127">SqlCryptOpenSession</span></span>|  
|<span data-ttu-id="83499-128">4</span><span class="sxs-lookup"><span data-stu-id="83499-128">4</span></span>|<span data-ttu-id="83499-129">SqlCryptCloseSession</span><span class="sxs-lookup"><span data-stu-id="83499-129">SqlCryptCloseSession</span></span>|  
|<span data-ttu-id="83499-130">5</span><span class="sxs-lookup"><span data-stu-id="83499-130">5</span></span>|<span data-ttu-id="83499-131">SqlCryptGetProviderInfo</span><span class="sxs-lookup"><span data-stu-id="83499-131">SqlCryptGetProviderInfo</span></span>|  
|<span data-ttu-id="83499-132">6</span><span class="sxs-lookup"><span data-stu-id="83499-132">6</span></span>|<span data-ttu-id="83499-133">SqlCryptGetNextAlgorithmId</span><span class="sxs-lookup"><span data-stu-id="83499-133">SqlCryptGetNextAlgorithmId</span></span>|  
|<span data-ttu-id="83499-134">7</span><span class="sxs-lookup"><span data-stu-id="83499-134">7</span></span>|<span data-ttu-id="83499-135">SqlCryptGetAlgorithmInfo</span><span class="sxs-lookup"><span data-stu-id="83499-135">SqlCryptGetAlgorithmInfo</span></span>|  
|<span data-ttu-id="83499-136">8</span><span class="sxs-lookup"><span data-stu-id="83499-136">8</span></span>|<span data-ttu-id="83499-137">SqlCryptCreateKey</span><span class="sxs-lookup"><span data-stu-id="83499-137">SqlCryptCreateKey</span></span>|  
|<span data-ttu-id="83499-138">9</span><span class="sxs-lookup"><span data-stu-id="83499-138">9</span></span>|<span data-ttu-id="83499-139">SqlCryptDropKey</span><span class="sxs-lookup"><span data-stu-id="83499-139">SqlCryptDropKey</span></span>|  
|<span data-ttu-id="83499-140">10</span><span class="sxs-lookup"><span data-stu-id="83499-140">10</span></span>|<span data-ttu-id="83499-141">SqlCryptGetNextKeyId</span><span class="sxs-lookup"><span data-stu-id="83499-141">SqlCryptGetNextKeyId</span></span>|  
|<span data-ttu-id="83499-142">11</span><span class="sxs-lookup"><span data-stu-id="83499-142">11</span></span>|<span data-ttu-id="83499-143">SqlCryptGetKeyInfoByKeyId</span><span class="sxs-lookup"><span data-stu-id="83499-143">SqlCryptGetKeyInfoByKeyId</span></span>|  
|<span data-ttu-id="83499-144">12</span><span class="sxs-lookup"><span data-stu-id="83499-144">12</span></span>|<span data-ttu-id="83499-145">SqlCryptGetKeyInfoByThumb</span><span class="sxs-lookup"><span data-stu-id="83499-145">SqlCryptGetKeyInfoByThumb</span></span>|  
|<span data-ttu-id="83499-146">13</span><span class="sxs-lookup"><span data-stu-id="83499-146">13</span></span>|<span data-ttu-id="83499-147">SqlCryptGetKeyInfoByName</span><span class="sxs-lookup"><span data-stu-id="83499-147">SqlCryptGetKeyInfoByName</span></span>|  
|<span data-ttu-id="83499-148">14</span><span class="sxs-lookup"><span data-stu-id="83499-148">14</span></span>|<span data-ttu-id="83499-149">SqlCryptExportKey</span><span class="sxs-lookup"><span data-stu-id="83499-149">SqlCryptExportKey</span></span>|  
|<span data-ttu-id="83499-150">15</span><span class="sxs-lookup"><span data-stu-id="83499-150">15</span></span>|<span data-ttu-id="83499-151">SqlCryptImportKey</span><span class="sxs-lookup"><span data-stu-id="83499-151">SqlCryptImportKey</span></span>|  
|<span data-ttu-id="83499-152">16</span><span class="sxs-lookup"><span data-stu-id="83499-152">16</span></span>|<span data-ttu-id="83499-153">SqlCryptEncrypt</span><span class="sxs-lookup"><span data-stu-id="83499-153">SqlCryptEncrypt</span></span>|  
|<span data-ttu-id="83499-154">17</span><span class="sxs-lookup"><span data-stu-id="83499-154">17</span></span>|<span data-ttu-id="83499-155">SqlCryptDecrypt</span><span class="sxs-lookup"><span data-stu-id="83499-155">SqlCryptDecrypt</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="83499-156">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="83499-156">User Action</span></span>  
 <span data-ttu-id="83499-157">Обратитесь к поставщику служб шифрования за дополнительными сведениями.</span><span class="sxs-lookup"><span data-stu-id="83499-157">Contact the cryptographic provider for more information.</span></span>  
  
  
