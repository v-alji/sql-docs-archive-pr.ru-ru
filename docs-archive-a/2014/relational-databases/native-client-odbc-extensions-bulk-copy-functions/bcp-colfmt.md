---
title: bcp_colfmt | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_colfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_colfmt function
ms.assetid: 5c3b6299-80c7-4e84-8e69-4ff33009548e
author: rothja
ms.author: jroth
ms.openlocfilehash: f646f3aaf9a8f640d829020bd6762c07c406b61f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750915"
---
# <a name="bcp_colfmt"></a><span data-ttu-id="5ade0-102">bcp_colfmt</span><span class="sxs-lookup"><span data-stu-id="5ade0-102">bcp_colfmt</span></span>
  <span data-ttu-id="5ade0-103">Указывает исходный или целевой формат данных в пользовательском файле.</span><span class="sxs-lookup"><span data-stu-id="5ade0-103">Specifies the source or target format of the data in a user file.</span></span> <span data-ttu-id="5ade0-104">При использовании в качестве исходного формата **bcp_colfmt** задает формат существующего файла данных, используемого в качестве источника данных при выполнении операции с массовым копированием в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] таблицу.</span><span class="sxs-lookup"><span data-stu-id="5ade0-104">When used as a source format, **bcp_colfmt** specifies the format of an existing data file used as the source of data in a bulk copy to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="5ade0-105">При использовании в качестве целевого формата файл данных создается с использованием форматов столбцов, указанных в **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="5ade0-105">When used as a target format, the data file is created using the column formats specified with **bcp_colfmt**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ade0-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ade0-106">Syntax</span></span>  
  
```  
  
RETCODE bcp_colfmt (  
HDBC   
hdbc  
,  
INT  
idxUserDataCol  
,  
BYTE   
eUserDataType  
,  
INT   
cbIndicator  
,  
DBINT   
cbUserData  
,  
LPCBYTE   
pUserDataTerm  
,  
INT   
cbUserDataTerm  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="5ade0-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5ade0-107">Arguments</span></span>  
 <span data-ttu-id="5ade0-108">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="5ade0-108">*hdbc*</span></span>  
 <span data-ttu-id="5ade0-109">Дескриптор соединения ODBC с поддержкой массового копирования.</span><span class="sxs-lookup"><span data-stu-id="5ade0-109">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="5ade0-110">*idxUserDataCol*</span><span class="sxs-lookup"><span data-stu-id="5ade0-110">*idxUserDataCol*</span></span>  
 <span data-ttu-id="5ade0-111">Порядковый номер столбца в пользовательском файле данных, для которого указывается формат.</span><span class="sxs-lookup"><span data-stu-id="5ade0-111">Is the ordinal column number in the user data file for which the format is being specified.</span></span> <span data-ttu-id="5ade0-112">Первый столбец имеет номер 1.</span><span class="sxs-lookup"><span data-stu-id="5ade0-112">The first column is 1.</span></span>  
  
 <span data-ttu-id="5ade0-113">*eUserDataType*</span><span class="sxs-lookup"><span data-stu-id="5ade0-113">*eUserDataType*</span></span>  
 <span data-ttu-id="5ade0-114">Тип данных этого столбца в файле пользователя.</span><span class="sxs-lookup"><span data-stu-id="5ade0-114">Is the data type of this column in the user file.</span></span> <span data-ttu-id="5ade0-115">Если это отличается от типа данных соответствующего столбца в таблице базы данных (*идкссерверколумн*), то при выполнении операции по возможности по мере их выполнения операция по мере их преобразования будет преобразована.</span><span class="sxs-lookup"><span data-stu-id="5ade0-115">If different from the data type of the corresponding column in the database table (*idxServerColumn*), bulk copy converts the data if possible.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]<span data-ttu-id="5ade0-116">Добавлена поддержка токенов типа данных SQLXML и SQLUDT в параметре *еусердататипе* .</span><span class="sxs-lookup"><span data-stu-id="5ade0-116">introduced support for SQLXML and SQLUDT data type tokens in the *eUserDataType* parameter.</span></span>  
  
 <span data-ttu-id="5ade0-117">Параметр *еусердататипе* перечисляется [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] маркерами типа данных в sqlncli. h, а не в перечислителях типа данных ODBC C.</span><span class="sxs-lookup"><span data-stu-id="5ade0-117">The *eUserDataType* parameter is enumerated by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type tokens in sqlncli.h, not the ODBC C data type enumerators.</span></span> <span data-ttu-id="5ade0-118">Например, можно указать символьную строку SQL_C_CHAR типа ODBC с помощью специфического для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] типа SQLCHARACTER.</span><span class="sxs-lookup"><span data-stu-id="5ade0-118">For example, you can specify a character string, ODBC type SQL_C_CHAR, using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific type SQLCHARACTER.</span></span>  
  
 <span data-ttu-id="5ade0-119">Чтобы задать представление данных по умолчанию для типа данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , установите этот параметр в значение 0.</span><span class="sxs-lookup"><span data-stu-id="5ade0-119">To specify the default data representation for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, set this parameter to 0.</span></span>  
  
 <span data-ttu-id="5ade0-120">Для полного копирования из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в файл, если *еусердататипе* имеет значение SQLDECIMAL или SQLNUMERIC:</span><span class="sxs-lookup"><span data-stu-id="5ade0-120">For a bulk copy out of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] into a file, when *eUserDataType* is SQLDECIMAL or SQLNUMERIC:</span></span>  
  
-   <span data-ttu-id="5ade0-121">Если исходный столбец не является **десятичным** или **числовым**, используются точность и масштаб по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ade0-121">If the source column is not **decimal** or **numeric**, the default precision and scale are used.</span></span>  
  
-   <span data-ttu-id="5ade0-122">Если исходный столбец имеет тип **Decimal** или **numeric**, то используются точность и масштаб исходного столбца.</span><span class="sxs-lookup"><span data-stu-id="5ade0-122">If the source column is **decimal** or **numeric**, the precision and scale of the source column are used.</span></span>  
  
 <span data-ttu-id="5ade0-123">*cbIndicator*</span><span class="sxs-lookup"><span data-stu-id="5ade0-123">*cbIndicator*</span></span>  
 <span data-ttu-id="5ade0-124">Длина в байтах признака длины и допустимости значений NULL в данных столбца.</span><span class="sxs-lookup"><span data-stu-id="5ade0-124">Is the length, in bytes, of a length/null indicator within the column data.</span></span> <span data-ttu-id="5ade0-125">Допускаются следующие значения длины признака: 0 (если признак не используется), 1, 2, 4 или 8.</span><span class="sxs-lookup"><span data-stu-id="5ade0-125">Valid indicator length values are 0 (when using no indicator), 1, 2, 4, or 8.</span></span>  
  
 <span data-ttu-id="5ade0-126">Чтобы задать для признака массового копирования использование по умолчанию, установите этот параметр в значение SQL_VARLEN_DATA.</span><span class="sxs-lookup"><span data-stu-id="5ade0-126">To specify default bulk copy indicator usage, set this parameter to SQL_VARLEN_DATA.</span></span>  
  
 <span data-ttu-id="5ade0-127">Признаки располагаются в памяти непосредственно перед данными, а в файле данных — непосредственно перед данными, к которым они применяются.</span><span class="sxs-lookup"><span data-stu-id="5ade0-127">Indicators appear in memory directly before any data, and in the data file directly before the data to which they apply.</span></span>  
  
 <span data-ttu-id="5ade0-128">Если для столбца файла данных используется несколько способов задания длины (например, признак и максимальная длина столбца или признак и последовательность-признак конца), то для массового копирования выбирается способ, применение которого вызовет копирование данных наименьшего объема.</span><span class="sxs-lookup"><span data-stu-id="5ade0-128">If more than one means of specifying a data file column length is used (such as an indicator and a maximum column length, or an indicator and a terminator sequence), bulk copy chooses the one that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="5ade0-129">Если пользователь не изменяет формат данных, то создаваемые при массовом копировании файлы данных содержат признаки, которые определяют, когда столбец может принимать значение NULL или его данные имеют переменную длину.</span><span class="sxs-lookup"><span data-stu-id="5ade0-129">Data files generated by bulk copy when no user intervention adjusts the format of the data contain indicators when the column data can vary in length or the column can accept NULL as a value.</span></span>  
  
 <span data-ttu-id="5ade0-130">*cbUserData*</span><span class="sxs-lookup"><span data-stu-id="5ade0-130">*cbUserData*</span></span>  
 <span data-ttu-id="5ade0-131">Максимальная длина в байтах данных в столбце пользовательского файла, не включая длину признака длины или признака конца.</span><span class="sxs-lookup"><span data-stu-id="5ade0-131">Is the maximum length, in bytes, of this column's data in the user file, not including the length of any length indicator or terminator.</span></span>  
  
 <span data-ttu-id="5ade0-132">Если для параметра *cbUserData* задано значение SQL_NULL_DATA, то все значения в столбце файла данных должны быть или равны NULL.</span><span class="sxs-lookup"><span data-stu-id="5ade0-132">Setting *cbUserData* to SQL_NULL_DATA indicates that all values in the data file column are, or should be set to NULL.</span></span>  
  
 <span data-ttu-id="5ade0-133">Установка параметра *cbUserData* в значение SQL_VARLEN_DATA указывает, что система должна определить длину данных в каждом столбце.</span><span class="sxs-lookup"><span data-stu-id="5ade0-133">Setting *cbUserData* to SQL_VARLEN_DATA indicates that the system should determine the length of data in each column.</span></span> <span data-ttu-id="5ade0-134">Для некоторых столбцов это может означать, что создаваемые признаки длины и допустимости значений NULL предваряют данные при копировании из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], или ожидается их наличие в данных, копируемых в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ade0-134">For some columns, this could mean that a length/null indicator is generated to precede data on a copy from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or that the indicator is expected in data copied to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5ade0-135">Для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] символьных и двоичных типов данных *cbUserData* может быть SQL_VARLEN_DATA, SQL_NULL_DATA, 0 или положительным значением.</span><span class="sxs-lookup"><span data-stu-id="5ade0-135">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character and binary data types, *cbUserData* can be SQL_VARLEN_DATA, SQL_NULL_DATA, 0, or some positive value.</span></span> <span data-ttu-id="5ade0-136">Если *cbUserData* SQL_VARLEN_DATA, система использует либо индикатор длины, если он присутствует, либо последовательность признаков конца для определения длины данных.</span><span class="sxs-lookup"><span data-stu-id="5ade0-136">If *cbUserData* is SQL_VARLEN_DATA, the system uses either the length indicator, if present, or a terminator sequence to determine the length of the data.</span></span> <span data-ttu-id="5ade0-137">Если задан и признак длины, и последовательность признака конца, то при массовом копировании используется значение, применение которого вызывает копирование данных наименьшего объема.</span><span class="sxs-lookup"><span data-stu-id="5ade0-137">If both a length indicator and a terminator sequence are supplied, bulk copy uses the one that results in the least amount of data being copied.</span></span> <span data-ttu-id="5ade0-138">Если *cbUserData* имеет SQL_VARLEN_DATA, то типом данных является [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] символьный или двоичный тип, и не указан ни индикатор длины, ни последовательность признаков конца, система возвращает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5ade0-138">If *cbUserData* is SQL_VARLEN_DATA, the data type is an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character or binary type, and neither a length indicator nor a terminator sequence is specified, the system returns an error message.</span></span>  
  
 <span data-ttu-id="5ade0-139">Если значение *cbUserData* больше или равно 0, то система рассматривает значение *cbUserData* как максимальную длину данных.</span><span class="sxs-lookup"><span data-stu-id="5ade0-139">If *cbUserData* is 0 or a positive value, the system uses *cbUserData* as the maximum data length.</span></span> <span data-ttu-id="5ade0-140">Но если в дополнение к положительному значению для *cbUserData*указан признак длины или последовательность признака конца, то система определяет объем данных методом, который приведет к копированию наименьшего объема данных.</span><span class="sxs-lookup"><span data-stu-id="5ade0-140">However, if, in addition to a positive *cbUserData*, a length indicator or terminator sequence is provided, the system determines the data length by using the method that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="5ade0-141">Значение *cbUserData* представляет объем данных в байтах.</span><span class="sxs-lookup"><span data-stu-id="5ade0-141">The *cbUserData* value represents the count of bytes of data.</span></span> <span data-ttu-id="5ade0-142">Если символьные данные представлены строкой знаков в Юникоде, то положительное значение параметра *cbUserData* представляет количество символов, умноженное на размер символа в байтах.</span><span class="sxs-lookup"><span data-stu-id="5ade0-142">If character data is represented by Unicode wide characters, then a positive *cbUserData* parameter value represents the number of characters multiplied by the size, in bytes, of each character.</span></span>  
  
 <span data-ttu-id="5ade0-143">*pUserDataTerm*</span><span class="sxs-lookup"><span data-stu-id="5ade0-143">*pUserDataTerm*</span></span>  
 <span data-ttu-id="5ade0-144">Последовательность-признак конца, используемая для этого столбца.</span><span class="sxs-lookup"><span data-stu-id="5ade0-144">Is the terminator sequence to be used for this column.</span></span> <span data-ttu-id="5ade0-145">Этот параметр предназначен главным образом для символьных типов данных, поскольку все другие типы имеют фиксированную длину или, как в случае с двоичными данными, требуют наличия признака длины, в котором записано точное число присутствующих байтов.</span><span class="sxs-lookup"><span data-stu-id="5ade0-145">This parameter is useful mainly for character data types because all other types are of fixed length or, in the case of binary data, require an indicator of length to accurately record the number of bytes present.</span></span>  
  
 <span data-ttu-id="5ade0-146">Чтобы исключить обработку признака конца в извлекаемых данных или указать, что данные в файле пользователя не имеют признака конца, установите этот параметр в значение NULL.</span><span class="sxs-lookup"><span data-stu-id="5ade0-146">To avoid terminating extracted data, or to indicate that data in a user file is not terminated, set this parameter to NULL.</span></span>  
  
 <span data-ttu-id="5ade0-147">Если для столбца файла пользователя используется несколько способов задания длины (например, признак конца и признак длины или признак конца и максимальная длина столбца), то для массового копирования выбирается способ, применение которого вызывает копирование данных наименьшего объема.</span><span class="sxs-lookup"><span data-stu-id="5ade0-147">If more than one means of specifying a user-file column length is used (such as a terminator and a length indicator, or a terminator and a maximum column length), bulk copy chooses the one that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="5ade0-148">При необходимости API-интерфейс массового копирования выполнит преобразование символов из Юникода в многобайтовую кодировку (MBCS).</span><span class="sxs-lookup"><span data-stu-id="5ade0-148">The bulk copy API performs Unicode-to-MBCS character conversion as required.</span></span> <span data-ttu-id="5ade0-149">Обратите особое внимание, правильно ли задана строка байтов, служащая признаком конца, а также ее длина.</span><span class="sxs-lookup"><span data-stu-id="5ade0-149">Care must be taken to ensure that both the terminator byte string and the length of the byte string are set correctly.</span></span>  
  
 <span data-ttu-id="5ade0-150">*cbUserDataTerm*</span><span class="sxs-lookup"><span data-stu-id="5ade0-150">*cbUserDataTerm*</span></span>  
 <span data-ttu-id="5ade0-151">Длина в байтах последовательности-признака конца, используемой для этого столбца.</span><span class="sxs-lookup"><span data-stu-id="5ade0-151">Is the length, in bytes, of the terminator sequence to be used for this column.</span></span> <span data-ttu-id="5ade0-152">Если в данных признак конца отсутствует или нежелателен, то установите это значение в 0.</span><span class="sxs-lookup"><span data-stu-id="5ade0-152">If no terminator is present or desired in the data, set this value to 0.</span></span>  
  
 <span data-ttu-id="5ade0-153">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="5ade0-153">*idxServerCol*</span></span>  
 <span data-ttu-id="5ade0-154">Порядковый номер столбца в таблице базы данных.</span><span class="sxs-lookup"><span data-stu-id="5ade0-154">Is the ordinal position of the column in the database table.</span></span> <span data-ttu-id="5ade0-155">Первый столбец имеет номер 1.</span><span class="sxs-lookup"><span data-stu-id="5ade0-155">The first column number is 1.</span></span> <span data-ttu-id="5ade0-156">Порядковый номер столбца возвращается функцией [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="5ade0-156">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
 <span data-ttu-id="5ade0-157">Если это значение равно 0, операция массового копирования пропускает столбец в файле данных.</span><span class="sxs-lookup"><span data-stu-id="5ade0-157">If this value is 0, bulk copy ignores the column in the data file.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="5ade0-158">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5ade0-158">Returns</span></span>  
 <span data-ttu-id="5ade0-159">SUCCEED или FAIL.</span><span class="sxs-lookup"><span data-stu-id="5ade0-159">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ade0-160">Remarks</span><span class="sxs-lookup"><span data-stu-id="5ade0-160">Remarks</span></span>  
 <span data-ttu-id="5ade0-161">Функция **bcp_colfmt** позволяет указать формат пользовательского файла для операций с массовым копированием.</span><span class="sxs-lookup"><span data-stu-id="5ade0-161">The **bcp_colfmt** function allows you to specify the user-file format for bulk copies.</span></span> <span data-ttu-id="5ade0-162">Формат для массового копирования состоит из следующих частей:</span><span class="sxs-lookup"><span data-stu-id="5ade0-162">For bulk copy, a format contains the following parts:</span></span>  
  
-   <span data-ttu-id="5ade0-163">сопоставление столбцов файла пользователя со столбцами базы данных;</span><span class="sxs-lookup"><span data-stu-id="5ade0-163">A mapping from user-file columns to database columns.</span></span>  
  
-   <span data-ttu-id="5ade0-164">тип данных каждого столбца в файле пользователя;</span><span class="sxs-lookup"><span data-stu-id="5ade0-164">The data type of each user-file column.</span></span>  
  
-   <span data-ttu-id="5ade0-165">длина дополнительного признака для каждого столбца;</span><span class="sxs-lookup"><span data-stu-id="5ade0-165">The length of the optional indicator for each column.</span></span>  
  
-   <span data-ttu-id="5ade0-166">максимальная длина данных в каждом столбце файла пользователя;</span><span class="sxs-lookup"><span data-stu-id="5ade0-166">The maximum length of data per user-file column.</span></span>  
  
-   <span data-ttu-id="5ade0-167">дополнительная последовательность байт, служащая признаком конца для каждого столбца;</span><span class="sxs-lookup"><span data-stu-id="5ade0-167">The optional terminating byte sequence for each column.</span></span>  
  
-   <span data-ttu-id="5ade0-168">длина дополнительной последовательности байт, служащей признаком конца.</span><span class="sxs-lookup"><span data-stu-id="5ade0-168">The length of the optional terminating byte sequence.</span></span>  
  
 <span data-ttu-id="5ade0-169">Каждый вызов **bcp_colfmt** задает формат для одного столбца пользовательского файла.</span><span class="sxs-lookup"><span data-stu-id="5ade0-169">Each call to **bcp_colfmt** specifies the format for one user-file column.</span></span> <span data-ttu-id="5ade0-170">Например, чтобы изменить параметры по умолчанию для трех столбцов в файле пользовательских данных, состоящий из пяти столбцов, сначала вызовите [bcp_columns](bcp-columns.md)**(5)**, а затем вызовите **bcp_colfmt** пять раз, и три из этих вызовов задавая свой собственный формат.</span><span class="sxs-lookup"><span data-stu-id="5ade0-170">For example, to change the default settings for three columns in a five-column user data file, first call [bcp_columns](bcp-columns.md)**(5)**, and then call **bcp_colfmt** five times, with three of those calls setting your custom format.</span></span> <span data-ttu-id="5ade0-171">Для оставшихся двух вызовов задайте для *еусердататипе* значение 0, а для свойств *кбиндикатор*, *cbUserData*и *кбусердататерм* — 0, SQL_VARLEN_DATA и 0 соответственно.</span><span class="sxs-lookup"><span data-stu-id="5ade0-171">For the remaining two calls, set *eUserDataType* to 0, and set *cbIndicator*, *cbUserData*, and *cbUserDataTerm* to 0, SQL_VARLEN_DATA, and 0 respectively.</span></span> <span data-ttu-id="5ade0-172">Эта процедура копирует все пять столбцов. Для трех применяется заданный измененный формат, а для двух оставшихся — формат по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ade0-172">This procedure copies all five columns, three with your customized format and two with the default format.</span></span>  
  
 <span data-ttu-id="5ade0-173">Для *кбиндикатор*значение 8 означает, что тип больших значений теперь является допустимым.</span><span class="sxs-lookup"><span data-stu-id="5ade0-173">For *cbIndicator*, a value of 8 to indicate a large value type is now valid.</span></span> <span data-ttu-id="5ade0-174">Если для поля, которому соответствует столбец с новым типом max, указан префикс, его значение можно установить только в 8.</span><span class="sxs-lookup"><span data-stu-id="5ade0-174">If the prefix is specified for a field whose corresponding column is a new max type, it can only be set to 8.</span></span> <span data-ttu-id="5ade0-175">Дополнительные сведения см. в разделе [bcp_bind](bcp-bind.md).</span><span class="sxs-lookup"><span data-stu-id="5ade0-175">For details, see [bcp_bind](bcp-bind.md).</span></span>  
  
 <span data-ttu-id="5ade0-176">Функция **bcp_columns** должна вызываться перед вызовами функции **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="5ade0-176">The **bcp_columns** function must be called before any calls to **bcp_colfmt**.</span></span>  
  
 <span data-ttu-id="5ade0-177">Необходимо вызвать **bcp_colfmt** один раз для каждого столбца в файле пользователя.</span><span class="sxs-lookup"><span data-stu-id="5ade0-177">You must call **bcp_colfmt** once for each column in the user file.</span></span>  
  
 <span data-ttu-id="5ade0-178">Вызов **bcp_colfmt** более одного раза для любого столбца файла пользователя приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="5ade0-178">Calling **bcp_colfmt** more than once for any user-file column causes an error.</span></span>  
  
 <span data-ttu-id="5ade0-179">Нет необходимости копировать все данные из пользовательского файла в таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ade0-179">You do not need to copy all data in a user file to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="5ade0-180">Чтобы пропустить столбец, укажите формат данных для этого столбца, установив для параметра *idxServerCol* значение 0.</span><span class="sxs-lookup"><span data-stu-id="5ade0-180">To skip a column, specify the format of the data for the column, setting the *idxServerCol* parameter to 0.</span></span> <span data-ttu-id="5ade0-181">Если требуется пропустить столбец, необходимо указать его тип.</span><span class="sxs-lookup"><span data-stu-id="5ade0-181">If you want to skip a column, you must specify its type.</span></span>  
  
 <span data-ttu-id="5ade0-182">Для сохранения спецификации формата можно воспользоваться функцией [bcp_writefmt](bcp-writefmt.md) .</span><span class="sxs-lookup"><span data-stu-id="5ade0-182">The [bcp_writefmt](bcp-writefmt.md) function can be used to persist the format specification.</span></span>  
  
## <a name="bcp_colfmt-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="5ade0-183">Поддержка функцией bcp_colfmt улучшенных возможностей даты и времени</span><span class="sxs-lookup"><span data-stu-id="5ade0-183">bcp_colfmt Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="5ade0-184">Сведения о типах, используемых с параметром *еусердататипе* для типов даты и времени, см. в разделе [изменения в ходе операции копирования для расширенных типов даты и времени &#40;OLE DB и ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="5ade0-184">For information aboutt he types used with the *eUserDataType* parameter for date/time types, see [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="5ade0-185">Дополнительные сведения см. в разделе [улучшения даты и времени &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="5ade0-185">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ade0-186">См. также:</span><span class="sxs-lookup"><span data-stu-id="5ade0-186">See Also</span></span>  
 [<span data-ttu-id="5ade0-187">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="5ade0-187">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
