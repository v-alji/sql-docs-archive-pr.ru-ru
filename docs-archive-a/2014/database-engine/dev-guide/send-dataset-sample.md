---
title: Пример отправки набора данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: d10dacbc-1b0f-4a4b-b53b-83eae2a6d809
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: de50007641dd39dc7aa2bcb16ea8da9fde4cabb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669080"
---
# <a name="send-dataset-sample"></a><span data-ttu-id="ebc24-102">Образец отправки DataSet</span><span class="sxs-lookup"><span data-stu-id="ebc24-102">Send DataSet Sample</span></span>
  <span data-ttu-id="ebc24-103">Образец Send `DataSet` показывает, как с помощью серверной хранимой процедуры, основанной на среде CLR, возвратить клиенту в виде результирующего набора элемент `DataSet` на основе ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="ebc24-103">The Send `DataSet` sample demonstrates how to return an ADO.NET based `DataSet` within a server side common language runtime (CLR)-based stored procedure as a result set to the client.</span></span> <span data-ttu-id="ebc24-104">Данный способ используется, например, когда хранимая процедура заполняет элемент `DataSet` результатами запроса, а затем манипулирует данными, содержащимися в `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="ebc24-104">This is useful, for example, when such a stored procedure fills a `DataSet` using the results of a query, and then manipulates the data that is contained in that `DataSet`.</span></span> <span data-ttu-id="ebc24-105">Также подобный подход используется при создании и заполнении объекта `DataSet` при помощи хранимых процедур. Образец состоит из двух классов: `DataSetUtilities` и `TestSendDataSet`.</span><span class="sxs-lookup"><span data-stu-id="ebc24-105">Alternatively this is useful if the stored procedure creates and populates a `DataSet` from scratch.The sample is composed of two classes, `DataSetUtilities` and `TestSendDataSet`.</span></span> <span data-ttu-id="ebc24-106">Метод `SendDataSet`, принадлежащий к классу `DataSetUtilities`, представляет собой наиболее общий способ передачи содержимого экземпляра `DataSet` клиенту.</span><span class="sxs-lookup"><span data-stu-id="ebc24-106">The method `SendDataSet` on the `DataSetUtilities` class implements a general-purpose way to transmit the contents of a `DataSet` instance to the client.</span></span> <span data-ttu-id="ebc24-107">Метод `DoTest` , определенный в классе `TestSendDataSet` , проверяет работу метода `SendDataSet` . Для этого создается экземпляр `DataSet` , который заполняется данными, поступающими из хранимой процедуры `uspGetTwoBOMTestData` Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="ebc24-107">The `DoTest` method that is defined on the `TestSendDataSet` class verifies that the `SendDataSet` method works by creating a `DataSet` and filling it with data from the `uspGetTwoBOMTestData` Transact-SQL stored procedure.</span></span> <span data-ttu-id="ebc24-108">Процедура `uspGetTwoBOMTestData` дважды запускает процедуру Transact-SQL `uspGetBillOfMaterials` , чтобы выполнить рекурсивный запрос счетов за материалы по двум видам продуктов, указанным в качестве параметров хранимой процедуры `usp_GetTwoBOMTestData` .</span><span class="sxs-lookup"><span data-stu-id="ebc24-108">The `uspGetTwoBOMTestData` runs the Transact-SQL stored procedure `uspGetBillOfMaterials` twice to recursively query for the bill of materials for two products specified as parameters to the `usp_GetTwoBOMTestData` stored procedure.</span></span> <span data-ttu-id="ebc24-109">Обычно после заполнения набора данных данные изменяются до вызова метода `SendDataSet` для доставки их клиенту в виде результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="ebc24-109">Ordinarily, after filling the data set, the data would be modified before invoking `SendDataSet` to deliver the data within the data set as a result set to the client.</span></span> <span data-ttu-id="ebc24-110">В этом образце для простоты данные передаются без обработки.</span><span class="sxs-lookup"><span data-stu-id="ebc24-110">For simplicity, this sample returns the data without modification.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ebc24-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="ebc24-111">Prerequisites</span></span>  
 <span data-ttu-id="ebc24-112">Для создания и запуска этого проекта должно быть установлено следующее программное обеспечение:</span><span class="sxs-lookup"><span data-stu-id="ebc24-112">To create and run this project the following the following software must be installed:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ebc24-113">или [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="ebc24-113">or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span></span> <span data-ttu-id="ebc24-114">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express можно получить бесплатно на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] веб-сайте [с документацией и примерами по](https://www.microsoft.com/sql-server/sql-server-editions-express)Express.</span><span class="sxs-lookup"><span data-stu-id="ebc24-114">You can obtain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express free of charge from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [Web site](https://www.microsoft.com/sql-server/sql-server-editions-express)</span></span>  
  
-   <span data-ttu-id="ebc24-115">База данных AdventureWorks, доступная на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] веб-сайте [разработки](https://go.microsoft.com/fwlink/?linkid=62796).</span><span class="sxs-lookup"><span data-stu-id="ebc24-115">The AdventureWorks database that is available at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer [Web site](https://go.microsoft.com/fwlink/?linkid=62796)</span></span>  
  
-   <span data-ttu-id="ebc24-116">Пакет SDK 2.0 для платформы .NET Framework или более поздняя версия либо среда Microsoft Visual Studio 2005 или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="ebc24-116">.NET Framework SDK 2.0 or later or Microsoft Visual Studio 2005 or later.</span></span> <span data-ttu-id="ebc24-117">Пакет SDK для платформы .NET Framework можно получить бесплатно.</span><span class="sxs-lookup"><span data-stu-id="ebc24-117">You can obtain .NET Framework SDK free of charge.</span></span>  
  
-   <span data-ttu-id="ebc24-118">Кроме того, должны выполняться следующие условия.</span><span class="sxs-lookup"><span data-stu-id="ebc24-118">In addition, the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="ebc24-119">Для используемого экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должна быть включена интеграция со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="ebc24-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using must have CLR integration enabled.</span></span>  
  
-   <span data-ttu-id="ebc24-120">Чтобы включить интеграцию со средой CLR, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ebc24-120">In order to enable CLR integration, perform the following steps:</span></span>  
  
    #### <a name="enabling-clr-integration"></a><span data-ttu-id="ebc24-121">Включение интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="ebc24-121">Enabling CLR Integration</span></span>  
  
    -   <span data-ttu-id="ebc24-122">Выполните следующие команды [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="ebc24-122">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] commands:</span></span>  
  
     `sp_configure 'clr enabled', 1`  
  
     `GO`  
  
     `RECONFIGURE`  
  
     `GO`  
  
    > [!NOTE]  
    >  <span data-ttu-id="ebc24-123">Чтобы включить CLR, необходимо иметь разрешение `ALTER SETTINGS` на уровне сервера, которое неявно предоставляется членам предопределенных ролей сервера `sysadmin` и `serveradmin`.</span><span class="sxs-lookup"><span data-stu-id="ebc24-123">To enable CLR, you must have `ALTER SETTINGS` server level permission, which is implicitly held by members of the `sysadmin` and `serveradmin` fixed server roles.</span></span>  
  
-   <span data-ttu-id="ebc24-124">На используемом экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должна быть установлена база данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ebc24-124">The AdventureWorks database must be installed on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using.</span></span>  
  
-   <span data-ttu-id="ebc24-125">Если вы не являетесь администратором [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] экземпляра, который вы используете, у вас должен быть администратор, который предоставил вам разрешение **CreateAssembly** для завершения установки.</span><span class="sxs-lookup"><span data-stu-id="ebc24-125">If you are not an administrator for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using, you must have an administrator grant you **CreateAssembly**  permission to complete the installation.</span></span>  
  
## <a name="building-the-sample"></a><span data-ttu-id="ebc24-126">Построение образца</span><span class="sxs-lookup"><span data-stu-id="ebc24-126">Building the Sample</span></span>  
  
#### <a name="create-and-run-the-sample-by-using-the-following-instructions"></a><span data-ttu-id="ebc24-127">Создайте и запустите образец в соответствии со следующими инструкциями.</span><span class="sxs-lookup"><span data-stu-id="ebc24-127">Create and run the sample by using the following instructions:</span></span>  
  
1.  <span data-ttu-id="ebc24-128">Откройте командную строку Visual Studio или .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ebc24-128">Open a Visual Studio or .NET Framework command prompt.</span></span>  
  
2.  <span data-ttu-id="ebc24-129">Если необходимо, создайте каталог для своего образца.</span><span class="sxs-lookup"><span data-stu-id="ebc24-129">If necessary, create a directory for your sample.</span></span> <span data-ttu-id="ebc24-130">В данном примере будет использоваться каталог C:\MySample.</span><span class="sxs-lookup"><span data-stu-id="ebc24-130">For this example, we will use C:\MySample.</span></span>  
  
3.  <span data-ttu-id="ebc24-131">В каталоге c:\MySample создайте файл `SendDataSet.vb` (для образца на языке Visual Basic) или `SendDataSet.cs` (для образца на языке C#) и скопируйте в него соответствующий образец кода на языке Visual Basic или C#, приведенный ниже.</span><span class="sxs-lookup"><span data-stu-id="ebc24-131">In c:\MySample, create `SendDataSet.vb` (for the Visual Basic sample) or `SendDataSet.cs` (for the C# sample) and copy the appropriate Visual Basic or C# sample code (below) into the file.</span></span>  
  
4.  <span data-ttu-id="ebc24-132">Скомпилируйте образец кода из командной строки в нужную сборку, выполнив одну из следующих команд, в зависимости от выбранного языка.</span><span class="sxs-lookup"><span data-stu-id="ebc24-132">Compile the sample code into the required assembly from the command line prompt by executing one of the following, depending on your choice of language.</span></span>  
  
    -   `Vbc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll  /target:library SendDataSet.vb`  
  
    -   `Csc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll /target:library SendDataSet.cs`  
  
5.  <span data-ttu-id="ebc24-133">Скопируйте код установки [!INCLUDE[tsql](../../includes/tsql-md.md)] в файл и сохраните его в файле `Install.sql` в том же каталоге.</span><span class="sxs-lookup"><span data-stu-id="ebc24-133">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation code into a file and save it as `Install.sql` in the sample directory.</span></span>  
  
6.  <span data-ttu-id="ebc24-134">Если образец установлен в каталоге, отличном от `C:\MySample\`, внесите изменения в файл `Install.sql` , указав там этот каталог.</span><span class="sxs-lookup"><span data-stu-id="ebc24-134">If the sample is installed in a directory other then `C:\MySample\`, edit the file `Install.sql` as indicated to point to that location.</span></span>  
  
7.  <span data-ttu-id="ebc24-135">Разверните сборку, хранимую процедуру и функции, выполнив</span><span class="sxs-lookup"><span data-stu-id="ebc24-135">Deploy the assembly, stored procedure and functions by executing</span></span>  
  
    -   `sqlcmd -E -I -i install.sql`  
  
8.  <span data-ttu-id="ebc24-136">Скопируйте проверочный скрипт на [!INCLUDE[tsql](../../includes/tsql-md.md)] и сохраните его в файле `test.sql` в том же каталоге.</span><span class="sxs-lookup"><span data-stu-id="ebc24-136">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] test script into a file and save it as `test.sql` in the sample directory.</span></span>  
  
    -   `sqlcmd -E -I -i test.sql`  
  
9. <span data-ttu-id="ebc24-137">Скопируйте скрипт очистки [!INCLUDE[tsql](../../includes/tsql-md.md)] в файл и сохраните его в файле `cleanup.sql` в том же каталоге.</span><span class="sxs-lookup"><span data-stu-id="ebc24-137">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] cleanup script into a file and save it as `cleanup.sql` in the sample directory.</span></span>  
  
10. <span data-ttu-id="ebc24-138">Выполните скрипт следующей командой</span><span class="sxs-lookup"><span data-stu-id="ebc24-138">Execute the script with the  following command</span></span>  
  
    -   `sqlcmd -E -I -i cleanup.sql`  
  
## <a name="sample-code"></a><span data-ttu-id="ebc24-139">Пример кода</span><span class="sxs-lookup"><span data-stu-id="ebc24-139">Sample Code</span></span>  
 <span data-ttu-id="ebc24-140">Ниже приведены листинги кода для данного образца.</span><span class="sxs-lookup"><span data-stu-id="ebc24-140">The following are the code listings for this sample.</span></span>  
  
 <span data-ttu-id="ebc24-141">C#</span><span class="sxs-lookup"><span data-stu-id="ebc24-141">C#</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
  
    public static class DataSetUtilities  
    {  
  
        public static void SendDataSet(DataSet ds)  
        {  
            if (ds == null)  
            {  
                throw new ArgumentException("SendDataSet requires a non-null data set.");  
            }  
            else  
            {  
                foreach (DataTable dt in ds.Tables)  
                {  
                    SendDataTable(dt);  
                }  
            }  
        }  
  
        public static void SendDataTable(DataTable dt)  
        {  
            bool[] coerceToString;  // Do we need to coerce this column to string?  
            SqlMetaData[] metaData = ExtractDataTableColumnMetaData(dt, out coerceToString);  
  
            SqlDataRecord record = new SqlDataRecord(metaData);  
            SqlPipe pipe = SqlContext.Pipe;  
            pipe.SendResultsStart(record);  
            try  
            {  
                foreach (DataRow row in dt.Rows)  
                {  
                    for (int index = 0; index < record.FieldCount; index++)  
                    {  
                        object value = row[index];  
                        if (null != value && coerceToString[index])  
                            value = value.ToString();  
                        record.SetValue(index, value);  
                    }  
  
                    pipe.SendResultsRow(record);  
                }  
            }  
            finally  
            {  
                pipe.SendResultsEnd();  
            }  
        }  
  
        private static SqlMetaData[] ExtractDataTableColumnMetaData(DataTable dt, out bool[] coerceToString)  
        {  
            SqlMetaData[] metaDataResult = new SqlMetaData[dt.Columns.Count];  
            coerceToString = new bool[dt.Columns.Count];  
            for (int index = 0; index < dt.Columns.Count; index++)  
            {  
                DataColumn column = dt.Columns[index];  
                metaDataResult[index] = SqlMetaDataFromColumn(column, out coerceToString[index]);  
            }  
  
            return metaDataResult;  
        }  
  
        private static Exception InvalidDataTypeCode(TypeCode code)  
        {  
            return new ArgumentException("Invalid type: " + code);  
        }  
  
        private static Exception UnknownDataType(Type clrType)  
        {  
            return new ArgumentException("Unknown type: " + clrType);  
        }  
  
        private static SqlMetaData SqlMetaDataFromColumn(DataColumn column, out bool coerceToString)  
        {  
            coerceToString = false;  
            SqlMetaData sql_md = null;  
            Type clrType = column.DataType;  
            string name = column.ColumnName;  
            switch (Type.GetTypeCode(clrType))  
            {  
                case TypeCode.Boolean: sql_md = new SqlMetaData(name, SqlDbType.Bit); break;  
                case TypeCode.Byte: sql_md = new SqlMetaData(name, SqlDbType.TinyInt); break;  
                case TypeCode.Char: sql_md = new SqlMetaData(name, SqlDbType.NVarChar, 1); break;  
                case TypeCode.DateTime: sql_md = new SqlMetaData(name, SqlDbType.DateTime); break;  
                case TypeCode.DBNull: throw InvalidDataTypeCode(TypeCode.DBNull);  
                case TypeCode.Decimal: sql_md = new SqlMetaData(name, SqlDbType.Decimal, 18, 0); break;  
                case TypeCode.Double: sql_md = new SqlMetaData(name, SqlDbType.Float); break;  
                case TypeCode.Empty: throw InvalidDataTypeCode(TypeCode.Empty);  
                case TypeCode.Int16: sql_md = new SqlMetaData(name, SqlDbType.SmallInt); break;  
                case TypeCode.Int32: sql_md = new SqlMetaData(name, SqlDbType.Int); break;  
                case TypeCode.Int64: sql_md = new SqlMetaData(name, SqlDbType.BigInt); break;  
                case TypeCode.SByte: throw InvalidDataTypeCode(TypeCode.SByte);  
                case TypeCode.Single: sql_md = new SqlMetaData(name, SqlDbType.Real); break;  
                case TypeCode.String: sql_md = new SqlMetaData(name, SqlDbType.NVarChar, column.MaxLength);  
                    break;  
                case TypeCode.UInt16: throw InvalidDataTypeCode(TypeCode.UInt16);  
                case TypeCode.UInt32: throw InvalidDataTypeCode(TypeCode.UInt32);  
                case TypeCode.UInt64: throw InvalidDataTypeCode(TypeCode.UInt64);  
                case TypeCode.Object:  
                    sql_md = SqlMetaDataFromObjectColumn(name, column, clrType);  
                    if (sql_md == null)  
                    {  
                        // Unknown type, try to treat it as string;  
                        sql_md = new SqlMetaData(name, SqlDbType.NVarChar, column.MaxLength);  
                        coerceToString = true;  
                    }  
                    break;  
  
                default: throw UnknownDataType(clrType);  
            }  
  
            return sql_md;  
        }  
  
        private static SqlMetaData SqlMetaDataFromObjectColumn(string name, DataColumn column, Type clrType)  
        {  
            SqlMetaData sql_md = null;  
            if (clrType == typeof(System.Byte[]) || clrType == typeof(SqlBinary) || clrType == typeof(SqlBytes) ||  
        clrType == typeof(System.Char[]) || clrType == typeof(SqlString) || clrType == typeof(SqlChars))  
                sql_md = new SqlMetaData(name, SqlDbType.VarBinary, column.MaxLength);  
            else if (clrType == typeof(System.Guid))  
                sql_md = new SqlMetaData(name, SqlDbType.UniqueIdentifier);  
            else if (clrType == typeof(System.Object))  
                sql_md = new SqlMetaData(name, SqlDbType.Variant);  
            else if (clrType == typeof(SqlBoolean))  
                sql_md = new SqlMetaData(name, SqlDbType.Bit);  
            else if (clrType == typeof(SqlByte))  
                sql_md = new SqlMetaData(name, SqlDbType.TinyInt);  
            else if (clrType == typeof(SqlDateTime))  
                sql_md = new SqlMetaData(name, SqlDbType.DateTime);  
            else if (clrType == typeof(SqlDouble))  
                sql_md = new SqlMetaData(name, SqlDbType.Float);  
            else if (clrType == typeof(SqlGuid))  
                sql_md = new SqlMetaData(name, SqlDbType.UniqueIdentifier);  
            else if (clrType == typeof(SqlInt16))  
                sql_md = new SqlMetaData(name, SqlDbType.SmallInt);  
            else if (clrType == typeof(SqlInt32))  
                sql_md = new SqlMetaData(name, SqlDbType.Int);  
            else if (clrType == typeof(SqlInt64))  
                sql_md = new SqlMetaData(name, SqlDbType.BigInt);  
            else if (clrType == typeof(SqlMoney))  
                sql_md = new SqlMetaData(name, SqlDbType.Money);  
            else if (clrType == typeof(SqlDecimal))  
                sql_md = new SqlMetaData(name, SqlDbType.Decimal, SqlDecimal.MaxPrecision, 0);  
            else if (clrType == typeof(SqlSingle))  
                sql_md = new SqlMetaData(name, SqlDbType.Real);  
            else if (clrType == typeof(SqlXml))  
                sql_md = new SqlMetaData(name, SqlDbType.Xml);  
            else  
                sql_md = null;  
  
            return sql_md;  
        }  
  
    }  
 public static class TestSendDataSet  
    {  
        private const string TestConnectionString = "context connection=true";  
        const int prod1ID = 750; //Product ID of Road-150 Red, 44 bicycle  
        const int prod2ID = 751; //Product ID of Road-150 Red, 48 bicycle  
  
        /// <summary>  
        /// Invoke a stored procedure to get some bill of material information and   
        /// fill a data set with the two result sets.  Return the data set to the client.  
        /// </summary>  
        public static void DoTest()  
        {  
            using (SqlConnection conn = new SqlConnection(TestConnectionString))  
            {  
                SqlCommand cmd = conn.CreateCommand();  
                cmd.CommandText = "usp_GetTwoBOMTestData";  
                cmd.CommandType = CommandType.StoredProcedure;  
  
                SqlParameter prod1Param = new SqlParameter("@ProductID1", SqlDbType.Int);  
                prod1Param.Value = prod1ID;  
                cmd.Parameters.Add(prod1Param);  
  
                SqlParameter prod2Param = new SqlParameter("@ProductID2", SqlDbType.Int);  
                prod2Param.Value = prod2ID;  
                cmd.Parameters.Add(prod2Param);  
  
                SqlParameter asOfDateParam = new SqlParameter("@AsOfDate", SqlDbType.DateTime);  
                asOfDateParam.Value = DateTime.Now;  
                cmd.Parameters.Add(asOfDateParam);  
  
                DataSet ds = new DataSet("TestData");  
                SqlDataAdapter sda = new SqlDataAdapter(cmd);  
                conn.Open();  
                sda.Fill(ds);  
  
// Normally, after filling the data set, rather than immediately returning it,   
// the data would be modified before invoking SendDataSet to deliver   
// the data within the data set as a result set to the client.  For simplicity   
// this sample simply returns the data.  
  
                DataSetUtilities.SendDataSet(ds);  
  
            }  
        }  
  
    }  
```  
  
 <span data-ttu-id="ebc24-142">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ebc24-142">Visual Basic</span></span>  
  
```  
Imports Microsoft.VisualBasic  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Diagnostics  
Imports System.Collections.Generic  
Imports System.Text  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Runtime.InteropServices  
  
Public Class DataSetUtilities  
  
    Public Shared Sub SendDataSet(ByVal ds As DataSet)  
        If ds Is Nothing Then  
            Throw New ArgumentException("SendDataSet requires a non-null data set.")  
        Else  
            For Each dt As DataTable In ds.Tables  
                SendDataTable(dt)  
            Next  
        End If  
    End Sub  
  
    Public Shared Sub SendDataTable(ByVal dt As DataTable)  
        Dim coerceToString() As Boolean = Nothing ' Do we need to coerce this column to string?  
        Dim metaData As SqlMetaData() = ExtractDataTableColumnMetaData(dt, coerceToString)  
  
        Dim record As New SqlDataRecord(metaData)  
        Dim pipe As SqlPipe = SqlContext.Pipe  
        pipe.SendResultsStart(record)  
  
        Try  
            For Each row As DataRow In dt.Rows  
                For index As Integer = 0 To record.FieldCount - 1  
                    Dim value As Object = row(index)  
                    If Nothing Is value AndAlso coerceToString(index) Then  
                        value = value.ToString()  
                    End If  
  
                    record.SetValue(index, value)  
                Next  
  
                pipe.SendResultsRow(record)  
            Next  
        Finally  
            pipe.SendResultsEnd()  
        End Try  
    End Sub  
  
    Private Shared Function ExtractDataTableColumnMetaData(ByVal dt As DataTable, <Out()> ByRef coerceToString() As Boolean) As SqlMetaData()  
        Dim metaDataResult(dt.Columns.Count - 1) As SqlMetaData  
        coerceToString = New Boolean(dt.Columns.Count - 1) {}  
        For index As Integer = 0 To dt.Columns.Count - 1  
            Dim column As DataColumn = dt.Columns(index)  
            metaDataResult(index) = SqlMetaDataFromColumn(column, coerceToString(index))  
        Next  
  
        Return metaDataResult  
    End Function  
    Private Shared Function InvalidDataTypeCode(ByVal code As TypeCode) As Exception  
        Return New ArgumentException("Invalid type: " & code.ToString())  
    End Function  
  
    Private Shared Function UnknownDataType(ByVal clrType As Type) As Exception  
        Return New ArgumentException("Unknown type: " & clrType.ToString())  
    End Function  
  
    Private Shared Function SqlMetaDataFromColumn(ByVal column As DataColumn, ByRef coerceToString As Boolean) As SqlMetaData  
        coerceToString = False  
        Dim sql_md As SqlMetaData = Nothing  
        Dim clrType As Type = column.DataType  
        Dim name As String = column.ColumnName  
        Select Case Type.GetTypeCode(clrType)  
            Case TypeCode.Boolean  
                sql_md = New SqlMetaData(name, SqlDbType.Bit)  
            Case TypeCode.Byte  
                sql_md = New SqlMetaData(name, SqlDbType.TinyInt)  
            Case TypeCode.Char  
                sql_md = New SqlMetaData(name, SqlDbType.NVarChar, 1)  
            Case TypeCode.DateTime  
                sql_md = New SqlMetaData(name, SqlDbType.DateTime)  
            Case TypeCode.DBNull  
                Throw InvalidDataTypeCode(TypeCode.DBNull)  
            Case TypeCode.Decimal  
                sql_md = New SqlMetaData(name, SqlDbType.Decimal)  
            Case TypeCode.Double  
                sql_md = New SqlMetaData(name, SqlDbType.Float)  
            Case TypeCode.Empty  
                Throw InvalidDataTypeCode(TypeCode.Empty)  
            Case TypeCode.Int16  
                sql_md = New SqlMetaData(name, SqlDbType.SmallInt)  
            Case TypeCode.Int32  
                sql_md = New SqlMetaData(name, SqlDbType.Int)  
            Case TypeCode.Int64  
                sql_md = New SqlMetaData(name, SqlDbType.BigInt)  
            Case TypeCode.SByte  
                Throw InvalidDataTypeCode(TypeCode.SByte)  
            Case TypeCode.Single  
                sql_md = New SqlMetaData(name, SqlDbType.Real)  
            Case TypeCode.String  
                sql_md = New SqlMetaData(name, SqlDbType.NVarChar, column.MaxLength)  
            Case TypeCode.UInt16  
                Throw InvalidDataTypeCode(TypeCode.UInt16)  
            Case TypeCode.UInt32  
                Throw InvalidDataTypeCode(TypeCode.UInt32)  
            Case TypeCode.UInt64  
                Throw InvalidDataTypeCode(TypeCode.UInt64)  
            Case TypeCode.Object  
                sql_md = SqlMetaDataFromObjectColumn(name, column, clrType)  
                If sql_md Is Nothing Then  
                    ' Unknown type, try to treat it as string  
                    sql_md = New SqlMetaData(name, SqlDbType.NVarChar, column.MaxLength)  
                    coerceToString = True  
                End If  
            Case Else  
                Throw UnknownDataType(clrType)  
        End Select  
  
        Return sql_md  
    End Function  
  
    Private Shared Function SqlMetaDataFromObjectColumn(ByVal name As String, ByVal column As DataColumn, ByVal clrType As Type) As SqlMetaData  
        Dim sql_md As SqlMetaData = Nothing  
  
        If (clrType Is GetType(System.Byte()) OrElse clrType Is GetType(SqlBinary) OrElse clrType Is GetType(SqlBytes) _  
            OrElse clrType Is GetType(System.Char()) OrElse clrType Is GetType(SqlString) OrElse clrType Is GetType(SqlChars)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.VarBinary, column.MaxLength)  
        ElseIf (clrType Is GetType(System.Guid)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.UniqueIdentifier)  
        ElseIf (clrType Is GetType(System.Object)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.Variant)  
        ElseIf (clrType Is GetType(SqlBoolean)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.Bit)  
        ElseIf (clrType Is GetType(SqlByte)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.TinyInt)  
        ElseIf (clrType Is GetType(SqlDateTime)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.DateTime)  
        ElseIf (clrType Is GetType(SqlDouble)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.Float)  
        ElseIf (clrType Is GetType(SqlGuid)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.UniqueIdentifier)  
        ElseIf (clrType Is GetType(SqlInt16)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.SmallInt)  
        ElseIf (clrType Is GetType(SqlInt32)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.Int)  
        ElseIf (clrType Is GetType(SqlInt64)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.BigInt)  
        ElseIf (clrType Is GetType(SqlMoney)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.Money)  
        ElseIf (clrType Is GetType(SqlDecimal)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.Decimal, SqlDecimal.MaxPrecision, 0)  
        ElseIf (clrType Is GetType(SqlSingle)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.Real)  
        ElseIf (clrType Is GetType(SqlXml)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.Xml)  
        Else  
            sql_md = Nothing  
        End If  
  
        Return sql_md  
    End Function  
End Class  
  
Public Class TestSendDataSet  
    Private Const TestConnectionString As String = "context connection=true"  
    Private Const prod1ID As Integer = 750  'Product ID of Road-150 Red, 44 bicycle  
    Private Const prod2ID As Integer = 751  'Product ID of Road-150 Red, 48 bicycle  
  
    ''' <summary>  
    ''' Invoke a stored procedure to get some bill of material information and   
    ''' fill a data set with the two result sets.  Return the data set to the client.  
  
    <SqlProcedure(Name:="usp_TestSendDataSet")> _  
    Public Shared Sub DoTest()  
        Dim conn As New SqlConnection(TestConnectionString)  
        Try  
            Dim cmd As SqlCommand = conn.CreateCommand()  
            cmd.CommandText = "usp_GetTwoBOMTestData"  
            cmd.CommandType = CommandType.StoredProcedure  
  
            Dim prod1Param As New SqlParameter("@ProductID1", SqlDbType.Int)  
            prod1Param.Value = prod1ID  
            cmd.Parameters.Add(prod1Param)  
  
            Dim prod2Param As New SqlParameter("@ProductID2", SqlDbType.Int)  
            prod2Param.Value = prod2ID  
            cmd.Parameters.Add(prod2Param)  
  
            Dim asOfDateParam As New SqlParameter("@AsOfDate", SqlDbType.DateTime)  
            asOfDateParam.Value = DateTime.Now  
            cmd.Parameters.Add(asOfDateParam)  
  
            Dim ds As New DataSet("TestData")  
            Dim sda As New SqlDataAdapter(cmd)  
            conn.Open()  
            sda.Fill(ds)  
  
            ' Normally, after filling the data set, rather than immediately returning it,   
            ' the data would be modified before invoking SendDataSet to deliver   
            ' the data within the data set as a result set to the client.  For simplicity   
            ' this sample simply returns the data.  
            DataSetUtilities.SendDataSet(ds)  
        Finally  
            conn.Dispose()  
        End Try  
    End Sub  
End Class  
  
```  
  
 <span data-ttu-id="ebc24-143">Это установочный скрипт [!INCLUDE[tsql](../../includes/tsql-md.md)] (`Install.sql`), который выполняет развертывание сборки и создает хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="ebc24-143">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation script (`Install.sql`), which deploys the assembly and creates the stored procedures.</span></span>  
  
```  
USE AdventureWorks;  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'usp_GetTwoBOMTestData')  
DROP PROCEDURE usp_GetTwoBOMTestData;  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'usp_TestSendDataSet')  
DROP PROCEDURE usp_TestSendDataSet;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE name = N'SendDataSet')   
DROP ASSEMBLY SendDataSet;  
GO  
  
-- Procedure used to generate test data to fill the data set being returned to the client  
CREATE PROCEDURE usp_GetTwoBOMTestData  
(  
@ProductID1 int,  
@ProductID2 int,  
@AsOfDate DateTime  
)  
AS  
BEGIN  
EXEC uspGetBillOfMaterials @ProductID1, @AsOfDate;  
EXEC uspGetBillOfMaterials @ProductID2, @AsOfDate;  
END;  
GO  
  
DECLARE @SamplesPath nvarchar(1024)  
-- You may need to modify the value of the this variable if you have installed the sample someplace other than the default location.  
Set @SamplesPath = N'C:\MySample\'  
  
CREATE ASSEMBLY SendDataSet from @SamplesPath +'SendDataSet.dll'  
WITH PERMISSION_SET = Safe;  
GO  
  
CREATE PROCEDURE usp_TestSendDataSet  
AS  
EXTERNAL NAME [SendDataSet].[TestSendDataSet].[DoTest];  
GO  
```  
  
 <span data-ttu-id="ebc24-144">Это скрипт проверки [!INCLUDE[tsql](../../includes/tsql-md.md)] (`test.sql`), который проверяет образец.</span><span class="sxs-lookup"><span data-stu-id="ebc24-144">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] test script (`test.sql`), which tests the sample.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
EXEC usp_TestSendDataSet  
GO  
```  
  
 <span data-ttu-id="ebc24-145">В следующем образце [!INCLUDE[tsql](../../includes/tsql-md.md)] сборка и хранимая процедура удаляются из базы данных.</span><span class="sxs-lookup"><span data-stu-id="ebc24-145">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] removes the assembly and stored procedure from the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'usp_GetTwoBOMTestData')  
DROP PROCEDURE usp_GetTwoBOMTestData;  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'usp_TestSendDataSet')  
DROP PROCEDURE usp_TestSendDataSet;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE name = N'SendDataSet')   
DROP ASSEMBLY SendDataSet;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="ebc24-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="ebc24-146">See Also</span></span>  
 [<span data-ttu-id="ebc24-147">Сценарии использования и примеры интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="ebc24-147">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
