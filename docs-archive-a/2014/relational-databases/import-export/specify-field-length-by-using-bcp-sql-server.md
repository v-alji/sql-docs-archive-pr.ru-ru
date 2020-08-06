---
title: Указание длины поля с помощью программы bcp (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- native data format [SQL Server]
- default field lengths
- field length [SQL Server]
- data formats [SQL Server], field length
- bcp utility [SQL Server], field length
ms.assetid: 240f33ca-ef4a-413a-a4de-831885cb505b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 13343b4f3778df1bbe7ef1c99b3d06338f18631c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729482"
---
# <a name="specify-field-length-by-using-bcp-sql-server"></a><span data-ttu-id="f14a7-102">Указание длины поля с помощью программы bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f14a7-102">Specify Field Length by Using bcp (SQL Server)</span></span>
  <span data-ttu-id="f14a7-103">Длина поля указывает максимальное количество символов, необходимых для представления данных в символьном формате.</span><span class="sxs-lookup"><span data-stu-id="f14a7-103">The field length indicates the maximum number of characters that are required to represent data in character format.</span></span> <span data-ttu-id="f14a7-104">Длина поля известна заранее, если данные хранятся в собственном формате, например значение типа `int` занимает 4 байта.</span><span class="sxs-lookup"><span data-stu-id="f14a7-104">The field length is already known if the data is stored in the native format; for example, the `int` data type takes 4 bytes.</span></span> <span data-ttu-id="f14a7-105">Если для длины префикса указано значение 0, то команда **bcp** запрашивает длину поля, длину полей по умолчанию и влияние длины поля на хранение данных в файлах данных, содержащих `char` данные.</span><span class="sxs-lookup"><span data-stu-id="f14a7-105">If you have indicated 0 for the prefix length, the **bcp** command prompts you for field length, the default field lengths, and the impact of field-length on data storage in data files that contain `char` data.</span></span>  
  
## <a name="the-bcp-prompt-for-field-length"></a><span data-ttu-id="f14a7-106">Запрос командой bcp значения длины поля</span><span class="sxs-lookup"><span data-stu-id="f14a7-106">The bcp Prompt for Field Length</span></span>  
 <span data-ttu-id="f14a7-107">Если интерактивная команда **bcp** содержит параметр **in** или **out** без параметра файла форматирования ( **-f**) либо параметра формата данных ( **-n**, **-c**, **-w** или **-N**), то команда запрашивает длину каждого поля данных следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f14a7-107">If an interactive **bcp** command contains the **in** or **out** option without either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**), the command prompts for the field length of each data field, as follows:</span></span>  
  
 `Enter length of field <field_name> [<default>]:`  
  
 <span data-ttu-id="f14a7-108">Пример с описанием данного запроса см. в разделе [Указание форматов данных для совместимости с помощью программы bcp (SQL Server)](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f14a7-108">For an example that shows this prompt in context, see [Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f14a7-109">После интерактивного заполнения всех полей в команде **bcp** появится запрос на сохранение введенных ответов для каждого поля в файле форматирования в формате, отличном от XML.</span><span class="sxs-lookup"><span data-stu-id="f14a7-109">After you interactively specify all of the fields in a **bcp** command, the command prompts you save your responses for each field in a non-XML format file.</span></span> <span data-ttu-id="f14a7-110">Дополнительные сведения о файлах форматирования в формате, отличном от XML, см. в разделе [Файлы формата, отличные от XML (SQL Server)](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f14a7-110">For more information on non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
 <span data-ttu-id="f14a7-111">Будут ли командные строки **bcp** выводить запросы для указания значений длины полей, зависит от нескольких факторов, как указано ниже.</span><span class="sxs-lookup"><span data-stu-id="f14a7-111">Whether a **bcp** command prompts for field length depends on several factors, as follows:</span></span>  
  
-   <span data-ttu-id="f14a7-112">Если происходит копирование данных таких типов, которые не имеют постоянной длины, и задана длина префикса, равная 0, то **bcp** выводит приглашения для указания длины полей.</span><span class="sxs-lookup"><span data-stu-id="f14a7-112">When you copy data types that are not of fixed length and you specify a prefix length of 0, **bcp** prompts for a field length.</span></span>  
  
-   <span data-ttu-id="f14a7-113">Если происходит преобразование несимвольных данных в символьные данные, то **bcp** предлагает по умолчанию длину поля, достаточно большую для сохранения данных.</span><span class="sxs-lookup"><span data-stu-id="f14a7-113">When converting noncharacter data to character data, **bcp** suggests a default field length large enough to store the data.</span></span>  
  
-   <span data-ttu-id="f14a7-114">Если по своему типу хранилище файлов не является символьным, то команда **bcp** не выводит приглашения для указания длины полей.</span><span class="sxs-lookup"><span data-stu-id="f14a7-114">If the file storage type is noncharacter, the **bcp** command does not prompt for a field length.</span></span> <span data-ttu-id="f14a7-115">Данные хранятся в собственном представлении данных [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (в собственном формате).</span><span class="sxs-lookup"><span data-stu-id="f14a7-115">The data is stored in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data representation (native format).</span></span>  
  
## <a name="using-default-field-lengths"></a><span data-ttu-id="f14a7-116">Использование значения длины поля по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f14a7-116">Using Default Field Lengths</span></span>  
 <span data-ttu-id="f14a7-117">В общем случае [!INCLUDE[msCoName](../../includes/msconame-md.md)] рекомендует принимать значения по умолчанию для длины полей, предлагаемые командой **bcp**.</span><span class="sxs-lookup"><span data-stu-id="f14a7-117">Generally, [!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that you accept the **bcp**-suggested default values for the field length.</span></span> <span data-ttu-id="f14a7-118">Использование значений длины поля по умолчанию при создании файла символьных данных помогает избежать усечения данных и возникновения ошибок переполнения.</span><span class="sxs-lookup"><span data-stu-id="f14a7-118">When a character mode data file is created, using the default field length ensures that data is not truncated and that numeric overflow errors do not occur.</span></span>  
  
 <span data-ttu-id="f14a7-119">При указании некорректного значения длины поля могут возникнуть проблемы.</span><span class="sxs-lookup"><span data-stu-id="f14a7-119">If you specify a field length that is incorrect, problems can occur.</span></span> <span data-ttu-id="f14a7-120">Например, если при копировании числовых данных была задана слишком малая длина поля, программа **bcp** выдает сообщение о переполнении, а копирование данных не выполняется.</span><span class="sxs-lookup"><span data-stu-id="f14a7-120">For instance, if you copy numeric data and you specify a field length that is too short for the data, the **bcp** utility prints an overflow message and does not copy the data.</span></span> <span data-ttu-id="f14a7-121">Кроме того, при экспорте `datetime` данных и задании длины поля менее 26 байт для символьной строки программа **bcp** усекает данные без сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="f14a7-121">Also, if you export `datetime` data and specify a field length of less than 26 bytes for the character string, the **bcp** utility truncates the data without an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f14a7-122">При использовании размера, заданного по умолчанию, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] считывает всю строку.</span><span class="sxs-lookup"><span data-stu-id="f14a7-122">When the default size option is used, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] expects to read an entire string.</span></span> <span data-ttu-id="f14a7-123">В некоторых случаях использование значения длины поля по умолчанию приводит к возникновению ошибки «неожиданный конец файла».</span><span class="sxs-lookup"><span data-stu-id="f14a7-123">In some situations, use of a default field length can lead to an "unexpected end of file" error.</span></span> <span data-ttu-id="f14a7-124">Как правило, эта ошибка возникает с `money` `datetime` типами данных и, если только часть ожидаемого поля встречается в файле данных. Например, если `datetime` значение *mm* / *DD* / *гг* задано без компонента времени и имеет значение, оно короче ожидаемой 24-символьной длины `datetime` значения в `char` формате.</span><span class="sxs-lookup"><span data-stu-id="f14a7-124">Typically, this error occurs with the `money` and `datetime` data types when only part of the expected field occurs in the data file; for example, when a `datetime` value of *mm*/*dd*/*yy* is specified without the time component and is, therefore, shorter than the expected 24 character length of a `datetime` value in `char` format.</span></span> <span data-ttu-id="f14a7-125">Чтобы избежать указанной ошибки типов, необходимо использовать признаки конца поля или файлы данных фиксированной длины, либо изменить значение длины поля по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f14a7-125">To avoid this type of error, use field terminators or fixed-length data fields, or change the default field length by specifying another value.</span></span>  
  
### <a name="default-field-lengths-for-character-file-storage"></a><span data-ttu-id="f14a7-126">Значения длины поля по умолчанию для файлов символьных данных</span><span class="sxs-lookup"><span data-stu-id="f14a7-126">Default Field Lengths for Character File Storage</span></span>  
 <span data-ttu-id="f14a7-127">В представленной ниже таблице приведены значения длины поля для данных, хранимых в символьной форме.</span><span class="sxs-lookup"><span data-stu-id="f14a7-127">The following table lists the default field lengths for data to be stored as a character-file storage type.</span></span> <span data-ttu-id="f14a7-128">Данные, которые могут и не могут принимать значение NULL, имеют одинаковую длину поля.</span><span class="sxs-lookup"><span data-stu-id="f14a7-128">Nullable data is the same length as nonnull data.</span></span>  
  
|<span data-ttu-id="f14a7-129">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f14a7-129">Data type</span></span>|<span data-ttu-id="f14a7-130">Длина по умолчанию (в символах)</span><span class="sxs-lookup"><span data-stu-id="f14a7-130">Default length (characters)</span></span>|  
|---------------|-----------------------------------|  
|`char`|<span data-ttu-id="f14a7-131">Длина, определенная для столбца</span><span class="sxs-lookup"><span data-stu-id="f14a7-131">Length defined for the column</span></span>|  
|`varchar`|<span data-ttu-id="f14a7-132">Длина, определенная для столбца</span><span class="sxs-lookup"><span data-stu-id="f14a7-132">Length defined for the column</span></span>|  
|`nchar`|<span data-ttu-id="f14a7-133">Удвоенная длина, определенная для столбца</span><span class="sxs-lookup"><span data-stu-id="f14a7-133">Twice the length defined for the column</span></span>|  
|`nvarchar`|<span data-ttu-id="f14a7-134">Удвоенная длина, определенная для столбца</span><span class="sxs-lookup"><span data-stu-id="f14a7-134">Twice the length defined for the column</span></span>|  
|`Text`|<span data-ttu-id="f14a7-135">0</span><span class="sxs-lookup"><span data-stu-id="f14a7-135">0</span></span>|  
|`ntext`|<span data-ttu-id="f14a7-136">0</span><span class="sxs-lookup"><span data-stu-id="f14a7-136">0</span></span>|  
|`bit`|<span data-ttu-id="f14a7-137">1</span><span class="sxs-lookup"><span data-stu-id="f14a7-137">1</span></span>|  
|`binary`|<span data-ttu-id="f14a7-138">Удвоенная длина, определенная для столбца + 1</span><span class="sxs-lookup"><span data-stu-id="f14a7-138">Twice the length defined for the column + 1</span></span>|  
|`varbinary`|<span data-ttu-id="f14a7-139">Удвоенная длина, определенная для столбца + 1</span><span class="sxs-lookup"><span data-stu-id="f14a7-139">Twice the length defined for the column + 1</span></span>|  
|`image`|<span data-ttu-id="f14a7-140">0</span><span class="sxs-lookup"><span data-stu-id="f14a7-140">0</span></span>|  
|`datetime`|<span data-ttu-id="f14a7-141">24</span><span class="sxs-lookup"><span data-stu-id="f14a7-141">24</span></span>|  
|`smalldatetime`|<span data-ttu-id="f14a7-142">24</span><span class="sxs-lookup"><span data-stu-id="f14a7-142">24</span></span>|  
|`float`|<span data-ttu-id="f14a7-143">30</span><span class="sxs-lookup"><span data-stu-id="f14a7-143">30</span></span>|  
|`real`|<span data-ttu-id="f14a7-144">30</span><span class="sxs-lookup"><span data-stu-id="f14a7-144">30</span></span>|  
|`int`|<span data-ttu-id="f14a7-145">12</span><span class="sxs-lookup"><span data-stu-id="f14a7-145">12</span></span>|  
|`bigint`|<span data-ttu-id="f14a7-146">19</span><span class="sxs-lookup"><span data-stu-id="f14a7-146">19</span></span>|  
|`smallint`|<span data-ttu-id="f14a7-147">7</span><span class="sxs-lookup"><span data-stu-id="f14a7-147">7</span></span>|  
|`tinyint`|<span data-ttu-id="f14a7-148">5</span><span class="sxs-lookup"><span data-stu-id="f14a7-148">5</span></span>|  
|`money`|<span data-ttu-id="f14a7-149">30</span><span class="sxs-lookup"><span data-stu-id="f14a7-149">30</span></span>|  
|`smallmoney`|<span data-ttu-id="f14a7-150">30</span><span class="sxs-lookup"><span data-stu-id="f14a7-150">30</span></span>|  
|`decimal`|<span data-ttu-id="f14a7-151">41\*</span><span class="sxs-lookup"><span data-stu-id="f14a7-151">41\*</span></span>|  
|`numeric`|<span data-ttu-id="f14a7-152">41\*</span><span class="sxs-lookup"><span data-stu-id="f14a7-152">41\*</span></span>|  
|`uniqueidentifier`|<span data-ttu-id="f14a7-153">37</span><span class="sxs-lookup"><span data-stu-id="f14a7-153">37</span></span>|  
|`timestamp`|<span data-ttu-id="f14a7-154">17</span><span class="sxs-lookup"><span data-stu-id="f14a7-154">17</span></span>|  
|`varchar(max)`|<span data-ttu-id="f14a7-155">0</span><span class="sxs-lookup"><span data-stu-id="f14a7-155">0</span></span>|  
|`varbinary(max)`|<span data-ttu-id="f14a7-156">0</span><span class="sxs-lookup"><span data-stu-id="f14a7-156">0</span></span>|  
|`nvarchar(max)`|<span data-ttu-id="f14a7-157">0</span><span class="sxs-lookup"><span data-stu-id="f14a7-157">0</span></span>|  
|<span data-ttu-id="f14a7-158">(UDT)</span><span class="sxs-lookup"><span data-stu-id="f14a7-158">UDT</span></span>|<span data-ttu-id="f14a7-159">Длина столбца определенного пользователем типа (UDT)</span><span class="sxs-lookup"><span data-stu-id="f14a7-159">Length of the user-defined term (UDT) column</span></span>|  
|<span data-ttu-id="f14a7-160">XML</span><span class="sxs-lookup"><span data-stu-id="f14a7-160">XML</span></span>|<span data-ttu-id="f14a7-161">0</span><span class="sxs-lookup"><span data-stu-id="f14a7-161">0</span></span>|  
  
 <span data-ttu-id="f14a7-162">\*Дополнительные сведения о `decimal` `numeric` типах данных и см. в разделе [десятичные и числовые &#40;языке Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f14a7-162">\*For more information about the `decimal` and `numeric` data types, see [decimal and numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f14a7-163">Столбец данных типа `tinyint` может содержать целые значения от 0 до 255; максимальное количество символов, необходимых для представления чисел данного диапазона, равно 3 (для записи чисел от 100 до 255).</span><span class="sxs-lookup"><span data-stu-id="f14a7-163">A column of type `tinyint` can have values from 0 through 255; the maximum number of characters that are needed to represent any number in that range is three (representing values 100 through 255).</span></span>  
  
### <a name="default-field-lengths-for-native-file-storage"></a><span data-ttu-id="f14a7-164">Значения длины поля по умолчанию для файлов собственных данных</span><span class="sxs-lookup"><span data-stu-id="f14a7-164">Default Field Lengths for Native File Storage</span></span>  
 <span data-ttu-id="f14a7-165">В представленной ниже таблице приведены значения длины поля для данных, хранимых в собственном формате.</span><span class="sxs-lookup"><span data-stu-id="f14a7-165">The following table lists the default field lengths for data to be stored as native file storage type.</span></span> <span data-ttu-id="f14a7-166">Данные, которые могут и не могут принимать значение NULL, имеют одинаковую длину поля, а символьные данные всегда хранятся в собственном формате.</span><span class="sxs-lookup"><span data-stu-id="f14a7-166">Nullable data is the same length as nonnull data, and character data is always stored in character format.</span></span>  
  
|<span data-ttu-id="f14a7-167">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f14a7-167">Data type</span></span>|<span data-ttu-id="f14a7-168">Длина по умолчанию (в символах)</span><span class="sxs-lookup"><span data-stu-id="f14a7-168">Default length (characters)</span></span>|  
|---------------|-----------------------------------|  
|`bit`|<span data-ttu-id="f14a7-169">1</span><span class="sxs-lookup"><span data-stu-id="f14a7-169">1</span></span>|  
|`binary`|<span data-ttu-id="f14a7-170">Длина, определенная для столбца</span><span class="sxs-lookup"><span data-stu-id="f14a7-170">Length defined for the column</span></span>|  
|`varbinary`|<span data-ttu-id="f14a7-171">Длина, определенная для столбца</span><span class="sxs-lookup"><span data-stu-id="f14a7-171">Length defined for the column</span></span>|  
|`image`|<span data-ttu-id="f14a7-172">0</span><span class="sxs-lookup"><span data-stu-id="f14a7-172">0</span></span>|  
|`datetime`|<span data-ttu-id="f14a7-173">8</span><span class="sxs-lookup"><span data-stu-id="f14a7-173">8</span></span>|  
|`smalldatetime`|<span data-ttu-id="f14a7-174">4</span><span class="sxs-lookup"><span data-stu-id="f14a7-174">4</span></span>|  
|`float`|<span data-ttu-id="f14a7-175">8</span><span class="sxs-lookup"><span data-stu-id="f14a7-175">8</span></span>|  
|`real`|<span data-ttu-id="f14a7-176">4</span><span class="sxs-lookup"><span data-stu-id="f14a7-176">4</span></span>|  
|`int`|<span data-ttu-id="f14a7-177">4</span><span class="sxs-lookup"><span data-stu-id="f14a7-177">4</span></span>|  
|`bigint`|<span data-ttu-id="f14a7-178">8</span><span class="sxs-lookup"><span data-stu-id="f14a7-178">8</span></span>|  
|`smallint`|<span data-ttu-id="f14a7-179">2</span><span class="sxs-lookup"><span data-stu-id="f14a7-179">2</span></span>|  
|`tinyint`|<span data-ttu-id="f14a7-180">1</span><span class="sxs-lookup"><span data-stu-id="f14a7-180">1</span></span>|  
|`money`|<span data-ttu-id="f14a7-181">8</span><span class="sxs-lookup"><span data-stu-id="f14a7-181">8</span></span>|  
|`smallmoney`|<span data-ttu-id="f14a7-182">4</span><span class="sxs-lookup"><span data-stu-id="f14a7-182">4</span></span>|  
|<span data-ttu-id="f14a7-183">`decimal` <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f14a7-183">`decimal` <sup>1</sup></span></span>|<sup>*</sup>|  
|<span data-ttu-id="f14a7-184">`numeric` <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f14a7-184">`numeric` <sup>1</sup></span></span>|<sup>*</sup>|  
|`uniqueidentifier`|<span data-ttu-id="f14a7-185">16</span><span class="sxs-lookup"><span data-stu-id="f14a7-185">16</span></span>|  
|`timestamp`|<span data-ttu-id="f14a7-186">8</span><span class="sxs-lookup"><span data-stu-id="f14a7-186">8</span></span>|  
  
 <span data-ttu-id="f14a7-187"><sup>1</sup> дополнительные сведения о `decimal` `numeric` типах данных и см. в разделе [десятичные и числовые &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f14a7-187"><sup>1</sup> For more information about the `decimal` and `numeric` data types, see [decimal and numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span></span>  
  
 <span data-ttu-id="f14a7-188">Во всех перечисленных случаях для создания файла данных для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , занимающего наименьшее количество памяти, необходимо использовать префикс, задающий тип файлов и длину поля по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f14a7-188">In all of the preceding cases, to create a data file for later reloading into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that keeps the storage space to a minimum, use a length prefix with the default file storage type and the default field length.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f14a7-189">См. также:</span><span class="sxs-lookup"><span data-stu-id="f14a7-189">See Also</span></span>  
 <span data-ttu-id="f14a7-190">[bcp Utility](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="f14a7-190">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="f14a7-191">[Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f14a7-191">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="f14a7-192">[Определение признаков конца поля и строки (SQL Server)](specify-field-and-row-terminators-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f14a7-192">[Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span></span>  
 <span data-ttu-id="f14a7-193">[Определение длины префикса в файлах данных с помощью программы bcp (SQL Server)](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f14a7-193">[Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md) </span></span>  
 <span data-ttu-id="f14a7-194">[Указание типа файлового хранилища с помощью программы bcp (SQL Server)](specify-file-storage-type-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f14a7-194">[Specify File Storage Type by Using bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md) </span></span>  
 [<span data-ttu-id="f14a7-195">Сохранение значений NULL или использование значений по умолчанию при массовом импорте данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f14a7-195">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
  
