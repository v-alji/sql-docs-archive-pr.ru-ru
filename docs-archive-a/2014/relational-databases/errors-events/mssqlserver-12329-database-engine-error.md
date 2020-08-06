---
title: MSSQLSERVER_12329 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 12329 (Database Engine error)
ms.assetid: 43f90287-36d5-46c2-ac91-a37202dcf6d3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7576e32946ce0a453637273c449bbff20e5b6fac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664263"
---
# <a name="mssqlserver_12329"></a><span data-ttu-id="4b2b0-102">MSSQLSERVER_12329</span><span class="sxs-lookup"><span data-stu-id="4b2b0-102">MSSQLSERVER_12329</span></span>
    
## <a name="details"></a><span data-ttu-id="4b2b0-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="4b2b0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4b2b0-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="4b2b0-104">Product Name</span></span>|<span data-ttu-id="4b2b0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4b2b0-105">SQL Server</span></span>|  
|<span data-ttu-id="4b2b0-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="4b2b0-106">Event ID</span></span>|<span data-ttu-id="4b2b0-107">12329</span><span class="sxs-lookup"><span data-stu-id="4b2b0-107">12329</span></span>|  
|<span data-ttu-id="4b2b0-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="4b2b0-108">Event Source</span></span>|<span data-ttu-id="4b2b0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4b2b0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4b2b0-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="4b2b0-110">Component</span></span>|<span data-ttu-id="4b2b0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4b2b0-111">SQLEngine</span></span>|  
|<span data-ttu-id="4b2b0-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="4b2b0-112">Symbolic Name</span></span>|<span data-ttu-id="4b2b0-113">HK_UNSUPPORTED_NON_LATIN_CODEPAGE</span><span class="sxs-lookup"><span data-stu-id="4b2b0-113">HK_UNSUPPORTED_NON_LATIN_CODEPAGE</span></span>|  
|<span data-ttu-id="4b2b0-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="4b2b0-114">Message Text</span></span>|<span data-ttu-id="4b2b0-115">Типы данных char(n) и varchar(n) с параметрами сортировки, кодовая страница которых отлична от 1252, не поддерживаются *конструкцией*.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-115">The data types char(n) and varchar(n) using a collation that has a code page other than 1252 are not supported with  *construct*.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4b2b0-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="4b2b0-116">Explanation</span></span>  
 <span data-ttu-id="4b2b0-117">Не используйте типы данных char(n) и varchar(n) с параметрами сортировки, кодовая страница которых отлична от 1252.</span><span class="sxs-lookup"><span data-stu-id="4b2b0-117">Do not use the data types char(n) and varchar(n) using a collation that has a code page other than 1252.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4b2b0-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="4b2b0-118">User Action</span></span>  
 <span data-ttu-id="4b2b0-119">Одна непредвиденная ситуация, которая может привести к формированию этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="4b2b0-119">One unexpected situation that can generate this error is:</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = 'us_english')  
```  
  
 <span data-ttu-id="4b2b0-120">Вместо этого используйте:</span><span class="sxs-lookup"><span data-stu-id="4b2b0-120">Use this instead:</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
```  
  
  
