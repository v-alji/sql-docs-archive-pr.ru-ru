---
title: Доступ к данным FILESTREAM с помощью Transact-SQL | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], Transact-SQL
ms.assetid: a6bf0ce7-7e5e-4a07-8917-ee526c9d0a05
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 06d395f1acc3723fc6b45fdfa08efbae354d8014
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734169"
---
# <a name="access-filestream-data-with-transact-sql"></a><span data-ttu-id="4d99e-102">Доступ к данным FILESTREAM с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4d99e-102">Access FILESTREAM Data with Transact-SQL</span></span>
  <span data-ttu-id="4d99e-103">В этом разделе описаны способы использования инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT, UPDATE и DELETE для управления данными FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="4d99e-103">This topic describes how to use the [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT, UPDATE, and DELETE statements to manage FILESTREAM data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d99e-104">Для примеров в этом разделе требуется база данных с поддержкой FILESTREAM и таблица, которая создана в разделе [Создание базы данных с поддержкой FILESTREAM](create-a-filestream-enabled-database.md) и [Создание таблицы для хранения данных FILESTREAM](create-a-table-for-storing-filestream-data.md).</span><span class="sxs-lookup"><span data-stu-id="4d99e-104">The examples in this topic require the FILESTREAM-enabled database and table that are created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md) and [Create a Table for Storing FILESTREAM Data](create-a-table-for-storing-filestream-data.md).</span></span>  
  
##  <a name="inserting-a-row-that-contains-filestream-data"></a><a name="ins"></a> <span data-ttu-id="4d99e-105">Вставка строки, содержащей данные FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="4d99e-105">Inserting a Row That Contains FILESTREAM Data</span></span>  
 <span data-ttu-id="4d99e-106">Чтобы вставить строку в таблицу, которая поддерживает данные FILESTREAM, используйте инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT.</span><span class="sxs-lookup"><span data-stu-id="4d99e-106">To add a row to a table that supports FILESTREAM data, use the [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT statement.</span></span> <span data-ttu-id="4d99e-107">Значение, вставляемое в столбец FILESTREAM, может быть либо значением NULL, либо значением типа `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="4d99e-107">When you insert data into a FILESTREAM column, you can insert NULL or a `varbinary(max)` value.</span></span>  
  
### <a name="inserting-null"></a><span data-ttu-id="4d99e-108">Вставка значения NULL</span><span class="sxs-lookup"><span data-stu-id="4d99e-108">Inserting NULL</span></span>  
 <span data-ttu-id="4d99e-109">Следующий пример иллюстрирует порядок вставки значения `NULL`.</span><span class="sxs-lookup"><span data-stu-id="4d99e-109">The following example shows how to insert `NULL`.</span></span> <span data-ttu-id="4d99e-110">Если значение FILESTREAM равно `NULL`, компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] не создает файл в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="4d99e-110">When the FILESTREAM value is `NULL`, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not create a file in the file system.</span></span>  
  
 [!code-sql[FILESTREAM#FS_InsertNULL](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertnull)]  
  
### <a name="inserting-a-zero-length-record"></a><span data-ttu-id="4d99e-111">Вставка записи с нулевой длиной</span><span class="sxs-lookup"><span data-stu-id="4d99e-111">Inserting a Zero-Length Record</span></span>  
 <span data-ttu-id="4d99e-112">В следующем примере показано, как использовать инструкцию `INSERT` для создания записи с нулевой длиной.</span><span class="sxs-lookup"><span data-stu-id="4d99e-112">The following example shows how to use `INSERT` to create a zero-length record.</span></span> <span data-ttu-id="4d99e-113">Это бывает полезно в случае, если нужно получить дескриптор файла, работать с которым предполагается с помощью API-интерфейсов Win32.</span><span class="sxs-lookup"><span data-stu-id="4d99e-113">This is useful for when you want to obtain a file handle, but will be manipulating the file by using Win32 APIs.</span></span>  
  
 [!code-sql[FILESTREAM#FS_InsertZero](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertzero)]  
  
### <a name="creating-a-data-file"></a><span data-ttu-id="4d99e-114">Создание файла данных</span><span class="sxs-lookup"><span data-stu-id="4d99e-114">Creating a Data File</span></span>  
 <span data-ttu-id="4d99e-115">В следующем примере кода показывается, как использовать инструкцию `INSERT` для создания файла, содержащего данные.</span><span class="sxs-lookup"><span data-stu-id="4d99e-115">The following example shows how to use `INSERT` to create a file that contains data.</span></span> <span data-ttu-id="4d99e-116">Компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] преобразует строку `Seismic Data` в значение типа `varbinary(max)` .</span><span class="sxs-lookup"><span data-stu-id="4d99e-116">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] converts the string `Seismic Data` to a `varbinary(max)` value.</span></span> <span data-ttu-id="4d99e-117">FILESTREAM создает файл Windows, если он еще не был создан. Затем данные добавляются в файл данных.</span><span class="sxs-lookup"><span data-stu-id="4d99e-117">FILESTREAM creates the Windows file if it does not already exist.The data is then added to the data file.</span></span>  
  
 [!code-sql[FILESTREAM#FS_InsertData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertdata)]  
  
 <span data-ttu-id="4d99e-118">При выборке всех данных в таблице `Archive`.`dbo.Records`</span><span class="sxs-lookup"><span data-stu-id="4d99e-118">When you select all data from the `Archive`.`dbo.Records`</span></span> <span data-ttu-id="4d99e-119">результат напоминает тот, который приведен в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="4d99e-119">table, the results are similar to the results that are shown in the following table.</span></span> <span data-ttu-id="4d99e-120">Однако столбец `Id` будет содержать разные идентификаторы GUID.</span><span class="sxs-lookup"><span data-stu-id="4d99e-120">However, the `Id` column will contain different GUIDs.</span></span>  
  
|<span data-ttu-id="4d99e-121">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="4d99e-121">Id</span></span>|<span data-ttu-id="4d99e-122">SerialNumber</span><span class="sxs-lookup"><span data-stu-id="4d99e-122">SerialNumber</span></span>|<span data-ttu-id="4d99e-123">Возобновить</span><span class="sxs-lookup"><span data-stu-id="4d99e-123">Resume</span></span>|  
|--------|------------------|------------|  
|`C871B90F-D25E-47B3-A560-7CC0CA405DAC`|`1`|`NULL`|  
|`F8F5C314-0559-4927-8FA9-1535EE0BDF50`|`2`|`0x`|  
|`7F680840-B7A4-45D4-8CD5-527C44D35B3F`|`3`|`0x536569736D69632044617461`|  
  
##  <a name="updating-filestream-data"></a><a name="upd"></a> <span data-ttu-id="4d99e-124">Обновление данных FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="4d99e-124">Updating FILESTREAM Data</span></span>  
 <span data-ttu-id="4d99e-125">[!INCLUDE[tsql](../../includes/tsql-md.md)] можно использовать для обновления данных файла, хотя это может быть нежелательным при потоковой записи в файл больших объемов данных.</span><span class="sxs-lookup"><span data-stu-id="4d99e-125">You can use [!INCLUDE[tsql](../../includes/tsql-md.md)] to update the data in the file system file; although, you might not want to do this when you have to stream large amounts of data to a file.</span></span>  
  
 <span data-ttu-id="4d99e-126">В следующем примере любой текст в записи файла заменяется текстом `Xray 1`.</span><span class="sxs-lookup"><span data-stu-id="4d99e-126">The following example replaces any text in the file record with the text `Xray 1`.</span></span>  
  
 [!code-sql[FILESTREAM#FS_UpdateData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_updatedata)]  
  
##  <a name="deleting-filestream-data"></a><a name="del"></a> <span data-ttu-id="4d99e-127">Удаление данных FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="4d99e-127">Deleting FILESTREAM Data</span></span>  
 <span data-ttu-id="4d99e-128">При удалении строки, содержащей поле FILESTREAM, также удаляются и связанные с ней файлы файловой системы.</span><span class="sxs-lookup"><span data-stu-id="4d99e-128">When you delete a row that contains a FILESTREAM field, you also delete its underlying file system files.</span></span> <span data-ttu-id="4d99e-129">Единственным способом удаления строки и, как следствие, файла является использование инструкции DELETE языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d99e-129">The only way to delete a row, and therefore the file, is to use the [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE statement.</span></span>  
  
 <span data-ttu-id="4d99e-130">В следующем примере показано, как удалить строку и связанный с ней файл файловой системы.</span><span class="sxs-lookup"><span data-stu-id="4d99e-130">The following example shows how to delete a row and its associated file system files.</span></span>  
  
 [!code-sql[FILESTREAM#FS_DeleteData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_deletedata)]  
  
 <span data-ttu-id="4d99e-131">При выборке всех данных в таблице `dbo.Archive` строка удаляется.</span><span class="sxs-lookup"><span data-stu-id="4d99e-131">When you select all data from the `dbo.Archive` table, the row is gone.</span></span> <span data-ttu-id="4d99e-132">Связанный с ней файл больше нельзя использовать.</span><span class="sxs-lookup"><span data-stu-id="4d99e-132">You can no longer use the associated file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d99e-133">Базовые файлы удаляются сборщиком мусора FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="4d99e-133">The underlying files are removed by the FILESTREAM garbage collector.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d99e-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="4d99e-134">See Also</span></span>  
 <span data-ttu-id="4d99e-135">[Включение и настройка FILESTREAM](enable-and-configure-filestream.md) </span><span class="sxs-lookup"><span data-stu-id="4d99e-135">[Enable and Configure FILESTREAM](enable-and-configure-filestream.md) </span></span>  
 [<span data-ttu-id="4d99e-136">Избегание конфликтов в операциях баз данных в приложениях FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="4d99e-136">Avoid Conflicts with Database Operations in FILESTREAM Applications</span></span>](avoid-conflicts-with-database-operations-in-filestream-applications.md)  
  
  
