---
title: bcp_gettypename | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_gettypename
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_gettypename function
ms.assetid: 65f036d1-f60e-4b8a-97b3-76fccf0dfed4
author: rothja
ms.author: jroth
ms.openlocfilehash: b2d92498b9d863fa2cb700ec4d88868c0984c4d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657773"
---
# <a name="bcp_gettypename"></a><span data-ttu-id="d1513-102">bcp_gettypename</span><span class="sxs-lookup"><span data-stu-id="d1513-102">bcp_gettypename</span></span>
  <span data-ttu-id="d1513-103">Возвращает имя типа SQL для указанного токена типа BCP.</span><span class="sxs-lookup"><span data-stu-id="d1513-103">Returns the SQL type name for a specified BCP type token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1513-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1513-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_gettypename (  
INT   
token  
,  
DBBOOL   
fIsMaxType  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="d1513-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d1513-105">Arguments</span></span>  
 <span data-ttu-id="d1513-106">*token*</span><span class="sxs-lookup"><span data-stu-id="d1513-106">*token*</span></span>  
 <span data-ttu-id="d1513-107">Значение, указывающее токен типа BCP.</span><span class="sxs-lookup"><span data-stu-id="d1513-107">A value indicating a BCP type token.</span></span>  
  
 <span data-ttu-id="d1513-108">*полями*</span><span class="sxs-lookup"><span data-stu-id="d1513-108">*field*</span></span>  
 <span data-ttu-id="d1513-109">Указывает, запрашивает ли токен тип max.</span><span class="sxs-lookup"><span data-stu-id="d1513-109">Indicates if token requested is a max type.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="d1513-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d1513-110">Returns</span></span>  
 <span data-ttu-id="d1513-111">Строка, содержащая имя типа SQL, соответствующего типу BCP.</span><span class="sxs-lookup"><span data-stu-id="d1513-111">A string containing the SQL type name corresponding to the BCP type.</span></span> <span data-ttu-id="d1513-112">Если указывается недопустимый тип BCP, возвращается пустая строка.</span><span class="sxs-lookup"><span data-stu-id="d1513-112">If an invalid BCP type is specified, an empty string is returned..</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1513-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="d1513-113">Remarks</span></span>  
 <span data-ttu-id="d1513-114">Токены типа BCP определены в файле заголовка sqlncli.h и библиотеке sqlncli11.lib.</span><span class="sxs-lookup"><span data-stu-id="d1513-114">The BCP type tokens are defined in the sqlncli.h header file and the sqlncli11.lib library.</span></span>  
  
 <span data-ttu-id="d1513-115">В следующей таблице указаны возможные типы BCP, независимо от того, являются ли они типами max или нет, а также ожидаемые выходные данные.</span><span class="sxs-lookup"><span data-stu-id="d1513-115">The table below specifies the possible BCP types, whether or not they are max types, and the expected output.</span></span>  
  
|<span data-ttu-id="d1513-116">Имя типа BCP</span><span class="sxs-lookup"><span data-stu-id="d1513-116">BCP type name</span></span>|<span data-ttu-id="d1513-117">MaxType</span><span class="sxs-lookup"><span data-stu-id="d1513-117">MaxType</span></span>|<span data-ttu-id="d1513-118">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d1513-118">Output</span></span>|  
|-------------------|-------------|------------|  
|`SQLDECIMAL`|<span data-ttu-id="d1513-119">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-119">Either</span></span>|<span data-ttu-id="d1513-120">**decimal**</span><span class="sxs-lookup"><span data-stu-id="d1513-120">**decimal**</span></span>|  
|`SQLNUMERIC`|<span data-ttu-id="d1513-121">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-121">Either</span></span>|<span data-ttu-id="d1513-122">**numeric**</span><span class="sxs-lookup"><span data-stu-id="d1513-122">**numeric**</span></span>|  
|`SQLINT1`|<span data-ttu-id="d1513-123">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-123">Either</span></span>|<span data-ttu-id="d1513-124">**tinyint**</span><span class="sxs-lookup"><span data-stu-id="d1513-124">**tinyint**</span></span>|  
|`SQLINT2`|<span data-ttu-id="d1513-125">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-125">Either</span></span>|<span data-ttu-id="d1513-126">**smallint**</span><span class="sxs-lookup"><span data-stu-id="d1513-126">**smallint**</span></span>|  
|`SQLINT4`|<span data-ttu-id="d1513-127">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-127">Either</span></span>|<span data-ttu-id="d1513-128">**int**</span><span class="sxs-lookup"><span data-stu-id="d1513-128">**int**</span></span>|  
|`SQLMONEY`|<span data-ttu-id="d1513-129">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-129">Either</span></span>|<span data-ttu-id="d1513-130">**money**</span><span class="sxs-lookup"><span data-stu-id="d1513-130">**money**</span></span>|  
|`SQLFLT8`|<span data-ttu-id="d1513-131">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-131">Either</span></span>|<span data-ttu-id="d1513-132">**float**</span><span class="sxs-lookup"><span data-stu-id="d1513-132">**float**</span></span>|  
|`SQLDATETIME`|<span data-ttu-id="d1513-133">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-133">Either</span></span>|<span data-ttu-id="d1513-134">**datetime**</span><span class="sxs-lookup"><span data-stu-id="d1513-134">**datetime**</span></span>|  
|`SQLBITN`|<span data-ttu-id="d1513-135">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-135">Either</span></span>|<span data-ttu-id="d1513-136">**bit-null**</span><span class="sxs-lookup"><span data-stu-id="d1513-136">**bit-null**</span></span>|  
|`SQLBIT`|<span data-ttu-id="d1513-137">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-137">Either</span></span>|<span data-ttu-id="d1513-138">**bit**</span><span class="sxs-lookup"><span data-stu-id="d1513-138">**bit**</span></span>|  
|`SQLBIGCHAR`|<span data-ttu-id="d1513-139">Нет</span><span class="sxs-lookup"><span data-stu-id="d1513-139">No</span></span>|<span data-ttu-id="d1513-140">**char**</span><span class="sxs-lookup"><span data-stu-id="d1513-140">**char**</span></span>|  
|`SQLCHARACTER`|<span data-ttu-id="d1513-141">Нет</span><span class="sxs-lookup"><span data-stu-id="d1513-141">No</span></span>|<span data-ttu-id="d1513-142">**char**</span><span class="sxs-lookup"><span data-stu-id="d1513-142">**char**</span></span>|  
|`SQLBIGVARCHAR`|<span data-ttu-id="d1513-143">Нет</span><span class="sxs-lookup"><span data-stu-id="d1513-143">No</span></span>|<span data-ttu-id="d1513-144">**varchar**</span><span class="sxs-lookup"><span data-stu-id="d1513-144">**varchar**</span></span>|  
|`SQLVARCHAR`|<span data-ttu-id="d1513-145">Нет</span><span class="sxs-lookup"><span data-stu-id="d1513-145">No</span></span>|<span data-ttu-id="d1513-146">**varchar**</span><span class="sxs-lookup"><span data-stu-id="d1513-146">**varchar**</span></span>|  
|`SQLTEXT`|<span data-ttu-id="d1513-147">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-147">Either</span></span>|<span data-ttu-id="d1513-148">**text**</span><span class="sxs-lookup"><span data-stu-id="d1513-148">**text**</span></span>|  
|`SQLBIGBINARY`|<span data-ttu-id="d1513-149">Нет</span><span class="sxs-lookup"><span data-stu-id="d1513-149">No</span></span>|<span data-ttu-id="d1513-150">**binary**</span><span class="sxs-lookup"><span data-stu-id="d1513-150">**binary**</span></span>|  
|`SQLBINARY`|<span data-ttu-id="d1513-151">Нет</span><span class="sxs-lookup"><span data-stu-id="d1513-151">No</span></span>|<span data-ttu-id="d1513-152">**Двоичный**</span><span class="sxs-lookup"><span data-stu-id="d1513-152">**Binary**</span></span>|  
|`SQLBIGVARBINARY`|<span data-ttu-id="d1513-153">Нет</span><span class="sxs-lookup"><span data-stu-id="d1513-153">No</span></span>|<span data-ttu-id="d1513-154">**Varbinary**</span><span class="sxs-lookup"><span data-stu-id="d1513-154">**Varbinary**</span></span>|  
|`SQLVARBINARY`|<span data-ttu-id="d1513-155">Нет</span><span class="sxs-lookup"><span data-stu-id="d1513-155">No</span></span>|<span data-ttu-id="d1513-156">**Varbinary**</span><span class="sxs-lookup"><span data-stu-id="d1513-156">**Varbinary**</span></span>|  
|`SQLIMAGE`|<span data-ttu-id="d1513-157">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-157">Either</span></span>|<span data-ttu-id="d1513-158">**Изображение**</span><span class="sxs-lookup"><span data-stu-id="d1513-158">**Image**</span></span>|  
|`SQLINTN`|<span data-ttu-id="d1513-159">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-159">Either</span></span>|<span data-ttu-id="d1513-160">**int-null**</span><span class="sxs-lookup"><span data-stu-id="d1513-160">**int-null**</span></span>|  
|`SQLDATETIMN`|<span data-ttu-id="d1513-161">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-161">Either</span></span>|<span data-ttu-id="d1513-162">**datetime-null**</span><span class="sxs-lookup"><span data-stu-id="d1513-162">**datetime-null**</span></span>|  
|`SQLMONEYN`|<span data-ttu-id="d1513-163">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-163">Either</span></span>|<span data-ttu-id="d1513-164">**money-null**</span><span class="sxs-lookup"><span data-stu-id="d1513-164">**money-null**</span></span>|  
|`SQLFLTN`|<span data-ttu-id="d1513-165">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-165">Either</span></span>|<span data-ttu-id="d1513-166">**float-null**</span><span class="sxs-lookup"><span data-stu-id="d1513-166">**float-null**</span></span>|  
|`SQLAOPSUM`|<span data-ttu-id="d1513-167">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-167">Either</span></span>|<span data-ttu-id="d1513-168">**Функции**</span><span class="sxs-lookup"><span data-stu-id="d1513-168">**Sum**</span></span>|  
|`SQLAOPAVG`|<span data-ttu-id="d1513-169">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-169">Either</span></span>|<span data-ttu-id="d1513-170">**Обращения**</span><span class="sxs-lookup"><span data-stu-id="d1513-170">**Avg**</span></span>|  
|`SQLAOPCNT`|<span data-ttu-id="d1513-171">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-171">Either</span></span>|<span data-ttu-id="d1513-172">**Count**</span><span class="sxs-lookup"><span data-stu-id="d1513-172">**Count**</span></span>|  
|`SQLAOPMIN`|<span data-ttu-id="d1513-173">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-173">Either</span></span>|<span data-ttu-id="d1513-174">**Минимум**</span><span class="sxs-lookup"><span data-stu-id="d1513-174">**Min**</span></span>|  
|`SQLAOPMAX`|<span data-ttu-id="d1513-175">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-175">Either</span></span>|<span data-ttu-id="d1513-176">**Максимальной**</span><span class="sxs-lookup"><span data-stu-id="d1513-176">**Max**</span></span>|  
|`SQLDATETIM4`|<span data-ttu-id="d1513-177">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-177">Either</span></span>|<span data-ttu-id="d1513-178">**smalldatetime**</span><span class="sxs-lookup"><span data-stu-id="d1513-178">**smalldatetime**</span></span>|  
|`SQLMONEY4`|<span data-ttu-id="d1513-179">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-179">Either</span></span>|<span data-ttu-id="d1513-180">**Smallmoney**</span><span class="sxs-lookup"><span data-stu-id="d1513-180">**Smallmoney**</span></span>|  
|`SQLFLT4`|<span data-ttu-id="d1513-181">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-181">Either</span></span>|<span data-ttu-id="d1513-182">**Real**</span><span class="sxs-lookup"><span data-stu-id="d1513-182">**Real**</span></span>|  
|`SQLUNIQUEID`|<span data-ttu-id="d1513-183">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-183">Either</span></span>|<span data-ttu-id="d1513-184">**uniqueidentifier**</span><span class="sxs-lookup"><span data-stu-id="d1513-184">**uniqueidentifier**</span></span>|  
|`SQLNCHAR`|<span data-ttu-id="d1513-185">Нет</span><span class="sxs-lookup"><span data-stu-id="d1513-185">No</span></span>|<span data-ttu-id="d1513-186">**Nchar**</span><span class="sxs-lookup"><span data-stu-id="d1513-186">**Nchar**</span></span>|  
|`SQLNVARCHAR`|<span data-ttu-id="d1513-187">Нет</span><span class="sxs-lookup"><span data-stu-id="d1513-187">No</span></span>|<span data-ttu-id="d1513-188">**Nvarchar**</span><span class="sxs-lookup"><span data-stu-id="d1513-188">**Nvarchar**</span></span>|  
|`SQLNTEXT`|<span data-ttu-id="d1513-189">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-189">Either</span></span>|<span data-ttu-id="d1513-190">**Типы**</span><span class="sxs-lookup"><span data-stu-id="d1513-190">**Ntext**</span></span>|  
|`SQLVARIANT`|<span data-ttu-id="d1513-191">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-191">Either</span></span>|<span data-ttu-id="d1513-192">**sql_variant**</span><span class="sxs-lookup"><span data-stu-id="d1513-192">**sql_variant**</span></span>|  
|`SQLINT8`|<span data-ttu-id="d1513-193">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-193">Either</span></span>|<span data-ttu-id="d1513-194">**Bigint**</span><span class="sxs-lookup"><span data-stu-id="d1513-194">**Bigint**</span></span>|  
|`SQLCHARACTER`|<span data-ttu-id="d1513-195">Да</span><span class="sxs-lookup"><span data-stu-id="d1513-195">Yes</span></span>|<span data-ttu-id="d1513-196">**varchar(max)**</span><span class="sxs-lookup"><span data-stu-id="d1513-196">**varchar(max)**</span></span>|  
|`SQLBIGCHAR`|<span data-ttu-id="d1513-197">Да</span><span class="sxs-lookup"><span data-stu-id="d1513-197">Yes</span></span>|<span data-ttu-id="d1513-198">**varchar(max)**</span><span class="sxs-lookup"><span data-stu-id="d1513-198">**varchar(max)**</span></span>|  
|`SQLBIGVARCHAR`|<span data-ttu-id="d1513-199">Да</span><span class="sxs-lookup"><span data-stu-id="d1513-199">Yes</span></span>|<span data-ttu-id="d1513-200">**varchar(max)**</span><span class="sxs-lookup"><span data-stu-id="d1513-200">**varchar(max)**</span></span>|  
|`SQLVARCHAR`|<span data-ttu-id="d1513-201">Да</span><span class="sxs-lookup"><span data-stu-id="d1513-201">Yes</span></span>|<span data-ttu-id="d1513-202">**varchar(max)**</span><span class="sxs-lookup"><span data-stu-id="d1513-202">**varchar(max)**</span></span>|  
|`SQLBINARY`|<span data-ttu-id="d1513-203">Да</span><span class="sxs-lookup"><span data-stu-id="d1513-203">Yes</span></span>|<span data-ttu-id="d1513-204">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="d1513-204">**varbinary(max)**</span></span>|  
|`SQLBIGBINARY`|<span data-ttu-id="d1513-205">Да</span><span class="sxs-lookup"><span data-stu-id="d1513-205">Yes</span></span>|<span data-ttu-id="d1513-206">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="d1513-206">**varbinary(max)**</span></span>|  
|`SQLBIGVARBINARY`|<span data-ttu-id="d1513-207">Да</span><span class="sxs-lookup"><span data-stu-id="d1513-207">Yes</span></span>|<span data-ttu-id="d1513-208">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="d1513-208">**varbinary(max)**</span></span>|  
|`SQLVARBINARY`|<span data-ttu-id="d1513-209">Да</span><span class="sxs-lookup"><span data-stu-id="d1513-209">Yes</span></span>|<span data-ttu-id="d1513-210">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="d1513-210">**varbinary(max)**</span></span>|  
|`SQLNCHAR`|<span data-ttu-id="d1513-211">Да</span><span class="sxs-lookup"><span data-stu-id="d1513-211">Yes</span></span>|<span data-ttu-id="d1513-212">**nvarchar(max)**</span><span class="sxs-lookup"><span data-stu-id="d1513-212">**nvarchar(max)**</span></span>|  
|`SQLNVARCHAR`|<span data-ttu-id="d1513-213">Да</span><span class="sxs-lookup"><span data-stu-id="d1513-213">Yes</span></span>|<span data-ttu-id="d1513-214">**nvarchar(max)**</span><span class="sxs-lookup"><span data-stu-id="d1513-214">**nvarchar(max)**</span></span>|  
|`SQLXML`|<span data-ttu-id="d1513-215">Да</span><span class="sxs-lookup"><span data-stu-id="d1513-215">Yes</span></span>|<span data-ttu-id="d1513-216">**Xml**</span><span class="sxs-lookup"><span data-stu-id="d1513-216">**Xml**</span></span>|  
|`SQLUDT`|<span data-ttu-id="d1513-217">Можно использовать</span><span class="sxs-lookup"><span data-stu-id="d1513-217">Either</span></span>|<span data-ttu-id="d1513-218">**Байт**</span><span class="sxs-lookup"><span data-stu-id="d1513-218">**Udt**</span></span>|  
  
## <a name="bcp_gettypename-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="d1513-219">Поддержка функцией bcp_getcolfmt улучшенных возможностей работы с датой и временем</span><span class="sxs-lookup"><span data-stu-id="d1513-219">bcp_gettypename Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="d1513-220">Значения параметров токена для типов даты-времени описаны в столбце "тип в sqlncli. h" таблицы в разделе "изменения при [операции копирования для расширенных типов даты и времени" &#40;OLE DB и ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="d1513-220">The token parameter values for date/time types are described in the "Type in sqlncli.h" column of the table in [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span> <span data-ttu-id="d1513-221">Возвращенное значение находится в соответствующей строке столбца «Тип хранения файла».</span><span class="sxs-lookup"><span data-stu-id="d1513-221">The returned value is in the corresponding row of the "File storage type" column.</span></span>  
  
 <span data-ttu-id="d1513-222">Дополнительные сведения см. в разделе [улучшения даты и времени &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="d1513-222">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1513-223">См. также:</span><span class="sxs-lookup"><span data-stu-id="d1513-223">See Also</span></span>  
 [<span data-ttu-id="d1513-224">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="d1513-224">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
