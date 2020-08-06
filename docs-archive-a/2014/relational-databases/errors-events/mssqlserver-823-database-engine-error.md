---
title: MSSQLSERVER_823 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 823 (Database Engine error)
ms.assetid: 0d9fce3c-3772-46ce-a7a3-4f4988dc6cae
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fa5858bbdc9452a33a3d43fdd783e59556a11e57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664215"
---
# <a name="mssqlserver_823"></a><span data-ttu-id="3190f-102">MSSQLSERVER_823</span><span class="sxs-lookup"><span data-stu-id="3190f-102">MSSQLSERVER_823</span></span>
    
## <a name="details"></a><span data-ttu-id="3190f-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="3190f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3190f-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="3190f-104">Product Name</span></span>|<span data-ttu-id="3190f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3190f-105">SQL Server</span></span>|  
|<span data-ttu-id="3190f-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="3190f-106">Event ID</span></span>|<span data-ttu-id="3190f-107">823</span><span class="sxs-lookup"><span data-stu-id="3190f-107">823</span></span>|  
|<span data-ttu-id="3190f-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="3190f-108">Event Source</span></span>|<span data-ttu-id="3190f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3190f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3190f-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="3190f-110">Component</span></span>|<span data-ttu-id="3190f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3190f-111">SQLEngine</span></span>|  
|<span data-ttu-id="3190f-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="3190f-112">Symbolic Name</span></span>|<span data-ttu-id="3190f-113">B_HARDERR</span><span class="sxs-lookup"><span data-stu-id="3190f-113">B_HARDERR</span></span>|  
|<span data-ttu-id="3190f-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="3190f-114">Message Text</span></span>|<span data-ttu-id="3190f-115">Операционная система возвратила ошибку %ls в SQL Server при %S_MSG в смещении %#016I64x файла «%ls».</span><span class="sxs-lookup"><span data-stu-id="3190f-115">The operating system returned error %ls to SQL Server during a %S_MSG at offset %#016I64x in file '%ls'.</span></span> <span data-ttu-id="3190f-116">Дополнительные сведения см. в журнале ошибок SQL Server и журнале системных событий.</span><span class="sxs-lookup"><span data-stu-id="3190f-116">Additional messages in the SQL Server error log and system event log may provide more detail.</span></span> <span data-ttu-id="3190f-117">Это серьезная ошибка системного уровня, которая угрожает целостности базы данных, поэтому она должна быть немедленно исправлена.</span><span class="sxs-lookup"><span data-stu-id="3190f-117">This is a severe system-level error condition that threatens database integrity and must be corrected immediately.</span></span> <span data-ttu-id="3190f-118">Выполните полную проверку базы данных на согласованность (DBCC CHECKD).</span><span class="sxs-lookup"><span data-stu-id="3190f-118">Complete a full database consistency check (DBCC CHECKDB).</span></span> <span data-ttu-id="3190f-119">Эта ошибка может быть вызвана многими причинами. Дополнительные сведения см. в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3190f-119">This error can be caused by many factors; for more information, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3190f-120">Объяснение</span><span class="sxs-lookup"><span data-stu-id="3190f-120">Explanation</span></span>  
 <span data-ttu-id="3190f-121">Запрос Windows на чтение или запись завершился ошибкой.</span><span class="sxs-lookup"><span data-stu-id="3190f-121">A Windows read or write request has failed.</span></span> <span data-ttu-id="3190f-122">Код ошибки, возвращаемой Windows, и соответствующий текст содержатся в сообщении.</span><span class="sxs-lookup"><span data-stu-id="3190f-122">The error code that is returned by Windows and the corresponding text are inserted into the message.</span></span> <span data-ttu-id="3190f-123">В случае операции чтения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] повторяет попытку чтения четыре раза.</span><span class="sxs-lookup"><span data-stu-id="3190f-123">In the read case, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will have already retried the read request four times.</span></span> <span data-ttu-id="3190f-124">Такой сбой обычно является результатом ошибки оборудования, но в некоторых случаях причиной может являться неисправность драйвера устройства.</span><span class="sxs-lookup"><span data-stu-id="3190f-124">This error is often the result of a hardware error, but may be caused by the device driver.</span></span> <span data-ttu-id="3190f-125">Дополнительные сведения об ошибке 823 см. в разделе [https://support.microsoft.com/kb/828339](https://support.microsoft.com/kb/828339) .</span><span class="sxs-lookup"><span data-stu-id="3190f-125">For more information about error 823, see [https://support.microsoft.com/kb/828339](https://support.microsoft.com/kb/828339).</span></span> <span data-ttu-id="3190f-126">Дополнительные сведения об ошибках ввода-вывода см. в [главе 2 документации Майкрософт об основных операциях ввода-вывода в SQL Server](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="3190f-126">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3190f-127">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="3190f-127">User Action</span></span>  
 <span data-ttu-id="3190f-128">Просмотрите дополнительные сведения в журнале системных событий.</span><span class="sxs-lookup"><span data-stu-id="3190f-128">Check for additional information in the system event log.</span></span> <span data-ttu-id="3190f-129">Свяжитесь с производителем оборудования или со специалистами поддержки пользователей Майкрософт для выяснения причин сбоя и необходимых действий по его исправлению.</span><span class="sxs-lookup"><span data-stu-id="3190f-129">Contact the hardware manufacturer or Microsoft Customer Services and Support to determine the cause and corrective action.</span></span> <span data-ttu-id="3190f-130">После исправления ошибки оборудования восстановите все базы данных и запустите DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="3190f-130">After the hardware error is fixed, restore all databases and run DBCC CHECKDB.</span></span>  
  
  
