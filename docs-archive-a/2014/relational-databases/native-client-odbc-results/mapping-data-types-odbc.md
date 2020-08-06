---
title: Сопоставление типов данных (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- mapping data types [ODBC]
- result sets [ODBC], data types
- ODBC data types, mapping
- SQL Server Native Client ODBC driver, result sets
- ODBC applications, result sets
- data types [ODBC], mapping
- sql_variant data type
- SQL Server Native Client ODBC driver, data types
ms.assetid: 4ba0924d-9fca-4c48-aced-0a8d817b3dde
author: rothja
ms.author: jroth
ms.openlocfilehash: 545e738afb6b3283b2ff2f3830921da8ed13202f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750872"
---
# <a name="mapping-data-types-odbc"></a><span data-ttu-id="f6a1d-102">Сопоставление типов данных (ODBC)</span><span class="sxs-lookup"><span data-stu-id="f6a1d-102">Mapping Data Types (ODBC)</span></span>
  <span data-ttu-id="f6a1d-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента сопоставляет [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] типы данных SQL с ТИПАМИ данных ODBC SQL.</span><span class="sxs-lookup"><span data-stu-id="f6a1d-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver maps [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL data types to ODBC SQL data types.</span></span> <span data-ttu-id="f6a1d-104">В последующих разделах обсуждаются типы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL с типами данных ODBC SQL, с которыми они сопоставляются.</span><span class="sxs-lookup"><span data-stu-id="f6a1d-104">The sections below discuss the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL data types and the ODBC SQL data types to which they map.</span></span> <span data-ttu-id="f6a1d-105">В разделах также обсуждаются типы данных ODBC SQL и соответствующие им типы данных ODBC C, а также поддерживаемые преобразования и преобразования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f6a1d-105">They also discuss the ODBC SQL data types and their corresponding ODBC C data types, and the supported and default conversions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f6a1d-106">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Тип данных **timestamp** соответствует SQL_BINARY или SQL_VARBINARY типу данных ODBC, так как значения в столбцах **отметок времени** не являются значениями **DateTime** , а значения **binary (8)** или **varbinary (8)** , которые указывают последовательность [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] действий в строке.</span><span class="sxs-lookup"><span data-stu-id="f6a1d-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**timestamp** data type maps to the SQL_BINARY or SQL_VARBINARY ODBC data type because the values in **timestamp** columns are not **datetime** values, but **binary(8)** or **varbinary(8)** values that indicate the sequence of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] activity on the row.</span></span> <span data-ttu-id="f6a1d-107">Если драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] встречает значение типа SQL_C_WCHAR (Юникод), что означает нечетное число байт, то последний нечетный байт усекается.</span><span class="sxs-lookup"><span data-stu-id="f6a1d-107">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver encounters a SQL_C_WCHAR (Unicode) value that is an odd number of bytes, the trailing odd byte is truncated.</span></span>  
  
## <a name="dealing-with-sql_variant-data-type-in-odbc"></a><span data-ttu-id="f6a1d-108">Работа с типом данных sql_variant в ODBC</span><span class="sxs-lookup"><span data-stu-id="f6a1d-108">Dealing with sql_variant Data Type in ODBC</span></span>  
 <span data-ttu-id="f6a1d-109">Столбец типа данных **sql_variant** может содержать любые типы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , за исключением больших объектов (LOB), таких как **Text**, **ntext**и **Image**.</span><span class="sxs-lookup"><span data-stu-id="f6a1d-109">The **sql_variant** data type column can contain any of the data types in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] except large objects (LOBs), such as **text**, **ntext**, and **image**.</span></span> <span data-ttu-id="f6a1d-110">Например, столбец может содержать значения **smallint** для некоторых строк, значения **float** для других строк и значения **типа char/nchar** в оставшейся части.</span><span class="sxs-lookup"><span data-stu-id="f6a1d-110">For example, the column could contain **smallint** values for some rows, **float** values for other rows, and **char/nchar** values in the remainder.</span></span>  
  
 <span data-ttu-id="f6a1d-111">Тип данных **sql_variant** похож на тип данных **variant** в Microsoft Visual Basic??.</span><span class="sxs-lookup"><span data-stu-id="f6a1d-111">The **sql_variant** data type is similar to the **Variant** data type in Microsoft Visual Basic??.</span></span>  
  
### <a name="retrieving-data-from-the-server"></a><span data-ttu-id="f6a1d-112">Получение данных с сервера</span><span class="sxs-lookup"><span data-stu-id="f6a1d-112">Retrieving Data from the Server</span></span>  
 <span data-ttu-id="f6a1d-113">ODBC не имеет концепции типов Variant, ограничивая использование типа данных **sql_variant** с драйвером ODBC в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6a1d-113">ODBC does not have a concept of variant types, limiting the use of the **sql_variant** data type with an ODBC driver in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f6a1d-114">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , если указана привязка, **sql_variant** тип данных должен быть привязан к одному из документированных типов данных ODBC.</span><span class="sxs-lookup"><span data-stu-id="f6a1d-114">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], if binding is specified, the **sql_variant** data type must be bound to one of the documented ODBC data types.</span></span> <span data-ttu-id="f6a1d-115">**SQL_CA_SS_VARIANT_TYPE**, новый атрибут, относящийся к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйверу ODBC для собственного клиента, возвращает пользователю тип данных экземпляра в столбце **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="f6a1d-115">**SQL_CA_SS_VARIANT_TYPE**, a new attribute specific to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, returns the data type of an instance in the **sql_variant** column to the user.</span></span>  
  
 <span data-ttu-id="f6a1d-116">Если привязка не указана, можно использовать функцию [SQLGetData](../native-client-odbc-api/sqlgetdata.md) для определения типа данных экземпляра в столбце **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="f6a1d-116">If no binding is specified, the [SQLGetData](../native-client-odbc-api/sqlgetdata.md) function can be used to determine the data type of an instance in the **sql_variant** column.</span></span>  
  
 <span data-ttu-id="f6a1d-117">Чтобы получить **sql_variant** данные, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f6a1d-117">To retrieve **sql_variant** data follow these steps.</span></span>  
  
1.  <span data-ttu-id="f6a1d-118">Вызовите **SQLFetch** , чтобы поместить в полученную строку.</span><span class="sxs-lookup"><span data-stu-id="f6a1d-118">Call **SQLFetch** to position to the row retrieved.</span></span>  
  
2.  <span data-ttu-id="f6a1d-119">Вызовите **SQLGetData**, указав SQL_C_BINARY для типа и значение 0 для длины данных.</span><span class="sxs-lookup"><span data-stu-id="f6a1d-119">Call **SQLGetData**, specifying SQL_C_BINARY for the type and 0 for the data length.</span></span> <span data-ttu-id="f6a1d-120">Это приведет к тому, что драйвер прочитает заголовок **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="f6a1d-120">This forces the driver to read the **sql_variant** header.</span></span> <span data-ttu-id="f6a1d-121">Заголовок предоставляет тип данных этого экземпляра в столбце **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="f6a1d-121">The header provides the data type of that instance in the **sql_variant** column.</span></span> <span data-ttu-id="f6a1d-122">**SQLGetData** возвращает размер значения (в байтах).</span><span class="sxs-lookup"><span data-stu-id="f6a1d-122">**SQLGetData** returns the size (in bytes) of the value.</span></span>  
  
3.  <span data-ttu-id="f6a1d-123">Вызовите [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) , указав **SQL_CA_SS_VARIANT_TYPE** в качестве значения атрибута.</span><span class="sxs-lookup"><span data-stu-id="f6a1d-123">Call [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) by specifying **SQL_CA_SS_VARIANT_TYPE** as its attribute value.</span></span> <span data-ttu-id="f6a1d-124">Эта функция возвращает клиенту тип данных C экземпляра в столбце **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="f6a1d-124">This function will return the C data type of the instance in the **sql_variant** column to the client.</span></span>  
  
 <span data-ttu-id="f6a1d-125">Фрагмент кода, демонстрирующий вышеуказанные шаги:</span><span class="sxs-lookup"><span data-stu-id="f6a1d-125">Here is a code segment showing the preceding steps.</span></span>  
  
```  
while ((retcode = SQLFetch (hstmt))==SQL_SUCCESS)  
{  
    if (retcode != SQL_SUCCESS && retcode != SQL_SUCCESS_WITH_INFO)  
    {  
        SQLError (NULL, NULL, hstmt, NULL,   
                    &lNativeError,szError,MAX_DATA,&sReturned);  
        printf_s ("%s\n",szError);  
        goto Exit;  
    }  
    retcode = SQLGetData (hstmt, 1, SQL_C_BINARY,   
                                pBuff,0,&Indicator);//Figure out the length  
    if (retcode != SQL_SUCCESS_WITH_INFO && retcode != SQL_SUCCESS)  
    {  
        SQLError (NULL, NULL, hstmt, NULL, &lNativeError,   
                    szError,MAX_DATA,&sReturned);  
        printf_s ("%s\n",szError);  
        goto Exit;  
    }  
    printf_s ("Byte length : %d ",Indicator); //Print out the byte length  
  
    int iValue = 0;  
    retcode = SQLColAttribute (hstmt, 1, SQL_CA_SS_VARIANT_TYPE, NULL,   
                                        NULL,NULL,&iValue);  //Figure out the type  
    printf_s ("Sub type = %d ",iValue);//Print the type, the return is C_type of the column]  
  
// Set up a new binding or do the SQLGetData on that column with   
// the appropriate type  
}  
```  
  
 <span data-ttu-id="f6a1d-126">Если пользователь создает привязку с помощью [SQLBindCol](../native-client-odbc-api/sqlbindcol.md), драйвер считывает метаданные и данные.</span><span class="sxs-lookup"><span data-stu-id="f6a1d-126">If the user creates the binding using [SQLBindCol](../native-client-odbc-api/sqlbindcol.md), the driver reads the metadata and the data.</span></span> <span data-ttu-id="f6a1d-127">Затем драйвер преобразует данные к соответствующему типу ODBC, указанному в привязке.</span><span class="sxs-lookup"><span data-stu-id="f6a1d-127">The driver then converts the data to the appropriate ODBC type specified in the binding.</span></span>  
  
### <a name="sending-data-to-the-server"></a><span data-ttu-id="f6a1d-128">Отправка данных на сервер</span><span class="sxs-lookup"><span data-stu-id="f6a1d-128">Sending Data to the Server</span></span>  
 <span data-ttu-id="f6a1d-129">**SQL_SS_VARIANT**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для данных, отправляемых в столбец **sql_variant** , используется новый тип данных, ОТНОСЯЩийся к драйверу ODBC для собственного клиента.</span><span class="sxs-lookup"><span data-stu-id="f6a1d-129">**SQL_SS_VARIANT**, a new data type specific to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, is used for data sent to an **sql_variant** column.</span></span> <span data-ttu-id="f6a1d-130">При отправке данных на сервер с помощью параметров (например, вставка в значения TableName (?,?)) используется [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) для указания сведений о параметрах, включая тип C и соответствующий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] тип.</span><span class="sxs-lookup"><span data-stu-id="f6a1d-130">When sending data to the server using parameters (for example, INSERT INTO TableName VALUES (?,?)), [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) is used to specify the parameter information including the C type and the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type.</span></span> <span data-ttu-id="f6a1d-131">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента преобразует тип данных C в один из соответствующих подтипов **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="f6a1d-131">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver will convert the C data type to one of the appropriate **sql_variant** subtypes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6a1d-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="f6a1d-132">See Also</span></span>  
 [<span data-ttu-id="f6a1d-133">Обработка результатов &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="f6a1d-133">Processing Results &#40;ODBC&#41;</span></span>](processing-results-odbc.md)  
  
  
