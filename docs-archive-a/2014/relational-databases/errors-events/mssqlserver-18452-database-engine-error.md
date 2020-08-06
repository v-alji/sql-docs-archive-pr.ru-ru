---
title: MSSQLSERVER_18452 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18456 (Database Engine error)
- 18452 (Database Engine error)
ms.assetid: 21da332c-e81d-4dee-a9d2-95598911b3be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5786d5de4748f6bbf59d2bd4acecd7ca77977f11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665365"
---
# <a name="mssqlserver_18452"></a><span data-ttu-id="073c8-102">MSSQLSERVER_18452</span><span class="sxs-lookup"><span data-stu-id="073c8-102">MSSQLSERVER_18452</span></span>
    
## <a name="details"></a><span data-ttu-id="073c8-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="073c8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="073c8-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="073c8-104">Product Name</span></span>|<span data-ttu-id="073c8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="073c8-105">SQL Server</span></span>|  
|<span data-ttu-id="073c8-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="073c8-106">Event ID</span></span>|<span data-ttu-id="073c8-107">18452</span><span class="sxs-lookup"><span data-stu-id="073c8-107">18452</span></span>|  
|<span data-ttu-id="073c8-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="073c8-108">Event Source</span></span>|<span data-ttu-id="073c8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="073c8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="073c8-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="073c8-110">Component</span></span>|<span data-ttu-id="073c8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="073c8-111">SQLEngine</span></span>|  
|<span data-ttu-id="073c8-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="073c8-112">Symbolic Name</span></span>|<span data-ttu-id="073c8-113">LOGON_INVALID_CONNECT</span><span class="sxs-lookup"><span data-stu-id="073c8-113">LOGON_INVALID_CONNECT</span></span>|  
|<span data-ttu-id="073c8-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="073c8-114">Message Text</span></span>|<span data-ttu-id="073c8-115">Ошибка входа пользователя «%.\*ls».</span><span class="sxs-lookup"><span data-stu-id="073c8-115">Login failed for user '%.\*ls'.</span></span> <span data-ttu-id="073c8-116">Данное имя входа является именем входа SQL Server и не может использоваться для аутентификации Windows.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="073c8-116">The login is a SQL Server login and cannot be used with Windows Authentication.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="073c8-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="073c8-117">Explanation</span></span>  
 <span data-ttu-id="073c8-118">Пользователь попытался выполнить вход с учетными данными, правильность которых нельзя проверить.</span><span class="sxs-lookup"><span data-stu-id="073c8-118">The user attempted to login with credentials that cannot be validated.</span></span> <span data-ttu-id="073c8-119">Возможные причины.</span><span class="sxs-lookup"><span data-stu-id="073c8-119">Possible causes are:</span></span>  
  
-   <span data-ttu-id="073c8-120">Имя входа может быть именем входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], но сервер допускает только проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="073c8-120">The login may be a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login but the server only accepts Windows Authentication.</span></span>  
  
-   <span data-ttu-id="073c8-121">Попытка подключения с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], но использованное имя входа не существует в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="073c8-121">You are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication but the login used does not exist on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="073c8-122">Процедура входа может использовать проверку подлинности Windows, но имя входа — неопознанный участник Windows.</span><span class="sxs-lookup"><span data-stu-id="073c8-122">The login may use Windows Authentication but the login is an unrecognized Windows principal.</span></span> <span data-ttu-id="073c8-123">Неопознанный участник Windows означает, что имя входа не может быть проверено Windows.</span><span class="sxs-lookup"><span data-stu-id="073c8-123">An unrecognized Windows principal means that the login cannot be verified by Windows.</span></span> <span data-ttu-id="073c8-124">Причина может быть в том, что имя входа Windows принадлежит домену, который не является доверенным.</span><span class="sxs-lookup"><span data-stu-id="073c8-124">This could be because the Windows login is from an untrusted domain.</span></span>  
  
 <span data-ttu-id="073c8-125">Аналогичные неполадки могут вызвать менее определенную ошибку 18456.</span><span class="sxs-lookup"><span data-stu-id="073c8-125">Similar problems can cause the less-specific error 18456.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="073c8-126">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="073c8-126">User Action</span></span>  
 <span data-ttu-id="073c8-127">При попытке подключения с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] убедитесь, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] настроен в режиме смешанной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="073c8-127">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured in Mixed Authentication Mode.</span></span>  
  
 <span data-ttu-id="073c8-128">При попытке подключения с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] убедитесь, что имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] существует.</span><span class="sxs-lookup"><span data-stu-id="073c8-128">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login exists.</span></span>  
  
 <span data-ttu-id="073c8-129">При попытке подключения с использованием проверки подлинности Windows убедитесь, что выполнен правильный вход в нужный домен.</span><span class="sxs-lookup"><span data-stu-id="073c8-129">If you are trying to connect using Windows Authentication, verify that you are properly logged into the correct domain.</span></span>  
  
  
