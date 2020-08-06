---
title: MSSQLSERVER_15404 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15404 (Database Engine error)
ms.assetid: 69677f02-bc81-4e4a-99b8-5c1bd1de36df
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: beb854c866256728574e06f8c9efb50fb354e15a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667166"
---
# <a name="mssqlserver_15404"></a><span data-ttu-id="8f26a-102">MSSQLSERVER_15404</span><span class="sxs-lookup"><span data-stu-id="8f26a-102">MSSQLSERVER_15404</span></span>
    
## <a name="details"></a><span data-ttu-id="8f26a-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="8f26a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8f26a-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="8f26a-104">Product Name</span></span>|<span data-ttu-id="8f26a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8f26a-105">SQL Server</span></span>|  
|<span data-ttu-id="8f26a-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="8f26a-106">Event ID</span></span>|<span data-ttu-id="8f26a-107">15404</span><span class="sxs-lookup"><span data-stu-id="8f26a-107">15404</span></span>|  
|<span data-ttu-id="8f26a-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="8f26a-108">Event Source</span></span>|<span data-ttu-id="8f26a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8f26a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8f26a-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="8f26a-110">Component</span></span>|<span data-ttu-id="8f26a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8f26a-111">SQLEngine</span></span>|  
|<span data-ttu-id="8f26a-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="8f26a-112">Symbolic Name</span></span>|<span data-ttu-id="8f26a-113">SEC_NTGRP_ERROR</span><span class="sxs-lookup"><span data-stu-id="8f26a-113">SEC_NTGRP_ERROR</span></span>|  
|<span data-ttu-id="8f26a-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="8f26a-114">Message Text</span></span>|<span data-ttu-id="8f26a-115">Не удалось получить сведения о пользователе/группе Windows NT "*пользователь*", код ошибки *код_ошибки*.</span><span class="sxs-lookup"><span data-stu-id="8f26a-115">Could not obtain information about Windows NT group/user '*user*', error code *code*.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8f26a-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="8f26a-116">Explanation</span></span>  
 <span data-ttu-id="8f26a-117">15404 используется при проверке подлинности, если указан недопустимый участник.</span><span class="sxs-lookup"><span data-stu-id="8f26a-117">15404 is used in authentication when an invalid principal is specified.</span></span> <span data-ttu-id="8f26a-118">Или олицетворение учетной записи Windows не выполняется, так как не существует связи полного уровня доверия между учетной записью [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и учетной записью домена Windows.</span><span class="sxs-lookup"><span data-stu-id="8f26a-118">Or, impersonation of a Windows account fails because there is no full trust relationship between the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and the domain of the Windows account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8f26a-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="8f26a-119">User Action</span></span>  
 <span data-ttu-id="8f26a-120">Убедитесь, что участник Windows существует и его имя указано верно.</span><span class="sxs-lookup"><span data-stu-id="8f26a-120">Check that the Windows principal exists and is not misspelled.</span></span>  
  
 <span data-ttu-id="8f26a-121">Если эта ошибка — результат отсутствия связи полного уровня доверия между учетной записью службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и учетной записью домена Windows, то ошибку можно устранить одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="8f26a-121">If this error is the result of a lack of a full trust relationship between the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and the domain of the Windows account, one of the following actions can resolve the error:</span></span>  
  
-   <span data-ttu-id="8f26a-122">Используйте для службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] учетную запись из домена, к которому относится пользователь Windows.</span><span class="sxs-lookup"><span data-stu-id="8f26a-122">Use an account from the same domain as the Windows user for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
-   <span data-ttu-id="8f26a-123">Если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] использует учетную запись компьютера, например Network Service или Local System, то домен, на котором находится пользователь Windows, должен доверенную связь с компьютером.</span><span class="sxs-lookup"><span data-stu-id="8f26a-123">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is using a machine account such as Network Service or Local System, the machine must be trusted by the domain containing the Windows User.</span></span>  
  
-   <span data-ttu-id="8f26a-124">Используйте учетную запись [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f26a-124">Use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
  
