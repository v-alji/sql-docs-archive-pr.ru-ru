---
title: MSSQLSERVER_1803 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1803 (Database Engine error)
ms.assetid: d4315390-82f1-4c4c-8d1b-1a4989537cca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 11302f882846c49c6e9998608967e7042ac9860c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665372"
---
# <a name="mssqlserver_1803"></a><span data-ttu-id="d94f1-102">MSSQLSERVER_1803</span><span class="sxs-lookup"><span data-stu-id="d94f1-102">MSSQLSERVER_1803</span></span>
    
## <a name="details"></a><span data-ttu-id="d94f1-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="d94f1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d94f1-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="d94f1-104">Product Name</span></span>|<span data-ttu-id="d94f1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d94f1-105">SQL Server</span></span>|  
|<span data-ttu-id="d94f1-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="d94f1-106">Event ID</span></span>|<span data-ttu-id="d94f1-107">1803</span><span class="sxs-lookup"><span data-stu-id="d94f1-107">1803</span></span>|  
|<span data-ttu-id="d94f1-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="d94f1-108">Event Source</span></span>|<span data-ttu-id="d94f1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d94f1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d94f1-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="d94f1-110">Component</span></span>|<span data-ttu-id="d94f1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d94f1-111">SQLEngine</span></span>|  
|<span data-ttu-id="d94f1-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="d94f1-112">Symbolic Name</span></span>|<span data-ttu-id="d94f1-113">NO_SPACE</span><span class="sxs-lookup"><span data-stu-id="d94f1-113">NO_SPACE</span></span>|  
|<span data-ttu-id="d94f1-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="d94f1-114">Message Text</span></span>|<span data-ttu-id="d94f1-115">Ошибка операции CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="d94f1-115">CREATE DATABASE failed.</span></span> <span data-ttu-id="d94f1-116">Размер первичного ключа должен быть как минимум %d МБ, чтобы вместить копию базы данных model.</span><span class="sxs-lookup"><span data-stu-id="d94f1-116">Primary file must be at least %d MB to accommodate a copy of the model database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d94f1-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="d94f1-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d94f1-118">создает базу данных путем копирования базы данных model.</span><span class="sxs-lookup"><span data-stu-id="d94f1-118">creates a database by making a copy of the model database.</span></span> <span data-ttu-id="d94f1-119">Затем [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] переименовывает копию и увеличивает новую базу данных до необходимого размера.</span><span class="sxs-lookup"><span data-stu-id="d94f1-119">Then [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] renames the copy, and enlarges the new database to the requested size.</span></span> <span data-ttu-id="d94f1-120">В этом случае пользователь выполняет попытку создания базы данных, размер которой меньше размера базы данных model.</span><span class="sxs-lookup"><span data-stu-id="d94f1-120">In this case, the user tried to create a database smaller than the model database.</span></span> <span data-ttu-id="d94f1-121">При выполнении операции произошла ошибка, поскольку копия базы данных model не помещалась в первичном файле данных, так как размер файла меньше размера базы данных model.</span><span class="sxs-lookup"><span data-stu-id="d94f1-121">The operation failed because the copy of the model database could not fit on the primary data file, because the file was smaller than the model database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d94f1-122">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="d94f1-122">User Action</span></span>  
 <span data-ttu-id="d94f1-123">Создайте базу данных с помощью файла базы данных большего размера.</span><span class="sxs-lookup"><span data-stu-id="d94f1-123">Create the database by using a larger database file size.</span></span> <span data-ttu-id="d94f1-124">Затем при необходимости сожмите базу данных с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или инструкции DBCC SHRINKDATABASE.</span><span class="sxs-lookup"><span data-stu-id="d94f1-124">Then shrink the database if you want by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], or the DBCC SHRINKDATABASE statement.</span></span>  
  
  
