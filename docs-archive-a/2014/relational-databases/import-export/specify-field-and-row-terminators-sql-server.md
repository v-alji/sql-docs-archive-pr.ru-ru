---
title: Определение признаков конца поля и строки (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bcp utility [SQL Server], terminators
- field terminators [SQL Server]
- data formats [SQL Server], terminators
- row terminators [SQL Server]
- terminators [SQL Server]
ms.assetid: f68b6782-f386-4947-93c4-e89110800704
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 548beeae68f5585c5cf2ba56b67027532ab43b71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749940"
---
# <a name="specify-field-and-row-terminators-sql-server"></a><span data-ttu-id="1cc33-102">Определение признаков конца поля и строки (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1cc33-102">Specify Field and Row Terminators (SQL Server)</span></span>
  <span data-ttu-id="1cc33-103">Для символьных полей данных можно определить символы, которые являются разделителями полей и строк в файле данных, указав *признак конца поля* и *признак конца строки*.</span><span class="sxs-lookup"><span data-stu-id="1cc33-103">For character data fields, optional terminating characters allow you to mark the end of each field in a data file with a *field terminator* and the end of each row with a *row terminator*.</span></span> <span data-ttu-id="1cc33-104">Для программ, считывающих файлы данных, это единственный способ определить, какими символами в нем разделяются строки и столбцы.</span><span class="sxs-lookup"><span data-stu-id="1cc33-104">Terminating characters are one way to indicate to programs that read the data file where one field or row ends and another field or row begins.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1cc33-105">При использовании собственного формата или собственного формата в кодировке Юникод вместо признаков конца поля используются префиксы длины.</span><span class="sxs-lookup"><span data-stu-id="1cc33-105">When you use native or Unicode native format, use length prefixes rather than field terminators.</span></span> <span data-ttu-id="1cc33-106">Данные в собственном формате могут конфликтовать со знаками завершения, так как файл данных в собственном формате хранится во внутреннем двоичном формате данных [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1cc33-106">Native format data can conflict with terminators because a native-format data file is stored in the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] internal binary data format.</span></span>  
  
## <a name="characters-supported-as-terminators"></a><span data-ttu-id="1cc33-107">Символы, поддерживаемые в качестве признаков конца полей и строк</span><span class="sxs-lookup"><span data-stu-id="1cc33-107">Characters Supported As Terminators</span></span>  
 <span data-ttu-id="1cc33-108">Команда **bcp** , инструкция BULK INSERT и поставщик больших наборов строк OPENROWSET поддерживают в качестве признака конца поля или строки различные знаки и всегда производят поиск первого вхождения указанного знака завершения.</span><span class="sxs-lookup"><span data-stu-id="1cc33-108">The **bcp** command, BULK INSERT statement, and the OPENROWSET bulk rowset provider support a variety of characters as field or row terminators and always look for the first instance of each terminator.</span></span> <span data-ttu-id="1cc33-109">В следующей таблице содержится список поддерживаемых в качестве признаков конца поля или строки символов.</span><span class="sxs-lookup"><span data-stu-id="1cc33-109">The following table lists the supported characters for terminators.</span></span>  
  
|<span data-ttu-id="1cc33-110">Символ признака</span><span class="sxs-lookup"><span data-stu-id="1cc33-110">Terminating character</span></span>|<span data-ttu-id="1cc33-111">Обозначается как</span><span class="sxs-lookup"><span data-stu-id="1cc33-111">Indicated by</span></span>|  
|---------------------------|------------------|  
|<span data-ttu-id="1cc33-112">Вкладка</span><span class="sxs-lookup"><span data-stu-id="1cc33-112">Tab</span></span>|<span data-ttu-id="1cc33-113">\t</span><span class="sxs-lookup"><span data-stu-id="1cc33-113">\t</span></span><br /><br /> <span data-ttu-id="1cc33-114">Признак конца поля по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1cc33-114">This is the default field terminator.</span></span>|  
|<span data-ttu-id="1cc33-115">Символ перевода строки</span><span class="sxs-lookup"><span data-stu-id="1cc33-115">Newline character</span></span>|<span data-ttu-id="1cc33-116">\n</span><span class="sxs-lookup"><span data-stu-id="1cc33-116">\n</span></span><br /><br /> <span data-ttu-id="1cc33-117">Признак конца строки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1cc33-117">This is the default row terminator.</span></span>|  
|<span data-ttu-id="1cc33-118">Возврат каретки и перевод строки</span><span class="sxs-lookup"><span data-stu-id="1cc33-118">Carriage return/line feed</span></span>|<span data-ttu-id="1cc33-119">\r</span><span class="sxs-lookup"><span data-stu-id="1cc33-119">\r</span></span>|  
|<span data-ttu-id="1cc33-120">Обратная косая черта<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1cc33-120">Backslash<sup>1</sup></span></span>|\\\|  
|<span data-ttu-id="1cc33-121">Символ завершения null (невидимый признак)<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="1cc33-121">Null terminator (nonvisible terminator)<sup>2</sup></span></span>|<span data-ttu-id="1cc33-122">\0</span><span class="sxs-lookup"><span data-stu-id="1cc33-122">\0</span></span>|  
|<span data-ttu-id="1cc33-123">Любой печатаемый символ (управляющие символы, за исключением символа NULL, символов табуляции, перевода строки и возврата каретки, являются непечатными)</span><span class="sxs-lookup"><span data-stu-id="1cc33-123">Any printable character (control characters are not printable, except null, tab, newline, and carriage return)</span></span>|<span data-ttu-id="1cc33-124">(\*, A, t, l и т. д.)</span><span class="sxs-lookup"><span data-stu-id="1cc33-124">(\*, A, t, l, and so on)</span></span>|  
|<span data-ttu-id="1cc33-125">Строка, которая может содержать до десяти печатных символов, включая некоторые или все указанные выше признаки конца</span><span class="sxs-lookup"><span data-stu-id="1cc33-125">String of up to 10 printable characters, including some or all of the terminators listed earlier</span></span>|<span data-ttu-id="1cc33-126">(\*\*\t\*\*, end, !!!!!!!!!!, \t-\n и т. д.)</span><span class="sxs-lookup"><span data-stu-id="1cc33-126">(\*\*\t\*\*, end, !!!!!!!!!!, \t-\n, and so on)</span></span>|  
  
 <span data-ttu-id="1cc33-127"><sup>1</sup> символы t, n, r, 0 и "\ 0" работают с escape-символом обратной косой черты для создания управляющего символа.</span><span class="sxs-lookup"><span data-stu-id="1cc33-127"><sup>1</sup> Only the t, n, r, 0 and '\0' characters work with the backslash escape character to produce a control character.</span></span>  
  
 <span data-ttu-id="1cc33-128"><sup>2</sup> несмотря на то, что управляющий символ null (\ 0) не отображается при печати, он является отдельным символом в файле данных.</span><span class="sxs-lookup"><span data-stu-id="1cc33-128"><sup>2</sup> Even though the null control character (\0) is not visible when printed, it is a distinct character in the data file.</span></span> <span data-ttu-id="1cc33-129">то есть если управляющий символ NULL используется в качестве признака конца поля или строки, то это не то же самое, что и полное отсутствие признака конца.</span><span class="sxs-lookup"><span data-stu-id="1cc33-129">This means that using the null control character as a field or row terminator is different than having no field or row terminator at all.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1cc33-130">Если символ признака конца поля или строки содержится в данных, он интерпретируется именно как признак, и данные после него интерпретируются как относящиеся к следующему полю или записи данных.</span><span class="sxs-lookup"><span data-stu-id="1cc33-130">If a terminator character occurs within the data, it is interpreted as a terminator, not as data, and the data after that character is interpreted as belonging to the next field or record.</span></span> <span data-ttu-id="1cc33-131">Поэтому следует выбирать символы признака конца так, чтобы они никогда не встречались в передаваемых данных.</span><span class="sxs-lookup"><span data-stu-id="1cc33-131">Therefore, choose your terminators carefully to make sure that they never appear in your data.</span></span> <span data-ttu-id="1cc33-132">Например, младший символ-заместитель признака конца поля не рекомендуется использовать в качестве признака конца поля, если этот младший символ-заместитель содержится в данных.</span><span class="sxs-lookup"><span data-stu-id="1cc33-132">For example, a low surrogate field terminator would not be a good choice for a field terminator if the data contains that low surrogate.</span></span>  
  
## <a name="using-row-terminators"></a><span data-ttu-id="1cc33-133">Использование признаков конца строки</span><span class="sxs-lookup"><span data-stu-id="1cc33-133">Using Row Terminators</span></span>  
 <span data-ttu-id="1cc33-134">Признаком конца строки может быть тот же символ, что и символ признака конца последнего поля.</span><span class="sxs-lookup"><span data-stu-id="1cc33-134">The row terminator can be the same character as the terminator for the last field.</span></span> <span data-ttu-id="1cc33-135">Но все же лучше выделить в качестве признака конца строки отдельный символ.</span><span class="sxs-lookup"><span data-stu-id="1cc33-135">Generally, however, a distinct row terminator is useful.</span></span> <span data-ttu-id="1cc33-136">Например, для формирования табличного вывода завершайте последнее поле каждой строки символом перевода строки (\n), а конец поля — символом табуляции (\t).</span><span class="sxs-lookup"><span data-stu-id="1cc33-136">For example, to produce tabular output, terminate the last field in each row with the newline character (\n) and all other fields with the tab character (\t).</span></span> <span data-ttu-id="1cc33-137">Чтобы каждая строка файла данных попала в отдельную строку таблицы, в качестве признака конца строки задайте сочетание \r\n.</span><span class="sxs-lookup"><span data-stu-id="1cc33-137">To place each data record on its own line in the data file, specify the combination \r\n as the row terminator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1cc33-138">Если при использовании **bcp** в интерактивном режиме в качестве признака конца строки задан знак \n (перевод строки), **bcp** автоматически добавляет к ней префикс \r (возврат каретки), в результате чего формируется признак конца строки \r\n.</span><span class="sxs-lookup"><span data-stu-id="1cc33-138">When you use **bcp** interactively and specify \n (newline) as the row terminator, **bcp** automatically prefixes it with a \r (carriage return) character, which results in a row terminator of \r\n.</span></span>  
  
## <a name="specifying-terminators-for-bulk-export"></a><span data-ttu-id="1cc33-139">Задание признаков конца полей и строк при массовом экспорте</span><span class="sxs-lookup"><span data-stu-id="1cc33-139">Specifying Terminators for Bulk Export</span></span>  
 <span data-ttu-id="1cc33-140">При выполнении операции с массовым экспортом `char` или `nchar` данными и необходимости использования признака конца, отличного от значения по умолчанию, необходимо указать признак конца для команды **bcp** .</span><span class="sxs-lookup"><span data-stu-id="1cc33-140">When you bulk export `char` or `nchar` data, and want to use a non-default terminator, you must specify the terminator to the **bcp** command.</span></span> <span data-ttu-id="1cc33-141">Это можно сделать одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="1cc33-141">You can specify terminators in any of the following ways:</span></span>  
  
-   <span data-ttu-id="1cc33-142">При помощи файла форматирования, задающего признаки конца каждого поля отдельно.</span><span class="sxs-lookup"><span data-stu-id="1cc33-142">With a format file that specifies the terminator on a field-by-field basis.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1cc33-143">Дополнительные сведения об использовании файлов форматирования см. в разделе [Файлы форматирования для импорта или экспорта данных (SQL Server )](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1cc33-143">For information about how to use format files, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
-   <span data-ttu-id="1cc33-144">Существуют также следующие возможности без использования файла форматирования:</span><span class="sxs-lookup"><span data-stu-id="1cc33-144">Without a format file, the following alternatives exist:</span></span>  
  
    -   <span data-ttu-id="1cc33-145">Указать параметр **-t**, задающий признак конца строки для всех полей, за исключением последнего поля в строке, и параметр **-r**, задающий признак конца строки.</span><span class="sxs-lookup"><span data-stu-id="1cc33-145">Using the **-t** switch to specify the row terminator for all the fields except the last field in the row and using the **-r** switch to specify a row terminator.</span></span>  
  
    -   <span data-ttu-id="1cc33-146">Указать параметр символьного формата ( **-c** или **-w**) без параметра **-t** , который задает в качестве признака конца поля знак табуляции \t.</span><span class="sxs-lookup"><span data-stu-id="1cc33-146">Using a character-format switch (**-c** or **-w**) without the **-t** switch, which sets the field terminator to the tab character, \t.</span></span> <span data-ttu-id="1cc33-147">Это аналогично указанию **-t**\t.</span><span class="sxs-lookup"><span data-stu-id="1cc33-147">This is the same as specifying **-t**\t.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="1cc33-148">Если указан параметр **-n** (данные в собственном формате) или **-N** (данные в собственном формате в кодировке Юникод), то признаки конца полей и строк не вставляются.</span><span class="sxs-lookup"><span data-stu-id="1cc33-148">If you specify the **-n** (native data) or **-N** (Unicode native) switch, terminators are not inserted.</span></span>  
  
    -   <span data-ttu-id="1cc33-149">Если интерактивная команда **bcp** содержит параметр **in** или **out** без указания параметра файла форматирования ( **-f**) или параметра формата данных ( **-n**, **-c**, **-w**или **-N**) и если предписано не указывать длину префикса и поля, команда предлагает пользователю указать признак конца каждого поля, причем по умолчанию признак конца отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1cc33-149">If an interactive **bcp** command contains the **in** or **out** option without either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**), and you have chosen not to specify prefix length and field length, the command prompts for the field terminator of each field, with a default of none:</span></span>  
  
         `Enter field terminator [none]:`  
  
         <span data-ttu-id="1cc33-150">Обычно приемлемо значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1cc33-150">Generally, the default is a suitable choice.</span></span> <span data-ttu-id="1cc33-151">Однако для полей данных типа `char` или `nchar` существуют особенности, которые рассмотрены в следующем подразделе «Правила использования признаков конца полей и строк».</span><span class="sxs-lookup"><span data-stu-id="1cc33-151">However, for `char` or `nchar` data fields, see the following subsection, "Guidelines for Using Terminators."</span></span> <span data-ttu-id="1cc33-152">Пример с описанием данного запроса см. в разделе [Указание форматов данных для совместимости с помощью программы bcp (SQL Server)](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1cc33-152">For an example that shows this prompt in context, see [Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="1cc33-153">После интерактивного заполнения всех полей в команде **bcp** появится запрос на сохранение введенных ответов для каждого поля в файле форматирования в формате, отличном от XML.</span><span class="sxs-lookup"><span data-stu-id="1cc33-153">After you interactively specify all of the fields in a **bcp** command, the command prompts you save your responses for each field in a non-XML format file.</span></span> <span data-ttu-id="1cc33-154">Дополнительные сведения о файлах форматирования в формате, отличном от XML, см. в разделе [Файлы формата, отличные от XML (SQL Server)](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1cc33-154">For more information about non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="guidelines-for-using-terminators"></a><span data-ttu-id="1cc33-155">Рекомендации по использованию признаков конца полей и строк</span><span class="sxs-lookup"><span data-stu-id="1cc33-155">Guidelines for Using Terminators</span></span>  
 <span data-ttu-id="1cc33-156">В некоторых ситуациях для данных типа `char` или `nchar` имеет смысл использовать признаки конца поля,</span><span class="sxs-lookup"><span data-stu-id="1cc33-156">In some situations, a terminator is useful for a `char` or `nchar` data field.</span></span> <span data-ttu-id="1cc33-157">Пример:</span><span class="sxs-lookup"><span data-stu-id="1cc33-157">For example:</span></span>  
  
-   <span data-ttu-id="1cc33-158">Для столбца данных, содержащего значение NULL в файле данных, который будет импортирован в программу, не распознающую сведения о длине префикса.</span><span class="sxs-lookup"><span data-stu-id="1cc33-158">For a data column that contains a null value in a data file that will be imported into a program that does not understand the prefix length information.</span></span>  
  
     <span data-ttu-id="1cc33-159">Любой столбец данных, содержащий значение NULL, считается столбцом переменной длины.</span><span class="sxs-lookup"><span data-stu-id="1cc33-159">Any data column that contains a null value is considered variable length.</span></span> <span data-ttu-id="1cc33-160">В отсутствие сведений о длине префикса признак конца необходим, чтобы указать конец поля NULL и удостовериться, что данные интерпретируются верно.</span><span class="sxs-lookup"><span data-stu-id="1cc33-160">In the absence of prefix lengths, a terminator is necessary to identify the end of a null field, making sure that the data is correctly interpreted.</span></span>  
  
-   <span data-ttu-id="1cc33-161">Длинный столбец фиксированной длины, пространство которого лишь частично используется многими строками.</span><span class="sxs-lookup"><span data-stu-id="1cc33-161">For a long fixed-length column whose space is only partially used by many rows.</span></span>  
  
     <span data-ttu-id="1cc33-162">В этой ситуации задание признака конца может минимизировать занимаемый данными объем, что позволит обрабатывать поле как поле переменной длины.</span><span class="sxs-lookup"><span data-stu-id="1cc33-162">In this situation, specifying a terminator can minimize storage space allowing the field to be treated as a variable-length field.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="1cc33-163">Примеры</span><span class="sxs-lookup"><span data-stu-id="1cc33-163">Examples</span></span>  
 <span data-ttu-id="1cc33-164">В этом примере выполняется массовый экспорт данных из таблицы `AdventureWorks``HumanResources.Department` в файл данных `Department-c-t.txt` в символьном формате с запятой в качестве признака конца поля и знаком новой строки (\n) в качестве признака конца строки.</span><span class="sxs-lookup"><span data-stu-id="1cc33-164">This example bulk exports the data from the `AdventureWorks``HumanResources.Department` table to the `Department-c-t.txt` data file using character format, with a comma as a field terminator and the newline character (\n) as the row terminator.</span></span>  
  
 <span data-ttu-id="1cc33-165">Команда **bcp** поддерживает следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="1cc33-165">The **bcp** command contains the following switches.</span></span>  
  
|<span data-ttu-id="1cc33-166">Параметр</span><span class="sxs-lookup"><span data-stu-id="1cc33-166">Switch</span></span>|<span data-ttu-id="1cc33-167">Описание</span><span class="sxs-lookup"><span data-stu-id="1cc33-167">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1cc33-168">**-c**</span><span class="sxs-lookup"><span data-stu-id="1cc33-168">**-c**</span></span>|<span data-ttu-id="1cc33-169">Указывает, что поля данных должны загружаться как символьные данные.</span><span class="sxs-lookup"><span data-stu-id="1cc33-169">Specifies that the data fields be loaded as character data.</span></span>|  
|<span data-ttu-id="1cc33-170">**-t** `,`</span><span class="sxs-lookup"><span data-stu-id="1cc33-170">**-t** `,`</span></span>|<span data-ttu-id="1cc33-171">Задает запятую (,) в качестве признака конца поля.</span><span class="sxs-lookup"><span data-stu-id="1cc33-171">Specifies a comma (,) as the field terminator.</span></span>|  
|<span data-ttu-id="1cc33-172">**-r** \n</span><span class="sxs-lookup"><span data-stu-id="1cc33-172">**-r** \n</span></span>|<span data-ttu-id="1cc33-173">Задает в качестве признака конца строки символ перевода строки.</span><span class="sxs-lookup"><span data-stu-id="1cc33-173">Specifies the row terminator as a newline character.</span></span> <span data-ttu-id="1cc33-174">Это признак конца строки по умолчанию, поэтому его задание необязательно.</span><span class="sxs-lookup"><span data-stu-id="1cc33-174">This is the default row terminator, so specifying it is optional.</span></span>|  
|<span data-ttu-id="1cc33-175">**-T**</span><span class="sxs-lookup"><span data-stu-id="1cc33-175">**-T**</span></span>|<span data-ttu-id="1cc33-176">Указывает, что программа **bcp** устанавливает доверительное соединение с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с использованием встроенной безопасности.</span><span class="sxs-lookup"><span data-stu-id="1cc33-176">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="1cc33-177">Если параметр **-T** не указан, для входа необходимо указать **-U** и **-P** .</span><span class="sxs-lookup"><span data-stu-id="1cc33-177">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="1cc33-178">Дополнительные сведения см. в разделе [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="1cc33-178">For more information, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
 <span data-ttu-id="1cc33-179">В командной строке [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows введите:</span><span class="sxs-lookup"><span data-stu-id="1cc33-179">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.Department out C:\myDepartment-c-t.txt -c -t, -r \n -T  
```  
  
 <span data-ttu-id="1cc33-180">В результате этого будет создан файл `Department-c-t.txt`, содержащий 16 записей, каждая из которых имеет четыре поля.</span><span class="sxs-lookup"><span data-stu-id="1cc33-180">This creates `Department-c-t.txt`, which contains 16 records with four fields each.</span></span> <span data-ttu-id="1cc33-181">Поля разделены с помощью символа запятой.</span><span class="sxs-lookup"><span data-stu-id="1cc33-181">The fields are separated by a comma.</span></span>  
  
## <a name="specifying-terminators-for-bulk-import"></a><span data-ttu-id="1cc33-182">Задание признаков конца для массового импорта</span><span class="sxs-lookup"><span data-stu-id="1cc33-182">Specifying Terminators for Bulk Import</span></span>  
 <span data-ttu-id="1cc33-183">При выполнении массового импорта данных типа `char` или `nchar` команда должна распознавать признаки конца полей и строк, используемые в файле данных.</span><span class="sxs-lookup"><span data-stu-id="1cc33-183">When you bulk import `char` or `nchar` data, the bulk-import command must recognize the terminators that are used in the data file.</span></span> <span data-ttu-id="1cc33-184">В зависимости от команды массового импорта признаки конца полей и строк могут задаваться следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1cc33-184">How terminators can be specified depends on the bulk-import command, as follows:</span></span>  
  
-   <span data-ttu-id="1cc33-185">**bcp**</span><span class="sxs-lookup"><span data-stu-id="1cc33-185">**bcp**</span></span>  
  
     <span data-ttu-id="1cc33-186">При определении признака конца полей и строк в операциях импорта используется тот же самый синтаксис, что и для операций экспорта.</span><span class="sxs-lookup"><span data-stu-id="1cc33-186">Specifying terminators for an import operation uses the same syntax as for an export operation.</span></span> <span data-ttu-id="1cc33-187">Дополнительные сведения см. в подразделе «Задание признаков конца полей и строк при массовом экспорте» ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1cc33-187">For more information, see "Specifying Terminators for Bulk Export," earlier in this topic.</span></span>  
  
-   <span data-ttu-id="1cc33-188">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="1cc33-188">BULK INSERT</span></span>  
  
     <span data-ttu-id="1cc33-189">Признаки конца в файле форматирования могут быть определены как для отдельных полей, так и для всего файла данных при помощи квалификаторов, приведенных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="1cc33-189">Terminators can be specified for individual fields in a format file or for the whole data file by using the qualifiers shown in the following table.</span></span>  
  
    |<span data-ttu-id="1cc33-190">Квалификатор</span><span class="sxs-lookup"><span data-stu-id="1cc33-190">Qualifier</span></span>|<span data-ttu-id="1cc33-191">Описание</span><span class="sxs-lookup"><span data-stu-id="1cc33-191">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="1cc33-192">FIELDTERMINATOR **= " *`field_terminator`* "**</span><span class="sxs-lookup"><span data-stu-id="1cc33-192">FIELDTERMINATOR **='*`field_terminator`*'**</span></span>|<span data-ttu-id="1cc33-193">Задает признак конца поля, используемый для символьных файлов данных и файлов в кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="1cc33-193">Specifies the field terminator to be used for character and Unicode character data files.</span></span><br /><br /> <span data-ttu-id="1cc33-194">Значением по умолчанию является \t (символ табуляции).</span><span class="sxs-lookup"><span data-stu-id="1cc33-194">The default is \t (tab character).</span></span>|  
    |<span data-ttu-id="1cc33-195">ROWTERMINATOR **= " *`row_terminator`* "**</span><span class="sxs-lookup"><span data-stu-id="1cc33-195">ROWTERMINATOR **='*`row_terminator`*'**</span></span>|<span data-ttu-id="1cc33-196">Задает признак конца строки, используемый для символьных файлов данных и файлов в кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="1cc33-196">Specifies the row terminator to be used for character and Unicode character data files.</span></span><br /><br /> <span data-ttu-id="1cc33-197">Значением по умолчанию является \n (символ перевода строки).</span><span class="sxs-lookup"><span data-stu-id="1cc33-197">The default is \n (newline character).</span></span>|  
  
     <span data-ttu-id="1cc33-198">Дополнительные сведения см. в разделе [BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1cc33-198">For more information, see [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
-   <span data-ttu-id="1cc33-199">Инструкции INSERT ... SELECT \* FROM OPENROWSET(BULK...).</span><span class="sxs-lookup"><span data-stu-id="1cc33-199">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>  
  
     <span data-ttu-id="1cc33-200">Для поставщика массовых наборов строк OPENROWSET признаки конца могут задаваться только в файле форматирования (который обязателен для всех типов данных, кроме типа данных больших объектов).</span><span class="sxs-lookup"><span data-stu-id="1cc33-200">For the OPENROWSET bulk rowset provider, terminators can be specified only in the format file (which is required except for large-object data types).</span></span> <span data-ttu-id="1cc33-201">Если в файле символьных данных используется признак, отличный от установленного по умолчанию, он должен быть определен в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="1cc33-201">If a character data file uses a non-default terminator, it must be defined in the format file.</span></span> <span data-ttu-id="1cc33-202">Дополнительные сведения см. в разделах [Создание файла форматирования (SQL Server)](create-a-format-file-sql-server.md) и [Использование файла форматирования для массового импорта данных (SQL Server)](use-a-format-file-to-bulk-import-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1cc33-202">For more information, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md) and [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span></span>  
  
     <span data-ttu-id="1cc33-203">Дополнительные сведения о предложении OPENROWSET BULK см. в разделе [OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1cc33-203">For more information about the OPENROWSET BULK clause, see [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="1cc33-204">Примеры</span><span class="sxs-lookup"><span data-stu-id="1cc33-204">Examples</span></span>  
 <span data-ttu-id="1cc33-205">В примерах, содержащихся в этом разделе, рассматривается массовый импорт символьных данных из файла данных `Department-c-t.txt` , созданного в предыдущем примере, в таблицу `myDepartment` образца базы данных [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1cc33-205">The examples in this section bulk import character data form the `Department-c-t.txt` data file created in the preceding example into the `myDepartment` table in the [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] sample database.</span></span> <span data-ttu-id="1cc33-206">Перед выполнением примеров следует создать эту таблицу.</span><span class="sxs-lookup"><span data-stu-id="1cc33-206">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="1cc33-207">Для этого в схеме **dbo** в редакторе запросов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните следующий код:</span><span class="sxs-lookup"><span data-stu-id="1cc33-207">To create this table under the **dbo** schema, in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>  
  
```  
USE AdventureWorks;  
GO  
DROP TABLE myDepartment;  
CREATE TABLE myDepartment   
(DepartmentID smallint,  
Name nvarchar(50),  
GroupName nvarchar(50) NULL,  
ModifiedDate datetime not NULL CONSTRAINT DF_AddressType_ModifiedDate DEFAULT (GETDATE())  
);  
GO  
  
```  
  
#### <a name="a-using-bcp-to-interactively-specify-terminators"></a><span data-ttu-id="1cc33-208">A.</span><span class="sxs-lookup"><span data-stu-id="1cc33-208">A.</span></span> <span data-ttu-id="1cc33-209">Задание признаков конца полей и строк в интерактивном режиме с помощью bcp</span><span class="sxs-lookup"><span data-stu-id="1cc33-209">Using bcp to interactively specify terminators</span></span>  
 <span data-ttu-id="1cc33-210">В следующем примере выполняется массовый импорт файла данных `Department-c-t.txt` при помощи команды `bcp` .</span><span class="sxs-lookup"><span data-stu-id="1cc33-210">The following example bulk imports the `Department-c-t.txt` data file using a `bcp` command.</span></span> <span data-ttu-id="1cc33-211">Эта команда использует те же самые параметры, что и команда массового экспорта.</span><span class="sxs-lookup"><span data-stu-id="1cc33-211">This command uses the same command switches as the bulk export command.</span></span> <span data-ttu-id="1cc33-212">Дополнительные сведения см. в подразделе «Задание признаков конца полей и строк при массовом экспорте» ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1cc33-212">For more information, see "Specifying Terminators for Bulk Export," earlier in this topic.</span></span>  
  
 <span data-ttu-id="1cc33-213">В командной строке Windows введите:</span><span class="sxs-lookup"><span data-stu-id="1cc33-213">At the Windows command prompt enter:</span></span>  
  
```  
bcp AdventureWorks..myDepartment in C:\myDepartment-c-t.txt -c -t , -r \n -T  
```  
  
#### <a name="b-using-bulk-insert-to-interactively-specify-terminators"></a><span data-ttu-id="1cc33-214">Б.</span><span class="sxs-lookup"><span data-stu-id="1cc33-214">B.</span></span> <span data-ttu-id="1cc33-215">Задание признаков конца в интерактивном режиме с помощью инструкции BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="1cc33-215">Using BULK INSERT to interactively specify terminators</span></span>  
 <span data-ttu-id="1cc33-216">В следующем примере производится массовый импорт файла данных `Department-c-t.txt` инструкцией `BULK INSERT` , которая использует квалификаторы, показанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="1cc33-216">The following example bulk imports the `Department-c-t.txt` data file using a `BULK INSERT` statement that uses the qualifiers shown in the following table.</span></span>  
  
|<span data-ttu-id="1cc33-217">Параметр</span><span class="sxs-lookup"><span data-stu-id="1cc33-217">Option</span></span>|<span data-ttu-id="1cc33-218">attribute</span><span class="sxs-lookup"><span data-stu-id="1cc33-218">Attribute</span></span>|  
|------------|---------------|  
|<span data-ttu-id="1cc33-219">DATAFILETYPE **= " `char` "**</span><span class="sxs-lookup"><span data-stu-id="1cc33-219">DATAFILETYPE **='`char`'**</span></span>|<span data-ttu-id="1cc33-220">Указывает, что поля данных должны загружаться как символьные данные.</span><span class="sxs-lookup"><span data-stu-id="1cc33-220">Specifies that the data fields be loaded as character data.</span></span>|  
|<span data-ttu-id="1cc33-221">FIELDTERMINATOR **='** `,` **'**</span><span class="sxs-lookup"><span data-stu-id="1cc33-221">FIELDTERMINATOR **='**`,`**'**</span></span>|<span data-ttu-id="1cc33-222">Задает запятую (`,`) в качестве признака конца поля.</span><span class="sxs-lookup"><span data-stu-id="1cc33-222">Specifies a comma (`,`) as the field terminator.</span></span>|  
|<span data-ttu-id="1cc33-223">ROWTERMINATOR **='** `\n` **'**</span><span class="sxs-lookup"><span data-stu-id="1cc33-223">ROWTERMINATOR **='**`\n`**'**</span></span>|<span data-ttu-id="1cc33-224">Задает в качестве признака конца строки символ перевода строки.</span><span class="sxs-lookup"><span data-stu-id="1cc33-224">Specifies the row terminator as a newline character.</span></span>|  
  
 <span data-ttu-id="1cc33-225">В редакторе запросов в среде [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] выполните следующий код:</span><span class="sxs-lookup"><span data-stu-id="1cc33-225">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT myDepartment FROM 'C:\myDepartment-c-t.txt'  
   WITH (  
      DATAFILETYPE = 'char',  
      FIELDTERMINATOR = ',',  
      ROWTERMINATOR = '\n'  
);  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="1cc33-226">См. также:</span><span class="sxs-lookup"><span data-stu-id="1cc33-226">See Also</span></span>  
 <span data-ttu-id="1cc33-227">[bcp Utility](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="1cc33-227">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="1cc33-228">[BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1cc33-228">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="1cc33-229">[OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1cc33-229">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="1cc33-230">[Указание длины поля с помощью программы bcp (SQL Server)](specify-field-length-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1cc33-230">[Specify Field Length by Using bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md) </span></span>  
 <span data-ttu-id="1cc33-231">[Определение длины префикса в файлах данных с помощью программы bcp (SQL Server)](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1cc33-231">[Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md) </span></span>  
 [<span data-ttu-id="1cc33-232">Указание типа файлового хранилища с помощью программы bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1cc33-232">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
  
