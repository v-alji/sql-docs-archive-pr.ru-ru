---
title: Использование файлов данных и файлов форматирования | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], file formats
- ODBC, functions
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [SQL Server Native Client]
- ODBC, bulk copy operations
- bulk copy [ODBC], data files
ms.assetid: c01b7155-3f0a-473d-90b7-87a97bc56ca5
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e0ee92f79e2c8cab9605db0188e01898df8c23e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750927"
---
# <a name="using-data-files-and-format-files"></a><span data-ttu-id="f02eb-102">Использование файлов данных и файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="f02eb-102">Using Data Files and Format Files</span></span>
  <span data-ttu-id="f02eb-103">Простейшая программа массового копирования выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f02eb-103">The simplest bulk copy program does the following:</span></span>  
  
1.  <span data-ttu-id="f02eb-104">Вызывает [bcp_init](../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) , чтобы указать групповое копирование (задание BCP_OUT) из таблицы или представления в файл данных.</span><span class="sxs-lookup"><span data-stu-id="f02eb-104">Calls [bcp_init](../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to specify bulk copying out (set BCP_OUT) from a table or view to a data file.</span></span>  
  
2.  <span data-ttu-id="f02eb-105">Вызывает [bcp_exec](../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) для выполнения операции с массовым копированием.</span><span class="sxs-lookup"><span data-stu-id="f02eb-105">Calls [bcp_exec](../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="f02eb-106">Файл данных создается в собственном режиме; следовательно, данные из всех столбцов таблицы или представления хранятся в файле данных в том же формате, что и в базе данных.</span><span class="sxs-lookup"><span data-stu-id="f02eb-106">The data file is created in native mode; therefore, data from all columns in the table or view are stored in the data file in the same format as in the database.</span></span> <span data-ttu-id="f02eb-107">Затем файл можно с помощью операции массового копирования скопировать на сервер, выполнив те же шаги и установив значение DB_IN вместо DB_OUT.</span><span class="sxs-lookup"><span data-stu-id="f02eb-107">The file can then be bulk copied into a server by using these same steps and setting DB_IN instead of DB_OUT.</span></span> <span data-ttu-id="f02eb-108">Это возможно только в случае, когда структура исходной и целевой таблиц идентична.</span><span class="sxs-lookup"><span data-stu-id="f02eb-108">This works only if both the source and target tables have exactly the same structure.</span></span> <span data-ttu-id="f02eb-109">Полученный файл данных также может быть введен в служебную программу **bcp** с помощью параметра **/n** (собственный режим).</span><span class="sxs-lookup"><span data-stu-id="f02eb-109">The resulting data file can also be input to the **bcp** utility by using the **/n** (native mode) switch.</span></span>  
  
 <span data-ttu-id="f02eb-110">Для массового копирования результирующего набора из инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)], а не непосредственно из таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="f02eb-110">To bulk copy out the result set of a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement instead of directly from a table or view:</span></span>  
  
1.  <span data-ttu-id="f02eb-111">Вызовите **bcp_init** , чтобы указать групповое копирование, но укажите значение NULL для имени таблицы.</span><span class="sxs-lookup"><span data-stu-id="f02eb-111">Call **bcp_init** to specify bulk copying out, but specify NULL for the table name.</span></span>  
  
2.  <span data-ttu-id="f02eb-112">Вызовите [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) с параметром *eOption* , для которого задано значение bcphints а, а *iValue* — указателем на строку SQLTCHAR, содержащую инструкцию Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="f02eb-112">Call [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) with *eOption* set to BCPHINTS and *iValue* set to a pointer to a SQLTCHAR string containing the Transact-SQL statement.</span></span>  
  
3.  <span data-ttu-id="f02eb-113">Вызовите **bcp_exec** , чтобы выполнить операцию с массовым копированием.</span><span class="sxs-lookup"><span data-stu-id="f02eb-113">Call **bcp_exec** to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="f02eb-114">В качестве инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] подходит любая инструкция, которая создает результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="f02eb-114">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statement can be any statement that generates a result set.</span></span> <span data-ttu-id="f02eb-115">Создается файл данных, содержащий первый результирующий набор инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f02eb-115">The data file is created containing the first result set of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="f02eb-116">Если инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)] создает несколько результирующих наборов, операция массового копирования пропускает все результирующие наборы, следующие за первым.</span><span class="sxs-lookup"><span data-stu-id="f02eb-116">Bulk copy ignores any result set after the first if the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement generates multiple result sets.</span></span>  
  
 <span data-ttu-id="f02eb-117">Чтобы создать файл данных, в котором данные столбца хранятся в другом формате, чем в таблице, вызовите [bcp_columns](../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) , чтобы указать, сколько столбцов будет изменено, а затем вызовите [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) для каждого столбца, формат которого необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="f02eb-117">To create a data file in which column data is stored in a different format than in the table, call [bcp_columns](../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) to specify how many columns will be changed, then call [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) for each column whose format you want to change.</span></span> <span data-ttu-id="f02eb-118">Это выполняется после вызова **bcp_init** , но перед вызовом **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="f02eb-118">This is done after calling **bcp_init** but before calling **bcp_exec**.</span></span> <span data-ttu-id="f02eb-119">**bcp_colfmt** указывает формат, в котором данные столбца хранятся в файле данных.</span><span class="sxs-lookup"><span data-stu-id="f02eb-119">**bcp_colfmt** specifies the format in which the column's data is stored in the data file.</span></span> <span data-ttu-id="f02eb-120">Его можно использовать при выполнении операций копирования или извлечения. Для установки признаков конца строки и столбца можно также использовать **bcp_colfmt** .</span><span class="sxs-lookup"><span data-stu-id="f02eb-120">It can be used when bulk copying in or out. You can also use **bcp_colfmt** to set the row and column terminators.</span></span> <span data-ttu-id="f02eb-121">Например, если в данных нет символов табуляции, можно создать файл с разделителями-символами табуляции с помощью **bcp_colfmt** , чтобы задать символ табуляции в качестве признака конца для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="f02eb-121">For example, if your data contains no tab characters, you can create a tab-delimited file by using **bcp_colfmt** to set the tab character as the terminator for each column.</span></span>  
  
 <span data-ttu-id="f02eb-122">При выполнении операций с массовым копированием и использованием **bcp_colfmt**можно легко создать файл форматирования с описанием созданного файла данных, вызвав [bcp_writefmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) после последнего вызова **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="f02eb-122">When bulk copying out and using **bcp_colfmt**, you can easily create a format file describing the data file you have created by calling [bcp_writefmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) after the last call to **bcp_colfmt**.</span></span>  
  
 <span data-ttu-id="f02eb-123">При выполнении операции с массовым копированием из файла данных, описанного в файле форматирования, прочтите файл форматирования, вызвав [bcp_readfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) после **bcp_init** , но до **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="f02eb-123">When bulk copying in from a data file described by a format file, read the format file by calling [bcp_readfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) after **bcp_init** but before **bcp_exec**.</span></span>  
  
 <span data-ttu-id="f02eb-124">Функция **bcp_control** управляет несколькими параметрами при выполнении операции копирования [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из файла данных.</span><span class="sxs-lookup"><span data-stu-id="f02eb-124">The **bcp_control** function controls several options when bulk copying into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a data file.</span></span> <span data-ttu-id="f02eb-125">**bcp_control** задает параметры, такие как максимальное количество ошибок перед завершением, строка в файле, с которой начинается копирование, строка, которую нужно присвоить, и размер пакета.</span><span class="sxs-lookup"><span data-stu-id="f02eb-125">**bcp_control** sets options, such as the maximum number of errors before termination, the row in the file on which to start the bulk copy, the row to stop on, and the batch size.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f02eb-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="f02eb-126">See Also</span></span>  
 [<span data-ttu-id="f02eb-127">Выполнение операций с массовым копированием &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="f02eb-127">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](performing-bulk-copy-operations-odbc.md)  
  
  
