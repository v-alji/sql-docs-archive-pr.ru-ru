---
title: MSSQLSERVER_33027 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33027 (Database Engine error)
ms.assetid: bfdc626e-7958-4511-987d-3b687824e8af
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f6bb461b42b66368224fffd2c14f9b4da61abf5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658775"
---
# <a name="mssqlserver_33027"></a><span data-ttu-id="c27a7-102">MSSQLSERVER_33027</span><span class="sxs-lookup"><span data-stu-id="c27a7-102">MSSQLSERVER_33027</span></span>
    
## <a name="details"></a><span data-ttu-id="c27a7-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="c27a7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c27a7-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="c27a7-104">Product Name</span></span>|<span data-ttu-id="c27a7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c27a7-105">SQL Server</span></span>|  
|<span data-ttu-id="c27a7-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="c27a7-106">Event ID</span></span>|<span data-ttu-id="c27a7-107">33027</span><span class="sxs-lookup"><span data-stu-id="c27a7-107">33027</span></span>|  
|<span data-ttu-id="c27a7-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="c27a7-108">Event Source</span></span>|<span data-ttu-id="c27a7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c27a7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c27a7-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="c27a7-110">Component</span></span>|<span data-ttu-id="c27a7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c27a7-111">SQLEngine</span></span>|  
|<span data-ttu-id="c27a7-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="c27a7-112">Symbolic Name</span></span>|<span data-ttu-id="c27a7-113">SEC_CRYPTOPROV_CANTLOADDLL</span><span class="sxs-lookup"><span data-stu-id="c27a7-113">SEC_CRYPTOPROV_CANTLOADDLL</span></span>|  
|<span data-ttu-id="c27a7-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="c27a7-114">Message Text</span></span>|<span data-ttu-id="c27a7-115">Не удалось загрузить поставщик служб шифрования "%.\*ls" из-за недействительной подписи Authenticode или недействительного пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="c27a7-115">Failed to load cryptographic provider '%.\*ls' due to an invalid Authenticode signature or invalid file path.</span></span> <span data-ttu-id="c27a7-116">Проверьте наличие других ошибок в предыдущих сообщениях.</span><span class="sxs-lookup"><span data-stu-id="c27a7-116">Check previous messages for other failures.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c27a7-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="c27a7-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c27a7-118">не смог использовать поставщик служб шифрования, указанный в сообщении об ошибке, так как [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не смог загрузить DLL-библиотеку.</span><span class="sxs-lookup"><span data-stu-id="c27a7-118">was unable to use the cryptographic provider listed in the error message, because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] could not load the DLL.</span></span> <span data-ttu-id="c27a7-119">Недействительное имя или подпись Authenticode.</span><span class="sxs-lookup"><span data-stu-id="c27a7-119">Either the name is invalid or the Authenticode signature is invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c27a7-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="c27a7-120">User Action</span></span>  
 <span data-ttu-id="c27a7-121">Проверьте, что файл присутствует, а [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имеет разрешение на доступ к местоположению файла.</span><span class="sxs-lookup"><span data-stu-id="c27a7-121">Check that the file is present and that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has permission to access that location.</span></span> <span data-ttu-id="c27a7-122">Проверьте дополнительные связанные сообщения в журнале ошибок.</span><span class="sxs-lookup"><span data-stu-id="c27a7-122">Check the error log for additional related messages.</span></span> <span data-ttu-id="c27a7-123">Или обратитесь к поставщику служб шифрования за дополнительными сведениями.</span><span class="sxs-lookup"><span data-stu-id="c27a7-123">Otherwise, contact the cryptographic provider for more information.</span></span>  
  
  
