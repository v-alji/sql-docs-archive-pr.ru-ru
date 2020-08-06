---
title: MSSQLSERVER_5554 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5554 (Database Engine error)
ms.assetid: 7134bbe5-d240-4a98-85ce-b13cc8ae9b0e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5095a50f257abafb6ebde97bb32c57bc71fc4e09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664938"
---
# <a name="mssqlserver_5554"></a><span data-ttu-id="3a785-102">MSSQLSERVER_5554</span><span class="sxs-lookup"><span data-stu-id="3a785-102">MSSQLSERVER_5554</span></span>
    
## <a name="details"></a><span data-ttu-id="3a785-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="3a785-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3a785-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="3a785-104">Product Name</span></span>|<span data-ttu-id="3a785-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3a785-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3a785-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="3a785-106">Event ID</span></span>|<span data-ttu-id="3a785-107">5554</span><span class="sxs-lookup"><span data-stu-id="3a785-107">5554</span></span>|  
|<span data-ttu-id="3a785-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="3a785-108">Event Source</span></span>|<span data-ttu-id="3a785-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3a785-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3a785-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="3a785-110">Component</span></span>|<span data-ttu-id="3a785-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3a785-111">SQLEngine</span></span>|  
|<span data-ttu-id="3a785-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="3a785-112">Symbolic Name</span></span>|<span data-ttu-id="3a785-113">FS_MINIVER_OVERFLOW</span><span class="sxs-lookup"><span data-stu-id="3a785-113">FS_MINIVER_OVERFLOW</span></span>|  
|<span data-ttu-id="3a785-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="3a785-114">Message Text</span></span>|<span data-ttu-id="3a785-115">Достигнут максимальный предел общего числа версий одного файла, установленный для файловой системы.</span><span class="sxs-lookup"><span data-stu-id="3a785-115">The total number of versions for a single file has reached the maximum limit set by the file system.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3a785-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="3a785-116">Explanation</span></span>  
 <span data-ttu-id="3a785-117">В режиме MARS и скриптах триггера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] использует мини-версию, указанную операционной системой.</span><span class="sxs-lookup"><span data-stu-id="3a785-117">In multiple active result sets (MARS) or trigger scenarios, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the miniversion specified by the operating system.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3a785-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="3a785-118">User Action</span></span>  
 <span data-ttu-id="3a785-119">Постарайтесь избежать повторного обновления данных в одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="3a785-119">Try to avoid repeated updates to the data in the same transaction.</span></span>  
  
  
