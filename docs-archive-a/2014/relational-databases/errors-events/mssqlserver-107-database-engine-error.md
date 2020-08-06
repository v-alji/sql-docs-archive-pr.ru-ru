---
title: MSSQLSERVER_107 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 107 (Database Engine error)
ms.assetid: f33f514c-56aa-42e2-841b-e91244da90e2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b9388bbda6f00b1aafd02caee1b6a7b8387564f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666663"
---
# <a name="mssqlserver_107"></a><span data-ttu-id="0d181-102">MSSQLSERVER_107</span><span class="sxs-lookup"><span data-stu-id="0d181-102">MSSQLSERVER_107</span></span>
    
## <a name="details"></a><span data-ttu-id="0d181-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="0d181-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0d181-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="0d181-104">Product Name</span></span>|<span data-ttu-id="0d181-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0d181-105">SQL Server</span></span>|  
|<span data-ttu-id="0d181-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="0d181-106">Event ID</span></span>|<span data-ttu-id="0d181-107">107</span><span class="sxs-lookup"><span data-stu-id="0d181-107">107</span></span>|  
|<span data-ttu-id="0d181-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="0d181-108">Event Source</span></span>|<span data-ttu-id="0d181-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0d181-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0d181-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="0d181-110">Component</span></span>|<span data-ttu-id="0d181-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0d181-111">SQLEngine</span></span>|  
|<span data-ttu-id="0d181-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="0d181-112">Symbolic Name</span></span>|<span data-ttu-id="0d181-113">P_NOCORRMATCH</span><span class="sxs-lookup"><span data-stu-id="0d181-113">P_NOCORRMATCH</span></span>|  
|<span data-ttu-id="0d181-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="0d181-114">Message Text</span></span>|<span data-ttu-id="0d181-115">Префикс столбца «%.\*ls» не совпадает с именем таблицы или псевдонимом, используемым в запросе.</span><span class="sxs-lookup"><span data-stu-id="0d181-115">The column prefix '%.\*ls' does not match with a table name or alias name used in the query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0d181-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="0d181-116">Explanation</span></span>  
 <span data-ttu-id="0d181-117">Список выбора запроса содержит звездочку (\*), которая неправильно дополнена префиксом столбца.</span><span class="sxs-lookup"><span data-stu-id="0d181-117">The select list of the query contains an asterisk (\*) that is incorrectly qualified with a column prefix.</span></span> <span data-ttu-id="0d181-118">Эта ошибка может быть возвращена при следующих условиях.</span><span class="sxs-lookup"><span data-stu-id="0d181-118">This error can be returned under the following conditions:</span></span>  
  
-   <span data-ttu-id="0d181-119">Префикс столбца не соответствует ни одному имени таблицы или псевдониму, используемому в запросе.</span><span class="sxs-lookup"><span data-stu-id="0d181-119">The column prefix does not correspond to any table or alias name used in the query.</span></span> <span data-ttu-id="0d181-120">Например, в следующей инструкции в качестве префикса столбца используется псевдоним (`T1`), но этот псевдоним не определен в предложении FROM.</span><span class="sxs-lookup"><span data-stu-id="0d181-120">For example, the following statement uses an alias name (`T1`) as a column prefix, but the alias is not defined in the FROM clause.</span></span>  
  
    ```  
    SELECT T1.* FROM dbo.ErrorLog;  
    ```  
  
-   <span data-ttu-id="0d181-121">В качестве префикса столбца указано имя таблицы, а в предложении FROM для таблицы указан псевдоним.</span><span class="sxs-lookup"><span data-stu-id="0d181-121">A table name is specified as a column prefix when an alias name for the table is supplied in the FROM clause.</span></span> <span data-ttu-id="0d181-122">Например, в следующей инструкции в качестве префикса столбца используется имя таблицы `ErrorLog`, но таблица имеет псевдоним (`T1`), определенный в предложении FROM.</span><span class="sxs-lookup"><span data-stu-id="0d181-122">For example, the following statement uses the table name `ErrorLog` as the column prefix; however, the table has an alias (`T1`) defined in the FROM clause.</span></span>  
  
    ```  
    SELECT ErrorLog.* FROM dbo.ErrorLog AS T1;  
    ```  
  
     <span data-ttu-id="0d181-123">Если в предложении FROM предусмотрен псевдоним для имени таблицы, то для обозначения префиксом столбцов этой таблицы можно использовать только псевдоним.</span><span class="sxs-lookup"><span data-stu-id="0d181-123">If an alias has been provided for a table name in the FROM clause, you can only use the alias to prefix columns from the table.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0d181-124">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="0d181-124">User Action</span></span>  
 <span data-ttu-id="0d181-125">Префиксы столбцов должны быть согласованы с именами таблиц или псевдонимами, указанными в предложении FROM запроса.</span><span class="sxs-lookup"><span data-stu-id="0d181-125">Match the column prefixes against the table names or alias names specified in the FROM clause of the query.</span></span> <span data-ttu-id="0d181-126">Например, приведенные выше инструкции могут быть исправлены следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0d181-126">For example, the statements above can be corrected as follows:</span></span>  
  
```  
SELECT T1.* FROM dbo.ErrorLog AS T1;  
```  
  
 <span data-ttu-id="0d181-127">или диспетчер конфигурации служб</span><span class="sxs-lookup"><span data-stu-id="0d181-127">or</span></span>  
  
```  
SELECT ErrorLog.* FROM dbo.ErrorLog;  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d181-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="0d181-128">See Also</span></span>  
 [<span data-ttu-id="0d181-129">MSSQLSERVER_4104</span><span class="sxs-lookup"><span data-stu-id="0d181-129">MSSQLSERVER_4104</span></span>](mssqlserver-4104-database-engine-error.md)  
  
  
