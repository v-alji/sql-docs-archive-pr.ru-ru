---
title: Редактирование таблиц | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- tabProps
ms.assetid: fed8fada-2abc-45e2-8228-0656f9c599cb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8e8058a0c3e8b81814283f055e4c4ac2b08dd2fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655301"
---
# <a name="edit-tables"></a><span data-ttu-id="da8a8-102">Редактирование таблиц</span><span class="sxs-lookup"><span data-stu-id="da8a8-102">Edit Tables</span></span>
  <span data-ttu-id="da8a8-103">На вкладке **Таблицы** можно изменять таблицы и столбцы, выбранные в базе данных-источнике Oracle.</span><span class="sxs-lookup"><span data-stu-id="da8a8-103">Use the **Tables** tab to make changes to the tables and columns that you selected from the Oracle source database.</span></span> <span data-ttu-id="da8a8-104">Эта вкладка содержит следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="da8a8-104">This tab has the following elements:</span></span>  
  
 <span data-ttu-id="da8a8-105">**Список «Таблица»**</span><span class="sxs-lookup"><span data-stu-id="da8a8-105">**Table list**</span></span>  
 <span data-ttu-id="da8a8-106">Список таблиц состоит из трех столбцов:</span><span class="sxs-lookup"><span data-stu-id="da8a8-106">The table list has three columns:</span></span>  
  
-   <span data-ttu-id="da8a8-107">**Имя таблицы Oracle**: имя таблицы с указанием схемы.</span><span class="sxs-lookup"><span data-stu-id="da8a8-107">**Oracle Table Name**: The name of the table, including the table schema.</span></span>  
  
-   <span data-ttu-id="da8a8-108">**Экземпляр отслеживания**: имя экземпляра отслеживания, используемое для именования объектов отслеживания изменений данных по экземплярам.</span><span class="sxs-lookup"><span data-stu-id="da8a8-108">**Capture Instance**: The name of the capture instance used to name instance-specific change data capture objects.</span></span> <span data-ttu-id="da8a8-109">Значение экземпляра отслеживания не может быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="da8a8-109">The capture instance cannot be NULL.</span></span> <span data-ttu-id="da8a8-110">Если имя не указано, то оно образуется из имен исходных схемы и таблицы в формате `<schema-name>_<table-name>.` Длина имени экземпляра отслеживания не должна превышать 100 символов, а само имя должно быть уникальным в рамках базы данных.</span><span class="sxs-lookup"><span data-stu-id="da8a8-110">If not specified, the name is derived from the source schema name plus the source table name in the format `<schema-name>_<table-name>.` The capture instance name cannot exceed 100 characters and must be unique within the database.</span></span> <span data-ttu-id="da8a8-111">Щелкните любую ячейку в этом столбце, чтобы изменить **capture_instance**вручную.</span><span class="sxs-lookup"><span data-stu-id="da8a8-111">You can click in any cell in this column to manually edit the **capture_instance**.</span></span>  
  
-   <span data-ttu-id="da8a8-112">**Роль безопасности**: имя роли базы данных, используемой для получения доступа к данным об изменениях.</span><span class="sxs-lookup"><span data-stu-id="da8a8-112">**Security Role**: The name of the database role used to gain access to change data.</span></span> <span data-ttu-id="da8a8-113">Щелкните любую ячейку в этом столбце, чтобы изменить **security_role**вручную.</span><span class="sxs-lookup"><span data-stu-id="da8a8-113">You can click in any cell in this column to manually edit the **security_role**.</span></span>  
  
 <span data-ttu-id="da8a8-114">**Добавить таблицы**</span><span class="sxs-lookup"><span data-stu-id="da8a8-114">**Add Tables**</span></span>  
 <span data-ttu-id="da8a8-115">Нажмите кнопку **Добавить таблицы** , чтобы открыть диалоговое окно "Выбор таблицы", где вы можете [добавить таблицы в экземпляр CDC](add-tables-to-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="da8a8-115">Click **Add Tables** to open the Table Selection dialog box where you can [Add Tables to a CDC Instance](add-tables-to-a-cdc-instance.md).</span></span> <span data-ttu-id="da8a8-116">Если доступ к базе данных Oracle осуществляется впервые в ходе данного сеанса, необходимо [Connect to Oracle](connect-to-oracle.md).</span><span class="sxs-lookup"><span data-stu-id="da8a8-116">The first time this session that you access the Oracle database, you must [Connect to Oracle](connect-to-oracle.md).</span></span>  
  
 <span data-ttu-id="da8a8-117">**Edit** (Изменение)</span><span class="sxs-lookup"><span data-stu-id="da8a8-117">**Edit**</span></span>  
 <span data-ttu-id="da8a8-118">Выберите таблицу из списка, а затем **Правка** , чтобы открыть диалоговое окно **Свойства** этой таблицы, позволяющее [Изменение свойств таблицы](edit-the-table-properties.md).</span><span class="sxs-lookup"><span data-stu-id="da8a8-118">Select a table from the list and select **Edit** to open the **Properties** dialog box for that table where you can [Edit the Table Properties](edit-the-table-properties.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da8a8-119">Нельзя изменить сопоставление типа для таблиц, у которых уже есть зеркальные таблицы.</span><span class="sxs-lookup"><span data-stu-id="da8a8-119">You cannot edit type mapping for tables that already have mirror tables.</span></span> <span data-ttu-id="da8a8-120">Это можно сделать только для новых таблиц.</span><span class="sxs-lookup"><span data-stu-id="da8a8-120">You can do this for new tables only.</span></span>  
  
 <span data-ttu-id="da8a8-121">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="da8a8-121">**Remove**</span></span>  
 <span data-ttu-id="da8a8-122">Выберите таблицу из списка и нажмите **Удалить** , чтобы удалить таблицу из экземпляра CDC.</span><span class="sxs-lookup"><span data-stu-id="da8a8-122">Select a table from the list and click **Remove** to remove the table from the CDC instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da8a8-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="da8a8-123">See Also</span></span>  
 <span data-ttu-id="da8a8-124">[Как изменить свойства экземпляра CDC](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="da8a8-124">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 [<span data-ttu-id="da8a8-125">Выбор таблиц и столбцов Oracle</span><span class="sxs-lookup"><span data-stu-id="da8a8-125">Select Oracle Tables and Columns</span></span>](select-oracle-tables-and-columns.md)  
  
  
