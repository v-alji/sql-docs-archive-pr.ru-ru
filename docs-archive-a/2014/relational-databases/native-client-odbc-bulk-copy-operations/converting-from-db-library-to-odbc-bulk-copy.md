---
title: Преобразование из DB-Library в "групповое копирование ODBC" | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- converting DB-Library to ODBC bulk copy
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC], DB-Library bulk copy
- ODBC, bulk copy operations
- DB-Library bulk copy
ms.assetid: 0bc15bdb-f19f-4537-ac6c-f249f42cf07f
author: rothja
ms.author: jroth
ms.openlocfilehash: 866900606e582f08695fd4695a1098f34fb2b426
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666567"
---
# <a name="converting-from-db-library-to-odbc-bulk-copy"></a><span data-ttu-id="68763-102">Перевод массового копирования с DB-Library на ODBC</span><span class="sxs-lookup"><span data-stu-id="68763-102">Converting from DB-Library to ODBC Bulk Copy</span></span>
  <span data-ttu-id="68763-103">Преобразование программы пакетного копирования DB-Library в ODBC несложно, поскольку функции копирования, поддерживаемые [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвером ODBC для собственного клиента, похожи на функции операций с массовым копированием DB-Library, за исключением следующих.</span><span class="sxs-lookup"><span data-stu-id="68763-103">Converting a DB-Library bulk copy program to ODBC is easy because the bulk copy functions supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver are similar to the DB-Library bulk copy functions, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="68763-104">Приложения DB-Library передают указатель на структуру DBPROCESS как первый параметр функций массового копирования.</span><span class="sxs-lookup"><span data-stu-id="68763-104">DB-Library applications pass a pointer to a DBPROCESS structure as the first parameter of bulk copy functions.</span></span> <span data-ttu-id="68763-105">В приложениях ODBC указатель DBPROCESS заменяется дескриптором соединения ODBC.</span><span class="sxs-lookup"><span data-stu-id="68763-105">In ODBC applications, the DBPROCESS pointer is replaced with an ODBC connection handle.</span></span>  
  
-   <span data-ttu-id="68763-106">Приложения DB-Library вызывают **BCP_SETL** перед подключением для включения операций с массовым копированием в дбпроцесс.</span><span class="sxs-lookup"><span data-stu-id="68763-106">DB-Library applications call **BCP_SETL** before connecting to enable bulk copy operations on a DBPROCESS.</span></span> <span data-ttu-id="68763-107">Приложения ODBC вместо этого вызывают [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) перед подключением, чтобы включить групповые операции для маркера подключения:</span><span class="sxs-lookup"><span data-stu-id="68763-107">ODBC applications instead call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) before connecting to enable bulk operations on a connection handle:</span></span>  
  
    ```  
    SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP,  
        (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
    ```  
  
-   <span data-ttu-id="68763-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента не поддерживает сообщения и обработчики ошибок DB-Library. для получения ошибок и сообщений, вызванных функциями выполнения операций с массовым копированием ODBC, необходимо вызвать **SQLGetDiagRec** .</span><span class="sxs-lookup"><span data-stu-id="68763-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support DB-Library message and error handlers; you must call **SQLGetDiagRec** to get errors and messages raised by the ODBC bulk copy functions.</span></span> <span data-ttu-id="68763-109">Версии ODBC функций массового копирования возвращают стандартные коды возврата массового копирования SUCCEED или FAILED, а не коды возврата ODBC, такие как SQL_SUCCESS или SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="68763-109">The ODBC versions of bulk copy functions return the standard bulk copy return codes of SUCCEED or FAILED, not ODBC-style return codes, such as SQL_SUCCESS or SQL_ERROR.</span></span>  
  
-   <span data-ttu-id="68763-110">Значения, указанные для параметра DB-Library [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md)*Варлен* , обрабатываются иначе, чем параметр ODBC **bcp_bind**_cbData_ .</span><span class="sxs-lookup"><span data-stu-id="68763-110">The values specified for the DB-Library [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md)*varlen* parameter are interpreted differently than the ODBC **bcp_bind**_cbData_ parameter.</span></span>  
  
    |<span data-ttu-id="68763-111">Указанное условие</span><span class="sxs-lookup"><span data-stu-id="68763-111">Condition indicated</span></span>|<span data-ttu-id="68763-112">Значение *ВАРЛЕН* DB-Library</span><span class="sxs-lookup"><span data-stu-id="68763-112">DB-Library *varlen* value</span></span>|<span data-ttu-id="68763-113">Значение *CBDATA* ODBC</span><span class="sxs-lookup"><span data-stu-id="68763-113">ODBC *cbData* value</span></span>|  
    |-------------------------|--------------------------------|-------------------------|  
    |<span data-ttu-id="68763-114">Предоставлены значения NULL</span><span class="sxs-lookup"><span data-stu-id="68763-114">Null values supplied</span></span>|<span data-ttu-id="68763-115">0</span><span class="sxs-lookup"><span data-stu-id="68763-115">0</span></span>|<span data-ttu-id="68763-116">-1 (SQL_NULL_DATA)</span><span class="sxs-lookup"><span data-stu-id="68763-116">-1 (SQL_NULL_DATA)</span></span>|  
    |<span data-ttu-id="68763-117">Предоставлены данные переменной длины</span><span class="sxs-lookup"><span data-stu-id="68763-117">Variable data supplied</span></span>|<span data-ttu-id="68763-118">-1</span><span class="sxs-lookup"><span data-stu-id="68763-118">-1</span></span>|<span data-ttu-id="68763-119">-10 (SQL_VARLEN_DATA)</span><span class="sxs-lookup"><span data-stu-id="68763-119">-10 (SQL_VARLEN_DATA)</span></span>|  
    |<span data-ttu-id="68763-120">Символьная или двоичная строка нулевой длины</span><span class="sxs-lookup"><span data-stu-id="68763-120">Zero length character or binary string</span></span>|<span data-ttu-id="68763-121">Н/Д</span><span class="sxs-lookup"><span data-stu-id="68763-121">NA</span></span>|<span data-ttu-id="68763-122">0</span><span class="sxs-lookup"><span data-stu-id="68763-122">0</span></span>|  
  
     <span data-ttu-id="68763-123">В DB-Library значение *Варлен* , равное-1, указывает, что данные переменной длины передаются, что в ODBC *cbData* интерпретируется таким же, что предоставляются только значения NULL.</span><span class="sxs-lookup"><span data-stu-id="68763-123">In DB-Library, a *varlen* value of -1 indicates that variable length data is being supplied, which in the ODBC *cbData* is interpreted to mean that only NULL values are being supplied.</span></span> <span data-ttu-id="68763-124">Измените все спецификации *ВАРЛЕН* DB-Library с-1 на SQL_VARLEN_DATA и любые спецификации *Варлен* от 0 до SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="68763-124">Change any DB-Library *varlen* specifications of -1 to SQL_VARLEN_DATA and any *varlen* specifications of 0 to SQL_NULL_DATA.</span></span>  
  
-   <span data-ttu-id="68763-125">Файл DB-Library **bcp \_ колфмт**,_ \_ Коллен_ и ODBC [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md)*cbUserData* , имеют те же проблемы, что и параметры **bcp_bind**_Варлен_ и *cbData* , указанные выше.</span><span class="sxs-lookup"><span data-stu-id="68763-125">The DB-Library **bcp\_colfmt**_file\_collen_ and the ODBC [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md)*cbUserData* have the same issue as the **bcp_bind**_varlen_ and *cbData* parameters noted above.</span></span> <span data-ttu-id="68763-126">Измените все спецификации *FILE_COLLEN* DB-Library, равные-1, на SQL_VARLEN_DATA и любые *file_collen* спецификации от 0 до SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="68763-126">Change any DB-Library *file_collen* specifications of -1 to SQL_VARLEN_DATA and any *file_collen* specifications of 0 to SQL_NULL_DATA.</span></span>  
  
-   <span data-ttu-id="68763-127">Параметр *iValue* функции ODBC [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) является указателем void.</span><span class="sxs-lookup"><span data-stu-id="68763-127">The *iValue* parameter of the ODBC [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) function is a void pointer.</span></span> <span data-ttu-id="68763-128">В DB-Library *iValue* был целым числом.</span><span class="sxs-lookup"><span data-stu-id="68763-128">In DB-Library, *iValue* was an integer.</span></span> <span data-ttu-id="68763-129">Приведите значения для *IVALUE* ODBC к void \*.</span><span class="sxs-lookup"><span data-stu-id="68763-129">Cast the values for the ODBC *iValue* to void \*.</span></span>  
  
-   <span data-ttu-id="68763-130">Параметр **BCP_CONTROL** BCPMAXERRS указывает, сколько отдельных строк может содержать ошибки до тех пор, пока операция копирования не завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="68763-130">The **bcp_control** option BCPMAXERRS specifies how many individual rows can have errors before a bulk copy operation fails.</span></span> <span data-ttu-id="68763-131">Значение по умолчанию для BCPMAXERRS — 0 (ошибка при первой ошибке) в версии библиотеки DB-Library **bcp_control** и 10 в версии ODBC.</span><span class="sxs-lookup"><span data-stu-id="68763-131">The default for BCPMAXERRS is 0 (fail on first error) in the DB-Library version of **bcp_control** and 10 in the ODBC version.</span></span> <span data-ttu-id="68763-132">Приложения DB-Library, зависящие от значения по умолчанию 0 для завершения операции копирования, необходимо изменить для вызова **BCP_CONTROL** ODBC, чтобы установить значение 0 для BCPMAXERRS.</span><span class="sxs-lookup"><span data-stu-id="68763-132">DB-Library applications that depend on the default of 0 to terminate a bulk copy operation must be changed to call the ODBC **bcp_control** to set BCPMAXERRS to 0.</span></span>  
  
-   <span data-ttu-id="68763-133">Функция ODBC **bcp_control** поддерживает следующие параметры, не ПОДДЕРЖИВАЕМЫЕ версией DB-Library для **bcp_control**.</span><span class="sxs-lookup"><span data-stu-id="68763-133">The ODBC **bcp_control** function supports the following options not supported by the DB-Library version of **bcp_control**:</span></span>  
  
    -   <span data-ttu-id="68763-134">BCPODBC</span><span class="sxs-lookup"><span data-stu-id="68763-134">BCPODBC</span></span>  
  
         <span data-ttu-id="68763-135">Если задано значение TRUE, то указывает, что значения **DateTime** и **smalldatetime** , сохраненные в символьном формате, будут иметь префикс escape-последовательности и суффикс последовательного времени ODBC.</span><span class="sxs-lookup"><span data-stu-id="68763-135">When set to TRUE, specifies that **datetime** and **smalldatetime** values saved in character format will have the ODBC timestamp escape sequence prefix and suffix.</span></span> <span data-ttu-id="68763-136">Это относится только к операциям BCP_OUT.</span><span class="sxs-lookup"><span data-stu-id="68763-136">This only applies to BCP_OUT operations.</span></span>  
  
         <span data-ttu-id="68763-137">Если параметр BCPODBC имеет значение FALSE, то значение **DateTime** , преобразованное в символьную строку, выводится следующим образом:</span><span class="sxs-lookup"><span data-stu-id="68763-137">With BCPODBC set to FALSE, a **datetime** value converted to a character string is output as:</span></span>  
  
        ```  
        1997-01-01 00:00:00.000  
        ```  
  
         <span data-ttu-id="68763-138">Если для BCPODBC задано значение TRUE, то то же значение **DateTime** выводится следующим образом:</span><span class="sxs-lookup"><span data-stu-id="68763-138">With BCPODBC set to TRUE, the same **datetime** value is output as:</span></span>  
  
        ```  
        {ts '1997-01-01 00:00:00.000' }  
        ```  
  
    -   <span data-ttu-id="68763-139">BCPKEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="68763-139">BCPKEEPIDENTITY</span></span>  
  
         <span data-ttu-id="68763-140">Значение TRUE указывает, что функции массового копирования вставляют значения данных, предоставленные для столбцов с ограничениями идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="68763-140">When set to TRUE, specifies that bulk copy functions insert data values supplied for columns with identity constraints.</span></span> <span data-ttu-id="68763-141">Если эти значения не заданы, то для вставляемых строк создаются новые значения идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="68763-141">If this is not set, new identity values are generated for the inserted rows.</span></span>  
  
    -   <span data-ttu-id="68763-142">BCPHINTS</span><span class="sxs-lookup"><span data-stu-id="68763-142">BCPHINTS</span></span>  
  
         <span data-ttu-id="68763-143">Определяет различные оптимизации для массового копирования.</span><span class="sxs-lookup"><span data-stu-id="68763-143">Specifies various bulk copy optimizations.</span></span> <span data-ttu-id="68763-144">Этот параметр не может использоваться в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 6.5 и более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="68763-144">This option cannot be used on 6.5 or earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="68763-145">BCPFILECP</span><span class="sxs-lookup"><span data-stu-id="68763-145">BCPFILECP</span></span>  
  
         <span data-ttu-id="68763-146">Задает кодовую страницу файла массового копирования.</span><span class="sxs-lookup"><span data-stu-id="68763-146">Specifies the code page of the bulk copy file.</span></span>  
  
    -   <span data-ttu-id="68763-147">BCPUNICODEFILE</span><span class="sxs-lookup"><span data-stu-id="68763-147">BCPUNICODEFILE</span></span>  
  
         <span data-ttu-id="68763-148">Указывает, что файл массового копирования в символьном формате является файлом в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="68763-148">Specifies that a character mode bulk copy file is a Unicode file.</span></span>  
  
-   <span data-ttu-id="68763-149">Функция ODBC **bcp_colfmt** не поддерживает индикатор *file_type* SQLCHAR, так как он конфликтует с ОПРЕДЕЛЕНИЕМ типа данных ODBC SQLCHAR.</span><span class="sxs-lookup"><span data-stu-id="68763-149">The ODBC **bcp_colfmt** function does not support the *file_type* indicator of SQLCHAR because it conflicts with the ODBC SQLCHAR typedef.</span></span> <span data-ttu-id="68763-150">Вместо **bcp_colfmt**используйте SQLCHARACTER.</span><span class="sxs-lookup"><span data-stu-id="68763-150">Use SQLCHARACTER instead for **bcp_colfmt**.</span></span>  
  
-   <span data-ttu-id="68763-151">В версиях ODBC для функций операций с массовым копированием формат для работы с значениями **DateTime** и **smalldatetime** в символьных строках — это формат ODBC в формате "гггг-мм-дд чч: мм: СС. SSS;" значения **smalldatetime** используют формат ODBC в формате "гггг-мм-дд чч: мм: СС".</span><span class="sxs-lookup"><span data-stu-id="68763-151">In the ODBC versions of bulk copy functions, the format for working with **datetime** and **smalldatetime** values in character strings is the ODBC format of yyyy-mm-dd hh:mm:ss.sss; **smalldatetime** values use the ODBC format of yyyy-mm-dd hh:mm:ss.</span></span>  
  
     <span data-ttu-id="68763-152">Версии DB-Library функций с массовым копированием принимают значения **DateTime** и **smalldatetime** в символьных строках с использованием нескольких форматов:</span><span class="sxs-lookup"><span data-stu-id="68763-152">The DB-Library versions of the bulk copy functions accept **datetime** and **smalldatetime** values in character strings using several formats:</span></span>  
  
    -   <span data-ttu-id="68763-153">Формат по умолчанию — *МММ дд гггг чч: ммxx* , где *XX* — AM или PM.</span><span class="sxs-lookup"><span data-stu-id="68763-153">The default format is *mmm dd yyyy hh:mmxx* where *xx* is either AM or PM.</span></span>  
  
    -   <span data-ttu-id="68763-154">строки символов **DateTime** и **smalldatetime** в любом формате, поддерживаемом функцией DB-Library **дбконверт** .</span><span class="sxs-lookup"><span data-stu-id="68763-154">**datetime** and **smalldatetime** character strings in any format supported by the DB-Library **dbconvert** function.</span></span>  
  
    -   <span data-ttu-id="68763-155">Если флажок **использовать международные параметры** установлен на вкладке **Параметры** DB-Library [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] служебной программы "клиентская сеть", функции операций с массовым копированием DB-Library также принимают даты в региональном формате, определенном для параметра языкового стандарта реестра клиентского компьютера.</span><span class="sxs-lookup"><span data-stu-id="68763-155">When the **Use international settings** box is checked on the DB-Library **Options** tab of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client Network Utility, the DB-Library bulk copy functions also accept dates in the regional date format defined for the locale setting of the client computer registry.</span></span>  
  
     <span data-ttu-id="68763-156">Функции операций с массовым копированием DB-Library не принимают форматы **DateTime** и **smalldatetime** ODBC.</span><span class="sxs-lookup"><span data-stu-id="68763-156">The DB-Library bulk copy functions do not accept the ODBC **datetime** and **smalldatetime** formats.</span></span>  
  
     <span data-ttu-id="68763-157">Если атрибут инструкции SQL_SOPT_SS_REGIONALIZE установлен в значение SQL_RE_ON, функции массового копирования ODBC принимают даты в региональном формате данных, определенном для локали, установленной в реестре клиентского компьютера.</span><span class="sxs-lookup"><span data-stu-id="68763-157">If the SQL_SOPT_SS_REGIONALIZE statement attribute is set to SQL_RE_ON, the ODBC bulk copy functions accept dates in the regional date format defined for the locale setting of the client computer registry.</span></span>  
  
-   <span data-ttu-id="68763-158">При вводе **денежных** значений в символьном формате функции выполнения операций с массовым копированием ODBC предоставляют четыре цифры точности и без разделителей запятой. Версии DB-Library предоставляют только две цифры точности и включают разделители-запятые.</span><span class="sxs-lookup"><span data-stu-id="68763-158">When outputting **money** values in character format, ODBC bulk copy functions supply four digits of precision and no comma separators; DB-Library versions only supply two digits of precision and include the comma separators.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68763-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="68763-159">See Also</span></span>  
 <span data-ttu-id="68763-160">[Выполнение операций с массовым копированием &#40;ODBC&#41;](performing-bulk-copy-operations-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="68763-160">[Performing Bulk Copy Operations &#40;ODBC&#41;](performing-bulk-copy-operations-odbc.md) </span></span>  
 [<span data-ttu-id="68763-161">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="68763-161">Bulk Copy Functions</span></span>](../native-client-odbc-extensions-bulk-copy-functions/sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
