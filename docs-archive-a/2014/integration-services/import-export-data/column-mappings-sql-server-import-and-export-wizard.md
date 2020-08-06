---
title: Сопоставления столбцов (мастер импорта и экспорта SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.columnmapandtransform.f1
ms.assetid: eadc54a6-f936-4ffc-91d7-fbfd2bdcab93
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7994de1292677421447d441c1ac5aeb2b6fbc618
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666158"
---
# <a name="column-mappings-sql-server-import-and-export-wizard"></a><span data-ttu-id="244ae-102">Сопоставления столбцов (мастер импорта и экспорта SQL Server)</span><span class="sxs-lookup"><span data-stu-id="244ae-102">Column Mappings (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="244ae-103">Используйте диалоговое окно **сопоставления столбцов** для изменения параметров преобразования.</span><span class="sxs-lookup"><span data-stu-id="244ae-103">Use the **Column Mappings** dialog box to edit transformation parameters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="244ae-104">Если выбирается параметр «Копирование таблицы», необязательно копировать все столбцы таблицы.</span><span class="sxs-lookup"><span data-stu-id="244ae-104">You do not have to copy all the columns in a table when you select the Table Copy option.</span></span> <span data-ttu-id="244ae-105">**\<ignore>** В столбце **назначение** этого диалогового окна выберите столбцы, которые необходимо пропустить.</span><span class="sxs-lookup"><span data-stu-id="244ae-105">Select **\<ignore>** in the **Destination** column of this dialog box for columns that you want to skip.</span></span>  
  
 <span data-ttu-id="244ae-106">Дополнительные сведения о работе этого мастера см. в разделе [Мастер импорта и экспорта SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="244ae-106">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="244ae-107">Дополнительные сведения о параметрах запуска мастера, а также о разрешениях, необходимых для успешного запуска мастера, см. в разделе [Запуск мастера импорта и экспорта SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="244ae-107">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="244ae-108">Назначение мастера импорта и экспорта SQL Server заключается в копировании данных из исходного расположения в целевое.</span><span class="sxs-lookup"><span data-stu-id="244ae-108">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="244ae-109">Этот мастер может также создать целевую базу данных и целевые таблицы.</span><span class="sxs-lookup"><span data-stu-id="244ae-109">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="244ae-110">Однако если нужно скопировать несколько баз данных, таблиц или других объектов базы данных, следует использовать мастер копирования баз данных.</span><span class="sxs-lookup"><span data-stu-id="244ae-110">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="244ae-111">Дополнительные сведения см. в статье [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="244ae-111">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="244ae-112">Варианты</span><span class="sxs-lookup"><span data-stu-id="244ae-112">Options</span></span>  
 <span data-ttu-id="244ae-113">**Source**</span><span class="sxs-lookup"><span data-stu-id="244ae-113">**Source**</span></span>  
 <span data-ttu-id="244ae-114">Определяет выбранную исходную таблицу, представление или запрос.</span><span class="sxs-lookup"><span data-stu-id="244ae-114">Identifies the selected source table, view, or query.</span></span>  
  
 <span data-ttu-id="244ae-115">**Назначение**</span><span class="sxs-lookup"><span data-stu-id="244ae-115">**Destination**</span></span>  
 <span data-ttu-id="244ae-116">Определяет выбранную целевую таблицу, представление или запрос.</span><span class="sxs-lookup"><span data-stu-id="244ae-116">Identifies the selected destination table, view, or query.</span></span>  
  
 <span data-ttu-id="244ae-117">**Создать целевую таблицу или файл**</span><span class="sxs-lookup"><span data-stu-id="244ae-117">**Create destination table/file**</span></span>  
 <span data-ttu-id="244ae-118">Указывает, нужно ли создавать целевую таблицу, если она не существует.</span><span class="sxs-lookup"><span data-stu-id="244ae-118">Specify whether to create the destination table if it does not already exist.</span></span>  
  
 <span data-ttu-id="244ae-119">**Удалять строки в целевой таблице или файле**</span><span class="sxs-lookup"><span data-stu-id="244ae-119">**Delete rows in destination table/file**</span></span>  
 <span data-ttu-id="244ae-120">Указывает, необходимо ли очищать данные, содержащиеся в существующей таблице, перед помещением в нее новых данных.</span><span class="sxs-lookup"><span data-stu-id="244ae-120">Specify whether to clear the data from an existing table before loading new data.</span></span>  
  
 <span data-ttu-id="244ae-121">**Присоединять строки к целевой таблице или файлу**</span><span class="sxs-lookup"><span data-stu-id="244ae-121">**Append rows to destination table/file**</span></span>  
 <span data-ttu-id="244ae-122">Определяет, нужно ли присоединять новые данные к данным, уже находящимся в существующей таблице.</span><span class="sxs-lookup"><span data-stu-id="244ae-122">Specify whether to append the new data to the data already present in an existing table.</span></span>  
  
 <span data-ttu-id="244ae-123">**Изменить SQL**</span><span class="sxs-lookup"><span data-stu-id="244ae-123">**Edit SQL**</span></span>  
 <span data-ttu-id="244ae-124">Используйте инструкцию Default в диалоговом окне **инструкция SQL CREATE TABLE** или измените ее в целях.</span><span class="sxs-lookup"><span data-stu-id="244ae-124">Use the default statement in the **Create Table SQL Statement** dialog box, or modify it for your purposes.</span></span> <span data-ttu-id="244ae-125">При изменении этой инструкции необходимо также внести соответствующие изменения в сопоставление таблиц.</span><span class="sxs-lookup"><span data-stu-id="244ae-125">If you modify this statement, you must also make associated changes to table mapping.</span></span>  
  
 <span data-ttu-id="244ae-126">**Удалить и создать повторно целевую таблицу**</span><span class="sxs-lookup"><span data-stu-id="244ae-126">**Drop and re-create destination table**</span></span>  
 <span data-ttu-id="244ae-127">Выберите этот параметр для перезаписи целевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="244ae-127">Choose this option to overwrite the destination table.</span></span> <span data-ttu-id="244ae-128">Этот параметр доступен только при условии использования мастера для создания целевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="244ae-128">This option is only available when you use the wizard to create the destination table.</span></span> <span data-ttu-id="244ae-129">Целевая таблица удаляется и повторно создается только в случае, если созданный мастером пакет был сохранен, а затем запущен снова.</span><span class="sxs-lookup"><span data-stu-id="244ae-129">The destination table is only dropped and re-created if you save the package that the wizard creates, and then run the package again.</span></span>  
  
 <span data-ttu-id="244ae-130">**Разрешить вставку в столбец идентификаторов**</span><span class="sxs-lookup"><span data-stu-id="244ae-130">**Enable identity insert**</span></span>  
 <span data-ttu-id="244ae-131">Установка этого параметра позволяет вставлять значения идентификаторов, существующие в исходных данных, в столбец идентификаторов целевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="244ae-131">Choose this option to allow existing identity values in the source data to be inserted into an identity column in the destination table.</span></span> <span data-ttu-id="244ae-132">По умолчанию для целевого столбца идентификаторов это не разрешено.</span><span class="sxs-lookup"><span data-stu-id="244ae-132">By default, the destination identity column does not allow this.</span></span>  
  
 <span data-ttu-id="244ae-133">**Сопоставления**</span><span class="sxs-lookup"><span data-stu-id="244ae-133">**Mappings**</span></span>  
 <span data-ttu-id="244ae-134">Показывает сопоставление каждого столбца источника данных столбцу назначения.</span><span class="sxs-lookup"><span data-stu-id="244ae-134">Displays how each column in the data source maps to a column in the destination.</span></span>  
  
 <span data-ttu-id="244ae-135">Этот список содержит следующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="244ae-135">This list has the following columns:</span></span>  
  
 <span data-ttu-id="244ae-136">**Source**</span><span class="sxs-lookup"><span data-stu-id="244ae-136">**Source**</span></span>  
 <span data-ttu-id="244ae-137">Просмотр всех исходных столбцов, для которых можно задать параметры преобразования.</span><span class="sxs-lookup"><span data-stu-id="244ae-137">View each source column for which you can set transformation parameters.</span></span>  
  
 <span data-ttu-id="244ae-138">**Назначение**</span><span class="sxs-lookup"><span data-stu-id="244ae-138">**Destination**</span></span>  
 <span data-ttu-id="244ae-139">Укажите, должен ли столбец пропускаться во время операции копирования.</span><span class="sxs-lookup"><span data-stu-id="244ae-139">Specify whether you want to ignore a column during the copy operation.</span></span> <span data-ttu-id="244ae-140">Можно скопировать только подмножество столбцов, выбрав **\<ignore>** в этом столбце столбцы, которые нужно пропустить.</span><span class="sxs-lookup"><span data-stu-id="244ae-140">You can copy only a subset of columns by selecting **\<ignore>** in this column for columns that you want to skip.</span></span> <span data-ttu-id="244ae-141">Перед сопоставлением столбцов необходимо установить пропуск всех столбцов, которые не будут сопоставляться.</span><span class="sxs-lookup"><span data-stu-id="244ae-141">Before you map columns, you must ignore all columns that will not be mapped.</span></span>  
  
 <span data-ttu-id="244ae-142">**Тип**</span><span class="sxs-lookup"><span data-stu-id="244ae-142">**Type**</span></span>  
 <span data-ttu-id="244ae-143">Укажите тип данных столбца.</span><span class="sxs-lookup"><span data-stu-id="244ae-143">Select a data type for the column.</span></span>  
  
 <span data-ttu-id="244ae-144">**Допускает значения NULL**</span><span class="sxs-lookup"><span data-stu-id="244ae-144">**Nullable**</span></span>  
 <span data-ttu-id="244ae-145">Укажите, могут ли в столбце содержаться значения NULL.</span><span class="sxs-lookup"><span data-stu-id="244ae-145">Specify whether a column will allow a null value.</span></span>  
  
 <span data-ttu-id="244ae-146">**Размер**</span><span class="sxs-lookup"><span data-stu-id="244ae-146">**Size**</span></span>  
 <span data-ttu-id="244ae-147">Укажите количество символов в столбце.</span><span class="sxs-lookup"><span data-stu-id="244ae-147">Specify the number of characters in the column.</span></span>  
  
 <span data-ttu-id="244ae-148">**Точность**</span><span class="sxs-lookup"><span data-stu-id="244ae-148">**Precision**</span></span>  
 <span data-ttu-id="244ae-149">Определяет точность отображаемых данных, измеряемую количеством десятичных цифр.</span><span class="sxs-lookup"><span data-stu-id="244ae-149">Specify the precision of displayed data, referring to the number of digits.</span></span>  
  
 <span data-ttu-id="244ae-150">**Масштаб**</span><span class="sxs-lookup"><span data-stu-id="244ae-150">**Scale**</span></span>  
 <span data-ttu-id="244ae-151">Определяет масштаб отображаемых данных, измеряемый числом десятичных знаков.</span><span class="sxs-lookup"><span data-stu-id="244ae-151">Specify the scale of displayed data, referring to the number of decimal places.</span></span>  
  
  
