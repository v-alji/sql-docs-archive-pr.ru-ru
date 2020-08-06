---
title: Сопоставление данных параметров среды CLR | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- SqlBinary data type
- SqlInt16 data type
- SqlMoney data type
- SqlString data type
- SqlSingle data type
- data types [CLR integration]
- SqlInt64 data type
- SqlDateTime data type
- SqlXml data type
- SqlBoolean data type
- SqlDecimal data type
- SqlBytes data type
- mapping data types [CLR integration]
- SqlChars data type
- SqlInt32 data type
ms.assetid: 89b43ee9-b9ad-4281-a4bf-c7c8d116daa2
author: rothja
ms.author: jroth
ms.openlocfilehash: 7025c5180eac793534961af63df9ac701c95c03f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751176"
---
# <a name="mapping-clr-parameter-data"></a><span data-ttu-id="0f812-102">Сопоставление данных о параметрах CLR</span><span class="sxs-lookup"><span data-stu-id="0f812-102">Mapping CLR Parameter Data</span></span>
  <span data-ttu-id="0f812-103">В следующей таблице перечислены [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] типы данных, их эквиваленты в среде CLR для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в `System.Data.SqlTypes` пространстве имен и их собственные эквиваленты в среде CLR в [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0f812-103">The following table lists [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, their equivalents in the common language runtime (CLR) for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the `System.Data.SqlTypes` namespace, and their native CLR equivalents in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="0f812-104">**Тип данных SQL Server**</span><span class="sxs-lookup"><span data-stu-id="0f812-104">**SQL Server data type**</span></span>|<span data-ttu-id="0f812-105">Тип (в System.Data.SqlTypes or Microsoft.SqlServer.Types)</span><span class="sxs-lookup"><span data-stu-id="0f812-105">Type (in System.Data.SqlTypes or Microsoft.SqlServer.Types)</span></span>|<span data-ttu-id="0f812-106">**Тип данных среды CLR (.NET Framework)**</span><span class="sxs-lookup"><span data-stu-id="0f812-106">**CLR data type (.NET Framework)**</span></span>|  
|`bigint`|`SqlInt64`|<span data-ttu-id="0f812-107">**Int64, Nullable\<Int64>**</span><span class="sxs-lookup"><span data-stu-id="0f812-107">**Int64, Nullable\<Int64>**</span></span>|  
|`binary`|`SqlBytes, SqlBinary`|`Byte[]`|  
|`bit`|`SqlBoolean`|<span data-ttu-id="0f812-108">**Логическое значение, допускающее значение null\<Boolean>**</span><span class="sxs-lookup"><span data-stu-id="0f812-108">**Boolean, Nullable\<Boolean>**</span></span>|  
|`char`|<span data-ttu-id="0f812-109">None</span><span class="sxs-lookup"><span data-stu-id="0f812-109">None</span></span>|<span data-ttu-id="0f812-110">None</span><span class="sxs-lookup"><span data-stu-id="0f812-110">None</span></span>|  
|`cursor`|<span data-ttu-id="0f812-111">None</span><span class="sxs-lookup"><span data-stu-id="0f812-111">None</span></span>|<span data-ttu-id="0f812-112">None</span><span class="sxs-lookup"><span data-stu-id="0f812-112">None</span></span>|  
|`date`|`SqlDateTime`|<span data-ttu-id="0f812-113">**DateTime, Nullable\<DateTime>**</span><span class="sxs-lookup"><span data-stu-id="0f812-113">**DateTime, Nullable\<DateTime>**</span></span>|  
|`datetime`|`SqlDateTime`|<span data-ttu-id="0f812-114">**DateTime, Nullable\<DateTime>**</span><span class="sxs-lookup"><span data-stu-id="0f812-114">**DateTime, Nullable\<DateTime>**</span></span>|  
|`datetime2`|<span data-ttu-id="0f812-115">Нет</span><span class="sxs-lookup"><span data-stu-id="0f812-115">None</span></span>|<span data-ttu-id="0f812-116">**DateTime, Nullable\<DateTime>**</span><span class="sxs-lookup"><span data-stu-id="0f812-116">**DateTime, Nullable\<DateTime>**</span></span>|  
|`DATETIMEOFFSET`|`None`|<span data-ttu-id="0f812-117">**DateTimeOffset, Nullable\<DateTimeOffset>**</span><span class="sxs-lookup"><span data-stu-id="0f812-117">**DateTimeOffset, Nullable\<DateTimeOffset>**</span></span>|  
|`decimal`|`SqlDecimal`|<span data-ttu-id="0f812-118">**Decimal, допускающий значения NULL\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="0f812-118">**Decimal, Nullable\<Decimal>**</span></span>|  
|`float`|`SqlDouble`|<span data-ttu-id="0f812-119">**Double, null\<Double>**</span><span class="sxs-lookup"><span data-stu-id="0f812-119">**Double, Nullable\<Double>**</span></span>|  
|`geography`|`SqlGeography`<br /><br /> <span data-ttu-id="0f812-120">`SqlGeography`определяется в Microsoft.SqlServer.Types.dll, который устанавливается вместе с SQL Server и может быть скачан из [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [пакета дополнительных компонентов](https://www.microsoft.com/download/details.aspx?id=53164).</span><span class="sxs-lookup"><span data-stu-id="0f812-120">`SqlGeography` is defined in Microsoft.SqlServer.Types.dll, which is installed with SQL Server and can be downloaded from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][feature pack](https://www.microsoft.com/download/details.aspx?id=53164).</span></span>|<span data-ttu-id="0f812-121">Нет</span><span class="sxs-lookup"><span data-stu-id="0f812-121">None</span></span>|  
|`geometry`|`SqlGeometry`<br /><br /> <span data-ttu-id="0f812-122">`SqlGeometry`определяется в Microsoft.SqlServer.Types.dll, который устанавливается вместе с SQL Server и может быть скачан из [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [пакета дополнительных компонентов](https://www.microsoft.com/download/details.aspx?id=53164).</span><span class="sxs-lookup"><span data-stu-id="0f812-122">`SqlGeometry` is defined in Microsoft.SqlServer.Types.dll, which is installed with SQL Server and can be downloaded from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][feature pack](https://www.microsoft.com/download/details.aspx?id=53164).</span></span>|<span data-ttu-id="0f812-123">Нет</span><span class="sxs-lookup"><span data-stu-id="0f812-123">None</span></span>|  
|`hierarchyid`|`SqlHierarchyId`<br /><br /> <span data-ttu-id="0f812-124">`SqlHierarchyId`определяется в Microsoft.SqlServer.Types.dll, который устанавливается вместе с SQL Server и может быть скачан из [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [пакета дополнительных компонентов](https://www.microsoft.com/download/details.aspx?id=53164).</span><span class="sxs-lookup"><span data-stu-id="0f812-124">`SqlHierarchyId` is defined in Microsoft.SqlServer.Types.dll, which is installed with SQL Server and can be downloaded from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][feature pack](https://www.microsoft.com/download/details.aspx?id=53164).</span></span>|<span data-ttu-id="0f812-125">None</span><span class="sxs-lookup"><span data-stu-id="0f812-125">None</span></span>|  
|`image`|<span data-ttu-id="0f812-126">None</span><span class="sxs-lookup"><span data-stu-id="0f812-126">None</span></span>|<span data-ttu-id="0f812-127">None</span><span class="sxs-lookup"><span data-stu-id="0f812-127">None</span></span>|  
|`int`|`SqlInt32`|<span data-ttu-id="0f812-128">**Int32, Nullable\<Int32>**</span><span class="sxs-lookup"><span data-stu-id="0f812-128">**Int32, Nullable\<Int32>**</span></span>|  
|`money`|`SqlMoney`|<span data-ttu-id="0f812-129">**Decimal, допускающий значения NULL\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="0f812-129">**Decimal, Nullable\<Decimal>**</span></span>|  
|`nchar`|`SqlChars, SqlString`|`String, Char[]`|  
|`ntext`|<span data-ttu-id="0f812-130">None</span><span class="sxs-lookup"><span data-stu-id="0f812-130">None</span></span>|<span data-ttu-id="0f812-131">None</span><span class="sxs-lookup"><span data-stu-id="0f812-131">None</span></span>|  
|`numeric`|`SqlDecimal`|<span data-ttu-id="0f812-132">**Decimal, допускающий значения NULL\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="0f812-132">**Decimal, Nullable\<Decimal>**</span></span>|  
|`nvarchar`|`SqlChars, SqlString`<br /><br /> <span data-ttu-id="0f812-133">`SQLChars` лучше подходит для передачи данных и доступа, тогда как `SQLString` более подходит для выполнения строковых операций.</span><span class="sxs-lookup"><span data-stu-id="0f812-133">`SQLChars` is a better match for data transfer and access, and `SQLString` is a better match for performing String operations.</span></span>|`String, Char[]`|  
|`nvarchar(1), nchar(1)`|`SqlChars, SqlString`|<span data-ttu-id="0f812-134">**Char, String, char [], Nullable\<char>**</span><span class="sxs-lookup"><span data-stu-id="0f812-134">**Char, String, Char[], Nullable\<char>**</span></span>|  
|`real`|<span data-ttu-id="0f812-135">`SqlSingle` (но `SqlSingle` поддерживает больший диапазон значений, чем `real`)</span><span class="sxs-lookup"><span data-stu-id="0f812-135">`SqlSingle` (the range of `SqlSingle`, however, is larger than `real`)</span></span>|<span data-ttu-id="0f812-136">**Single, допускающий значения NULL\<Single>**</span><span class="sxs-lookup"><span data-stu-id="0f812-136">**Single, Nullable\<Single>**</span></span>|  
|`rowversion`|<span data-ttu-id="0f812-137">Нет</span><span class="sxs-lookup"><span data-stu-id="0f812-137">None</span></span>|`Byte[]`|  
|`smallint`|`SqlInt16`|<span data-ttu-id="0f812-138">**Int16, Nullable\<Int16>**</span><span class="sxs-lookup"><span data-stu-id="0f812-138">**Int16, Nullable\<Int16>**</span></span>|  
|`smallmoney`|`SqlMoney`|<span data-ttu-id="0f812-139">**Decimal, допускающий значения NULL\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="0f812-139">**Decimal, Nullable\<Decimal>**</span></span>|  
|`sql_variant`|<span data-ttu-id="0f812-140">None</span><span class="sxs-lookup"><span data-stu-id="0f812-140">None</span></span>|`Object`|  
|`table`|<span data-ttu-id="0f812-141">None</span><span class="sxs-lookup"><span data-stu-id="0f812-141">None</span></span>|<span data-ttu-id="0f812-142">None</span><span class="sxs-lookup"><span data-stu-id="0f812-142">None</span></span>|  
|`text`|<span data-ttu-id="0f812-143">None</span><span class="sxs-lookup"><span data-stu-id="0f812-143">None</span></span>|<span data-ttu-id="0f812-144">None</span><span class="sxs-lookup"><span data-stu-id="0f812-144">None</span></span>|  
|`time`|<span data-ttu-id="0f812-145">None</span><span class="sxs-lookup"><span data-stu-id="0f812-145">None</span></span>|<span data-ttu-id="0f812-146">**TimeSpan, Nullable\<TimeSpan>**</span><span class="sxs-lookup"><span data-stu-id="0f812-146">**TimeSpan, Nullable\<TimeSpan>**</span></span>|  
|`timestamp`|<span data-ttu-id="0f812-147">None</span><span class="sxs-lookup"><span data-stu-id="0f812-147">None</span></span>|<span data-ttu-id="0f812-148">None</span><span class="sxs-lookup"><span data-stu-id="0f812-148">None</span></span>|  
|`tinyint`|`SqlByte`|<span data-ttu-id="0f812-149">**Byte, допускает значение null\<Byte>**</span><span class="sxs-lookup"><span data-stu-id="0f812-149">**Byte, Nullable\<Byte>**</span></span>|  
|`uniqueidentifier`|`SqlGuid`|<span data-ttu-id="0f812-150">**GUID, допускающий значение null\<Guid>**</span><span class="sxs-lookup"><span data-stu-id="0f812-150">**Guid, Nullable\<Guid>**</span></span>|  
|`User-defined type(UDT)`|<span data-ttu-id="0f812-151">Нет</span><span class="sxs-lookup"><span data-stu-id="0f812-151">None</span></span>|<span data-ttu-id="0f812-152">Тот же класс связывается с определяемым пользователем типом данных в той же сборке или в зависимой сборке.</span><span class="sxs-lookup"><span data-stu-id="0f812-152">The same class that is bound to the user-defined type in the same assembly or a dependent assembly.</span></span>|  
|<span data-ttu-id="0f812-153">**varbinary**</span><span class="sxs-lookup"><span data-stu-id="0f812-153">**varbinary**</span></span>|`SqlBytes, SqlBinary`|`Byte[]`|  
|`varbinary(1), binary(1)`|`SqlBytes, SqlBinary`|<span data-ttu-id="0f812-154">**Byte, Byte [], допускающий значения NULL\<byte>**</span><span class="sxs-lookup"><span data-stu-id="0f812-154">**byte, Byte[], Nullable\<byte>**</span></span>|  
|`varchar`|<span data-ttu-id="0f812-155">None</span><span class="sxs-lookup"><span data-stu-id="0f812-155">None</span></span>|<span data-ttu-id="0f812-156">None</span><span class="sxs-lookup"><span data-stu-id="0f812-156">None</span></span>|  
|`xml`|`SqlXml`|<span data-ttu-id="0f812-157">None</span><span class="sxs-lookup"><span data-stu-id="0f812-157">None</span></span>|  
  
## <a name="automatic-data-type-conversion-with-out-parameters"></a><span data-ttu-id="0f812-158">Автоматическое преобразование типов данных для выходных параметров</span><span class="sxs-lookup"><span data-stu-id="0f812-158">Automatic Data Type Conversion with Out Parameters</span></span>  
 <span data-ttu-id="0f812-159">Метод CLR может возвращать данные вызывающему коду или программе, сопровождая входной параметр модификатором `out` (Microsoft Visual C#) или `<Out()> ByRef` (Microsoft Visual Basic). Если входной параметр принадлежит типу данных CLR в пространстве имен `System.Data.SqlTypes`, и вызывающая программа указывает свой соответствующий тип данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] как входной параметр, преобразование типов осуществляется автоматически, когда метод CLR возвращает тип данных.</span><span class="sxs-lookup"><span data-stu-id="0f812-159">A CLR method can return information to the calling code or program by marking an input parameter with the `out` modifier (Microsoft Visual C#) or `<Out()> ByRef` (Microsoft Visual Basic) If the input parameter is a CLR data type in the `System.Data.SqlTypes` namespace, and the calling program specifies its equivalent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type as the input parameter, a type conversion occurs automatically when the CLR method returns the data type.</span></span>  
  
 <span data-ttu-id="0f812-160">Так, следующая хранимая процедура CLR имеет входной параметр с типом данных CLR `SqlInt32`, помеченный модификатором `out` (C#) или `<Out()> ByRef` (Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="0f812-160">For example, the following CLR stored procedure has an input parameter of `SqlInt32` CLR data type that is marked with `out` (C#) or `<Out()> ByRef` (Visual Basic):</span></span>  
  
```csharp  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void PriceSum(out SqlInt32 value)  
{ ... }  
```  
  
```vb  
<Microsoft.SqlServer.Server.SqlProcedure> _  
Public Shared Sub PriceSum( <Out()> ByRef value As SqlInt32)  
...  
End Sub  
```  
  
 <span data-ttu-id="0f812-161">После формирования сборки в базе данных хранимая процедура создается в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] со следующим кодом Transact-SQL, который указывает тип данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]`int` для параметра OUTPUT:</span><span class="sxs-lookup"><span data-stu-id="0f812-161">After the assembly is built and created in the database, the stored procedure is created in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with the following Transact-SQL, which specifies a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type of `int` as an OUTPUT parameter:</span></span>  
  
```  
CREATE PROCEDURE PriceSum (@sum int OUTPUT)  
AS EXTERNAL NAME TestStoredProc.StoredProcedures.PriceSum  
```  
  
 <span data-ttu-id="0f812-162">При вызове хранимой процедуры CLR тип данных `SqlInt32` автоматически преобразуется в тип данных `int` и возвращается вызывающей программе.</span><span class="sxs-lookup"><span data-stu-id="0f812-162">When the CLR stored procedure is called, the `SqlInt32` data type is automatically converted to an `int` data type, and returned to the calling program.</span></span>  
  
 <span data-ttu-id="0f812-163">Однако не все типы данных CLR могут автоматически преобразовываться в эквивалентные им типы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью выходного параметра.</span><span class="sxs-lookup"><span data-stu-id="0f812-163">Not all CLR data types can be automatically converted to their equivalent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types through an out parameter, however.</span></span> <span data-ttu-id="0f812-164">В следующей таблице перечислены эти исключения.</span><span class="sxs-lookup"><span data-stu-id="0f812-164">The following table lists these exceptions.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0f812-165">**Тип данных CLR (SQL Server)**</span><span class="sxs-lookup"><span data-stu-id="0f812-165">**CLR data type (SQL Server)**</span></span>|<span data-ttu-id="0f812-166">**Тип данных SQL Server**</span><span class="sxs-lookup"><span data-stu-id="0f812-166">**SQL Server data type**</span></span>|  
|`Decimal`|<span data-ttu-id="0f812-167">smallmoney</span><span class="sxs-lookup"><span data-stu-id="0f812-167">smallmoney</span></span>|  
|`SqlMoney`|<span data-ttu-id="0f812-168">smallmoney</span><span class="sxs-lookup"><span data-stu-id="0f812-168">smallmoney</span></span>|  
|`Decimal`|<span data-ttu-id="0f812-169">money</span><span class="sxs-lookup"><span data-stu-id="0f812-169">money</span></span>|  
|`DateTime`|<span data-ttu-id="0f812-170">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="0f812-170">smalldatetime</span></span>|  
|`SQLDateTime`|<span data-ttu-id="0f812-171">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="0f812-171">smalldatetime</span></span>|  
  
## <a name="change-history"></a><span data-ttu-id="0f812-172">Журнал изменений</span><span class="sxs-lookup"><span data-stu-id="0f812-172">Change History</span></span>  
  
|<span data-ttu-id="0f812-173">Обновленное содержимое</span><span class="sxs-lookup"><span data-stu-id="0f812-173">Updated content</span></span>|  
|---------------------|  
|<span data-ttu-id="0f812-174">В таблицу сопоставления добавлены типы `SqlGeography`, `SqlGeometry` и `SqlHierarchyId`.</span><span class="sxs-lookup"><span data-stu-id="0f812-174">Added `SqlGeography`, `SqlGeometry`, and `SqlHierarchyId` types to the mapping table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f812-175">См. также:</span><span class="sxs-lookup"><span data-stu-id="0f812-175">See Also</span></span>  
 [<span data-ttu-id="0f812-176">Типы данных SQL Server в платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0f812-176">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
