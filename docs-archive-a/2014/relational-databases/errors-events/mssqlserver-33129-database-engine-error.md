---
title: MSSQLSERVER_33129 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33129 (Database Engine error)
ms.assetid: 83b5f368-f1a1-4a40-9bb6-c77e2dec690f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da7735889dce8bfc33e624115e8245f8a02f46b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658770"
---
# <a name="mssqlserver_33129"></a><span data-ttu-id="ef0c9-102">MSSQLSERVER_33129</span><span class="sxs-lookup"><span data-stu-id="ef0c9-102">MSSQLSERVER_33129</span></span>
    
## <a name="details"></a><span data-ttu-id="ef0c9-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="ef0c9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ef0c9-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="ef0c9-104">Product Name</span></span>|<span data-ttu-id="ef0c9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ef0c9-105">SQL Server</span></span>|  
|<span data-ttu-id="ef0c9-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ef0c9-106">Event ID</span></span>|<span data-ttu-id="ef0c9-107">33129</span><span class="sxs-lookup"><span data-stu-id="ef0c9-107">33129</span></span>|  
|<span data-ttu-id="ef0c9-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="ef0c9-108">Event Source</span></span>|<span data-ttu-id="ef0c9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ef0c9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ef0c9-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="ef0c9-110">Component</span></span>|<span data-ttu-id="ef0c9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ef0c9-111">SQLEngine</span></span>|  
|<span data-ttu-id="ef0c9-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="ef0c9-112">Symbolic Name</span></span>|<span data-ttu-id="ef0c9-113">SEC_CANNOT_DISABLE_WIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="ef0c9-113">SEC_CANNOT_DISABLE_WIN_GROUP</span></span>|  
|<span data-ttu-id="ef0c9-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="ef0c9-114">Message Text</span></span>|<span data-ttu-id="ef0c9-115">Нельзя использовать параметр ALTER_LOGIN с аргументом DISABLE, чтобы запретить доступ группе Windows.</span><span class="sxs-lookup"><span data-stu-id="ef0c9-115">Cannot use ALTER_LOGIN with the DISABLE argument to deny access to a Windows group.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ef0c9-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="ef0c9-116">Explanation</span></span>  
 <span data-ttu-id="ef0c9-117">Это сообщение появляется при попытке отключить имя входа группы Windows.</span><span class="sxs-lookup"><span data-stu-id="ef0c9-117">This message occurs when attempting to disable the login of a Windows Group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ef0c9-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="ef0c9-118">User Action</span></span>  
 <span data-ttu-id="ef0c9-119">Имя входа группы Windows не может быть отключено.</span><span class="sxs-lookup"><span data-stu-id="ef0c9-119">The login of a Windows Group cannot be disabled.</span></span> <span data-ttu-id="ef0c9-120">Чтобы временно удалить разрешения на доступ, предоставленные группе Windows, отзовите (REVOKE) разрешение на подключение (CONNECT) у имени входа группы Windows.</span><span class="sxs-lookup"><span data-stu-id="ef0c9-120">To temporarily remove access permission granted to a Windows Group, REVOKE the CONNECT permission of the login for the Windows Group.</span></span> <span data-ttu-id="ef0c9-121">Пользователи Windows по-прежнему имеют доступ с индивидуальным именем входа или именем входа другой группы Windows.</span><span class="sxs-lookup"><span data-stu-id="ef0c9-121">Windows users might still have access through their individual login or through another Windows Group.</span></span> <span data-ttu-id="ef0c9-122">В следующем примере отменяется разрешение на подключение, предоставленное группе учетных записей домена WESTCOAST.</span><span class="sxs-lookup"><span data-stu-id="ef0c9-122">The following example revokes the connect permission to the Accounting Group of the WESTCOAST domain.</span></span>  
  
```sql  
REVOKE CONNECT TO [WESTCOAST\Accounting];  
```  
  
  
