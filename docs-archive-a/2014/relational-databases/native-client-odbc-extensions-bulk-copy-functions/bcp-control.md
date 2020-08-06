---
title: bcp_control | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_control
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_control function
ms.assetid: 32187282-1385-4c52-9134-09f061eb44f5
author: rothja
ms.author: jroth
ms.openlocfilehash: 7ea5d60da8069707a53f3bdf2de53345cd11090f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654249"
---
# <a name="bcp_control"></a><span data-ttu-id="e6944-102">bcp_control</span><span class="sxs-lookup"><span data-stu-id="e6944-102">bcp_control</span></span>
  <span data-ttu-id="e6944-103">Изменяет значения по умолчанию различных параметров управления для массового копирования между файлом и [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6944-103">Changes the default settings for various control parameters for a bulk copy between a file and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6944-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6944-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_control (  
HDBC   
hdbc  
,  
INT   
eOption  
,  
void*   
iValue  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="e6944-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e6944-105">Arguments</span></span>  
 <span data-ttu-id="e6944-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="e6944-106">*hdbc*</span></span>  
 <span data-ttu-id="e6944-107">Дескриптор соединения ODBC с поддержкой массового копирования.</span><span class="sxs-lookup"><span data-stu-id="e6944-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="e6944-108">*eOption*</span><span class="sxs-lookup"><span data-stu-id="e6944-108">*eOption*</span></span>  
 <span data-ttu-id="e6944-109">Принимает одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="e6944-109">Is one of the following:</span></span>  
  
 <span data-ttu-id="e6944-110">BCPABORT</span><span class="sxs-lookup"><span data-stu-id="e6944-110">BCPABORT</span></span>  
 <span data-ttu-id="e6944-111">Останавливает текущую операцию массового копирования.</span><span class="sxs-lookup"><span data-stu-id="e6944-111">Stops a bulk-copy operation that is already in progress.</span></span> <span data-ttu-id="e6944-112">Вызовите **bcp_control** с *eOption* бкпаборт из другого потока, чтобы прерывать выполнение операции с массовым копированием.</span><span class="sxs-lookup"><span data-stu-id="e6944-112">Call **bcp_control** with an *eOption* of BCPABORT from another thread to stop a running bulk copy operation.</span></span> <span data-ttu-id="e6944-113">Параметр *iValue* игнорируется.</span><span class="sxs-lookup"><span data-stu-id="e6944-113">The *iValue* parameter is ignored.</span></span>  
  
 <span data-ttu-id="e6944-114">BCPBATCH</span><span class="sxs-lookup"><span data-stu-id="e6944-114">BCPBATCH</span></span>  
 <span data-ttu-id="e6944-115">Число строк в пакете.</span><span class="sxs-lookup"><span data-stu-id="e6944-115">Is the number of rows per batch.</span></span> <span data-ttu-id="e6944-116">Значение по умолчанию — 0, что указывает либо все строки в таблице при извлечении данных, либо все строки в пользовательском файле данных, когда данные копируются в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6944-116">The default is 0, which indicates either all rows in a table, when data is being extracted, or all rows in the user data file, when data is being copied to an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e6944-117">Если задать для этого параметра значение меньше 1, то значению BCPBATCH будет установлено значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6944-117">A value less than 1 resets BCPBATCH to the default.</span></span>  
  
 <span data-ttu-id="e6944-118">BCPDELAYREADFMT</span><span class="sxs-lookup"><span data-stu-id="e6944-118">BCPDELAYREADFMT</span></span>  
 <span data-ttu-id="e6944-119">Логическое значение, если установлено значение true, вызовет [bcp_readfmt](bcp-readfmt.md) чтение во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e6944-119">A Boolean, if set to true, will cause [bcp_readfmt](bcp-readfmt.md) to read at execution.</span></span> <span data-ttu-id="e6944-120">Если значение равно false (по умолчанию), bcp_readfmt немедленно прочитает файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="e6944-120">If false (the default), bcp_readfmt will immediately read the format file.</span></span> <span data-ttu-id="e6944-121">Если BCPDELAYREADFMT имеет значение true и вы вызываете bcp_columns или bcp_setcolfmt, возникнет ошибка последовательности.</span><span class="sxs-lookup"><span data-stu-id="e6944-121">A sequence error will occur if BCPDELAYREADFMT is true and you call bcp_columns or bcp_setcolfmt.</span></span>  
  
 <span data-ttu-id="e6944-122">Ошибка последовательности также возникает при вызове `bcp_control(hdbc,` BCPDELAYREADFMT `, (void *)FALSE)` после вызова `bcp_control(hdbc,` BCPDELAYREADFMT `, (void *)TRUE)` и bcp_writefmt.</span><span class="sxs-lookup"><span data-stu-id="e6944-122">A sequence error will also occur if you call `bcp_control(hdbc,` BCPDELAYREADFMT`, (void *)FALSE)` after calling `bcp_control(hdbc,` BCPDELAYREADFMT`, (void *)TRUE)` and bcp_writefmt.</span></span>  
  
 <span data-ttu-id="e6944-123">Дополнительные сведения см. в разделе [Обнаружение метаданных](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="e6944-123">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
 <span data-ttu-id="e6944-124">BCPFILECP</span><span class="sxs-lookup"><span data-stu-id="e6944-124">BCPFILECP</span></span>  
 <span data-ttu-id="e6944-125">*iValue* содержит номер кодовой страницы для файла данных.</span><span class="sxs-lookup"><span data-stu-id="e6944-125">*iValue* contains the number of the code page for the data file.</span></span> <span data-ttu-id="e6944-126">Можно указать номер кодовой страницы, например 1252 или 850, либо одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="e6944-126">You can specify the number of the code page, such as 1252 or 850, or one of these values:</span></span>  
  
 <span data-ttu-id="e6944-127">BCPFILE_ACP: данные в файле находятся в Microsoft Windows??</span><span class="sxs-lookup"><span data-stu-id="e6944-127">BCPFILE_ACP: data in the file is in the Microsoft Windows??</span></span> <span data-ttu-id="e6944-128">Кодовая страница клиента.</span><span class="sxs-lookup"><span data-stu-id="e6944-128">code page of the client.</span></span>  
  
 <span data-ttu-id="e6944-129">BCPFILE_OEMCP: данные в файле хранятся в кодовой странице изготовителя оборудования (OEM) клиента (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e6944-129">BCPFILE_OEMCP: data in the file is in the OEM code page of the client (default).</span></span>  
  
 <span data-ttu-id="e6944-130">BCPFILE_RAW: данные в файле хранятся в кодовой странице [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6944-130">BCPFILE_RAW: data in the file is in the code page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e6944-131">BCPFILEFMT</span><span class="sxs-lookup"><span data-stu-id="e6944-131">BCPFILEFMT</span></span>  
 <span data-ttu-id="e6944-132">Номер версии для формата файла данных.</span><span class="sxs-lookup"><span data-stu-id="e6944-132">The version number of the data file format.</span></span> <span data-ttu-id="e6944-133">Может иметь значение 80 ([!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]), 90 ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]), 100 ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] или [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]), 110 ([!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]) или 120 ([!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="e6944-133">This can be 80 ([!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]), 90 ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]), 100 ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]), 110 ([!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]), or 120 ([!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span></span> <span data-ttu-id="e6944-134">120 используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6944-134">120 is the default.</span></span> <span data-ttu-id="e6944-135">Это может оказаться полезным при экспорте или импорте данных в форматах, которые поддерживались прежними версиями сервера.</span><span class="sxs-lookup"><span data-stu-id="e6944-135">This is useful for exporting and importing data in formats that were supported by earlier version of the server.</span></span> <span data-ttu-id="e6944-136">Например, чтобы импортировать данные, полученные из текстового столбца [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] сервера в столбец **varchar (max)** на [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] сервере или более поздней версии, следует указать 80.</span><span class="sxs-lookup"><span data-stu-id="e6944-136">For example, to import data that was obtained from a text column in a [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] server into a **varchar(max)** column in a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later server, you should specify 80.</span></span> <span data-ttu-id="e6944-137">Аналогично, если указать 80 при экспорте данных из столбца **varchar (max)** , они будут сохранены так же, как текстовые столбцы, сохраняются в [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] формате и могут быть импортированы в текстовый столбец [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] сервера.</span><span class="sxs-lookup"><span data-stu-id="e6944-137">Similarly, if you specify 80 when exporting data from a **varchar(max)** column, it will be saved just like text columns are saved in the [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] format, and can be imported into a text column of a [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] server.</span></span>  
  
 <span data-ttu-id="e6944-138">BCPFIRST</span><span class="sxs-lookup"><span data-stu-id="e6944-138">BCPFIRST</span></span>  
 <span data-ttu-id="e6944-139">Первая строка данных, копируемых в файл или таблицу.</span><span class="sxs-lookup"><span data-stu-id="e6944-139">Is the first row of data to file or table to copy.</span></span> <span data-ttu-id="e6944-140">Значение по умолчанию равно 1. Если задать для этого параметра значение меньше 1, то будет установлено значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6944-140">The default is 1; a value less than 1 resets this option to its default.</span></span>  
  
 <span data-ttu-id="e6944-141">BCPFIRSTEX</span><span class="sxs-lookup"><span data-stu-id="e6944-141">BCPFIRSTEX</span></span>  
 <span data-ttu-id="e6944-142">В операциях bcp out задает первую строку таблицы базы данных для копирования в файл данных.</span><span class="sxs-lookup"><span data-stu-id="e6944-142">For BCP out operations, specifies the first row of the database table to copy into the data file.</span></span>  
  
 <span data-ttu-id="e6944-143">В операциях bcp in задает первую строку файла данных для копирования в таблицу базы данных.</span><span class="sxs-lookup"><span data-stu-id="e6944-143">For BCP in operations, specifies the first row of the data file to copy into the database table.</span></span>  
  
 <span data-ttu-id="e6944-144">Параметр *iValue* должен быть адресом 64-разрядного целого числа со знаком, содержащим значение.</span><span class="sxs-lookup"><span data-stu-id="e6944-144">The *iValue* parameter is expected to be the address of a signed 64-bit integer containing the value.</span></span> <span data-ttu-id="e6944-145">Максимальное значение, передаваемое в BCPFIRSTEX, составляет 2^63-1.</span><span class="sxs-lookup"><span data-stu-id="e6944-145">The maximum value that can be passed to BCPFIRSTEX is 2^63-1.</span></span>  
  
 <span data-ttu-id="e6944-146">BCPFMTXML</span><span class="sxs-lookup"><span data-stu-id="e6944-146">BCPFMTXML</span></span>  
 <span data-ttu-id="e6944-147">Указывает, что формируемый файл форматирования должен быть в формате XML.</span><span class="sxs-lookup"><span data-stu-id="e6944-147">Specifies that the format file generated should be in XML format.</span></span> <span data-ttu-id="e6944-148">По умолчанию эта настройка отключена.</span><span class="sxs-lookup"><span data-stu-id="e6944-148">It is off by default.</span></span>  
  
 <span data-ttu-id="e6944-149">XML-файлы форматирования обеспечивают большую гибкость, но имеют некоторые ограничения.</span><span class="sxs-lookup"><span data-stu-id="e6944-149">XML format files provide greater flexibility but with some added constraints.</span></span> <span data-ttu-id="e6944-150">Например, нельзя одновременно указать префикс и признак конца для поля, что было возможно в более старых файлах форматирования.</span><span class="sxs-lookup"><span data-stu-id="e6944-150">For example, you can not specify the prefix and terminator for a field simultaneously, which was possible in older format files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6944-151">XML-файлы форматирования поддерживаются только при установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] вместе с собственным клиентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6944-151">XML format files are only supported when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed along with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 <span data-ttu-id="e6944-152">BCPHINTS</span><span class="sxs-lookup"><span data-stu-id="e6944-152">BCPHINTS</span></span>  
 <span data-ttu-id="e6944-153">*iValue* содержит указатель на SQLTCHAR строку символов.</span><span class="sxs-lookup"><span data-stu-id="e6944-153">*iValue* contains an SQLTCHAR character string pointer.</span></span> <span data-ttu-id="e6944-154">Адресуемая строка задает указания для обработки массового копирования [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или инструкцию Transact-SQL, которая возвращает результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="e6944-154">The string addressed specifies either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk-copy processing hints or a Transact-SQL statement that returns a result set.</span></span> <span data-ttu-id="e6944-155">Если задана инструкция Transact-SQL, которая возвращает несколько результирующих наборов, все результирующие наборы после первого пропускаются.</span><span class="sxs-lookup"><span data-stu-id="e6944-155">If a Transact-SQL statement is specified that returns more than one result set, all result sets after the first are ignored.</span></span> <span data-ttu-id="e6944-156">Дополнительные сведения о указаниях по обработке массовых копий см. в разделе [программа bcp](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="e6944-156">For more information about bulk-copy processing hints, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
 <span data-ttu-id="e6944-157">BCPKEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="e6944-157">BCPKEEPIDENTITY</span></span>  
 <span data-ttu-id="e6944-158">Если *iValue* имеет значение true, то указывает, что функции операций с массовым копированием вставляют значения данных, предоставляемые для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] столбцов, определенных с помощью ограничения IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="e6944-158">When *iValue* is TRUE, specifies that bulk copy functions insert data values supplied for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] columns defined with an identity constraint.</span></span> <span data-ttu-id="e6944-159">Входной файл должен содержать значения для столбцов идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="e6944-159">The input file must supply values for the identity columns.</span></span> <span data-ttu-id="e6944-160">Если эти значения не заданы, то для вставляемых строк создаются новые значения идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="e6944-160">If this is not set, new identity values are generated for the inserted rows.</span></span> <span data-ttu-id="e6944-161">Данные в файле, предназначенные для столбцов идентификаторов, не учитываются.</span><span class="sxs-lookup"><span data-stu-id="e6944-161">Any data present in the file for the identity columns is ignored.</span></span>  
  
 <span data-ttu-id="e6944-162">BCPKEEPNULLS</span><span class="sxs-lookup"><span data-stu-id="e6944-162">BCPKEEPNULLS</span></span>  
 <span data-ttu-id="e6944-163">Указывает, будут ли пустые значения данных в файле преобразовываться в значения NULL в таблице [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e6944-163">Specifies whether empty data values in the file will be converted to NULL values in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="e6944-164">Если *iValue* имеет значение true, пустые значения будут преобразованы в значение NULL в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] таблице.</span><span class="sxs-lookup"><span data-stu-id="e6944-164">When *iValue* is TRUE, empty values will be converted to NULL in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="e6944-165">По умолчанию пустые значения преобразовываются в значения по умолчанию для столбца в таблице [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , если значение по умолчанию существует.</span><span class="sxs-lookup"><span data-stu-id="e6944-165">The default is for empty values to be converted to a default value for the column in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table if a default exists.</span></span>  
  
 <span data-ttu-id="e6944-166">BCPLAST</span><span class="sxs-lookup"><span data-stu-id="e6944-166">BCPLAST</span></span>  
 <span data-ttu-id="e6944-167">Последняя строка для копирования.</span><span class="sxs-lookup"><span data-stu-id="e6944-167">Is the last row to copy.</span></span> <span data-ttu-id="e6944-168">По умолчанию установлено копирование всех строк; если задать для этого параметра значение меньше 1, то ему будет установлено значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6944-168">The default is to copy all rows; a value less than 1 resets this option to its default.</span></span>  
  
 <span data-ttu-id="e6944-169">BCPLASTEX</span><span class="sxs-lookup"><span data-stu-id="e6944-169">BCPLASTEX</span></span>  
 <span data-ttu-id="e6944-170">В операциях bcp out задает последнюю строку таблицы базы данных для копирования в файл данных.</span><span class="sxs-lookup"><span data-stu-id="e6944-170">For BCP out operations, specifies the last row of the database table to copy into the data file.</span></span>  
  
 <span data-ttu-id="e6944-171">В операциях bcp in задает последнюю строку файла данных для копирования в таблицу базы данных.</span><span class="sxs-lookup"><span data-stu-id="e6944-171">For BCP in operations, specifies the last row of the data file to copy into the database table.</span></span>  
  
 <span data-ttu-id="e6944-172">Параметр *iValue* должен быть адресом 64-разрядного целого числа со знаком, содержащим значение.</span><span class="sxs-lookup"><span data-stu-id="e6944-172">The *iValue* parameter is expected to be the address of a signed 64-bit integer containing the value.</span></span> <span data-ttu-id="e6944-173">Максимальное значение, передаваемое в BCPLASTEX, составляет 2^63-1.</span><span class="sxs-lookup"><span data-stu-id="e6944-173">The maximum value that can be passed to BCPLASTEX is 2^63-1.</span></span>  
  
 <span data-ttu-id="e6944-174">BCPMAXERRS</span><span class="sxs-lookup"><span data-stu-id="e6944-174">BCPMAXERRS</span></span>  
 <span data-ttu-id="e6944-175">Число ошибок, после которого произойдет сбой операции массового копирования.</span><span class="sxs-lookup"><span data-stu-id="e6944-175">Is the number of errors allowed before the bulk copy operation fails.</span></span> <span data-ttu-id="e6944-176">Значение по умолчанию — 10. значение меньше 1 сбрасывает этот параметр до значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6944-176">The default is 10; a value less than 1 resets this option to its default.</span></span> <span data-ttu-id="e6944-177">В операции массового копирования допускается не более 65 535 ошибок.</span><span class="sxs-lookup"><span data-stu-id="e6944-177">Bulk copy imposes a maximum of 65,535 errors.</span></span> <span data-ttu-id="e6944-178">Если выполнить попытку установить этот параметр в значение, превышающее 65 535, будет установлено значение 65 535.</span><span class="sxs-lookup"><span data-stu-id="e6944-178">An attempt to set this option to a value larger than 65,535 results in the option being set to 65,535.</span></span>  
  
 <span data-ttu-id="e6944-179">BCPODBC</span><span class="sxs-lookup"><span data-stu-id="e6944-179">BCPODBC</span></span>  
 <span data-ttu-id="e6944-180">Если значение равно TRUE, то указывает, что значения **DateTime** и **smalldatetime** , сохраненные в символьном формате, будут использовать префикс и суффикс последовательной отметки времени ODBC.</span><span class="sxs-lookup"><span data-stu-id="e6944-180">When TRUE, specifies that **datetime** and **smalldatetime** values saved in character format will use the ODBC timestamp escape sequence prefix and suffix.</span></span> <span data-ttu-id="e6944-181">Параметр BCPODBC применяется только к BCP_OUT.</span><span class="sxs-lookup"><span data-stu-id="e6944-181">The BCPODBC option only applies to BCP_OUT.</span></span>  
  
 <span data-ttu-id="e6944-182">При значении FALSE значение **DateTime** , представляющее 1 января 1997, преобразуется в символьную строку: 1997-01-01 00:00:00.000.</span><span class="sxs-lookup"><span data-stu-id="e6944-182">When FALSE, a **datetime** value representing January 1, 1997 is converted to the character string: 1997-01-01 00:00:00.000.</span></span> <span data-ttu-id="e6944-183">При значении TRUE одно и то же значение **DateTime** представлено следующим образом: {ts ' 1997-01-01 00:00:00.000 '}.</span><span class="sxs-lookup"><span data-stu-id="e6944-183">When TRUE, the same **datetime** value is represented as: {ts '1997-01-01 00:00:00.000'}.</span></span>  
  
 <span data-ttu-id="e6944-184">BCPROWCOUNT</span><span class="sxs-lookup"><span data-stu-id="e6944-184">BCPROWCOUNT</span></span>  
 <span data-ttu-id="e6944-185">Возвращает число строк, на которые распространяется действие текущей (или последней) операции bcp.</span><span class="sxs-lookup"><span data-stu-id="e6944-185">Returns the number of rows affected by the current (or last) BCP operation.</span></span>  
  
 <span data-ttu-id="e6944-186">BCPTEXTFILE</span><span class="sxs-lookup"><span data-stu-id="e6944-186">BCPTEXTFILE</span></span>  
 <span data-ttu-id="e6944-187">Значение TRUE указывает, что файл данных является текстовым, а не двоичным файлом.</span><span class="sxs-lookup"><span data-stu-id="e6944-187">When TRUE, specifies that the data file is a text file, rather than a binary file.</span></span> <span data-ttu-id="e6944-188">Если файл является текстовым, BCP определяет, является ли его кодировка кодировкой Юникод, путем проверки байтового маркера Юникода в первых двух байтах файла данных.</span><span class="sxs-lookup"><span data-stu-id="e6944-188">If the file is a text file, BCP determines whether or not it is Unicode by checking the Unicode byte marker in the first two bytes of the data file.</span></span>  
  
 <span data-ttu-id="e6944-189">BCPUNICODEFILE</span><span class="sxs-lookup"><span data-stu-id="e6944-189">BCPUNICODEFILE</span></span>  
 <span data-ttu-id="e6944-190">В значении TRUE указывает, что входной файл является файлом в кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="e6944-190">When TRUE, specifies the input file is a Unicode file.</span></span>  
  
 <span data-ttu-id="e6944-191">*iValue*</span><span class="sxs-lookup"><span data-stu-id="e6944-191">*iValue*</span></span>  
 <span data-ttu-id="e6944-192">Значение для указанного *eOption*.</span><span class="sxs-lookup"><span data-stu-id="e6944-192">Is the value for the specified *eOption*.</span></span> <span data-ttu-id="e6944-193">*iValue* — это целочисленное значение (лонглонг), приведенное к указателю void, чтобы обеспечить будущее расширение до 64 битовых значений.</span><span class="sxs-lookup"><span data-stu-id="e6944-193">*iValue* is an integer (LONGLONG) value cast to a void pointer to allow for future expansion to 64 bit values.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="e6944-194">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e6944-194">Returns</span></span>  
 <span data-ttu-id="e6944-195">SUCCEED или FAIL.</span><span class="sxs-lookup"><span data-stu-id="e6944-195">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6944-196">Remarks</span><span class="sxs-lookup"><span data-stu-id="e6944-196">Remarks</span></span>  
 <span data-ttu-id="e6944-197">Эта функция задает различные параметры управления для операций массового копирования, включая число ошибок, после которого массовое копирование будет отменено, номера первой и последней строк для копирования из файла данных, а также размер пакета.</span><span class="sxs-lookup"><span data-stu-id="e6944-197">This function sets various control parameters for bulk-copy operations, including the number of errors allowed before canceling a bulk copy, the numbers of the first and last rows to copy from a data file, and the batch size.</span></span>  
  
 <span data-ttu-id="e6944-198">Эта функция также используется для указания инструкции SELECT при массовом копировании результирующего набора инструкции SELECT из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6944-198">This function is also used to specify the SELECT statement when bulk copying out from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] the result set of a SELECT.</span></span> <span data-ttu-id="e6944-199">Присвойте параметру *eOption* значение bcphints а и задайте для *iValue* значение указатель на строку SQLTCHAR, содержащую инструкцию SELECT.</span><span class="sxs-lookup"><span data-stu-id="e6944-199">Set *eOption* to BCPHINTS and set *iValue* to have a pointer to an SQLTCHAR string containing the SELECT statement.</span></span>  
  
 <span data-ttu-id="e6944-200">Эти параметры управления имеют значение только при копировании между пользовательским файлом и таблицей [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6944-200">These control parameters are only meaningful when copying between a user file and an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="e6944-201">Параметры управления параметрами не влияют на строки, скопированные в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="e6944-201">Control parameter settings have no effect on rows copied to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6944-202">Пример</span><span class="sxs-lookup"><span data-stu-id="e6944-202">Example</span></span>  
  
```  
// Variables like henv not specified.  
SQLHDBC      hdbc;  
DBINT      nRowsProcessed;  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source, return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bulk copy.   
if (bcp_init(hdbc, _T("address"), _T("address.add"), _T("addr.err"),  
   DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Set the number of rows per batch.   
if (bcp_control(hdbc, BCPBATCH, (void*) 1000) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Set file column count.   
if (bcp_columns(hdbc, 1) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Set the file format.   
if (bcp_colfmt(hdbc, 1, 0, 0, SQL_VARLEN_DATA, '\n', 1, 1)  
   == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Execute the bulk copy.   
if (bcp_exec(hdbc, &nRowsProcessed) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
printf_s("%ld rows processed by bulk copy.", nRowsProcessed);  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6944-203">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6944-203">See Also</span></span>  
 [<span data-ttu-id="e6944-204">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="e6944-204">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
