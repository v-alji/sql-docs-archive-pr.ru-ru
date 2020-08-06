---
title: MSSQLSERVER_511 | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 511 (Database Engine error)
ms.assetid: 0c85686a-53c1-4180-ba8c-2000e68a0d63
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5b69d2c043997e2947563de119bc4ee89fdf4e32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730701"
---
# <a name="mssqlserver_511"></a><span data-ttu-id="7bcc8-102">MSSQLSERVER_511</span><span class="sxs-lookup"><span data-stu-id="7bcc8-102">MSSQLSERVER_511</span></span>
    
## <a name="details"></a><span data-ttu-id="7bcc8-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="7bcc8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7bcc8-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="7bcc8-104">Product Name</span></span>|<span data-ttu-id="7bcc8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7bcc8-105">SQL Server</span></span>|  
|<span data-ttu-id="7bcc8-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="7bcc8-106">Event ID</span></span>|<span data-ttu-id="7bcc8-107">511</span><span class="sxs-lookup"><span data-stu-id="7bcc8-107">511</span></span>|  
|<span data-ttu-id="7bcc8-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="7bcc8-108">Event Source</span></span>|<span data-ttu-id="7bcc8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7bcc8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7bcc8-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="7bcc8-110">Component</span></span>|<span data-ttu-id="7bcc8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7bcc8-111">SQLEngine</span></span>|  
|<span data-ttu-id="7bcc8-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="7bcc8-112">Symbolic Name</span></span>|<span data-ttu-id="7bcc8-113">ROW_TOOBIG</span><span class="sxs-lookup"><span data-stu-id="7bcc8-113">ROW_TOOBIG</span></span>|  
|<span data-ttu-id="7bcc8-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="7bcc8-114">Message Text</span></span>|<span data-ttu-id="7bcc8-115">Не удалось создать строку размером %d, который превышает допустимый максимум, равный %d.</span><span class="sxs-lookup"><span data-stu-id="7bcc8-115">Cannot create a row of size %d which is greater than the allowable maximum of %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7bcc8-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="7bcc8-116">Explanation</span></span>  
 <span data-ttu-id="7bcc8-117">При попытке выполнения операции был превышен максимальный размер строки.</span><span class="sxs-lookup"><span data-stu-id="7bcc8-117">The operation you have tried has exceeded the maximum size of a row.</span></span> <span data-ttu-id="7bcc8-118">Обычно максимальный размер строки составляет 8 060 байт.</span><span class="sxs-lookup"><span data-stu-id="7bcc8-118">Usually, the maximum size of a row is 8,060 bytes.</span></span> <span data-ttu-id="7bcc8-119">При использовании некоторых форматов хранения возникают издержки, которые становятся причиной сокращения размера строки, доступного для записи данных.</span><span class="sxs-lookup"><span data-stu-id="7bcc8-119">Some storage formats contain overhead that can reduce the row size that is available for data.</span></span> <span data-ttu-id="7bcc8-120">Например, при использовании разреженных столбцов максимальный размер строки составляет 8 018 байт.</span><span class="sxs-lookup"><span data-stu-id="7bcc8-120">For example, when you use sparse columns, the maximum size of a row is 8,018 bytes.</span></span> <span data-ttu-id="7bcc8-121">При выполнении некоторых операций по добавлению или удалению строк, а также некоторых операций, изменяющих тип данных столбца, строка перезаписывается на странице данных, после чего исходная строка удаляется.</span><span class="sxs-lookup"><span data-stu-id="7bcc8-121">Some operations that add or remove rows and some operations that change the data type of a column require the row to be rewritten on the data page, and then the original row is removed.</span></span> <span data-ttu-id="7bcc8-122">В процессе выполнения такой операции эффективный размер строки ограничен половиной максимального размера.</span><span class="sxs-lookup"><span data-stu-id="7bcc8-122">In these operations, the effective limit to the size of the row is half the maximum limit.</span></span> <span data-ttu-id="7bcc8-123">Причина этого заключается в том, что страница данных должна в течение краткого периода времени содержать обе строки — исходную и измененную.</span><span class="sxs-lookup"><span data-stu-id="7bcc8-123">This is because the original row and the modified row must both be contained on the data page for a short period.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="7bcc8-124">Для каждого столбца **varchar (max)** или **nvarchar (max)** , отличного от NULL, требуется 24 байта дополнительного фиксированного выделения, которое подсчитывается до предельного числа 8 060 байт в строке во время операции сортировки.</span><span class="sxs-lookup"><span data-stu-id="7bcc8-124">Each non-null  **varchar(max)** or **nvarchar(max)** column requires 24 bytes of additional fixed allocation which counts against the 8,060 byte row limit during a sort operation.</span></span> <span data-ttu-id="7bcc8-125">Это может привести к неявному ограничению числа столбцов **varchar (max)** или **nvarchar (max)** , отличных от NULL, которые могут быть созданы в таблице.</span><span class="sxs-lookup"><span data-stu-id="7bcc8-125">This can create an implicit limit to the number of non-null **varchar(max)** or **nvarchar(max)** columns that can be created in a table.</span></span> <span data-ttu-id="7bcc8-126">При создании таблицы или во время вставки данных не возникает особых ошибок (кроме обычного предупреждения о том, что максимальный размер строки превышает максимально допустимое значение в 8060 байт).</span><span class="sxs-lookup"><span data-stu-id="7bcc8-126">No special error is provided when the table is created (beyond the usual warning that the maximum row size exceeds the allowed maximum of 8060 bytes) or at the time of data insertion.</span></span> <span data-ttu-id="7bcc8-127">Этот крупный размер строки может вызывать ошибки (например, ошибку 512) во время некоторых обычных операций, таких как обновление ключа кластеризованного индекса, или сортировать полный набор столбцов, который пользователи не могут использовать до выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="7bcc8-127">This large row size can cause errors (such as error 512) during some normal operations, such as a clustered index key update, or sorts of the full column set, which users cannot anticipate until performing an operation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7bcc8-128">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="7bcc8-128">User Action</span></span>  
 <span data-ttu-id="7bcc8-129">Если возможно, сократите размер строки.</span><span class="sxs-lookup"><span data-stu-id="7bcc8-129">If it is possible, reduce the size of the row.</span></span>  
  
 <span data-ttu-id="7bcc8-130">Если проблема может быть вызвана обновлением строки на месте, необходимо изменять таблицу в несколько этапов.</span><span class="sxs-lookup"><span data-stu-id="7bcc8-130">If you think the problem is caused by an in-place update of the row, you must change the table in multiple steps.</span></span> <span data-ttu-id="7bcc8-131">Создайте новую таблицу и передайте в нее данные.</span><span class="sxs-lookup"><span data-stu-id="7bcc8-131">Create a new table, and transfer the data into the new table.</span></span> <span data-ttu-id="7bcc8-132">Затем удалите исходную таблицу и переименуйте новую таблицу либо выполните усечение исходной таблицы, измените строки в исходной таблице, а затем переместите данные обратно в нее.</span><span class="sxs-lookup"><span data-stu-id="7bcc8-132">Then, either delete the original table and rename the new table, or truncate the original table, modify the rows in the original table, and then move the data back into it.</span></span>  
  
  
