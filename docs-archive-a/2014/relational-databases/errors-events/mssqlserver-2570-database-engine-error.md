---
title: MSSQLSERVER_2570 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2570 (Database Engine error)
ms.assetid: 29800aa9-81aa-4371-992c-487dbb617f46
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 79137d0f70c05c6aa7b758f7e073d152681a14b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729509"
---
# <a name="mssqlserver_2570"></a><span data-ttu-id="926d0-102">MSSQLSERVER_2570</span><span class="sxs-lookup"><span data-stu-id="926d0-102">MSSQLSERVER_2570</span></span>
    
## <a name="details"></a><span data-ttu-id="926d0-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="926d0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="926d0-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="926d0-104">Product Name</span></span>|<span data-ttu-id="926d0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="926d0-105">SQL Server</span></span>|  
|<span data-ttu-id="926d0-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="926d0-106">Event ID</span></span>|<span data-ttu-id="926d0-107">2570</span><span class="sxs-lookup"><span data-stu-id="926d0-107">2570</span></span>|  
|<span data-ttu-id="926d0-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="926d0-108">Event Source</span></span>|<span data-ttu-id="926d0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="926d0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="926d0-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="926d0-110">Component</span></span>|<span data-ttu-id="926d0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="926d0-111">SQLEngine</span></span>|  
|<span data-ttu-id="926d0-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="926d0-112">Symbolic Name</span></span>|<span data-ttu-id="926d0-113">DBCC_COLUMN_VALUE_OUT_OF_RANGE</span><span class="sxs-lookup"><span data-stu-id="926d0-113">DBCC_COLUMN_VALUE_OUT_OF_RANGE</span></span>|  
|<span data-ttu-id="926d0-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="926d0-114">Message Text</span></span>|<span data-ttu-id="926d0-115">Страница P_ID, область памяти S_ID в идентификаторе объекта O_ID, идентификатор индекса I_ID, идентификатор секции PN_ID, идентификатор единицы распределения A_ID (тип TYPE).</span><span class="sxs-lookup"><span data-stu-id="926d0-115">Page P_ID, slot S_ID in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="926d0-116">Значение столбца COLUMN_NAME вне допустимого диапазона типа данных «DATATYPE».</span><span class="sxs-lookup"><span data-stu-id="926d0-116">Column COLUMN_NAME value is out of range for data type "DATATYPE".</span></span> <span data-ttu-id="926d0-117">Замените значение столбца на допустимое.</span><span class="sxs-lookup"><span data-stu-id="926d0-117">Update column to a legal value.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="926d0-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="926d0-118">Explanation</span></span>  
 <span data-ttu-id="926d0-119">Значение указанного столбца выходит за пределы допустимого диапазона возможных значений для типа данных этого столбца.</span><span class="sxs-lookup"><span data-stu-id="926d0-119">The column value that is contained in the specified column is outside the range of possible values for the column data type.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="926d0-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="926d0-120">User Action</span></span>  
 <span data-ttu-id="926d0-121">Исправить ошибку невозможно.</span><span class="sxs-lookup"><span data-stu-id="926d0-121">The error is not repairable.</span></span> <span data-ttu-id="926d0-122">Замените значение столбца на допустимое в пределах диапазона для типа данных этого столбца и выполните команду еще раз.</span><span class="sxs-lookup"><span data-stu-id="926d0-122">Update the column to a value within the range for the data type of the column and run the command again.</span></span>  <span data-ttu-id="926d0-123">Дополнительные сведения см. в статье базы знаний [923247](https://support.microsoft.com/kb/923247).</span><span class="sxs-lookup"><span data-stu-id="926d0-123">For more information, see this KB article [923247](https://support.microsoft.com/kb/923247).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="926d0-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="926d0-124">See Also</span></span>  
 <span data-ttu-id="926d0-125">[UPDATE (Transact-SQL)](/sql/t-sql/queries/update-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="926d0-125">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span></span>  
 [<span data-ttu-id="926d0-126">Типы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="926d0-126">Data Types &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
