---
title: MSSQLSERVER_3151 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3151 (Database Engine error)
ms.assetid: a8657a91-ec75-4649-a09a-21920e0030ff
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c34414754ea9d25ad89f6aba767197eb1dfc10d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664247"
---
# <a name="mssqlserver_3151"></a><span data-ttu-id="b7bfb-102">MSSQLSERVER_3151</span><span class="sxs-lookup"><span data-stu-id="b7bfb-102">MSSQLSERVER_3151</span></span>
    
## <a name="details"></a><span data-ttu-id="b7bfb-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="b7bfb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b7bfb-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="b7bfb-104">Product Name</span></span>|<span data-ttu-id="b7bfb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b7bfb-105">SQL Server</span></span>|  
|<span data-ttu-id="b7bfb-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="b7bfb-106">Event ID</span></span>|<span data-ttu-id="b7bfb-107">3151</span><span class="sxs-lookup"><span data-stu-id="b7bfb-107">3151</span></span>|  
|<span data-ttu-id="b7bfb-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="b7bfb-108">Event Source</span></span>|<span data-ttu-id="b7bfb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b7bfb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b7bfb-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="b7bfb-110">Component</span></span>|<span data-ttu-id="b7bfb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b7bfb-111">SQLEngine</span></span>|  
|<span data-ttu-id="b7bfb-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="b7bfb-112">Symbolic Name</span></span>|<span data-ttu-id="b7bfb-113">LDDB_MASTER_LOAD_FAILED</span><span class="sxs-lookup"><span data-stu-id="b7bfb-113">LDDB_MASTER_LOAD_FAILED</span></span>|  
|<span data-ttu-id="b7bfb-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="b7bfb-114">Message Text</span></span>|<span data-ttu-id="b7bfb-115">Ошибка при восстановлении базы данных master.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-115">Failed to restore master database.</span></span> <span data-ttu-id="b7bfb-116">Завершение работы SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-116">Shutting down SQL Server.</span></span> <span data-ttu-id="b7bfb-117">Проверьте журналы ошибок и перестройте базу данных master.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-117">Check the error logs, and rebuild the master database.</span></span> <span data-ttu-id="b7bfb-118">Дополнительные сведения о перестроении базы данных master см. в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-118">For more information about how to rebuild the master database, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b7bfb-119">Объяснение</span><span class="sxs-lookup"><span data-stu-id="b7bfb-119">Explanation</span></span>  
 <span data-ttu-id="b7bfb-120">Это общее сообщение об ошибке, которое может означать разные проблемы с базой данных **master**.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-120">This is a general error message indicating various problems with the **master** database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b7bfb-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="b7bfb-121">User Action</span></span>  
 <span data-ttu-id="b7bfb-122">Проверьте журналы ошибок для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-122">Check the error logs for more information.</span></span> <span data-ttu-id="b7bfb-123">Чтобы создать работоспособную базу данных **master**, запустите файл Setup.exe с параметром REBUILDDATABASE.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-123">To create a usable **master** database, run Setup.exe with the REBUILDDATABASE option.</span></span> <span data-ttu-id="b7bfb-124">Дополнительные сведения см. в разделе "Как установить SQL Server из командной строки" в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-124">For more information see "How to: Install SQL Server from the Command Prompt" in SQL Server Books Online.</span></span>  
  
  
