---
title: Массовый импорт данных большого объекта с помощью поставщика больших наборов строк OPENROWSET (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- SINGLE_NCLOB option
- bulk rowset providers [SQL Server]
- bulk importing [SQL Server], data formats
- OPENROWSET function, bulk importing large data
- SINGLE_CLOB option
- data formats [SQL Server], large-object data
- large data, bulk imports
- SINGLE_BLOB option
ms.assetid: 171cdd5c-1e47-4bd7-b99a-4f0fd4e10526
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0f43aa2fa5e7f7ef0b2c8f1f6e5e6ff28e02f9f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658710"
---
# <a name="bulk-import-large-object-data-by-using-the-openrowset-bulk-rowset-provider-sql-server"></a><span data-ttu-id="42f80-102">Массовый импорт данных больших объектов при помощи поставщика больших наборов строк OPENROWSET (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42f80-102">Bulk Import Large-Object Data by using the OPENROWSET Bulk Rowset Provider (SQL Server)</span></span>
  <span data-ttu-id="42f80-103">Поставщик больших наборов строк OPENROWSET в среде [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] позволяет выполнять массовый импорт файла данных как большого объекта данных.</span><span class="sxs-lookup"><span data-stu-id="42f80-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OPENROWSET Bulk Rowset Provider enables you to bulk import a data file as large-object data.</span></span>  
  
 <span data-ttu-id="42f80-104">Поставщик больших наборов строк OPENROWSET поддерживает следующие типы больших объектов данных: **varbinary**(max) или **image**, **varchar**(max) или **text**и **nvarchar**(max) или **ntext**.</span><span class="sxs-lookup"><span data-stu-id="42f80-104">The large-object data types supported by OPENROWSET Bulk Rowset Provider are **varbinary**(max) or **image**, **varchar**(max) or **text**, and **nvarchar**(max) or **ntext**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42f80-105">Типы данных **image**, **text** и **ntext** считаются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="42f80-105">The **image**, **text** and **ntext** data types are deprecated.</span></span>  
  
 <span data-ttu-id="42f80-106">В предложении OPENROWSET BULK поддерживаются три параметра для импорта содержимого файла данных в виде однострочного набора строк с одним столбцом.</span><span class="sxs-lookup"><span data-stu-id="42f80-106">The OPENROWSET BULK clause supports three options for importing the contents of a data file as a single-row, single-column rowset.</span></span> <span data-ttu-id="42f80-107">Вместо файла форматирования можно указать один из данных параметров для больших объектов.</span><span class="sxs-lookup"><span data-stu-id="42f80-107">You can specify one of these large-object options instead of using a format file.</span></span> <span data-ttu-id="42f80-108">Это следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="42f80-108">These options are as follows:</span></span>  
  
 <span data-ttu-id="42f80-109">SINGLE_BLOB</span><span class="sxs-lookup"><span data-stu-id="42f80-109">SINGLE_BLOB</span></span>  
 <span data-ttu-id="42f80-110">Считывает содержимое файла *data_file* в одну строку и возвращает его в виде набора строк, состоящего из одного столбца типа **varbinary(max)** .</span><span class="sxs-lookup"><span data-stu-id="42f80-110">Reads the contents of *data_file* as a single-row, returns the contents as a single-column rowset of type **varbinary(max)**.</span></span>  
  
 <span data-ttu-id="42f80-111">SINGLE_CLOB</span><span class="sxs-lookup"><span data-stu-id="42f80-111">SINGLE_CLOB</span></span>  
 <span data-ttu-id="42f80-112">Считывает содержимое указанного файла данных в виде символов и возвращает его в виде набора строк, состоящего из одной строки и одного столбца типа **varchar(max)** , с параметрами сортировки текущей базы данных; это может быть, например, текстовый документ или документ [!INCLUDE[msCoName](../../includes/msconame-md.md)] Word.</span><span class="sxs-lookup"><span data-stu-id="42f80-112">Reads the contents of the specified data file as characters, returns the contents as a single-row, single-column rowset of type **varchar(max)**, using the collation of the current database; such as a text or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Word document.</span></span>  
  
 <span data-ttu-id="42f80-113">SINGLE_NCLOB</span><span class="sxs-lookup"><span data-stu-id="42f80-113">SINGLE_NCLOB</span></span>  
 <span data-ttu-id="42f80-114">Считывает содержимое указанного файла данных в кодировке Юникод и возвращает содержимое в виде набора строк, состоящего из одной строки и одного столбца типа **varchar(max)** , с параметрами сортировки текущей базы данных.</span><span class="sxs-lookup"><span data-stu-id="42f80-114">Reads the contents of the specified data file as Unicode, returns the contents as a single-row, single-column rowset of type **nvarchar(max)**, using the collation of the current database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42f80-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="42f80-115">See Also</span></span>  
 <span data-ttu-id="42f80-116">[Массовый импорт данных при помощи инструкции BULK INSERT или OPENROWSET(BULK...) (SQL Server)](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="42f80-116">[Import Bulk Data by Using BULK INSERT or OPENROWSET&#40;BULK...&#41; &#40;SQL Server&#41;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md) </span></span>  
 <span data-ttu-id="42f80-117">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="42f80-117">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="42f80-118">[OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="42f80-118">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="42f80-119">[Сохранение значений NULL или использование значений по умолчанию при массовом импорте данных (SQL Server)](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="42f80-119">[Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md) </span></span>  
 <span data-ttu-id="42f80-120">[bcp Utility](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="42f80-120">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 [<span data-ttu-id="42f80-121">BULK INSERT (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="42f80-121">BULK INSERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/bulk-insert-transact-sql)  
  
  
