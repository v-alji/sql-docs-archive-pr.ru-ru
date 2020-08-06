---
title: MSSQLSERVER_3417 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3417 (Database Engine error)
ms.assetid: 005829c8-cf57-4828-818a-bbe8ee2e00f0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 680e5a4266c7d0d9aaacb7b3deb9525a002077e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667117"
---
# <a name="mssqlserver_3417"></a><span data-ttu-id="00b7e-102">MSSQLSERVER_3417</span><span class="sxs-lookup"><span data-stu-id="00b7e-102">MSSQLSERVER_3417</span></span>
    
## <a name="details"></a><span data-ttu-id="00b7e-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="00b7e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="00b7e-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="00b7e-104">Product Name</span></span>|<span data-ttu-id="00b7e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="00b7e-105">SQL Server</span></span>|  
|<span data-ttu-id="00b7e-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="00b7e-106">Event ID</span></span>|<span data-ttu-id="00b7e-107">3417</span><span class="sxs-lookup"><span data-stu-id="00b7e-107">3417</span></span>|  
|<span data-ttu-id="00b7e-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="00b7e-108">Event Source</span></span>|<span data-ttu-id="00b7e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="00b7e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="00b7e-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="00b7e-110">Component</span></span>|<span data-ttu-id="00b7e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="00b7e-111">SQLEngine</span></span>|  
|<span data-ttu-id="00b7e-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="00b7e-112">Symbolic Name</span></span>|<span data-ttu-id="00b7e-113">REC_BADMASTER</span><span class="sxs-lookup"><span data-stu-id="00b7e-113">REC_BADMASTER</span></span>|  
|<span data-ttu-id="00b7e-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="00b7e-114">Message Text</span></span>|<span data-ttu-id="00b7e-115">Невозможно восстановить базу данных master.</span><span class="sxs-lookup"><span data-stu-id="00b7e-115">Cannot recover the master database.</span></span> <span data-ttu-id="00b7e-116">Не удалось запустить SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00b7e-116">SQL Server is unable to run.</span></span> <span data-ttu-id="00b7e-117">Восстановите базу данных master из полной резервной копии, исправьте ее или перестройте.</span><span class="sxs-lookup"><span data-stu-id="00b7e-117">Restore master from a full backup, repair it, or rebuild it.</span></span> <span data-ttu-id="00b7e-118">Дополнительные сведения о перестроении базы данных master см. в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00b7e-118">For more information about how to rebuild the master database, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="00b7e-119">Объяснение</span><span class="sxs-lookup"><span data-stu-id="00b7e-119">Explanation</span></span>  
 <span data-ttu-id="00b7e-120">SQL Server не может запустить базу данных **master**.</span><span class="sxs-lookup"><span data-stu-id="00b7e-120">SQL Server cannot start the **master** database.</span></span> <span data-ttu-id="00b7e-121">Если базы данных **master** или **tempdb** не могут быть переведены в оперативный режим, то SQL Server запустить нельзя.</span><span class="sxs-lookup"><span data-stu-id="00b7e-121">If the **master** or **tempdb** cannot be brought online, SQL Server cannot run.</span></span> <span data-ttu-id="00b7e-122">Эта ошибка обычно предшествует другим ошибкам.</span><span class="sxs-lookup"><span data-stu-id="00b7e-122">This error is usually preceded by other errors.</span></span> <span data-ttu-id="00b7e-123">Чтобы найти источник ошибки, просмотрите журнал ошибок.</span><span class="sxs-lookup"><span data-stu-id="00b7e-123">Review error logs to find the root cause.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="00b7e-124">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="00b7e-124">User Action</span></span>  
 <span data-ttu-id="00b7e-125">Восстановите базу данных из резервной копии или исправьте ее.</span><span class="sxs-lookup"><span data-stu-id="00b7e-125">Restore backup of the database or repair the database.</span></span>  
  
  
