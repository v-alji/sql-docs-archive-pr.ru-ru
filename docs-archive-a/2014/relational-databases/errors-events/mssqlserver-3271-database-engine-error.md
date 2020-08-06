---
title: MSSQLSERVER_3271 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3271 (Database Engine error)
ms.assetid: 21b8de4b-6624-4163-9561-1a6cc8fe3d51
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56bdb5875dbba3fbe5037a308d713170a9b6f9ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658776"
---
# <a name="mssqlserver_3271"></a><span data-ttu-id="7bacc-102">MSSQLSERVER_3271</span><span class="sxs-lookup"><span data-stu-id="7bacc-102">MSSQLSERVER_3271</span></span>
    
## <a name="details"></a><span data-ttu-id="7bacc-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="7bacc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7bacc-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="7bacc-104">Product Name</span></span>|<span data-ttu-id="7bacc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7bacc-105">SQL Server</span></span>|  
|<span data-ttu-id="7bacc-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="7bacc-106">Event ID</span></span>|<span data-ttu-id="7bacc-107">3271</span><span class="sxs-lookup"><span data-stu-id="7bacc-107">3271</span></span>|  
|<span data-ttu-id="7bacc-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="7bacc-108">Event Source</span></span>|<span data-ttu-id="7bacc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7bacc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7bacc-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="7bacc-110">Component</span></span>|<span data-ttu-id="7bacc-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7bacc-111">SQLEngine</span></span>|  
|<span data-ttu-id="7bacc-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="7bacc-112">Symbolic Name</span></span>|<span data-ttu-id="7bacc-113">DMPIO_IO_ERROR</span><span class="sxs-lookup"><span data-stu-id="7bacc-113">DMPIO_IO_ERROR</span></span>|  
|<span data-ttu-id="7bacc-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="7bacc-114">Message Text</span></span>|<span data-ttu-id="7bacc-115">Произошла неустранимая ошибка ввода-вывода в файле "%ls:" %ls.</span><span class="sxs-lookup"><span data-stu-id="7bacc-115">A nonrecoverable I/O error occurred on file "%ls:" %ls.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7bacc-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="7bacc-116">Explanation</span></span>  
 <span data-ttu-id="7bacc-117">Это общая ошибка, возникающая, когда происходит ошибка ввода-вывода операционной системы во время операций резервного копирования или восстановления.</span><span class="sxs-lookup"><span data-stu-id="7bacc-117">This is a general error that occurs when the operating system raises an error while performing I/O during a backup or restore operation.</span></span> <span data-ttu-id="7bacc-118">В большинстве ситуаций причина состоит в том, что переполняется носитель данных резервных копий.</span><span class="sxs-lookup"><span data-stu-id="7bacc-118">In most situations the cause is simply that the backup medium is full.</span></span>  
  
 <span data-ttu-id="7bacc-119">Эта ошибка может содержать дополнительное сообщение операционной системы, указывающее, что диск заполнен.</span><span class="sxs-lookup"><span data-stu-id="7bacc-119">The error may include additional text from the operating system indicating that the disk is full.</span></span> <span data-ttu-id="7bacc-120">При выполнении операций резервного копирования или восстановления с помощью программ сторонних разработчиков может появляться дополнительное сообщение, указывающее на ошибку резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7bacc-120">When performing a backup or restore operation with third-party backup software an additional message may occur indicating that the backup failed.</span></span> <span data-ttu-id="7bacc-121">Это сообщение может напоминать следующий текст:</span><span class="sxs-lookup"><span data-stu-id="7bacc-121">The message may look similar to the following text:</span></span>  
  
```  
"2005-08-02 16:05:16.04 spid55 Error: 18210, Severity: 16, State: 1.  
 2005-08-02 16:05:16.04 spid55 BackupVirtualDeviceFile  
::RequestDurableMedia: Flush failure on backup device 'VDINULL'.   
Operating system error 995(The I/O operation has been aborted because   
of either a thread exit or an application request.)."  
```  
  
 <span data-ttu-id="7bacc-122">Оно указывает на то, что программа резервного копирования запросила завершение резервного копирования или восстановления.</span><span class="sxs-lookup"><span data-stu-id="7bacc-122">This is an indication that the backup software requested a termination of the backup or restore operation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7bacc-123">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="7bacc-123">User Action</span></span>  
 <span data-ttu-id="7bacc-124">При необходимости выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="7bacc-124">Perform the following tasks as appropriate:</span></span>  
  
-   <span data-ttu-id="7bacc-125">Для определения причины этой неполадки просмотрите сообщения об ошибках операционной системы и SQL Server, предшествующие ей.</span><span class="sxs-lookup"><span data-stu-id="7bacc-125">Review the underlying system error messages and SQL Server error messages preceding this one to identify the cause of the failure.</span></span>  
  
-   <span data-ttu-id="7bacc-126">Убедитесь в наличии достаточного места на носителе резервных данных.</span><span class="sxs-lookup"><span data-stu-id="7bacc-126">Ensure that the backup and restore medium has sufficient space.</span></span>  
  
-   <span data-ttu-id="7bacc-127">Исправьте все ошибки, возникшие в программе резервного копирования и восстановления данных от сторонних разработчиков.</span><span class="sxs-lookup"><span data-stu-id="7bacc-127">Correct any errors raised by third-party backup and restore software.</span></span>  
  
  
