---
title: Настройка назначения "Неструктурированный файл" (мастер импорта и экспорта SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.configureflatfiledest.f1
ms.assetid: 318e8da0-37d3-46cd-943a-fc5d66aad93a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2af8a1653d9a1aef0828aa112a25825ed23b8bf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666159"
---
# <a name="configure-flat-file-destination-sql-server-import-and-export-wizard"></a><span data-ttu-id="caab9-102">Настройка назначения «Неструктурированный файл» (мастер импорта и экспорта SQL Server)</span><span class="sxs-lookup"><span data-stu-id="caab9-102">Configure Flat File Destination (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="caab9-103">Используйте страницу **Настройка назначения «Неструктурированный файл** », чтобы задать параметры форматирования для целевого неструктурированного файла и просмотреть результаты перед продолжением.</span><span class="sxs-lookup"><span data-stu-id="caab9-103">Use the **Configure Flat File Destination** page to specify formatting options for the destination flat file, and to preview results before continuing.</span></span>  
  
 <span data-ttu-id="caab9-104">Дополнительные сведения о работе этого мастера см. в разделе [Мастер импорта и экспорта SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="caab9-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="caab9-105">Дополнительные сведения о параметрах запуска мастера, а также о разрешениях, необходимых для успешного запуска мастера, см. в разделе [Запуск мастера импорта и экспорта SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="caab9-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="caab9-106">Назначение мастера импорта и экспорта SQL Server заключается в копировании данных из исходного расположения в целевое.</span><span class="sxs-lookup"><span data-stu-id="caab9-106">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="caab9-107">Этот мастер может также создать целевую базу данных и целевые таблицы.</span><span class="sxs-lookup"><span data-stu-id="caab9-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="caab9-108">Однако если нужно скопировать несколько баз данных, таблиц или других объектов базы данных, следует использовать мастер копирования баз данных.</span><span class="sxs-lookup"><span data-stu-id="caab9-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="caab9-109">Дополнительные сведения см. в статье [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="caab9-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="caab9-110">Варианты</span><span class="sxs-lookup"><span data-stu-id="caab9-110">Options</span></span>  
 <span data-ttu-id="caab9-111">**Неструктурированный файл источника**</span><span class="sxs-lookup"><span data-stu-id="caab9-111">**Source flat file**</span></span>  
 <span data-ttu-id="caab9-112">Имя целевого файла.</span><span class="sxs-lookup"><span data-stu-id="caab9-112">The name of the destination file.</span></span>  
  
 <span data-ttu-id="caab9-113">**Разделитель строк**</span><span class="sxs-lookup"><span data-stu-id="caab9-113">**Row delimiter**</span></span>  
 <span data-ttu-id="caab9-114">Значение выбирается из списка разделителей для строк.</span><span class="sxs-lookup"><span data-stu-id="caab9-114">Select from the list of delimiters for rows.</span></span>  
  
|<span data-ttu-id="caab9-115">Значение</span><span class="sxs-lookup"><span data-stu-id="caab9-115">Value</span></span>|<span data-ttu-id="caab9-116">Описание</span><span class="sxs-lookup"><span data-stu-id="caab9-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="caab9-117">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="caab9-117">**{CR}{LF}**</span></span>|<span data-ttu-id="caab9-118">Строка отделена с помощью комбинации символов возврата каретки / перевода строки.</span><span class="sxs-lookup"><span data-stu-id="caab9-118">The row is delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="caab9-119">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="caab9-119">**{CR}**</span></span>|<span data-ttu-id="caab9-120">Строка отделена с помощью символа возврата каретки.</span><span class="sxs-lookup"><span data-stu-id="caab9-120">The row is delimited by a carriage return.</span></span>|  
|<span data-ttu-id="caab9-121">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="caab9-121">**{LF}**</span></span>|<span data-ttu-id="caab9-122">Строка отделена с помощью символа перевода строки.</span><span class="sxs-lookup"><span data-stu-id="caab9-122">The row is delimited by a line feed.</span></span>|  
|<span data-ttu-id="caab9-123">**Точка с запятой {;}**</span><span class="sxs-lookup"><span data-stu-id="caab9-123">**Semicolon {;}**</span></span>|<span data-ttu-id="caab9-124">Строка отделена с помощью символа точки с запятой.</span><span class="sxs-lookup"><span data-stu-id="caab9-124">The row is delimited by a semicolon.</span></span>|  
|<span data-ttu-id="caab9-125">**Двоеточие {:}**</span><span class="sxs-lookup"><span data-stu-id="caab9-125">**Colon {:}**</span></span>|<span data-ttu-id="caab9-126">Строка отделена с помощью символа двоеточия.</span><span class="sxs-lookup"><span data-stu-id="caab9-126">The row is delimited by a colon.</span></span>|  
|<span data-ttu-id="caab9-127">**Запятая {,}**</span><span class="sxs-lookup"><span data-stu-id="caab9-127">**Comma {,}**</span></span>|<span data-ttu-id="caab9-128">Строка отделена с помощью символа запятой.</span><span class="sxs-lookup"><span data-stu-id="caab9-128">The row is delimited by a comma.</span></span>|  
|<span data-ttu-id="caab9-129">**Табуляция {t}**</span><span class="sxs-lookup"><span data-stu-id="caab9-129">**Tab {t}**</span></span>|<span data-ttu-id="caab9-130">Строка отделена с помощью символа табуляции.</span><span class="sxs-lookup"><span data-stu-id="caab9-130">The row is delimited by a tab.</span></span>|  
|<span data-ttu-id="caab9-131">**Вертикальная черта {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="caab9-131">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="caab9-132">Строка отделена с помощью символа вертикальной черты.</span><span class="sxs-lookup"><span data-stu-id="caab9-132">The row is delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="caab9-133">**Разделитель столбцов**</span><span class="sxs-lookup"><span data-stu-id="caab9-133">**Column delimiter**</span></span>  
 <span data-ttu-id="caab9-134">Значение выбирается из списка разделителей для столбцов.</span><span class="sxs-lookup"><span data-stu-id="caab9-134">Select from the list of delimiters for columns.</span></span>  
  
|<span data-ttu-id="caab9-135">Значение</span><span class="sxs-lookup"><span data-stu-id="caab9-135">Value</span></span>|<span data-ttu-id="caab9-136">Описание</span><span class="sxs-lookup"><span data-stu-id="caab9-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="caab9-137">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="caab9-137">**{CR}{LF}**</span></span>|<span data-ttu-id="caab9-138">Столбцы разделены с помощью комбинации символов возврата каретки и перевода строки.</span><span class="sxs-lookup"><span data-stu-id="caab9-138">The columns are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="caab9-139">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="caab9-139">**{CR}**</span></span>|<span data-ttu-id="caab9-140">Столбцы разделены с помощью символа возврата каретки.</span><span class="sxs-lookup"><span data-stu-id="caab9-140">The columns are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="caab9-141">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="caab9-141">**{LF}**</span></span>|<span data-ttu-id="caab9-142">Столбцы разделены с помощью символа перевода строки.</span><span class="sxs-lookup"><span data-stu-id="caab9-142">The columns are delimited by a line feed.</span></span>|  
|<span data-ttu-id="caab9-143">**Точка с запятой {;}**</span><span class="sxs-lookup"><span data-stu-id="caab9-143">**Semicolon {;}**</span></span>|<span data-ttu-id="caab9-144">Столбцы разделены с помощью символа точки с запятой.</span><span class="sxs-lookup"><span data-stu-id="caab9-144">The columns are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="caab9-145">**Двоеточие {:}**</span><span class="sxs-lookup"><span data-stu-id="caab9-145">**Colon {:}**</span></span>|<span data-ttu-id="caab9-146">Столбцы разделены с помощью символа двоеточия.</span><span class="sxs-lookup"><span data-stu-id="caab9-146">The columns are delimited by a colon.</span></span>|  
|<span data-ttu-id="caab9-147">**Запятая {,}**</span><span class="sxs-lookup"><span data-stu-id="caab9-147">**Comma {,}**</span></span>|<span data-ttu-id="caab9-148">Столбцы разделены с помощью символа запятой.</span><span class="sxs-lookup"><span data-stu-id="caab9-148">The columns are delimited by a comma.</span></span>|  
|<span data-ttu-id="caab9-149">**Табуляция {t}**</span><span class="sxs-lookup"><span data-stu-id="caab9-149">**Tab {t}**</span></span>|<span data-ttu-id="caab9-150">Столбцы разделены с помощью символа табуляции.</span><span class="sxs-lookup"><span data-stu-id="caab9-150">The columns are delimited by a tab.</span></span>|  
|<span data-ttu-id="caab9-151">**Вертикальная черта {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="caab9-151">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="caab9-152">Столбцы разделены с помощью символа вертикальной черты.</span><span class="sxs-lookup"><span data-stu-id="caab9-152">The columns are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="caab9-153">**Предварительный просмотр**</span><span class="sxs-lookup"><span data-stu-id="caab9-153">**Preview**</span></span>  
 <span data-ttu-id="caab9-154">Просмотр в диалоговом окне " **Просмотр данных** ". результаты выбранных параметров форматирования для целевого неструктурированного файла.</span><span class="sxs-lookup"><span data-stu-id="caab9-154">View in the **Preview Data** dialog box the results of the selected formatting options for the destination flat file.</span></span>  
  
 <span data-ttu-id="caab9-155">**Изменить преобразования**</span><span class="sxs-lookup"><span data-stu-id="caab9-155">**Edit transform**</span></span>  
 <span data-ttu-id="caab9-156">Удаление строк, добавление строк и Настройка столбцов в целевом файле с помощью диалогового окна **сопоставления столбцов** .</span><span class="sxs-lookup"><span data-stu-id="caab9-156">Delete rows, append rows, and configure columns in the destination file by using the **Column Mappings** dialog box.</span></span>  
  
  
