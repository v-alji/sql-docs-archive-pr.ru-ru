---
title: Типы данных экземпляра CDC Oracle | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: eec13d8d-c15a-4542-bfc4-da66b1a6bfe0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 71d4ce02db89c1bfd11fe9a3a3535fc92fbc49fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728594"
---
# <a name="oracle-cdc-instance-data-types"></a><span data-ttu-id="14577-102">Типы данных экземпляра CDC Oracle</span><span class="sxs-lookup"><span data-stu-id="14577-102">Oracle CDC Instance Data Types</span></span>
  <span data-ttu-id="14577-103">Экземпляр Oracle CDC поддерживает большинство типов данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="14577-103">The Oracle CDC Instance supports most Oracle data types.</span></span> <span data-ttu-id="14577-104">В следующих разделах описаны поддерживаемые и неподдерживаемые типы данных.</span><span class="sxs-lookup"><span data-stu-id="14577-104">The following sections describe the supported data types and the non-supported data types.</span></span>  
  
## <a name="supported-data-types"></a><span data-ttu-id="14577-105">Поддерживаемые типы данных</span><span class="sxs-lookup"><span data-stu-id="14577-105">Supported Data Types</span></span>  
 <span data-ttu-id="14577-106">В следующей таблице указаны типы данных Oracle, для которых можно проводить отслеживание изменений, а также их сопоставление по умолчанию с типами данных SQL Server в таблицах изменений.</span><span class="sxs-lookup"><span data-stu-id="14577-106">The following table describes the Oracle data types that can be captured and their default mapping to SQL Server data types in the change tables.</span></span> <span data-ttu-id="14577-107">При добавлении экземпляра отслеживания для таблицы из исходной базы данных Oracle можно переопределить некоторые из этих сопоставлений.</span><span class="sxs-lookup"><span data-stu-id="14577-107">When adding a capture instance for a source Oracle table, you can override some of these mappings.</span></span>  
  
|<span data-ttu-id="14577-108">Тип данных базы данных Oracle</span><span class="sxs-lookup"><span data-stu-id="14577-108">Oracle Database Data Type</span></span>|<span data-ttu-id="14577-109">Тип данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="14577-109">SQL Server Data Type</span></span>|  
|-------------------------------|--------------------------|  
|<span data-ttu-id="14577-110">BINARY_FLOAT</span><span class="sxs-lookup"><span data-stu-id="14577-110">BINARY_FLOAT</span></span>|<span data-ttu-id="14577-111">real</span><span class="sxs-lookup"><span data-stu-id="14577-111">REAL</span></span>|  
|<span data-ttu-id="14577-112">BINARY_DOUBLE</span><span class="sxs-lookup"><span data-stu-id="14577-112">BINARY_DOUBLE</span></span>|<span data-ttu-id="14577-113">FLOAT</span><span class="sxs-lookup"><span data-stu-id="14577-113">FLOAT</span></span>|  
|<span data-ttu-id="14577-114">CHAR</span><span class="sxs-lookup"><span data-stu-id="14577-114">CHAR</span></span>|<span data-ttu-id="14577-115">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="14577-115">NVARCHAR</span></span>|  
|<span data-ttu-id="14577-116">DATE</span><span class="sxs-lookup"><span data-stu-id="14577-116">DATE</span></span>|<span data-ttu-id="14577-117">DATETIME</span><span class="sxs-lookup"><span data-stu-id="14577-117">DATETIME</span></span>|  
|<span data-ttu-id="14577-118">FLOAT</span><span class="sxs-lookup"><span data-stu-id="14577-118">FLOAT</span></span>|<span data-ttu-id="14577-119">FLOAT</span><span class="sxs-lookup"><span data-stu-id="14577-119">FLOAT</span></span>|  
|<span data-ttu-id="14577-120">INT</span><span class="sxs-lookup"><span data-stu-id="14577-120">INT</span></span>|<span data-ttu-id="14577-121">NUMERIC (38)</span><span class="sxs-lookup"><span data-stu-id="14577-121">NUMERIC (38)</span></span>|  
|<span data-ttu-id="14577-122">INTERVAL</span><span class="sxs-lookup"><span data-stu-id="14577-122">INTERVAL</span></span>|<span data-ttu-id="14577-123">DATETIME</span><span class="sxs-lookup"><span data-stu-id="14577-123">DATETIME</span></span>|  
|<span data-ttu-id="14577-124">NCHAR</span><span class="sxs-lookup"><span data-stu-id="14577-124">NCHAR</span></span>|<span data-ttu-id="14577-125">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="14577-125">NVARCHAR</span></span>|  
|<span data-ttu-id="14577-126">NUMBER</span><span class="sxs-lookup"><span data-stu-id="14577-126">NUMBER</span></span>|<span data-ttu-id="14577-127">FLOAT</span><span class="sxs-lookup"><span data-stu-id="14577-127">FLOAT</span></span>|  
|<span data-ttu-id="14577-128">NAVARCHAR2</span><span class="sxs-lookup"><span data-stu-id="14577-128">NAVARCHAR2</span></span>|<span data-ttu-id="14577-129">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="14577-129">NVARCHAR</span></span>|  
|<span data-ttu-id="14577-130">RAW</span><span class="sxs-lookup"><span data-stu-id="14577-130">RAW</span></span>|<span data-ttu-id="14577-131">VARBINARY</span><span class="sxs-lookup"><span data-stu-id="14577-131">VARBINARY</span></span>|  
|<span data-ttu-id="14577-132">real</span><span class="sxs-lookup"><span data-stu-id="14577-132">REAL</span></span>|<span data-ttu-id="14577-133">FLOAT</span><span class="sxs-lookup"><span data-stu-id="14577-133">FLOAT</span></span>|  
|<span data-ttu-id="14577-134">timestamp</span><span class="sxs-lookup"><span data-stu-id="14577-134">TIMESTAMP</span></span>|<span data-ttu-id="14577-135">DATETIME2</span><span class="sxs-lookup"><span data-stu-id="14577-135">DATETIME2</span></span>|  
|<span data-ttu-id="14577-136">TIMESTAMP WITH TIME ZONE</span><span class="sxs-lookup"><span data-stu-id="14577-136">TIMESTAMP WITH TIME ZONE</span></span>|<span data-ttu-id="14577-137">VARCHAR (37)</span><span class="sxs-lookup"><span data-stu-id="14577-137">VARCHAR (37)</span></span>|  
|<span data-ttu-id="14577-138">TIMESTAMP WITH LOCAL TIME ZONE</span><span class="sxs-lookup"><span data-stu-id="14577-138">TIMESTAMP WITH LOCAL TIME ZONE</span></span>|<span data-ttu-id="14577-139">VARCHAR (37)</span><span class="sxs-lookup"><span data-stu-id="14577-139">VARCHAR (37)</span></span>|  
|<span data-ttu-id="14577-140">VARCHAR2</span><span class="sxs-lookup"><span data-stu-id="14577-140">VARCHAR2</span></span>|<span data-ttu-id="14577-141">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="14577-141">VARCHAR</span></span>|  
|<span data-ttu-id="14577-142">XMLTYPE</span><span class="sxs-lookup"><span data-stu-id="14577-142">XMLTYPE</span></span>|<span data-ttu-id="14577-143">NVARCHAR (MAX)</span><span class="sxs-lookup"><span data-stu-id="14577-143">NVARCHAR (MAX)</span></span>|  
  
## <a name="non-supported-data-types"></a><span data-ttu-id="14577-144">Неподдерживаемые типы данных</span><span class="sxs-lookup"><span data-stu-id="14577-144">Non-Supported Data Types</span></span>  
 <span data-ttu-id="14577-145">Для исходных таблиц Oracle со столбцами следующих типов данных Oracle отслеживание изменений проводиться не может.</span><span class="sxs-lookup"><span data-stu-id="14577-145">Source Oracle tables with columns of the following Oracle data types cannot be captured.</span></span> <span data-ttu-id="14577-146">Отслеживаемые столбцы с данными этого типа будут показаны как столбцы со значениями NULL, однако изменения их значений будут указываться в маске изменения отслеживаемых таблиц.</span><span class="sxs-lookup"><span data-stu-id="14577-146">Captured columns with these data types will show as null; however, a change in their value is indicated in the change mask of the captured tables.</span></span>  
  
-   <span data-ttu-id="14577-147">LONG</span><span class="sxs-lookup"><span data-stu-id="14577-147">LONG</span></span>  
  
-   <span data-ttu-id="14577-148">XMLTYPE</span><span class="sxs-lookup"><span data-stu-id="14577-148">XMLTYPE</span></span>  
  
-   <span data-ttu-id="14577-149">BLOB</span><span class="sxs-lookup"><span data-stu-id="14577-149">BLOB</span></span>  
  
-   <span data-ttu-id="14577-150">CLOB</span><span class="sxs-lookup"><span data-stu-id="14577-150">CLOB</span></span>  
  
 <span data-ttu-id="14577-151">Для исходных таблиц Oracle со столбцами следующих типов данных Oracle отслеживание изменений проводиться не может.</span><span class="sxs-lookup"><span data-stu-id="14577-151">Source Oracle tables with columns of the following Oracle data types cannot be captured.</span></span>  
  
-   <span data-ttu-id="14577-152">BFILE</span><span class="sxs-lookup"><span data-stu-id="14577-152">BFILE</span></span>  
  
-   <span data-ttu-id="14577-153">ROWID</span><span class="sxs-lookup"><span data-stu-id="14577-153">ROWID</span></span>  
  
-   <span data-ttu-id="14577-154">REF</span><span class="sxs-lookup"><span data-stu-id="14577-154">REF</span></span>  
  
-   <span data-ttu-id="14577-155">UROWID</span><span class="sxs-lookup"><span data-stu-id="14577-155">UROWID</span></span>  
  
-   <span data-ttu-id="14577-156">Вложенная таблица</span><span class="sxs-lookup"><span data-stu-id="14577-156">Nested Table</span></span>  
  
 <span data-ttu-id="14577-157">Если в таблице имеются данные этих типов, средство интеллектуального анализа журнала не сможет получить какие-либо данные ни для одного столбца этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="14577-157">If the following data types are present in a table they will prevent the LogMinder from getting any data for any column of the table:</span></span>  
  
-   <span data-ttu-id="14577-158">Определяемые пользователем типы данных</span><span class="sxs-lookup"><span data-stu-id="14577-158">User-defined data types</span></span>  
  
-   <span data-ttu-id="14577-159">VARRAY</span><span class="sxs-lookup"><span data-stu-id="14577-159">VARRAY</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14577-160">См. также:</span><span class="sxs-lookup"><span data-stu-id="14577-160">See Also</span></span>  
 <span data-ttu-id="14577-161">[Конструктор системы отслеживания измененных данных для Oracle компании Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span><span class="sxs-lookup"><span data-stu-id="14577-161">[Change Data Capture Designer for Oracle by Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span></span>  
 [<span data-ttu-id="14577-162">Экземпляр CDC Oracle</span><span class="sxs-lookup"><span data-stu-id="14577-162">The Oracle CDC Instance</span></span>](the-oracle-cdc-instance.md)  
  
  
