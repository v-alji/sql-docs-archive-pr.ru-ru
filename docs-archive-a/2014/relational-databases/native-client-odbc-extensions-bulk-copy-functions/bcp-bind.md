---
title: bcp_bind | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_bind
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_bind function
ms.assetid: 6e335a5c-64b2-4bcf-a88f-35dc9393f329
author: rothja
ms.author: jroth
ms.openlocfilehash: db0a58398bf47bd0bb96bd1ef587d41890ed8461
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730653"
---
# <a name="bcp_bind"></a><span data-ttu-id="c3c58-102">bcp_bind</span><span class="sxs-lookup"><span data-stu-id="c3c58-102">bcp_bind</span></span>
  <span data-ttu-id="c3c58-103">Привязывает данные программной переменной к столбцу таблицы для массового копирования в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3c58-103">Binds data from a program variable to a table column for bulk copy into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3c58-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3c58-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_bind (  
HDBC   
hdbc  
,   
LPCBYTE   
pData  
,  
INT   
cbIndicator  
,  
DBINT   
cbData  
,  
LPCBYTE   
pTerm  
,  
INT   
cbTerm  
,  
INT   
eDataType  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="c3c58-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c3c58-105">Arguments</span></span>  
 <span data-ttu-id="c3c58-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="c3c58-106">*hdbc*</span></span>  
 <span data-ttu-id="c3c58-107">Дескриптор соединения ODBC с поддержкой массового копирования.</span><span class="sxs-lookup"><span data-stu-id="c3c58-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="c3c58-108">*pData*</span><span class="sxs-lookup"><span data-stu-id="c3c58-108">*pData*</span></span>  
 <span data-ttu-id="c3c58-109">Указатель на копируемые данные.</span><span class="sxs-lookup"><span data-stu-id="c3c58-109">Is a pointer to the data copied.</span></span> <span data-ttu-id="c3c58-110">Если *eDataType* имеет значение SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SqlBinary, SQLNCHAR или SQLIMAGE, *pData* может быть равен null.</span><span class="sxs-lookup"><span data-stu-id="c3c58-110">If *eDataType* is SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, SQLNCHAR or SQLIMAGE, *pData* can be NULL.</span></span> <span data-ttu-id="c3c58-111">ЗНАЧЕНИЕ типа *pData* , указывающее, что значения длинных данных будут отправляться [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в блоках с помощью [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="c3c58-111">A NULL *pData* indicates that long data values will be sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in chunks using [bcp_moretext](bcp-moretext.md).</span></span> <span data-ttu-id="c3c58-112">Пользователь должен задать для *pData* значение null, если столбец, соответствующий привязанному к пользователю полю, является столбцом большого двоичного объекта, иначе **bcp_bind** завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c3c58-112">The user should only set *pData* to NULL if the column corresponding to the user bound field is a BLOB column otherwise **bcp_bind** will fail.</span></span>  
  
 <span data-ttu-id="c3c58-113">Если в данных присутствуют признаки, они размещаются в памяти непосредственно перед данными.</span><span class="sxs-lookup"><span data-stu-id="c3c58-113">If indicators are present in the data, they appear in memory directly before the data.</span></span> <span data-ttu-id="c3c58-114">Параметр *pData* указывает на переменную индикатора в этом случае, а ширина индикатора, параметр *кбиндикатор* , используется массовым копированием для правильного адресации данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="c3c58-114">The *pData* parameter points to the indicator variable in this case, and the width of the indicator, the *cbIndicator* parameter, is used by bulk copy to address user data correctly.</span></span>  
  
 <span data-ttu-id="c3c58-115">*cbIndicator*</span><span class="sxs-lookup"><span data-stu-id="c3c58-115">*cbIndicator*</span></span>  
 <span data-ttu-id="c3c58-116">Ширина индикатора в байтах или значение NULL для данных столбца.</span><span class="sxs-lookup"><span data-stu-id="c3c58-116">Is the length, in bytes, of a length or null indicator for the column's data.</span></span> <span data-ttu-id="c3c58-117">Допускаются следующие значения длины признака: 0 (если признак не используется), 1, 2, 4 или 8.</span><span class="sxs-lookup"><span data-stu-id="c3c58-117">Valid indicator length values are 0 (when using no indicator), 1, 2, 4, or 8.</span></span> <span data-ttu-id="c3c58-118">Признаки размещаются в памяти непосредственно перед данными.</span><span class="sxs-lookup"><span data-stu-id="c3c58-118">Indicators appear in memory directly before any data.</span></span> <span data-ttu-id="c3c58-119">Например, следующее определение типа структуры можно использовать для вставки целочисленных значений в таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью массового копирования:</span><span class="sxs-lookup"><span data-stu-id="c3c58-119">For example, the following structure type definition could be used to insert integer values into an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table using bulk copy:</span></span>  
  
```  
typedef struct tagBCPBOUNDINT  
    {  
    int iIndicator;  
    int Value;  
    } BCPBOUNDINT;  
```  
  
 <span data-ttu-id="c3c58-120">В этом примере параметру *pData* присваивается адрес объявленного экземпляра структуры, адрес члена структуры *iIndicator* iIndicator.</span><span class="sxs-lookup"><span data-stu-id="c3c58-120">In the example case, the *pData* parameter would be set to the address of a declared instance of the structure, the address of the BCPBOUNDINT *iIndicator* structure member.</span></span> <span data-ttu-id="c3c58-121">Для параметра *кбиндикатор* будет задан размер целого числа (sizeof (int)), а для параметра *cbData* снова будет задан размер целого числа (sizeof (int)).</span><span class="sxs-lookup"><span data-stu-id="c3c58-121">The *cbIndicator* parameter would be set to the size of an integer (sizeof(int)), and the *cbData* parameter would again be set to the size of an integer (sizeof(int)).</span></span> <span data-ttu-id="c3c58-122">Чтобы выполнить операцию с массовым копированием строки на сервер, содержащий значение NULL для привязанного столбца, значение элемента *iIndicator* экземпляра должно быть установлено в SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="c3c58-122">To bulk copy a row to the server containing a NULL value for the bound column, the value of the instance's *iIndicator* member should be set to SQL_NULL_DATA.</span></span>  
  
 <span data-ttu-id="c3c58-123">*cbData*</span><span class="sxs-lookup"><span data-stu-id="c3c58-123">*cbData*</span></span>  
 <span data-ttu-id="c3c58-124">Количество байт данных в программной переменной, исключая любую длину, NULL-индикатор или признак конца.</span><span class="sxs-lookup"><span data-stu-id="c3c58-124">Is the count of bytes of data in the program variable, not including the length of any length or null indicator or terminator.</span></span>  
  
 <span data-ttu-id="c3c58-125">Установка параметра *cbData* в значение SQL_NULL_DATA означает, что все строки, скопированные на сервер, содержат значение NULL для столбца.</span><span class="sxs-lookup"><span data-stu-id="c3c58-125">Setting *cbData* to SQL_NULL_DATA signifies that all rows copied to the server contain a NULL value for the column.</span></span>  
  
 <span data-ttu-id="c3c58-126">Установка параметра *cbData* в значение SQL_VARLEN_DATA указывает, что система будет использовать признак конца строки или другой метод, чтобы определить длину копируемых данных.</span><span class="sxs-lookup"><span data-stu-id="c3c58-126">Setting *cbData* to SQL_VARLEN_DATA indicates that the system will use a string terminator, or other method, to determine the length of data copied.</span></span>  
  
 <span data-ttu-id="c3c58-127">Для типов данных фиксированной длины, например для целых чисел, система определяет длину данных на основе типа.</span><span class="sxs-lookup"><span data-stu-id="c3c58-127">For fixed-length data types, such as integers, the data type indicates the length of the data to the system.</span></span> <span data-ttu-id="c3c58-128">Таким образом, для типов данных фиксированной длины *cbData* можно безопасно SQL_VARLEN_DATA или длину данных.</span><span class="sxs-lookup"><span data-stu-id="c3c58-128">Therefore, for fixed-length data types, *cbData* can safely be SQL_VARLEN_DATA or the length of the data.</span></span>  
  
 <span data-ttu-id="c3c58-129">Для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] символьных и двоичных типов данных *cbData* может быть SQL_VARLEN_DATA, SQL_NULL_DATA, положительное значение или 0.</span><span class="sxs-lookup"><span data-stu-id="c3c58-129">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character and binary data types, *cbData* can be SQL_VARLEN_DATA, SQL_NULL_DATA, some positive value, or 0.</span></span> <span data-ttu-id="c3c58-130">Если *cbData* имеет SQL_VARLEN_DATA, система использует либо индикатор длины, либо значение null (если присутствует), либо последовательность признаков конца для определения длины данных.</span><span class="sxs-lookup"><span data-stu-id="c3c58-130">If *cbData* is SQL_VARLEN_DATA, the system uses either a length/null indicator (if present) or a terminator sequence to determine the length of the data.</span></span> <span data-ttu-id="c3c58-131">Если представлено и то, и другое, система использует то значение, которое приводит к наименьшему объему копируемых данных.</span><span class="sxs-lookup"><span data-stu-id="c3c58-131">If both are supplied, the system uses the one that results in the least amount of data being copied.</span></span> <span data-ttu-id="c3c58-132">Если *cbData* имеет SQL_VARLEN_DATA, то типом данных столбца является [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] символьный или двоичный тип, и не указан ни индикатор длины, ни последовательность признака конца, система возвращает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c3c58-132">If *cbData* is SQL_VARLEN_DATA, the data type of the column is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character or binary type, and neither a length indicator nor a terminator sequence is specified, the system returns an error message.</span></span>  
  
 <span data-ttu-id="c3c58-133">Если значение *cbData* равно 0 или положительному значению, система использует *cbData* в качестве длины данных.</span><span class="sxs-lookup"><span data-stu-id="c3c58-133">If *cbData* is 0 or a positive value, the system uses *cbData* as the data length.</span></span> <span data-ttu-id="c3c58-134">Однако если в дополнение к положительному значению *cbData* предоставляется индикатор длины или последовательность признака конца, система определяет длину данных с помощью метода, который приводит к наименьшему объему копируемых данных.</span><span class="sxs-lookup"><span data-stu-id="c3c58-134">However, if, in addition to a positive *cbData* value, a length indicator or terminator sequence is provided, the system determines the data length by using the method that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="c3c58-135">Значение параметра *cbData* представляет число байтов данных.</span><span class="sxs-lookup"><span data-stu-id="c3c58-135">The *cbData* parameter value represents the count of bytes of data.</span></span> <span data-ttu-id="c3c58-136">Если символьные данные представлены расширенными символами Юникода, то положительное значение параметра *cbData* представляет собой число символов, умноженное на размер в байтах каждого символа.</span><span class="sxs-lookup"><span data-stu-id="c3c58-136">If character data is represented by Unicode wide characters, then a positive *cbData* parameter value represents the number of characters multiplied by the size in bytes of each character.</span></span>  
  
 <span data-ttu-id="c3c58-137">*pTerm*</span><span class="sxs-lookup"><span data-stu-id="c3c58-137">*pTerm*</span></span>  
 <span data-ttu-id="c3c58-138">Указатель на байтовый шаблон, если таковой имеется, являющийся признаком конца программной переменной.</span><span class="sxs-lookup"><span data-stu-id="c3c58-138">Is a pointer to the byte pattern, if any, that marks the end of this program variable.</span></span> <span data-ttu-id="c3c58-139">Например, строки ANSI и MBCS C обычно имеют 1-байтовый признаки конца строки (\0).</span><span class="sxs-lookup"><span data-stu-id="c3c58-139">For example, ANSI and MBCS C strings usually have a 1-byte terminator (\0).</span></span>  
  
 <span data-ttu-id="c3c58-140">Если для переменной нет терминатора, задайте для *птерм* значение null.</span><span class="sxs-lookup"><span data-stu-id="c3c58-140">If there is no terminator for the variable, set *pTerm* to NULL.</span></span>  
  
 <span data-ttu-id="c3c58-141">Для обозначения символа конца строки в качестве признака конца программной переменной в языке C можно использовать пустую строку ("").</span><span class="sxs-lookup"><span data-stu-id="c3c58-141">You can use an empty string ("") to designate the C null terminator as the program-variable terminator.</span></span> <span data-ttu-id="c3c58-142">Поскольку пустая строка, заканчивающаяся нулем, образует один байт (сам байт признака конца), установите для *кбтерм* значение 1.</span><span class="sxs-lookup"><span data-stu-id="c3c58-142">Because the null-terminated empty string constitutes a single byte (the terminator byte itself), set *cbTerm* to 1.</span></span> <span data-ttu-id="c3c58-143">Например, чтобы указать, что строка в параметре *szName* завершается нулем, и что для обозначения длины следует использовать признак конца:</span><span class="sxs-lookup"><span data-stu-id="c3c58-143">For example, to indicate that the string in *szName* is null-terminated and that the terminator should be used to indicate the length:</span></span>  
  
```  
bcp_bind(hdbc, szName, 0,  
   SQL_VARLEN_DATA, "", 1,  
   SQLCHARACTER, 2)  
```  
  
 <span data-ttu-id="c3c58-144">Незавершенная форма этого примера может означать, что 15 символов будут скопированы из переменной *szName* во второй столбец связанной таблицы:</span><span class="sxs-lookup"><span data-stu-id="c3c58-144">A nonterminated form of this example could indicate that 15 characters be copied from the *szName* variable to the second column of the bound table:</span></span>  
  
```  
bcp_bind(hdbc, szName, 0, 15,   
   NULL, 0, SQLCHARACTER, 2)  
```  
  
 <span data-ttu-id="c3c58-145">При необходимости API-интерфейс массового копирования выполнит преобразование символов из Юникода в многобайтовую кодировку (MBCS).</span><span class="sxs-lookup"><span data-stu-id="c3c58-145">The bulk copy API performs Unicode-to-MBCS character conversion as required.</span></span> <span data-ttu-id="c3c58-146">Убедитесь, что правильно задана строка байтов признака конца и количество байт в строке.</span><span class="sxs-lookup"><span data-stu-id="c3c58-146">Make sure that both the terminator byte string and the length of the byte string are set correctly.</span></span> <span data-ttu-id="c3c58-147">Например, чтобы указать, что строка в параметре *szName* является строкой расширенных символов Юникода, заканчивающейся значением конца Юникода NULL:</span><span class="sxs-lookup"><span data-stu-id="c3c58-147">For example, to indicate that the string in *szName* is a Unicode wide character string, terminated by the Unicode null terminator value:</span></span>  
  
```  
bcp_bind(hdbc, szName, 0,   
   SQL_VARLEN_DATA, L"",  
   sizeof(WCHAR), SQLNCHAR, 2)  
```  
  
 <span data-ttu-id="c3c58-148">Если привязанный [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] столбец является расширенным символом, преобразование в [bcp_sendrow](bcp-sendrow.md)не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c3c58-148">If the bound [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column is wide character, no conversion is performed on [bcp_sendrow](bcp-sendrow.md).</span></span> <span data-ttu-id="c3c58-149">Если столбец [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имеет символьный тип в кодировке MBCS, при передаче данных в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняется преобразование расширенных символов в несколько символов.</span><span class="sxs-lookup"><span data-stu-id="c3c58-149">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column is an MBCS character type, wide character to multibyte character conversion is performed as the data is sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c3c58-150">*cbTerm*</span><span class="sxs-lookup"><span data-stu-id="c3c58-150">*cbTerm*</span></span>  
 <span data-ttu-id="c3c58-151">Количество байт в признаке конца программной переменной, если такой имеется.</span><span class="sxs-lookup"><span data-stu-id="c3c58-151">Is the count of bytes present in the terminator for the program variable, if any.</span></span> <span data-ttu-id="c3c58-152">Если для переменной нет терминатора, задайте для *кбтерм* значение 0.</span><span class="sxs-lookup"><span data-stu-id="c3c58-152">If there is no terminator for the variable, set *cbTerm* to 0.</span></span>  
  
 <span data-ttu-id="c3c58-153">*eDataType*</span><span class="sxs-lookup"><span data-stu-id="c3c58-153">*eDataType*</span></span>  
 <span data-ttu-id="c3c58-154">Тип данных языка C для программной переменной.</span><span class="sxs-lookup"><span data-stu-id="c3c58-154">Is the C data type of the program variable.</span></span> <span data-ttu-id="c3c58-155">Данные в программной переменной преобразуются в тип столбца базы данных.</span><span class="sxs-lookup"><span data-stu-id="c3c58-155">The data in the program variable is converted to the type of the database column.</span></span> <span data-ttu-id="c3c58-156">Если этот параметр равен 0, преобразование не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c3c58-156">If this parameter is 0, no conversion is performed.</span></span>  
  
 <span data-ttu-id="c3c58-157">Параметр *eDataType* перечисляется [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] маркерами типа данных в sqlncli. h, а не в перечислителях типа данных ODBC C.</span><span class="sxs-lookup"><span data-stu-id="c3c58-157">The *eDataType* parameter is enumerated by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type tokens in sqlncli.h, not the ODBC C data type enumerators.</span></span> <span data-ttu-id="c3c58-158">Например, можно задать целое двухбайтовое значение ODBC типа SQL_C_SHORT с помощью типа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQLINT2.</span><span class="sxs-lookup"><span data-stu-id="c3c58-158">For example, you can specify a two-byte integer, ODBC type SQL_C_SHORT, using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific type SQLINT2.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]<span data-ttu-id="c3c58-159">Добавлена поддержка токенов типа данных SQLXML и SQLUDT в параметре *`eDataType`* .</span><span class="sxs-lookup"><span data-stu-id="c3c58-159">introduced support for SQLXML and SQLUDT data type tokens in the *`eDataType`* paramenter.</span></span>  
  
 <span data-ttu-id="c3c58-160">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="c3c58-160">*idxServerCol*</span></span>  
 <span data-ttu-id="c3c58-161">Порядковый номер столбца в таблице базы данных, в которую копируются данные.</span><span class="sxs-lookup"><span data-stu-id="c3c58-161">Is the ordinal position of the column in the database table to which the data is copied.</span></span> <span data-ttu-id="c3c58-162">Первый столбец в таблице имеет порядковый номер 1.</span><span class="sxs-lookup"><span data-stu-id="c3c58-162">The first column in a table is column 1.</span></span> <span data-ttu-id="c3c58-163">Порядковый номер столбца возвращается функцией [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="c3c58-163">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="returns"></a><span data-ttu-id="c3c58-164">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c3c58-164">Returns</span></span>  
 <span data-ttu-id="c3c58-165">SUCCEED или FAIL.</span><span class="sxs-lookup"><span data-stu-id="c3c58-165">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3c58-166">Remarks</span><span class="sxs-lookup"><span data-stu-id="c3c58-166">Remarks</span></span>  
 <span data-ttu-id="c3c58-167">Используйте **bcp_bind** для быстрого и эффективного способа копирования данных из программной переменной в таблицу в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c3c58-167">Use **bcp_bind** for a fast, efficient way to copy data from a program variable into a table in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c3c58-168">Вызовите [bcp_init](bcp-init.md) перед вызовом этой или любой другой функции небольшого копирования.</span><span class="sxs-lookup"><span data-stu-id="c3c58-168">Call [bcp_init](bcp-init.md) before calling this or any other bulk-copy function.</span></span> <span data-ttu-id="c3c58-169">Вызов **bcp_init** задает [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] целевую таблицу для выполнения операции с массовым копированием.</span><span class="sxs-lookup"><span data-stu-id="c3c58-169">Calling **bcp_init** sets the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] target table for bulk copy.</span></span> <span data-ttu-id="c3c58-170">При вызове **bcp_init** для использования с **bcp_bind** и [bcp_sendrow](bcp-sendrow.md)параметр **bcp_init** _сздатафиле_ , указывающий файл данных, устанавливается в значение null. параметр **bcp_init**_eDirection_ имеет значение DB_IN.</span><span class="sxs-lookup"><span data-stu-id="c3c58-170">When calling **bcp_init** for use with **bcp_bind** and [bcp_sendrow](bcp-sendrow.md), the **bcp_init** _szDataFile_ parameter, indicating the data file, is set to NULL; the **bcp_init**_eDirection_ parameter is set to DB_IN.</span></span>  
  
 <span data-ttu-id="c3c58-171">Создайте отдельный **bcp_bind** вызов для каждого столбца в таблице, в которую необходимо выполнить [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] копирование.</span><span class="sxs-lookup"><span data-stu-id="c3c58-171">Make a separate **bcp_bind** call for every column in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table into which you want to copy.</span></span> <span data-ttu-id="c3c58-172">После выполнения необходимых **bcp_bind** вызовов вызовите **bcp_sendrow** , чтобы отправить строку данных из переменных программы в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c3c58-172">After the necessary **bcp_bind** calls have been made, then call **bcp_sendrow** to send a row of data from your program variables to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c3c58-173">Повторная привязка столбца не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c3c58-173">Rebinding a column is not supported.</span></span>  
  
 <span data-ttu-id="c3c58-174">Когда нужно [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] зафиксировать уже полученные строки, вызовите [bcp_batch](bcp-batch.md).</span><span class="sxs-lookup"><span data-stu-id="c3c58-174">Whenever you want [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to commit the rows already received, call [bcp_batch](bcp-batch.md).</span></span> <span data-ttu-id="c3c58-175">Например, вызовите **bcp_batch** один раз для каждых 1000 строк или в любой другой интервал.</span><span class="sxs-lookup"><span data-stu-id="c3c58-175">For example, call **bcp_batch** once for every 1000 rows inserted or at any other interval.</span></span>  
  
 <span data-ttu-id="c3c58-176">Если строки для вставки не найдены, вызовите [bcp_done](bcp-done.md).</span><span class="sxs-lookup"><span data-stu-id="c3c58-176">When there are no more rows to be inserted, call [bcp_done](bcp-done.md).</span></span> <span data-ttu-id="c3c58-177">Несоблюдение этого правила приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="c3c58-177">Failure to do so results in an error.</span></span>  
  
 <span data-ttu-id="c3c58-178">Параметры управления, указанные в параметре [bcp_control](bcp-control.md), не влияют на передачу **bcp_bind** строк.</span><span class="sxs-lookup"><span data-stu-id="c3c58-178">Control parameter settings, specified with [bcp_control](bcp-control.md), have no effect on **bcp_bind** row transfers.</span></span>  
  
 <span data-ttu-id="c3c58-179">Если *pData* для столбца имеет значение null, так как оно будет предоставлено вызовами [bcp_moretext](bcp-moretext.md), все последующие столбцы с *eDataType* , для которых заданы значения SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SqlBinary, SQLNCHAR или SQLIMAGE, также должны быть связаны с параметром *pData* , имеющим значение null, и их значения также должны быть предоставлены вызовами `bcp_moretext` .</span><span class="sxs-lookup"><span data-stu-id="c3c58-179">If *pData* for a column is set to NULL because its value will be supplied by calls to [bcp_moretext](bcp-moretext.md), any subsequent columns with *eDataType* set to SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, SQLNCHAR, or SQLIMAGE must also be bound with *pData* set to NULL, and their values must also be supplied by calls to `bcp_moretext`.</span></span>  
  
 <span data-ttu-id="c3c58-180">Для новых типов больших значений, таких как `varchar(max)` , `varbinary(max)` или `nvarchar(max)` , можно использовать SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SqlBinary и SQLNCHAR в качестве индикаторов типов в параметре *eDataType* .</span><span class="sxs-lookup"><span data-stu-id="c3c58-180">For new large value types, such as `varchar(max)`, `varbinary(max)`, or `nvarchar(max)`, you can use SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, and SQLNCHAR as type indicators in the *eDataType* parameter.</span></span>  
  
 <span data-ttu-id="c3c58-181">Если *кбтерм* не равен 0, то любое значение (1, 2, 4 или 8) допустимо для префикса (*кбиндикатор*).</span><span class="sxs-lookup"><span data-stu-id="c3c58-181">If *cbTerm* is not 0, any value (1, 2, 4, or 8) is valid for the prefix (*cbIndicator*).</span></span> <span data-ttu-id="c3c58-182">В этой ситуации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственный клиент выполняет поиск терминатора, вычисляет длину данных относительно терминатора (*i*) и устанавливает для *cbData* меньшее значение i и значение prefix.</span><span class="sxs-lookup"><span data-stu-id="c3c58-182">In this situation, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client will search for the terminator, calculate data length with respect to the terminator (*i*), and set the *cbData* to the smaller value of i and the value of prefix.</span></span>  
  
 <span data-ttu-id="c3c58-183">Если *кбтерм* имеет значение 0 и *кбиндикатор* (префикс) не равно 0, *кбиндикатор* должен быть равен 8.</span><span class="sxs-lookup"><span data-stu-id="c3c58-183">If *cbTerm* is 0 and *cbIndicator* (the prefix) is not 0, *cbIndicator* must be 8.</span></span> <span data-ttu-id="c3c58-184">Восьмибайтовый префикс может принимать следующие значения.</span><span class="sxs-lookup"><span data-stu-id="c3c58-184">The 8 byte prefix can take the following values:</span></span>  
  
-   <span data-ttu-id="c3c58-185">0xFFFFFFFFFFFFFFFF означает значение NULL для поля.</span><span class="sxs-lookup"><span data-stu-id="c3c58-185">0xFFFFFFFFFFFFFFFF means a null value for the field</span></span>  
  
-   <span data-ttu-id="c3c58-186">0xFFFFFFFFFFFFFFFE рассматривается как специальное значение префикса, которое используется для эффективной отправки на сервер данных, разбитых на фрагменты.</span><span class="sxs-lookup"><span data-stu-id="c3c58-186">0xFFFFFFFFFFFFFFFE is treated as a special prefix value which is used for efficiently sending data in chunks to the server.</span></span> <span data-ttu-id="c3c58-187">Данные со специальным префиксом имеют следующий формат.</span><span class="sxs-lookup"><span data-stu-id="c3c58-187">The format of data with this special prefix is:</span></span>  
  
-   <span data-ttu-id="c3c58-188"><SPECIAL_PREFIX> \<0 or more  DATA CHUNKS> <ZERO_CHUNK>, где:</span><span class="sxs-lookup"><span data-stu-id="c3c58-188"><SPECIAL_PREFIX> \<0 or more  DATA CHUNKS> <ZERO_CHUNK> where:</span></span>  
  
-   <span data-ttu-id="c3c58-189">СПЕЦИАЛЬНЫЙ_ПРЕФИКС имеет значение 0xFFFFFFFFFFFFFFFE.</span><span class="sxs-lookup"><span data-stu-id="c3c58-189">SPECIAL_PREFIX is 0xFFFFFFFFFFFFFFFE</span></span>  
  
-   <span data-ttu-id="c3c58-190">ФРАГМЕНТ_ДАННЫХ является 4-байтовым префиксом, содержащим длину фрагмента, за которым следуют фактические данные, длина которых задана 4-байтовым префиксом.</span><span class="sxs-lookup"><span data-stu-id="c3c58-190">DATA_CHUNK is a 4 byte prefix containing length of the chunk,followed by the actual data whose length is specified in the 4 byte prefix.</span></span>  
  
-   <span data-ttu-id="c3c58-191">НУЛЕВОЙ_ФРАГМЕНТ является 4-байтовым значением, содержащим все нули (00000000), которое указывает конец данных.</span><span class="sxs-lookup"><span data-stu-id="c3c58-191">ZERO_CHUNK is a 4 byte value containing all zeros (00000000) indicating the end of data.</span></span>  
  
-   <span data-ttu-id="c3c58-192">Любая другая 8-байтовая длина рассматривается как длина обычных данных.</span><span class="sxs-lookup"><span data-stu-id="c3c58-192">Any other valid 8 byte length is treated as a regular data length.</span></span>  
  
 <span data-ttu-id="c3c58-193">Вызов [bcp_columns](bcp-columns.md) при использовании **bcp_bind** приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="c3c58-193">Calling [bcp_columns](bcp-columns.md) when using **bcp_bind** results in an error.</span></span>  
  
## <a name="bcp_bind-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="c3c58-194">Поддержка функцией bcp_bind улучшенных возможностей даты и времени</span><span class="sxs-lookup"><span data-stu-id="c3c58-194">bcp_bind Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="c3c58-195">Дополнительные сведения о типах, используемых с параметром *eDataType* для типов даты и времени, см. в разделе " [изменения в ходе операции копирования для расширенных типов даты и времени &#40;OLE DB и ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="c3c58-195">For information about the types used with the *eDataType* parameter for date/time types, see [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="c3c58-196">Дополнительные сведения см. в разделе [улучшения даты и времени &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="c3c58-196">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3c58-197">Пример</span><span class="sxs-lookup"><span data-stu-id="c3c58-197">Example</span></span>  
  
```  
#include sql.h  
#include sqlext.h  
#include odbcss.h  
// Variables like henv not specified.  
HDBC      hdbc;  
char         szCompanyName[MAXNAME];  
DBINT      idCompany;  
DBINT      nRowsProcessed;  
DBBOOL      bMoreData;  
char*      pTerm = "\t\t";  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source; return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bcp.   
if (bcp_init(hdbc, "comdb..accounts_info", NULL, NULL  
   DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Bind program variables to table columns.   
if (bcp_bind(hdbc, (LPCBYTE) &idCompany, 0, sizeof(DBINT), NULL, 0,  
   SQLINT4, 1)    == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
if (bcp_bind(hdbc, (LPCBYTE) szCompanyName, 0, SQL_VARLEN_DATA,  
   (LPCBYTE) pTerm, strnlen(pTerm, sizeof(pTerm)), SQLCHARACTER, 2) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
while (TRUE)  
   {  
   // Retrieve and process program data.   
   if ((bMoreData = getdata(&idCompany, szCompanyName)) == TRUE)  
      {  
      // Send the data.   
      if (bcp_sendrow(hdbc) == FAIL)  
         {  
         // Raise error and return.  
         return;  
         }  
      }  
   else  
      {  
      // Break out of loop.  
      break;  
      }  
   }  
  
// Terminate the bulk copy operation.  
if ((nRowsProcessed = bcp_done(hdbc)) == -1)  
   {  
   printf_s("Bulk-copy unsuccessful.\n");  
   return;  
   }  
  
printf_s("%ld rows copied.\n", nRowsProcessed);  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3c58-198">См. также:</span><span class="sxs-lookup"><span data-stu-id="c3c58-198">See Also</span></span>  
 [<span data-ttu-id="c3c58-199">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="c3c58-199">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
