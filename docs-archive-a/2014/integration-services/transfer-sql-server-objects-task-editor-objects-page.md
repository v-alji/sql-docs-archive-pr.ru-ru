---
title: Редактор задачи «перемещение SQL Server объектов» (страница «объекты») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfersqlserverobjects.objects.f1
helpviewer_keywords:
- Transfer SQL Server Objects Task Editor
ms.assetid: 8cc09118-70ac-4013-8308-d87f8411ca0c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7038939b02d17b2449a374be51f7f9fa42eae7d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734277"
---
# <a name="transfer-sql-server-objects-task-editor-objects-page"></a><span data-ttu-id="0b6c3-102">Редактор задачи «Передача объектов SQL Server» (страница «Объекты» )</span><span class="sxs-lookup"><span data-stu-id="0b6c3-102">Transfer SQL Server Objects Task Editor (Objects Page)</span></span>
  <span data-ttu-id="0b6c3-103">Страница **Объекты** диалогового окна **Редактор задачи «Передача объектов SQL Server»** используется для задания свойств копирования одного или нескольких объектов [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] из одного экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] на другой.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-103">Use the **Objects** page of the **Transfer SQL Server Objects Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="0b6c3-104">Примерами объектов [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , которые можно копировать, являются таблицы, представления, хранимые процедуры и функции, определяемые пользователем.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-104">Tables, views, stored procedures, and user-defined functions are a few examples of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects that you can copy.</span></span> <span data-ttu-id="0b6c3-105">Дополнительные сведения об этой задаче см. в разделе [Transfer SQL Server Objects Task](control-flow/transfer-sql-server-objects-task.md).</span><span class="sxs-lookup"><span data-stu-id="0b6c3-105">For more information about this task, see [Transfer SQL Server Objects Task](control-flow/transfer-sql-server-objects-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0b6c3-106">Пользователь, создающий задачу "Передача объектов [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ", должен обладать достаточными разрешениями на объекты исходного сервера, чтобы выбирать их для копирования, а также разрешением на доступ к базе данных целевого сервера, куда объекты будут перенесены.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-106">The user who creates the Transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Objects task must have sufficient permissions on the source server objects to select them for copying, and permission to access the destination server database where the objects will be transferred.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="0b6c3-107">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="0b6c3-107">Static Options</span></span>  
 <span data-ttu-id="0b6c3-108">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-108">**SourceConnection**</span></span>  
 <span data-ttu-id="0b6c3-109">Выберите из списка диспетчер подключений SMO или нажмите кнопку **\<New connection...>** , чтобы создать новое подключение к исходному серверу.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="0b6c3-110">**SourceDatabase**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-110">**SourceDatabase**</span></span>  
 <span data-ttu-id="0b6c3-111">Выберите базу данных на исходном сервере, из которой будут копироваться объекты.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-111">Select a database on the source server from which objects will be copied.</span></span>  
  
 <span data-ttu-id="0b6c3-112">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-112">**DestinationConnection**</span></span>  
 <span data-ttu-id="0b6c3-113">Выберите из списка диспетчер подключений SMO или нажмите кнопку **\<New connection...>** , чтобы создать новое подключение к целевому серверу.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-113">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="0b6c3-114">**DestinationDatabase**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-114">**DestinationDatabase**</span></span>  
 <span data-ttu-id="0b6c3-115">Выберите базу данных на целевом сервере, в которую будут копироваться объекты.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-115">Select a database on the destination server to which objects will be copied.</span></span>  
  
 <span data-ttu-id="0b6c3-116">**DropObjectsFirst**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-116">**DropObjectsFirst**</span></span>  
 <span data-ttu-id="0b6c3-117">Выберите, будут ли выбранные объекты удаляться на целевом сервере перед копированием.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-117">Select whether the selected objects will be dropped first on the destination server before copying.</span></span>  
  
 <span data-ttu-id="0b6c3-118">**IncludeExtendedProperties**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-118">**IncludeExtendedProperties**</span></span>  
 <span data-ttu-id="0b6c3-119">Выберите, будут ли включаться расширенные свойства при копировании объектов с исходного сервера на целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-119">Select whether extended properties will be included when objects are copied from the source to the destination server.</span></span>  
  
 <span data-ttu-id="0b6c3-120">**CopyData**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-120">**CopyData**</span></span>  
 <span data-ttu-id="0b6c3-121">Выберите, будут ли включаться данные при копировании объектов с исходного сервера на целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-121">Select whether data will be included when objects are copied from the source to the destination server.</span></span>  
  
 <span data-ttu-id="0b6c3-122">**ExistingData**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-122">**ExistingData**</span></span>  
 <span data-ttu-id="0b6c3-123">Позволяет указать, как данные будут копироваться на целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-123">Specify how data will be copied to the destination server.</span></span> <span data-ttu-id="0b6c3-124">Параметры этого свойства приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-124">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="0b6c3-125">Значение</span><span class="sxs-lookup"><span data-stu-id="0b6c3-125">Value</span></span>|<span data-ttu-id="0b6c3-126">Description</span><span class="sxs-lookup"><span data-stu-id="0b6c3-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0b6c3-127">**Заменить**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-127">**Replace**</span></span>|<span data-ttu-id="0b6c3-128">Данные на целевом сервере будут перезаписаны.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-128">Data on the destination server will be overwritten.</span></span>|  
|<span data-ttu-id="0b6c3-129">**Append**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-129">**Append**</span></span>|<span data-ttu-id="0b6c3-130">Данные, копируемые с исходного сервера, будут присоединяться к существующим данным на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-130">Data copied from the source server will be appended to existing data on the destination server.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="0b6c3-131">Параметр **ExistingData** доступен только в случае, когда значение **CopyData** равно **True**.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-131">The **ExistingData** option is only available when **CopyData** is set to **True**.</span></span>  
  
 <span data-ttu-id="0b6c3-132">**CopySchema**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-132">**CopySchema**</span></span>  
 <span data-ttu-id="0b6c3-133">Выберите, будет ли копироваться схема в процессе выполнения задачи "Передача объектов [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ".</span><span class="sxs-lookup"><span data-stu-id="0b6c3-133">Select whether the schema is copied during the Transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Objects task.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0b6c3-134">**CopySchema** доступен только в версии [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b6c3-134">**CopySchema** is only available for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0b6c3-135">**UseCollation**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-135">**UseCollation**</span></span>  
 <span data-ttu-id="0b6c3-136">Выберите, будут ли при передаче объектов включаться параметры сортировки, заданные на исходном сервере.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-136">Select whether the transfer of objects should include the collation specified on the source server.</span></span>  
  
 <span data-ttu-id="0b6c3-137">**IncludeDependentObjects**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-137">**IncludeDependentObjects**</span></span>  
 <span data-ttu-id="0b6c3-138">Выберите, будут ли при копировании выбранных объектов каскадно включаться другие зависимые от них объекты.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-138">Select whether copying the selected objects will cascade to include other objects that depend on the objects selected for copying.</span></span>  
  
 <span data-ttu-id="0b6c3-139">**CopyAllObjects**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-139">**CopyAllObjects**</span></span>  
 <span data-ttu-id="0b6c3-140">Выберите, будут ли при выполнении задачи копироваться все объекты заданной базы данных-источника или только выбранные.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-140">Select whether the task will copy all objects in the specified source database or only selected objects.</span></span>  <span data-ttu-id="0b6c3-141">Установка значения этого параметра в False позволяет выбирать объекты для передачи и приводит к отображению динамических параметров этого раздела **CopyAllObjects**.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-141">Setting this option to False gives you the option to select the objects to transfer, and displays the dynamic options in the section, **CopyAllObjects**.</span></span>  
  
 <span data-ttu-id="0b6c3-142">**ObjectsToCopy**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-142">**ObjectsToCopy**</span></span>  
 <span data-ttu-id="0b6c3-143">Раскройте список **ObjectsToCopy** , чтобы указать объекты, которые следует копировать из базы данных-источника в целевую базу.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-143">Expand **ObjectsToCopy** to specify which objects should be copied from the source database to the destination database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0b6c3-144">**ObjectsToCopy** доступен только в случае, если значение **CopyAllObjects** равно **False**.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-144">**ObjectsToCopy** is only available when **CopyAllObjects** is set to **False**.</span></span>  
  
 <span data-ttu-id="0b6c3-145">Параметры копирования следующих типов объектов поддерживаются только в версии [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0b6c3-145">The options to copy the following types of objects are supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span></span>  
  
 <span data-ttu-id="0b6c3-146">Сборки</span><span class="sxs-lookup"><span data-stu-id="0b6c3-146">Assemblies</span></span>  
  
 <span data-ttu-id="0b6c3-147">функции секционирования</span><span class="sxs-lookup"><span data-stu-id="0b6c3-147">Partition functions</span></span>  
  
 <span data-ttu-id="0b6c3-148">схемы секционирования;</span><span class="sxs-lookup"><span data-stu-id="0b6c3-148">Partition schemes</span></span>  
  
 <span data-ttu-id="0b6c3-149">Схемы</span><span class="sxs-lookup"><span data-stu-id="0b6c3-149">Schemas</span></span>  
  
 <span data-ttu-id="0b6c3-150">определяемые пользователем агрегатные функции;</span><span class="sxs-lookup"><span data-stu-id="0b6c3-150">User-defined aggregates</span></span>  
  
 <span data-ttu-id="0b6c3-151">Определяемые пользователем типы</span><span class="sxs-lookup"><span data-stu-id="0b6c3-151">User-defined types</span></span>  
  
 <span data-ttu-id="0b6c3-152">коллекции XML-схем</span><span class="sxs-lookup"><span data-stu-id="0b6c3-152">XML schema collections</span></span>  
  
 <span data-ttu-id="0b6c3-153">**CopyDatabaseUsers**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-153">**CopyDatabaseUsers**</span></span>  
 <span data-ttu-id="0b6c3-154">Укажите, следует ли включать в передачу пользователей базы данных.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-154">Specify whether database users should be included in the transfer.</span></span>  
  
 <span data-ttu-id="0b6c3-155">**CopyDatabaseRoles**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-155">**CopyDatabaseRoles**</span></span>  
 <span data-ttu-id="0b6c3-156">Укажите, следует ли включать в передачу роли базы данных.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-156">Specify whether database roles should be included in the transfer.</span></span>  
  
 <span data-ttu-id="0b6c3-157">**CopySqlServerLogins**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-157">**CopySqlServerLogins**</span></span>  
 <span data-ttu-id="0b6c3-158">Укажите, следует ли включать в передачу имена входа [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0b6c3-158">Specify whether [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins should be included in the transfer.</span></span>  
  
 <span data-ttu-id="0b6c3-159">**CopyObjectLevelPermissions**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-159">**CopyObjectLevelPermissions**</span></span>  
 <span data-ttu-id="0b6c3-160">Укажите, следует ли включать в передачу разрешения уровня объекта.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-160">Specify whether object-level permissions should be included in the transfer.</span></span>  
  
 <span data-ttu-id="0b6c3-161">**CopyIndexes**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-161">**CopyIndexes**</span></span>  
 <span data-ttu-id="0b6c3-162">Укажите, следует ли включать в передачу индексы.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-162">Specify whether indexes should be included in the transfer.</span></span>  
  
 <span data-ttu-id="0b6c3-163">**CopyTriggers**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-163">**CopyTriggers**</span></span>  
 <span data-ttu-id="0b6c3-164">Укажите, следует ли включать в передачу триггеры.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-164">Specify whether triggers should be included in the transfer.</span></span>  
  
 <span data-ttu-id="0b6c3-165">**CopyFullTextIndexes**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-165">**CopyFullTextIndexes**</span></span>  
 <span data-ttu-id="0b6c3-166">Укажите, следует ли включать в передачу полнотекстовые индексы.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-166">Specify whether full-text indexes should be included in the transfer.</span></span>  
  
 <span data-ttu-id="0b6c3-167">**CopyPrimaryKeys**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-167">**CopyPrimaryKeys**</span></span>  
 <span data-ttu-id="0b6c3-168">Укажите, следует ли включать в передачу первичные ключи.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-168">Specify whether primary keys should be included in the transfer.</span></span>  
  
 <span data-ttu-id="0b6c3-169">**CopyForeignKeys**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-169">**CopyForeignKeys**</span></span>  
 <span data-ttu-id="0b6c3-170">Укажите, следует ли включать в передачу внешние ключи.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-170">Specify whether foreign keys should be included in the transfer.</span></span>  
  
 <span data-ttu-id="0b6c3-171">**GenerateScriptsInUnicode**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-171">**GenerateScriptsInUnicode**</span></span>  
 <span data-ttu-id="0b6c3-172">Укажите, имеют ли сформированные скрипты передачи формат Юникода.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-172">Specify whether the generated transfer scripts are in Unicode format.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="0b6c3-173">Динамические параметры</span><span class="sxs-lookup"><span data-stu-id="0b6c3-173">Dynamic Options</span></span>  
  
### <a name="copyallobjects--false"></a><span data-ttu-id="0b6c3-174">CopyAllObjects = False</span><span class="sxs-lookup"><span data-stu-id="0b6c3-174">CopyAllObjects = False</span></span>  
 <span data-ttu-id="0b6c3-175">**CopyAllTables**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-175">**CopyAllTables**</span></span>  
 <span data-ttu-id="0b6c3-176">Выберите, будут ли при выполнении задачи копироваться все таблицы заданной базы данных-источника или только выбранные.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-176">Select whether the task will copy all tables in the specified source database or only the selected tables.</span></span>  
  
 <span data-ttu-id="0b6c3-177">**TablesList**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-177">**TablesList**</span></span>  
 <span data-ttu-id="0b6c3-178">Выберите этот пункт, чтобы открыть диалоговое окно **Выбор таблиц** .</span><span class="sxs-lookup"><span data-stu-id="0b6c3-178">Click to open the **Select Tables** dialog box.</span></span>  
  
 <span data-ttu-id="0b6c3-179">**CopyAllViews**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-179">**CopyAllViews**</span></span>  
 <span data-ttu-id="0b6c3-180">Выберите, будут ли при выполнении задачи копироваться все представления из заданной базы данных-источника или только выбранные.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-180">Select whether the task will copy all views in the specified source database or only the selected views.</span></span>  
  
 <span data-ttu-id="0b6c3-181">**ViewsList**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-181">**ViewsList**</span></span>  
 <span data-ttu-id="0b6c3-182">Выберите этот пункт, чтобы открыть диалоговое окно **Выбор представлений** .</span><span class="sxs-lookup"><span data-stu-id="0b6c3-182">Click to open the **Select Views** dialog box.</span></span>  
  
 <span data-ttu-id="0b6c3-183">**CopyAllStoredProcedures**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-183">**CopyAllStoredProcedures**</span></span>  
 <span data-ttu-id="0b6c3-184">Выберите, будут ли при выполнении задачи копироваться все пользовательские хранимые процедуры из заданной базы данных-источника или только выбранные.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-184">Select whether the task will copy all user-defined stored procedures in the specified source database or only the selected procedures.</span></span>  
  
 <span data-ttu-id="0b6c3-185">**StoredProceduresList**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-185">**StoredProceduresList**</span></span>  
 <span data-ttu-id="0b6c3-186">Выберите этот пункт, чтобы открыть диалоговое окно **Выбор хранимых процедур** .</span><span class="sxs-lookup"><span data-stu-id="0b6c3-186">Click to open the **Select Stored Procedures** dialog box.</span></span>  
  
 <span data-ttu-id="0b6c3-187">**CopyAllUserDefinedFunctions**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-187">**CopyAllUserDefinedFunctions**</span></span>  
 <span data-ttu-id="0b6c3-188">Выберите, будут ли при выполнении задачи копироваться все определяемые пользователем функции из заданной базы данных-источника или только выбранные.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-188">Select whether the task will copy all user-defined functions in the specified source database or only the selected UDFs.</span></span>  
  
 <span data-ttu-id="0b6c3-189">**UserDefinedFunctionsList**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-189">**UserDefinedFunctionsList**</span></span>  
 <span data-ttu-id="0b6c3-190">Выберите этот пункт, чтобы открыть диалоговое окно **Выбор определяемых пользователем функций** .</span><span class="sxs-lookup"><span data-stu-id="0b6c3-190">Click to open the **Select User Defined Functions** dialog box.</span></span>  
  
 <span data-ttu-id="0b6c3-191">**CopyAllDefaults**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-191">**CopyAllDefaults**</span></span>  
 <span data-ttu-id="0b6c3-192">Выберите, будут ли при выполнении задачи копироваться все установленные по умолчанию значения из заданной базы данных-источника или только выбранные.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-192">Select whether the task will copy all defaults in the specified source database or only the selected defaults.</span></span>  
  
 <span data-ttu-id="0b6c3-193">**DefaultsList**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-193">**DefaultsList**</span></span>  
 <span data-ttu-id="0b6c3-194">Выберите этот пункт, чтобы открыть диалоговое окно **Выбор значений по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="0b6c3-194">Click to open the **Select Defaults** dialog box.</span></span>  
  
 <span data-ttu-id="0b6c3-195">**CopyAllUserDefinedDataTypes**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-195">**CopyAllUserDefinedDataTypes**</span></span>  
 <span data-ttu-id="0b6c3-196">Выберите, будут ли при выполнении задачи копироваться все пользовательские типы данных из заданной базы данных-источника или только выбранные.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-196">Select whether the task will copy all user-defined data types in the specified source database or only the selected user-defined data types.</span></span>  
  
 <span data-ttu-id="0b6c3-197">**UserDefinedDataTypesList**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-197">**UserDefinedDataTypesList**</span></span>  
 <span data-ttu-id="0b6c3-198">Выберите этот пункт, чтобы открыть диалоговое окно **Выбор определяемых пользователем типов данных** .</span><span class="sxs-lookup"><span data-stu-id="0b6c3-198">Click to open the **Select User-Defined Data Types** dialog box.</span></span>  
  
 <span data-ttu-id="0b6c3-199">**CopyAllPartitionFunctions**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-199">**CopyAllPartitionFunctions**</span></span>  
 <span data-ttu-id="0b6c3-200">Выберите, будут ли при выполнении задачи копироваться все пользовательские функции секционирования из заданной базы данных-источника или только выбранные.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-200">Select whether the task will copy all user-defined partition functions in the specified source database or only the selected partition functions.</span></span> <span data-ttu-id="0b6c3-201">Поддерживается только в версии [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b6c3-201">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0b6c3-202">**PartitionFunctionsList**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-202">**PartitionFunctionsList**</span></span>  
 <span data-ttu-id="0b6c3-203">Выберите этот пункт, чтобы открыть диалоговое окно **Выбор функций секционирования** .</span><span class="sxs-lookup"><span data-stu-id="0b6c3-203">Click to open the **Select Partition Functions** dialog box.</span></span>  
  
 <span data-ttu-id="0b6c3-204">**CopyAllPartitionSchemes**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-204">**CopyAllPartitionSchemes**</span></span>  
 <span data-ttu-id="0b6c3-205">Выберите, будут ли при выполнении задачи копироваться все схемы секционирования из заданной базы данных-источника или только выбранные.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-205">Select whether the task will copy all partition schemes in the specified source database or only the selected partition schemes.</span></span> <span data-ttu-id="0b6c3-206">Поддерживается только в версии [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b6c3-206">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0b6c3-207">**PartitionSchemesList**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-207">**PartitionSchemesList**</span></span>  
 <span data-ttu-id="0b6c3-208">Выберите этот пункт, чтобы открыть диалоговое окно **Выбор схем секционирования** .</span><span class="sxs-lookup"><span data-stu-id="0b6c3-208">Click to open the **Select Partition Schemes** dialog box.</span></span>  
  
 <span data-ttu-id="0b6c3-209">**CopyAllSchemas**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-209">**CopyAllSchemas**</span></span>  
 <span data-ttu-id="0b6c3-210">Выберите, будут ли при выполнении задачи копироваться все схемы из заданной базы данных-источника или только выбранные.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-210">Select whether the task will copy all schemas in the specified source database or only the selected schemas.</span></span> <span data-ttu-id="0b6c3-211">Поддерживается только в версии [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b6c3-211">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0b6c3-212">**SchemasList**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-212">**SchemasList**</span></span>  
 <span data-ttu-id="0b6c3-213">Выберите этот пункт, чтобы открыть диалоговое окно **Выбор схем** .</span><span class="sxs-lookup"><span data-stu-id="0b6c3-213">Click to open the **Select Schemas** dialog box.</span></span>  
  
 <span data-ttu-id="0b6c3-214">**CopyAllSqlAssemblies**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-214">**CopyAllSqlAssemblies**</span></span>  
 <span data-ttu-id="0b6c3-215">Выберите, будут ли при выполнении задачи копироваться все сборки SQL из заданной базы данных-источника или только выбранные.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-215">Select whether the task will copy all SQL assemblies in the specified source database or only the selected SQL assemblies.</span></span> <span data-ttu-id="0b6c3-216">Поддерживается только в версии [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b6c3-216">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0b6c3-217">**SqlAssembliesList**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-217">**SqlAssembliesList**</span></span>  
 <span data-ttu-id="0b6c3-218">Выберите этот пункт, чтобы открыть диалоговое окно **Выбор сборок SQL** .</span><span class="sxs-lookup"><span data-stu-id="0b6c3-218">Click to open the **Select SQL Assemblies** dialog box.</span></span>  
  
 <span data-ttu-id="0b6c3-219">**CopyAllUserDefinedAggregates**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-219">**CopyAllUserDefinedAggregates**</span></span>  
 <span data-ttu-id="0b6c3-220">Выберите, будут ли при выполнении задачи копироваться все пользовательские агрегатные функции из заданной базы данных-источника или только выбранные.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-220">Select whether the task will copy all user-defined aggregates in the specified source database or only the selected user-defined aggregates.</span></span> <span data-ttu-id="0b6c3-221">Поддерживается только в версии [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b6c3-221">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0b6c3-222">**UserDefinedAggregatesList**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-222">**UserDefinedAggregatesList**</span></span>  
 <span data-ttu-id="0b6c3-223">Выберите этот пункт, чтобы открыть диалоговое окно **Выбор определяемых пользователем статистических выражений** .</span><span class="sxs-lookup"><span data-stu-id="0b6c3-223">Click to open the **Select User-Defined Aggregates** dialog box.</span></span>  
  
 <span data-ttu-id="0b6c3-224">**CopyAllUserDefinedTypes**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-224">**CopyAllUserDefinedTypes**</span></span>  
 <span data-ttu-id="0b6c3-225">Выберите, будут ли при выполнении задачи копироваться все определяемые пользователем типы из заданной базы данных-источника или только выбранные.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-225">Select whether the task will copy all user-defined types in the specified source database or only the selected UDTs.</span></span> <span data-ttu-id="0b6c3-226">Поддерживается только в версии [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b6c3-226">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0b6c3-227">**UserDefinedTypes**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-227">**UserDefinedTypes**</span></span>  
 <span data-ttu-id="0b6c3-228">Выберите этот пункт, чтобы открыть диалоговое окно **Выбор определяемых пользователем типов** .</span><span class="sxs-lookup"><span data-stu-id="0b6c3-228">Click to open the **Select User-Defined Types** dialog box.</span></span>  
  
 <span data-ttu-id="0b6c3-229">**CopyAllXmlSchemaCollections**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-229">**CopyAllXmlSchemaCollections**</span></span>  
 <span data-ttu-id="0b6c3-230">Выберите, будут ли при выполнении задачи копироваться все коллекции XML-схем из заданной базы данных-источника или только выбранные.</span><span class="sxs-lookup"><span data-stu-id="0b6c3-230">Select whether the task will copy all XML Schema collections in the specified source database or only the selected XML schema collections.</span></span> <span data-ttu-id="0b6c3-231">Поддерживается только в версии [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b6c3-231">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0b6c3-232">**XmlSchemaCollectionsList**</span><span class="sxs-lookup"><span data-stu-id="0b6c3-232">**XmlSchemaCollectionsList**</span></span>  
 <span data-ttu-id="0b6c3-233">Выберите этот пункт, чтобы открыть диалоговое окно **Выбрать коллекции XML-схем** .</span><span class="sxs-lookup"><span data-stu-id="0b6c3-233">Click to open the **Select XML Schema Collections** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b6c3-234">См. также:</span><span class="sxs-lookup"><span data-stu-id="0b6c3-234">See Also</span></span>  
 <span data-ttu-id="0b6c3-235">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="0b6c3-235">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="0b6c3-236">[Задачи служб Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="0b6c3-236">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="0b6c3-237">[Редактор задачи "Передача объектов SQL Server" (страница "Общие")](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="0b6c3-237">[Transfer SQL Server Objects Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="0b6c3-238">[Страница «Выражения»](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="0b6c3-238">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="0b6c3-239">[Форматы данных для массового экспорта или импорта (SQL Server)](../relational-databases/import-export/data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0b6c3-239">[Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;](../relational-databases/import-export/data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span></span>  
 [<span data-ttu-id="0b6c3-240">Вопросы безопасности при установке SQL Server</span><span class="sxs-lookup"><span data-stu-id="0b6c3-240">Security Considerations for a SQL Server Installation</span></span>](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
  
