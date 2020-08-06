---
title: Выбор таблиц и столбцов Oracle | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- selTabCol
ms.assetid: bf73f80e-a954-4c5f-874e-17fdd4082715
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d51e597f1210643b1543ed981045ade7b2fc2b62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657842"
---
# <a name="select-oracle-tables-and-columns"></a><span data-ttu-id="d9760-102">Выберите столбцы и таблицы Oracle</span><span class="sxs-lookup"><span data-stu-id="d9760-102">Select Oracle Tables and Columns</span></span>
  <span data-ttu-id="d9760-103">Страница «Выбор столбцов и таблиц Oracle» используется для выбора таблиц из базы данных-источника Oracle, изменения в которых будут отслеживаться.</span><span class="sxs-lookup"><span data-stu-id="d9760-103">Use the Select Oracle Tables and Columns page to select the tables from the Oracle source database where changes are captured.</span></span> <span data-ttu-id="d9760-104">Эта страница содержит следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="d9760-104">This page has the following elements:</span></span>  
  
## <a name="options"></a><span data-ttu-id="d9760-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d9760-105">Options</span></span>  
 <span data-ttu-id="d9760-106">**Список «Таблица»**</span><span class="sxs-lookup"><span data-stu-id="d9760-106">**Table list**</span></span>  
 <span data-ttu-id="d9760-107">Список таблиц состоит из трех столбцов:</span><span class="sxs-lookup"><span data-stu-id="d9760-107">The table list has three columns:</span></span>  
  
-   <span data-ttu-id="d9760-108">**Имя таблицы Oracle**: имя таблицы с указанием схемы.</span><span class="sxs-lookup"><span data-stu-id="d9760-108">**Oracle Table Name**: The name of the table, including the table schema.</span></span>  
  
-   <span data-ttu-id="d9760-109">**Экземпляр отслеживания**: имя экземпляра отслеживания, используемое для именования объектов отслеживания изменений данных по экземплярам.</span><span class="sxs-lookup"><span data-stu-id="d9760-109">**Capture Instance**: The name of the capture instance used to name instance-specific change data capture objects.</span></span> <span data-ttu-id="d9760-110">Значение экземпляра отслеживания не может быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="d9760-110">The capture instance cannot be NULL.</span></span>  
  
     <span data-ttu-id="d9760-111">Если это имя не задано, то оно является производным от имени схемы источника и имени исходной таблицы в формате `<schema-name>_<table-name>`.</span><span class="sxs-lookup"><span data-stu-id="d9760-111">If not specified, the name is derived from the source schema name plus the source table name in the format `<schema-name>_<table-name>`.</span></span> <span data-ttu-id="d9760-112">Длина имени экземпляра отслеживания не может превышать 100 символов, оно должно быть уникальным в пределах базы данных.</span><span class="sxs-lookup"><span data-stu-id="d9760-112">The capture instance name cannot exceed 100 characters and must be unique within the database.</span></span>  
  
     <span data-ttu-id="d9760-113">Щелкните любую ячейку в этом столбце, чтобы изменить **capture_instance**вручную.</span><span class="sxs-lookup"><span data-stu-id="d9760-113">You can click in any cell in this column to manually edit the **capture_instance**.</span></span>  
  
-   <span data-ttu-id="d9760-114">**Роль безопасности**. Имя шлюзовой роли базы данных, используемой для управления доступом к информации об изменениях.</span><span class="sxs-lookup"><span data-stu-id="d9760-114">**Security Role**: The name of the database gating role used to control access to change data.</span></span>  
  
     <span data-ttu-id="d9760-115">Щелкните любую ячейку в этом столбце, чтобы изменить **security_role**вручную.</span><span class="sxs-lookup"><span data-stu-id="d9760-115">You can click in any cell in this column to manually edit the **security_role**.</span></span>  
  
 <span data-ttu-id="d9760-116">**Добавить таблицы**</span><span class="sxs-lookup"><span data-stu-id="d9760-116">**Add Tables**</span></span>  
 <span data-ttu-id="d9760-117">Нажмите кнопку **Добавить таблицы** , чтобы открыть диалоговое окно "Выбор таблицы", где вы можете [выбрать таблицы Oracle для отслеживания изменений](select-oracle-tables-for-capturing-changes.md).</span><span class="sxs-lookup"><span data-stu-id="d9760-117">Click **Add Tables** to open the Table Selection dialog box where you can [Select Oracle Tables for Capturing Changes](select-oracle-tables-for-capturing-changes.md).</span></span>  
  
 <span data-ttu-id="d9760-118">**Edit** (Изменение)</span><span class="sxs-lookup"><span data-stu-id="d9760-118">**Edit**</span></span>  
 <span data-ttu-id="d9760-119">Выберите таблицу из списка, а затем **Правка** , чтобы открыть диалоговое окно **Свойства** этой таблицы, позволяющее [вносить изменений в выбранные для отслеживания изменений таблицы](make-changes-to-the-tables-selected-for-capturing-changes.md).</span><span class="sxs-lookup"><span data-stu-id="d9760-119">Select a table from the list and select **Edit** to open the **Properties** dialog box for that table where you can [Make Changes to the Tables Selected for Capturing Changes](make-changes-to-the-tables-selected-for-capturing-changes.md).</span></span>  
  
 <span data-ttu-id="d9760-120">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="d9760-120">**Remove**</span></span>  
 <span data-ttu-id="d9760-121">Выберите таблицу из списка и нажмите **Удалить** , чтобы удалить таблицу из экземпляра CDC.</span><span class="sxs-lookup"><span data-stu-id="d9760-121">Select a table from the list and click **Remove** to remove the table from the CDC instance.</span></span>  
  
 <span data-ttu-id="d9760-122">После [выбора таблиц Oracle для отслеживания изменений](select-oracle-tables-for-capturing-changes.md) и (или) [внесения изменений в выбранные для отслеживания изменений таблицы](make-changes-to-the-tables-selected-for-capturing-changes.md) с помощью соответствующих диалоговых окон нажмите кнопку **Далее** , чтобы [создать и запустить скрипт дополнительного журналирования](generate-and-run-the-supplemental-logging-script.md).</span><span class="sxs-lookup"><span data-stu-id="d9760-122">After you [Select Oracle Tables for Capturing Changes](select-oracle-tables-for-capturing-changes.md) and/or [Make Changes to the Tables Selected for Capturing Changes](make-changes-to-the-tables-selected-for-capturing-changes.md) using the correct dialog boxes, click **Next** to [Generate and Run the Supplemental Logging Script](generate-and-run-the-supplemental-logging-script.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9760-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="d9760-123">See Also</span></span>  
 <span data-ttu-id="d9760-124">[Как создать экземпляр изменения базы данных SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="d9760-124">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 <span data-ttu-id="d9760-125">[Редактирование таблиц](edit-tables.md) </span><span class="sxs-lookup"><span data-stu-id="d9760-125">[Edit Tables](edit-tables.md) </span></span>  
 <span data-ttu-id="d9760-126">[Добавление таблиц в экземпляр CDC](add-tables-to-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="d9760-126">[Add Tables to a CDC Instance](add-tables-to-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="d9760-127">Изменение свойств таблицы</span><span class="sxs-lookup"><span data-stu-id="d9760-127">Edit the Table Properties</span></span>](edit-the-table-properties.md)  
  
  
