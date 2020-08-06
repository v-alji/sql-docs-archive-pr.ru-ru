---
title: MSSQLSERVER_825 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 825 (Database Engine error)
ms.assetid: f69f8214-5af1-4769-878b-117ad6eaff52
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3b17dfac371ad3c805fdbb0b5d3269fc451dd9d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658767"
---
# <a name="mssqlserver_825"></a><span data-ttu-id="0aeb3-102">MSSQLSERVER_825</span><span class="sxs-lookup"><span data-stu-id="0aeb3-102">MSSQLSERVER_825</span></span>
    
## <a name="details"></a><span data-ttu-id="0aeb3-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="0aeb3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0aeb3-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="0aeb3-104">Product Name</span></span>|<span data-ttu-id="0aeb3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0aeb3-105">SQL Server</span></span>|  
|<span data-ttu-id="0aeb3-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="0aeb3-106">Event ID</span></span>|<span data-ttu-id="0aeb3-107">825</span><span class="sxs-lookup"><span data-stu-id="0aeb3-107">825</span></span>|  
|<span data-ttu-id="0aeb3-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="0aeb3-108">Event Source</span></span>|<span data-ttu-id="0aeb3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0aeb3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0aeb3-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="0aeb3-110">Component</span></span>|<span data-ttu-id="0aeb3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0aeb3-111">SQLEngine</span></span>|  
|<span data-ttu-id="0aeb3-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="0aeb3-112">Symbolic Name</span></span>|<span data-ttu-id="0aeb3-113">B_RETRYWORKED</span><span class="sxs-lookup"><span data-stu-id="0aeb3-113">B_RETRYWORKED</span></span>|  
|<span data-ttu-id="0aeb3-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="0aeb3-114">Message Text</span></span>|<span data-ttu-id="0aeb3-115">Успешное чтение файла "%ls" при смещении %#016I64x после %d неудачных попыток с ошибкой: %ls.</span><span class="sxs-lookup"><span data-stu-id="0aeb3-115">A read of the file '%ls' at offset %#016I64x succeeded after failing %d time(s) with error: %ls.</span></span> <span data-ttu-id="0aeb3-116">Дополнительные сведения см. в журнале ошибок SQL Server и журнале системных событий.</span><span class="sxs-lookup"><span data-stu-id="0aeb3-116">Additional messages in the SQL Server error log and system event log may provide more detail.</span></span> <span data-ttu-id="0aeb3-117">Данное ошибочное условие может нарушить целостность базы данных и должно быть исправлено.</span><span class="sxs-lookup"><span data-stu-id="0aeb3-117">This error condition threatens database integrity and must be corrected.</span></span> <span data-ttu-id="0aeb3-118">Выполните полную проверку базы данных на согласованность (DBCC CHECKD).</span><span class="sxs-lookup"><span data-stu-id="0aeb3-118">Complete a full database consistency check (DBCC CHECKDB).</span></span> <span data-ttu-id="0aeb3-119">Эта ошибка может быть вызвана многими причинами. Дополнительные сведения см. в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0aeb3-119">This error can be caused by many factors; for more information, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0aeb3-120">Объяснение</span><span class="sxs-lookup"><span data-stu-id="0aeb3-120">Explanation</span></span>  
 <span data-ttu-id="0aeb3-121">Это сообщение указывает, что операцию чтения пришлось повторить, по меньшей мере, один раз, что свидетельствует о серьезной проблеме с оборудованием жесткого диска.</span><span class="sxs-lookup"><span data-stu-id="0aeb3-121">This message indicates that the read operation had to be reissued at least one time, and indicates a major problem with the disk hardware.</span></span> <span data-ttu-id="0aeb3-122">В настоящее время данное сообщение не указывает на проблему [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], но если не исправить ошибку диска вовремя, то она может привести к потере данных или повреждению базы данных.</span><span class="sxs-lookup"><span data-stu-id="0aeb3-122">This message does not currently indicate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] problem, but the disk problem could cause data loss or database corruption if it is not resolved.</span></span> <span data-ttu-id="0aeb3-123">В журнале системных событий могут содержаться связанные события, способствующие диагностированию проблемы.</span><span class="sxs-lookup"><span data-stu-id="0aeb3-123">The system event log may contain related events that help to diagnose the problem.</span></span> <span data-ttu-id="0aeb3-124">Дополнительные сведения об ошибках ввода-вывода см. в [главе 2 документации Майкрософт об основных операциях ввода-вывода в SQL Server](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="0aeb3-124">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0aeb3-125">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="0aeb3-125">User Action</span></span>  
 <span data-ttu-id="0aeb3-126">Следующие действия помогут идентифицировать и исправить основную проблему.</span><span class="sxs-lookup"><span data-stu-id="0aeb3-126">The following actions may help you identify and resolve the underlying problem:</span></span>  
  
-   <span data-ttu-id="0aeb3-127">Просмотрите журнал ошибок и переменный текст данного сообщения, объясняющие суть проблемы.</span><span class="sxs-lookup"><span data-stu-id="0aeb3-127">Review the error log and the variable text in this message for clues that explain the problem.</span></span>  
  
-   <span data-ttu-id="0aeb3-128">Проверьте дисковую систему.</span><span class="sxs-lookup"><span data-stu-id="0aeb3-128">Check your disk system.</span></span> <span data-ttu-id="0aeb3-129">Проблема может быть связана с жесткими дисками, контроллерами дисков, контроллерами дисковых массивов или драйверами дисков.</span><span class="sxs-lookup"><span data-stu-id="0aeb3-129">The problem could be related to the disks, the disk controllers, array cards, or disk drivers.</span></span>  
  
-   <span data-ttu-id="0aeb3-130">Обратитесь к производителю диска за новейшими утилитами проверки состояния дисковой системы.</span><span class="sxs-lookup"><span data-stu-id="0aeb3-130">Contact the disk manufacturer for the latest utilities for checking the status of your disk system.</span></span>  
  
-   <span data-ttu-id="0aeb3-131">Обратитесь к производителю диска за новейшими обновлениями драйверов.</span><span class="sxs-lookup"><span data-stu-id="0aeb3-131">Contact the disk manufacturer for the latest driver updates.</span></span>  
  
  
