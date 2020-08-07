---
title: Создание таблицы для хранения данных FILESTREAM | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], table storage
ms.assetid: 029c3059-5c83-43e2-a859-9027031b7de1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 484d7b58ce949df79dc7e17ee4dc7307b70c0154
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731729"
---
# <a name="create-a-table-for-storing-filestream-data"></a><span data-ttu-id="a021e-102">Создание таблицы для хранения данных FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="a021e-102">Create a Table for Storing FILESTREAM Data</span></span>
  <span data-ttu-id="a021e-103">В этом разделе приводятся сведения о создании таблицы для хранения данных FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="a021e-103">This topic shows how to create a table for storing FILESTREAM data.</span></span>  
  
 <span data-ttu-id="a021e-104">Если в базе данных имеется файловая группа FILESTREAM, можно создавать или изменять таблицы для хранения данных FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="a021e-104">When the database has a FILESTREAM filegroup, you can create or modify tables to store FILESTREAM data.</span></span> <span data-ttu-id="a021e-105">Чтобы указать, что в столбце будут содержаться данные типа FILESTREAM, необходимо создать столбец с типом данных `varbinary(max)` и добавить ему атрибут FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="a021e-105">To specify that a column contains FILESTREAM data, you create a `varbinary(max)` column and add the FILESTREAM attribute.</span></span>  
  
### <a name="to-create-a-table-to-store-filestream-data"></a><span data-ttu-id="a021e-106">Создание таблицы для хранения данных FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="a021e-106">To create a table to store FILESTREAM data</span></span>  
  
1.  <span data-ttu-id="a021e-107">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]нажмите кнопку **Создать запрос** , чтобы открыть редактор запросов.</span><span class="sxs-lookup"><span data-stu-id="a021e-107">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to display the Query Editor.</span></span>  
  
2.  <span data-ttu-id="a021e-108">Скопируйте следующий код [!INCLUDE[tsql](../../includes/tsql-md.md)] и вставьте его в редактор запросов.</span><span class="sxs-lookup"><span data-stu-id="a021e-108">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] code from the following example into the Query Editor.</span></span> <span data-ttu-id="a021e-109">Этот код [!INCLUDE[tsql](../../includes/tsql-md.md)] создает таблицу с поддержкой FILESTREAM, именуемую Records.</span><span class="sxs-lookup"><span data-stu-id="a021e-109">This [!INCLUDE[tsql](../../includes/tsql-md.md)] code creates a FILESTREAM-enabled table called Records.</span></span>  
  
3.  <span data-ttu-id="a021e-110">Чтобы создать таблицу, нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a021e-110">To create the table, click **Execute**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a021e-111">Пример</span><span class="sxs-lookup"><span data-stu-id="a021e-111">Example</span></span>  
 <span data-ttu-id="a021e-112">В следующем примере кода показано, как создать таблицу с именем `Records`.</span><span class="sxs-lookup"><span data-stu-id="a021e-112">The following code example shows how to create a table that is named `Records`.</span></span> <span data-ttu-id="a021e-113">Столбец `Id` является столбцом типа `ROWGUIDCOL` и необходим для использования данных FILESTREAM с API Win32.</span><span class="sxs-lookup"><span data-stu-id="a021e-113">The `Id` column is a `ROWGUIDCOL` column and is required to use FILESTREAM data with Win32 APIs.</span></span> <span data-ttu-id="a021e-114">Столбец `SerialNumber` имеет тип `UNIQUE INTEGER`.</span><span class="sxs-lookup"><span data-stu-id="a021e-114">The `SerialNumber` column is a `UNIQUE INTEGER`.</span></span> <span data-ttu-id="a021e-115">Столбец `Chart` является столбцом типа `FILESTREAM` и используется для хранения данных `Chart` в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="a021e-115">The `Chart` column is a `FILESTREAM` column and is used to store the `Chart` in the file system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a021e-116">Этот пример ссылается на базу данных Archive, созданную в разделе [Создание базы данных с поддержкой FILESTREAM](create-a-filestream-enabled-database.md).</span><span class="sxs-lookup"><span data-stu-id="a021e-116">This example refers to the Archive database that is created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md).</span></span>  
  
 [!code-sql[FILESTREAM#FS_CreateTable](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_createtable)]  
  
## <a name="see-also"></a><span data-ttu-id="a021e-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="a021e-117">See Also</span></span>  
 <span data-ttu-id="a021e-118">[CREATE TABLE (Transact-SQL)](/sql/t-sql/statements/create-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a021e-118">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span></span>  
 [<span data-ttu-id="a021e-119">ALTER TABLE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a021e-119">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
  
