---
title: MSSQLSERVER_3619 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3619 (Database Engine error)
ms.assetid: 7d94f8d9-65ca-4fde-9c17-7b83e94a3779
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2328ee6366d47130a02c444bce65b7b655af7965
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667109"
---
# <a name="mssqlserver_3619"></a><span data-ttu-id="285e2-102">MSSQLSERVER_3619</span><span class="sxs-lookup"><span data-stu-id="285e2-102">MSSQLSERVER_3619</span></span>
    
## <a name="details"></a><span data-ttu-id="285e2-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="285e2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="285e2-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="285e2-104">Product Name</span></span>|<span data-ttu-id="285e2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="285e2-105">SQL Server</span></span>|  
|<span data-ttu-id="285e2-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="285e2-106">Event ID</span></span>|<span data-ttu-id="285e2-107">3619</span><span class="sxs-lookup"><span data-stu-id="285e2-107">3619</span></span>|  
|<span data-ttu-id="285e2-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="285e2-108">Event Source</span></span>|<span data-ttu-id="285e2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="285e2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="285e2-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="285e2-110">Component</span></span>|<span data-ttu-id="285e2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="285e2-111">SQLEngine</span></span>|  
|<span data-ttu-id="285e2-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="285e2-112">Symbolic Name</span></span>|<span data-ttu-id="285e2-113">SYS_NOLOG</span><span class="sxs-lookup"><span data-stu-id="285e2-113">SYS_NOLOG</span></span>|  
|<span data-ttu-id="285e2-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="285e2-114">Message Text</span></span>|<span data-ttu-id="285e2-115">Нельзя сделать запись о контрольной точке в базе данных с идентификатором ID %d, поскольку закончилось место в журнале.</span><span class="sxs-lookup"><span data-stu-id="285e2-115">Could not write a checkpoint record in database ID %d because the log is out of space.</span></span> <span data-ttu-id="285e2-116">Свяжитесь с администратором базы данных, чтобы он очистил журнал или выделил больше места для файлов журнала базы данных.</span><span class="sxs-lookup"><span data-stu-id="285e2-116">Contact the database administrator to truncate the log or allocate more space to the database log files.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="285e2-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="285e2-117">Explanation</span></span>  
 <span data-ttu-id="285e2-118">Не хватает места на диске для журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="285e2-118">The transaction log is out of disk space.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="285e2-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="285e2-119">User Action</span></span>  
 <span data-ttu-id="285e2-120">Выполните усечение журнала для освобождения места на диске или выделите дополнительное место для журнала.</span><span class="sxs-lookup"><span data-stu-id="285e2-120">Truncate the log to release some space, or allocate more space to the log.</span></span> <span data-ttu-id="285e2-121">Дополнительные сведения см. в разделе «Устранение неполадок в полном журнале транзакций (ошибка 9002)» электронной документации по SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="285e2-121">For more information see, "Troubleshooting a Full Transaction Log (Error 9002)" in SQL Server Books Online.</span></span>  
  
  
