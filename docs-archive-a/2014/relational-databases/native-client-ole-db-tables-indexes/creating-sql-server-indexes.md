---
title: Создание индексов SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- CreateIndex function
- constraints [OLE DB]
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
- adding indexes
ms.assetid: 6239d440-2818-4b98-bb79-732dced41952
author: rothja
ms.author: jroth
ms.openlocfilehash: 3693355eec7a290c03658c10db500161aa52062d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739785"
---
# <a name="creating-sql-server-indexes"></a><span data-ttu-id="73941-102">Создание индексов SQL Server</span><span class="sxs-lookup"><span data-stu-id="73941-102">Creating SQL Server Indexes</span></span>
  <span data-ttu-id="73941-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик собственного клиента OLE DB предоставляет функцию **IIndexDefinition:: CreateIndex** , позволяющую потребителям определять новые индексы в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] таблицах.</span><span class="sxs-lookup"><span data-stu-id="73941-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **IIndexDefinition::CreateIndex** function, allowing consumers to define new indexes on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span>  
  
 <span data-ttu-id="73941-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента создает индексы таблицы как индексы или ограничения.</span><span class="sxs-lookup"><span data-stu-id="73941-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider creates table indexes as either indexes or constraints.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="73941-105">предоставляет право создания ограничений владельцу таблицы, владельцу базы данных и членам некоторых административных ролей.</span><span class="sxs-lookup"><span data-stu-id="73941-105">gives constraint-creation privilege to the table owner, database owner, and members of certain administrative roles.</span></span> <span data-ttu-id="73941-106">По умолчанию только владелец таблицы может создавать в ней индекс.</span><span class="sxs-lookup"><span data-stu-id="73941-106">By default, only the table owner can create an index on a table.</span></span> <span data-ttu-id="73941-107">Таким образом, успех или сбой функции **CreateIndex** зависит не только от прав доступа пользователя приложения, но и от типа создаваемого индекса.</span><span class="sxs-lookup"><span data-stu-id="73941-107">Therefore, the success or failure of **CreateIndex** depends not only on the application user's access rights but also on the type of index created.</span></span>  
  
 <span data-ttu-id="73941-108">Пользователь задает имя таблицы в виде символьной строки в Юникоде в элементе *pwszName* объединения *uName* в параметре *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="73941-108">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="73941-109">Элемент *eKind* параметра *pTableID* должен быть равен DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="73941-109">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="73941-110">Параметр *pIndexID* может иметь значение null, а если это так, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик собственного клиента OLE DB создает уникальное имя для индекса.</span><span class="sxs-lookup"><span data-stu-id="73941-110">The *pIndexID* parameter can be NULL, and if it is, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider creates a unique name for the index.</span></span> <span data-ttu-id="73941-111">Потребитель может сам задать имя индекса, указав для DBID допустимый указатель в параметре *ppIndexID*.</span><span class="sxs-lookup"><span data-stu-id="73941-111">The consumer can capture the name of the index by specifying a valid pointer to a DBID in the *ppIndexID* parameter.</span></span>  
  
 <span data-ttu-id="73941-112">Потребитель может задать имя индекса в виде символьной строки в Юникоде в элементе *pwszName* объединения *uName* параметра *pIndexID*.</span><span class="sxs-lookup"><span data-stu-id="73941-112">The consumer can specify the index name as a Unicode character string in the *pwszName* member of the *uName* union of the *pIndexID* parameter.</span></span> <span data-ttu-id="73941-113">Элемент *eKind* параметра *pIndexID* должен быть равен DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="73941-113">The *eKind* member of *pIndexID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="73941-114">Потребитель указывает столбец или столбцы, входящие в индекс, по имени.</span><span class="sxs-lookup"><span data-stu-id="73941-114">The consumer specifies the column or columns participating in the index by name.</span></span> <span data-ttu-id="73941-115">Для каждой структуры DBINDEXCOLUMNDESC, используемой в функции **CreateIndex**, элемент *eKind* параметра *pColumnID* должен быть DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="73941-115">For each DBINDEXCOLUMNDESC structure used in **CreateIndex**, the *eKind* member of the *pColumnID* must be DBKIND_NAME.</span></span> <span data-ttu-id="73941-116">Имя столбца задается в виде символьной строки в Юникоде в элементе *pwszName* объединения *uName* параметра *pColumnID*.</span><span class="sxs-lookup"><span data-stu-id="73941-116">The name of the column is specified as a Unicode character string in the *pwszName* member of the *uName* union in the *pColumnID*.</span></span>  
  
 <span data-ttu-id="73941-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик собственного клиента OLE DB и [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает сортировку по возрастанию значений в индексе.</span><span class="sxs-lookup"><span data-stu-id="73941-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support ascending order on values in the index.</span></span> <span data-ttu-id="73941-118">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента возвращает E_INVALIDARG, если потребитель указывает DBINDEX_COL_ORDER_DESC в любой структуре дбиндексколумндеск.</span><span class="sxs-lookup"><span data-stu-id="73941-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns E_INVALIDARG if the consumer specifies DBINDEX_COL_ORDER_DESC in any DBINDEXCOLUMNDESC structure.</span></span>  
  
 <span data-ttu-id="73941-119">Функция **CreateIndex** интерпретирует свойства индекса указанным ниже образом.</span><span class="sxs-lookup"><span data-stu-id="73941-119">**CreateIndex** interprets index properties as follows.</span></span>  
  
|<span data-ttu-id="73941-120">Идентификатор свойства</span><span class="sxs-lookup"><span data-stu-id="73941-120">Property ID</span></span>|<span data-ttu-id="73941-121">Описание</span><span class="sxs-lookup"><span data-stu-id="73941-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="73941-122">DBPROP_INDEX_AUTOUPDATE</span><span class="sxs-lookup"><span data-stu-id="73941-122">DBPROP_INDEX_AUTOUPDATE</span></span>|<span data-ttu-id="73941-123">Ч/З Чтение/запись</span><span class="sxs-lookup"><span data-stu-id="73941-123">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="73941-124">По умолчанию: нет</span><span class="sxs-lookup"><span data-stu-id="73941-124">Default: None</span></span><br /><br /> <span data-ttu-id="73941-125">Описание: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик собственного клиента OLE DB не поддерживает это свойство.</span><span class="sxs-lookup"><span data-stu-id="73941-125">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="73941-126">Попытки установить свойство в **CreateIndex** приводят к возврату значения DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="73941-126">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="73941-127">Элемент *dwStatus* структуры свойства указывает значение DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="73941-127">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="73941-128">DBPROP_INDEX_CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="73941-128">DBPROP_INDEX_CLUSTERED</span></span>|<span data-ttu-id="73941-129">Ч/З Чтение/запись</span><span class="sxs-lookup"><span data-stu-id="73941-129">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="73941-130">Значение по умолчанию: VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="73941-130">Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="73941-131">Описание: управляет кластеризацией индекса.</span><span class="sxs-lookup"><span data-stu-id="73941-131">Description: Controls index clustering.</span></span><br /><br /> <span data-ttu-id="73941-132">VARIANT_TRUE: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента пытается создать кластеризованный индекс для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] таблицы.</span><span class="sxs-lookup"><span data-stu-id="73941-132">VARIANT_TRUE: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider attempts to create a clustered index on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="73941-133">поддерживает не более одного кластеризованного индекса в любой таблице.</span><span class="sxs-lookup"><span data-stu-id="73941-133">supports at most one clustered index on any table.</span></span><br /><br /> <span data-ttu-id="73941-134">VARIANT_FALSE: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента пытается создать некластеризованный индекс для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] таблицы.</span><span class="sxs-lookup"><span data-stu-id="73941-134">VARIANT_FALSE: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider attempts to create a nonclustered index on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>|  
|<span data-ttu-id="73941-135">DBPROP_INDEX_FILLFACTOR</span><span class="sxs-lookup"><span data-stu-id="73941-135">DBPROP_INDEX_FILLFACTOR</span></span>|<span data-ttu-id="73941-136">Ч/З Чтение/запись</span><span class="sxs-lookup"><span data-stu-id="73941-136">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="73941-137">По умолчанию: 0</span><span class="sxs-lookup"><span data-stu-id="73941-137">Default: 0</span></span><br /><br /> <span data-ttu-id="73941-138">Описание: указывает процент страниц индекса, используемых для хранения.</span><span class="sxs-lookup"><span data-stu-id="73941-138">Description: Specifies the percentage of an index page used for storage.</span></span> <span data-ttu-id="73941-139">Дополнительные сведения см. в разделе [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="73941-139">For more information, see [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql).</span></span><br /><br /> <span data-ttu-id="73941-140">Тип варианта — VT_I4.</span><span class="sxs-lookup"><span data-stu-id="73941-140">The type of the variant is VT_I4.</span></span> <span data-ttu-id="73941-141">Значение должно находиться в диапазоне от 1 до 100.</span><span class="sxs-lookup"><span data-stu-id="73941-141">The value must be greater than or equal to 1 and less than or equal to 100.</span></span>|  
|<span data-ttu-id="73941-142">DBPROP_INDEX_INITIALIZE</span><span class="sxs-lookup"><span data-stu-id="73941-142">DBPROP_INDEX_INITIALIZE</span></span>|<span data-ttu-id="73941-143">Ч/З Чтение/запись</span><span class="sxs-lookup"><span data-stu-id="73941-143">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="73941-144">По умолчанию: нет</span><span class="sxs-lookup"><span data-stu-id="73941-144">Default: None</span></span><br /><br /> <span data-ttu-id="73941-145">Описание: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик собственного клиента OLE DB не поддерживает это свойство.</span><span class="sxs-lookup"><span data-stu-id="73941-145">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="73941-146">Попытки установить свойство в **CreateIndex** приводят к возврату значения DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="73941-146">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="73941-147">Элемент *dwStatus* структуры свойства указывает значение DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="73941-147">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="73941-148">DBPROP_INDEX_NULLCOLLATION</span><span class="sxs-lookup"><span data-stu-id="73941-148">DBPROP_INDEX_NULLCOLLATION</span></span>|<span data-ttu-id="73941-149">Ч/З Чтение/запись</span><span class="sxs-lookup"><span data-stu-id="73941-149">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="73941-150">По умолчанию: нет</span><span class="sxs-lookup"><span data-stu-id="73941-150">Default: None</span></span><br /><br /> <span data-ttu-id="73941-151">Описание: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик собственного клиента OLE DB не поддерживает это свойство.</span><span class="sxs-lookup"><span data-stu-id="73941-151">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="73941-152">Попытки установить свойство в **CreateIndex** приводят к возврату значения DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="73941-152">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="73941-153">Элемент *dwStatus* структуры свойства указывает значение DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="73941-153">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="73941-154">DBPROP_INDEX_NULLS</span><span class="sxs-lookup"><span data-stu-id="73941-154">DBPROP_INDEX_NULLS</span></span>|<span data-ttu-id="73941-155">Ч/З Чтение/запись</span><span class="sxs-lookup"><span data-stu-id="73941-155">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="73941-156">По умолчанию: нет</span><span class="sxs-lookup"><span data-stu-id="73941-156">Default: None</span></span><br /><br /> <span data-ttu-id="73941-157">Описание: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик собственного клиента OLE DB не поддерживает это свойство.</span><span class="sxs-lookup"><span data-stu-id="73941-157">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="73941-158">Попытки установить свойство в **CreateIndex** приводят к возврату значения DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="73941-158">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="73941-159">Элемент *dwStatus* структуры свойства указывает значение DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="73941-159">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="73941-160">DBPROP_INDEX_PRIMARYKEY</span><span class="sxs-lookup"><span data-stu-id="73941-160">DBPROP_INDEX_PRIMARYKEY</span></span>|<span data-ttu-id="73941-161">Ч/З Чтение/запись</span><span class="sxs-lookup"><span data-stu-id="73941-161">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="73941-162">Значение по умолчанию: VARIANT_FALSE Description: создает индекс как ссылочную целостность, ограничение ПЕРВИЧного ключа.</span><span class="sxs-lookup"><span data-stu-id="73941-162">Default: VARIANT_FALSE Description: Creates the index as a referential integrity, PRIMARY KEY constraint.</span></span><br /><br /> <span data-ttu-id="73941-163">VARIANT_TRUE: индекс создается для поддержки ограничения PRIMARY KEY таблицы.</span><span class="sxs-lookup"><span data-stu-id="73941-163">VARIANT_TRUE: The index is created to support the PRIMARY KEY constraint of the table.</span></span> <span data-ttu-id="73941-164">Столбцы не должны иметь значений NULL.</span><span class="sxs-lookup"><span data-stu-id="73941-164">The columns must be nonnullable.</span></span><br /><br /> <span data-ttu-id="73941-165">VARIANT_FALSE: индекс не используется в качестве ограничения PRIMARY KEY для значений строк таблицы.</span><span class="sxs-lookup"><span data-stu-id="73941-165">VARIANT_FALSE: The index is not used as a PRIMARY KEY constraint for row values in the table.</span></span>|  
|<span data-ttu-id="73941-166">DBPROP_INDEX_SORTBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="73941-166">DBPROP_INDEX_SORTBOOKMARKS</span></span>|<span data-ttu-id="73941-167">Ч/З Чтение/запись</span><span class="sxs-lookup"><span data-stu-id="73941-167">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="73941-168">По умолчанию: нет</span><span class="sxs-lookup"><span data-stu-id="73941-168">Default: None</span></span><br /><br /> <span data-ttu-id="73941-169">Описание: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик собственного клиента OLE DB не поддерживает это свойство.</span><span class="sxs-lookup"><span data-stu-id="73941-169">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="73941-170">Попытки установить свойство в **CreateIndex** приводят к возврату значения DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="73941-170">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="73941-171">Элемент *dwStatus* структуры свойства указывает значение DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="73941-171">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="73941-172">DBPROP_INDEX_TEMPINDEX</span><span class="sxs-lookup"><span data-stu-id="73941-172">DBPROP_INDEX_TEMPINDEX</span></span>|<span data-ttu-id="73941-173">Ч/З Чтение/запись</span><span class="sxs-lookup"><span data-stu-id="73941-173">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="73941-174">По умолчанию: нет</span><span class="sxs-lookup"><span data-stu-id="73941-174">Default: None</span></span><br /><br /> <span data-ttu-id="73941-175">Описание: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик собственного клиента OLE DB не поддерживает это свойство.</span><span class="sxs-lookup"><span data-stu-id="73941-175">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="73941-176">Попытки установить свойство в **CreateIndex** приводят к возврату значения DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="73941-176">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="73941-177">Элемент *dwStatus* структуры свойства указывает значение DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="73941-177">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="73941-178">DBPROP_INDEX_TYPE</span><span class="sxs-lookup"><span data-stu-id="73941-178">DBPROP_INDEX_TYPE</span></span>|<span data-ttu-id="73941-179">Ч/З Чтение/запись</span><span class="sxs-lookup"><span data-stu-id="73941-179">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="73941-180">По умолчанию: нет</span><span class="sxs-lookup"><span data-stu-id="73941-180">Default: None</span></span><br /><br /> <span data-ttu-id="73941-181">Описание: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик собственного клиента OLE DB не поддерживает это свойство.</span><span class="sxs-lookup"><span data-stu-id="73941-181">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="73941-182">Попытки установить свойство в **CreateIndex** приводят к возврату значения DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="73941-182">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="73941-183">Элемент *dwStatus* структуры свойства указывает значение DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="73941-183">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="73941-184">DBPROP_INDEX_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="73941-184">DBPROP_INDEX_UNIQUE</span></span>|<span data-ttu-id="73941-185">Ч/З Чтение/запись</span><span class="sxs-lookup"><span data-stu-id="73941-185">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="73941-186">Значение по умолчанию: VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="73941-186">Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="73941-187">Описание: создает индекс в виде ограничения UNIQUE для определенного столбца или столбцов.</span><span class="sxs-lookup"><span data-stu-id="73941-187">Description: Creates the index as a UNIQUE constraint on the participating column or columns.</span></span><br /><br /> <span data-ttu-id="73941-188">VARIANT_TRUE: индекс используется для уникального ограничения значений в строках таблицы.</span><span class="sxs-lookup"><span data-stu-id="73941-188">VARIANT_TRUE: The index is used to uniquely constrain row values in the table.</span></span><br /><br /> <span data-ttu-id="73941-189">VARIANT_FALSE: индекс не используется для уникального ограничения значений строк.</span><span class="sxs-lookup"><span data-stu-id="73941-189">VARIANT_FALSE: The index does not uniquely constrain row values.</span></span>|  
  
 <span data-ttu-id="73941-190">В DBPROPSET_SQLSERVERINDEX свойств, зависящих от поставщика, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента определяет следующее свойство сведений об источнике данных.</span><span class="sxs-lookup"><span data-stu-id="73941-190">In the provider-specific property set DBPROPSET_SQLSERVERINDEX, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following data source information property.</span></span>  
  
|<span data-ttu-id="73941-191">Идентификатор свойства</span><span class="sxs-lookup"><span data-stu-id="73941-191">Property ID</span></span>|<span data-ttu-id="73941-192">Описание</span><span class="sxs-lookup"><span data-stu-id="73941-192">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="73941-193">SSPROP_INDEX_XML</span><span class="sxs-lookup"><span data-stu-id="73941-193">SSPROP_INDEX_XML</span></span>|<span data-ttu-id="73941-194">Тип: VT_BOOL (R/W)</span><span class="sxs-lookup"><span data-stu-id="73941-194">Type: VT_BOOL (R/W)</span></span><br /><br /> <span data-ttu-id="73941-195">Значение по умолчанию: VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="73941-195">Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="73941-196">Описание: если при вызове метода IIndexDefinition::CreateIndex это свойство указывается со значением VARIANT_TRUE, создается первичный XML-индекс, соответствующий индексированному столбцу.</span><span class="sxs-lookup"><span data-stu-id="73941-196">Description: When this property is specified with a value of VARIANT_TRUE with IIndexDefinition::CreateIndex, it results in a primary xml index being created corresponding to the column being indexed.</span></span> <span data-ttu-id="73941-197">Если это свойство имеет значение VARIANT_TRUE, параметр cIndexColumnDescs должен быть равен 1. В противном случае возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="73941-197">If this property is VARIANT_TRUE, cIndexColumnDescs should be 1, otherwise it is an error.</span></span>|  
  
 <span data-ttu-id="73941-198">В данном примере создается индекс первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="73941-198">This example creates a primary key index:</span></span>  
  
```  
// This CREATE TABLE statement shows the referential integrity and   
// PRIMARY KEY constraint on the OrderDetails table that will be created   
// by the following example code.  
//  
// CREATE TABLE OrderDetails  
// (  
//    OrderID      int      NOT NULL  
//    ProductID   int      NOT NULL  
//        CONSTRAINT PK_OrderDetails  
//        PRIMARY KEY CLUSTERED (OrderID, ProductID),  
//    UnitPrice   money      NOT NULL,  
//    Quantity   int      NOT NULL,  
//    Discount   decimal(2,2)   NOT NULL  
//        DEFAULT 0  
// )  
//  
HRESULT CreatePrimaryKey  
    (  
    IIndexDefinition* pIIndexDefinition  
    )  
    {  
    HRESULT             hr = S_OK;  
  
    DBID                dbidTable;  
    DBID                dbidIndex;  
    const ULONG         nCols = 2;  
    ULONG               nCol;  
    const ULONG         nProps = 2;  
    ULONG               nProp;  
  
    DBINDEXCOLUMNDESC   dbidxcoldesc[nCols];  
    DBPROP              dbpropIndex[nProps];  
    DBPROPSET           dbpropset;  
  
    DBID*               pdbidIndexOut = NULL;  
  
    // Set up identifiers for the table and index.  
    dbidTable.eKind = DBKIND_NAME;  
    dbidTable.uName.pwszName = L"OrderDetails";  
  
    dbidIndex.eKind = DBKIND_NAME;  
    dbidIndex.uName.pwszName = L"PK_OrderDetails";  
  
    // Set up column identifiers.  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        dbidxcoldesc[nCol].pColumnID = new DBID;  
        dbidxcoldesc[nCol].pColumnID->eKind = DBKIND_NAME;  
  
        dbidxcoldesc[nCol].eIndexColOrder = DBINDEX_COL_ORDER_ASC;  
        }  
    dbidxcoldesc[0].pColumnID->uName.pwszName = L"OrderID";  
    dbidxcoldesc[1].pColumnID->uName.pwszName = L"ProductID";  
  
    // Set properties for the index. The index is clustered,  
    // PRIMARY KEY.  
    for (nProp = 0; nProp < nProps; nProp++)  
        {  
        dbpropIndex[nProp].dwOptions = DBPROPOPTIONS_REQUIRED;  
        dbpropIndex[nProp].colid = DB_NULLID;  
  
        VariantInit(&(dbpropIndex[nProp].vValue));  
  
        dbpropIndex[nProp].vValue.vt = VT_BOOL;  
        }  
    dbpropIndex[0].dwPropertyID = DBPROP_INDEX_CLUSTERED;  
    dbpropIndex[0].vValue.boolVal = VARIANT_TRUE;  
  
    dbpropIndex[1].dwPropertyID = DBPROP_INDEX_PRIMARYKEY;  
    dbpropIndex[1].vValue.boolVal = VARIANT_TRUE;  
  
    dbpropset.rgProperties = dbpropIndex;  
    dbpropset.cProperties = nProps;  
    dbpropset.guidPropertySet = DBPROPSET_INDEX;  
  
    hr = pIIndexDefinition->CreateIndex(&dbidTable, &dbidIndex, nCols,  
        dbidxcoldesc, 1, &dbpropset, &pdbidIndexOut);  
  
    // Clean up dynamically allocated DBIDs.  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        delete dbidxcoldesc[nCol].pColumnID;  
        }  
  
    return (hr);  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="73941-199">См. также:</span><span class="sxs-lookup"><span data-stu-id="73941-199">See Also</span></span>  
 [<span data-ttu-id="73941-200">Таблицы и индексы</span><span class="sxs-lookup"><span data-stu-id="73941-200">Tables and Indexes</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/tables-and-indexes.md)  
  
  
