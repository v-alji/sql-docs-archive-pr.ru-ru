---
title: Образец таблицы HumanResources.myTeam (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- myTeam sample table [SQL Server]
- bulk importing [SQL Server], examples
- bulk exporting [SQL Server], examples
ms.assetid: 27da45a0-c1f4-4bf4-ab24-6196e80d3834
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7d4e0cbbf42c2bdd25e3dd7c9577e4d0ec44549a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666601"
---
# <a name="humanresourcesmyteam-sample-table-sql-server"></a><span data-ttu-id="7abd6-102">Образец таблицы HumanResources.myTeam (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7abd6-102">HumanResources.myTeam Sample Table (SQL Server)</span></span>
  <span data-ttu-id="7abd6-103">Большинству примеров кода в разделе [Импорт и экспорт больших массивов данных](bulk-import-and-export-of-data-sql-server.md) требуется специальная учебная таблица **myTeam**.</span><span class="sxs-lookup"><span data-stu-id="7abd6-103">Many of the code examples in [Importing and Exporting Bulk Data](bulk-import-and-export-of-data-sql-server.md) require a special-purpose test table named **myTeam**.</span></span> <span data-ttu-id="7abd6-104">Перед выполнением примеров необходимо создать таблицу **myTeam** в схеме **HumanResources** базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7abd6-104">Before you can run the examples, you must create the **myTeam** table in the **HumanResources** schema of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] <span data-ttu-id="7abd6-105">— один из образцов баз данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7abd6-105">is one of the sample databases in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="7abd6-106">Таблица **myTeam** содержит следующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="7abd6-106">The **myTeam** table is contains the following columns.</span></span>  
  
|<span data-ttu-id="7abd6-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="7abd6-107">Column</span></span>|<span data-ttu-id="7abd6-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7abd6-108">Data type</span></span>|<span data-ttu-id="7abd6-109">Допускает значения NULL</span><span class="sxs-lookup"><span data-stu-id="7abd6-109">Nullability</span></span>|<span data-ttu-id="7abd6-110">Описание</span><span class="sxs-lookup"><span data-stu-id="7abd6-110">Description</span></span>|  
|------------|---------------|-----------------|-----------------|  
|<span data-ttu-id="7abd6-111">**EmployeeID**</span><span class="sxs-lookup"><span data-stu-id="7abd6-111">**EmployeeID**</span></span>|`smallint`|<span data-ttu-id="7abd6-112">Нет</span><span class="sxs-lookup"><span data-stu-id="7abd6-112">Not null</span></span>|<span data-ttu-id="7abd6-113">Первичный ключ для строк таблицы.</span><span class="sxs-lookup"><span data-stu-id="7abd6-113">Primary key for the rows.</span></span> <span data-ttu-id="7abd6-114">Идентификатор сотрудника — члена команды.</span><span class="sxs-lookup"><span data-stu-id="7abd6-114">Employee ID of a member of my team.</span></span>|  
|<span data-ttu-id="7abd6-115">**имя**;</span><span class="sxs-lookup"><span data-stu-id="7abd6-115">**Name**</span></span>|`nvarchar(50)`|<span data-ttu-id="7abd6-116">Нет</span><span class="sxs-lookup"><span data-stu-id="7abd6-116">Not null</span></span>|<span data-ttu-id="7abd6-117">Имя члена команды.</span><span class="sxs-lookup"><span data-stu-id="7abd6-117">Name of a member of my team.</span></span>|  
|<span data-ttu-id="7abd6-118">**Title**</span><span class="sxs-lookup"><span data-stu-id="7abd6-118">**Title**</span></span>|`nvarchar(50)`|<span data-ttu-id="7abd6-119">Допускает значения NULL</span><span class="sxs-lookup"><span data-stu-id="7abd6-119">Nullable</span></span>|<span data-ttu-id="7abd6-120">Должность, которую сотрудник занимает в команде.</span><span class="sxs-lookup"><span data-stu-id="7abd6-120">Title the employee performs on my team.</span></span>|  
|<span data-ttu-id="7abd6-121">**Вводная информация**</span><span class="sxs-lookup"><span data-stu-id="7abd6-121">**Background**</span></span>|`nvarchar(50)`|<span data-ttu-id="7abd6-122">Нет</span><span class="sxs-lookup"><span data-stu-id="7abd6-122">Not null</span></span>|<span data-ttu-id="7abd6-123">Дата и время последнего обновления строки</span><span class="sxs-lookup"><span data-stu-id="7abd6-123">Date and time the row was last updated.</span></span> <span data-ttu-id="7abd6-124">(по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7abd6-124">(Default)</span></span>|  
  
 <span data-ttu-id="7abd6-125">**Для создания таблицы HumanResources.myTeam**</span><span class="sxs-lookup"><span data-stu-id="7abd6-125">**To create HumanResources.myTeam**</span></span>  
  
-   <span data-ttu-id="7abd6-126">Используйте следующие инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="7abd6-126">Use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    --Create HumanResources.MyTeam:   
    USE AdventureWorks;  
    GO  
    CREATE TABLE HumanResources.myTeam   
    (EmployeeID smallint NOT NULL,  
    Name nvarchar(50) NOT NULL,  
    Title nvarchar(50) NULL,  
    Background nvarchar(50) NOT NULL DEFAULT ''  
    );  
    GO  
    ```  
  
 <span data-ttu-id="7abd6-127">**Для заполнения таблицы HumanResources.myTeam**</span><span class="sxs-lookup"><span data-stu-id="7abd6-127">**To populate HumanResources.myTeam**</span></span>  
  
-   <span data-ttu-id="7abd6-128">Чтобы вставить в таблицу две строки, выполните следующие инструкции `INSERT` .</span><span class="sxs-lookup"><span data-stu-id="7abd6-128">Execute following `INSERT` statements to populate the table with two rows:</span></span>  
  
    ```  
    USE AdventureWorks;  
    GO  
    INSERT INTO HumanResources.myTeam(EmployeeID,Name,Title,Background)  
       VALUES(77,'Mia Doppleganger','Administrative Assistant','Microsoft Office');  
    GO  
    INSERT INTO HumanResources.myTeam(EmployeeID,Name,Title,Background)  
       VALUES(49,'Hirum Mollicat','I.T. Specialist','Report Writing and Data Mining');  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="7abd6-129">В этих инструкциях пропущен четвертый столбец таблицы `Background`.</span><span class="sxs-lookup"><span data-stu-id="7abd6-129">These statements skip the fourth column, `Background`.</span></span> <span data-ttu-id="7abd6-130">У него есть значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7abd6-130">This has a default value.</span></span> <span data-ttu-id="7abd6-131">Если не указывать этот столбец в инструкции `INSERT` , поле останется пустым.</span><span class="sxs-lookup"><span data-stu-id="7abd6-131">Skipping this column causes this `INSERT` statement to leave this column blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7abd6-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="7abd6-132">See Also</span></span>  
 [<span data-ttu-id="7abd6-133">Массовый импорт и экспорт данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7abd6-133">Bulk Import and Export of Data &#40;SQL Server&#41;</span></span>](bulk-import-and-export-of-data-sql-server.md)  
  
  
