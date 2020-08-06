---
title: MSSQLSERVER_125 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "125"
helpviewer_keywords:
- 125 (Database Engine error)
ms.assetid: 0f58338d-2ea0-48b8-8a20-c438b0940433
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 59c732d80ccfafc8f242bb1c42fe60e3dea81f19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664264"
---
# <a name="mssqlserver_125"></a><span data-ttu-id="a422d-102">MSSQLSERVER_125</span><span class="sxs-lookup"><span data-stu-id="a422d-102">MSSQLSERVER_125</span></span>
    
## <a name="details"></a><span data-ttu-id="a422d-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="a422d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a422d-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a422d-104">Product Name</span></span>|<span data-ttu-id="a422d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a422d-105">SQL Server</span></span>|  
|<span data-ttu-id="a422d-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a422d-106">Event ID</span></span>|<span data-ttu-id="a422d-107">125</span><span class="sxs-lookup"><span data-stu-id="a422d-107">125</span></span>|  
|<span data-ttu-id="a422d-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="a422d-108">Event Source</span></span>|<span data-ttu-id="a422d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a422d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a422d-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="a422d-110">Component</span></span>|<span data-ttu-id="a422d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a422d-111">SQLEngine</span></span>|  
|<span data-ttu-id="a422d-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="a422d-112">Symbolic Name</span></span>||  
|<span data-ttu-id="a422d-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a422d-113">Message Text</span></span>|<span data-ttu-id="a422d-114">Выражения Case могут быть вложены только до уровня %d.</span><span class="sxs-lookup"><span data-stu-id="a422d-114">Case expressions may only be nested to level %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a422d-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a422d-115">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a422d-116">допускает применение в выражениях CASE не более 10 уровней вложенности.</span><span class="sxs-lookup"><span data-stu-id="a422d-116">allows for only 10 levels of nesting in CASE expressions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a422d-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a422d-117">User Action</span></span>  
 <span data-ttu-id="a422d-118">Ограничьте уровень вложенности выражений CASE до 10.</span><span class="sxs-lookup"><span data-stu-id="a422d-118">Reduce the level of CASE statements to 10 or less.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a422d-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="a422d-119">See Also</span></span>  
 [<span data-ttu-id="a422d-120">CASE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a422d-120">CASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/case-transact-sql)  
  
  
