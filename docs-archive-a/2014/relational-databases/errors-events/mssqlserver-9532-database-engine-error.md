---
title: MSSQLSERVER_ 9532 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9532 (Database Engine error)
ms.assetid: ab95cce8-4f97-4aea-a746-a73eea7c9aab
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c34ebc7c682d2ffe8bc0205565f5dfd44fdd5b66
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658749"
---
# <a name="mssqlserver_9532"></a><span data-ttu-id="b7abd-102">MSSQLSERVER_9532</span><span class="sxs-lookup"><span data-stu-id="b7abd-102">MSSQLSERVER_9532</span></span>
    
## <a name="details"></a><span data-ttu-id="b7abd-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="b7abd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b7abd-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="b7abd-104">Product Name</span></span>|<span data-ttu-id="b7abd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b7abd-105">SQL Server</span></span>|  
|<span data-ttu-id="b7abd-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="b7abd-106">Event ID</span></span>|<span data-ttu-id="b7abd-107">9532</span><span class="sxs-lookup"><span data-stu-id="b7abd-107">9532</span></span>|  
|<span data-ttu-id="b7abd-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="b7abd-108">Event Source</span></span>|<span data-ttu-id="b7abd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b7abd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b7abd-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="b7abd-110">Component</span></span>|<span data-ttu-id="b7abd-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b7abd-111">SQLEngine</span></span>|  
|<span data-ttu-id="b7abd-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="b7abd-112">Symbolic Name</span></span>|<span data-ttu-id="b7abd-113">XMLERR_COLUMNSET_CANNOT_CONVERT_FROM_TO</span><span class="sxs-lookup"><span data-stu-id="b7abd-113">XMLERR_COLUMNSET_CANNOT_CONVERT_FROM_TO</span></span>|  
|<span data-ttu-id="b7abd-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="b7abd-114">Message Text</span></span>|<span data-ttu-id="b7abd-115">При обработке запроса или операции DML над набором столбцов "%.\*ls" произошла ошибка преобразования данных типа "%ls" к типу "%ls" для столбца "%.\*ls".</span><span class="sxs-lookup"><span data-stu-id="b7abd-115">In the query/DML operation involving  column set '%.\*ls', conversion failed when converting from the data type '%ls' to the data type '%ls' for the column '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b7abd-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="b7abd-116">Explanation</span></span>  
 <span data-ttu-id="b7abd-117">Набор столбцов представляет собой нетипизированное XML-представление, объединяющее несколько столбцов таблицы в виде структурированного вывода.</span><span class="sxs-lookup"><span data-stu-id="b7abd-117">A column set is an untyped XML representation that combines some of the columns of a table into a structured output.</span></span> <span data-ttu-id="b7abd-118">При вставке или обновлении значений разреженного столбца в наборе XML-столбцов значения, вставляемые в базовые разреженные столбцы, неявным образом преобразуются из типа данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="b7abd-118">When you are inserting or updating sparse column values through the XML column set, the values that are inserted into the underlying sparse columns are implicitly converted from the `xml` data type.</span></span> <span data-ttu-id="b7abd-119">Было передано значение, которое не может быть преобразовано в тип данных столбца.</span><span class="sxs-lookup"><span data-stu-id="b7abd-119">A value was provided that cannot be converted to the data type of the column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b7abd-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="b7abd-120">User Action</span></span>  
 <span data-ttu-id="b7abd-121">Поскольку предоставленное значение не удалось неявно преобразовать, запись может оказаться недопустимой.</span><span class="sxs-lookup"><span data-stu-id="b7abd-121">Because the value provided could not be implicitly converted, it might be an invalid entry.</span></span> <span data-ttu-id="b7abd-122">Исправьте ошибку и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="b7abd-122">Correct the error and retry.</span></span> <span data-ttu-id="b7abd-123">Если значение является верным, измените инструкцию таким образом, чтобы использовались отдельные столбцы, а не набор столбцов.</span><span class="sxs-lookup"><span data-stu-id="b7abd-123">If the value is correct, modify the statement to use the individual columns instead of the column set.</span></span> <span data-ttu-id="b7abd-124">Это позволит выполнить приведение значения в правильный тип данных явным образом.</span><span class="sxs-lookup"><span data-stu-id="b7abd-124">This will allow you to explicitly cast the value into the correct data type.</span></span>  
  
  
