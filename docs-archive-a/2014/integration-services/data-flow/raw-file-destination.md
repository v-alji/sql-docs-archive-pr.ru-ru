---
title: Назначение "Необработанный файл" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfiledest.f1
helpviewer_keywords:
- append options [Integration Services]
- destinations [Integration Services], Raw File
- raw data [Integration Services]
- writing raw data
- Raw File destination
ms.assetid: d311b458-aefc-4b4d-b1a1-4c0ebbb34214
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fc5ce99be6e467ba323137ef885cbb13bfb328ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657177"
---
# <a name="raw-file-destination"></a><span data-ttu-id="44d8e-102">назначение «Необработанный файл»</span><span class="sxs-lookup"><span data-stu-id="44d8e-102">Raw File Destination</span></span>
  <span data-ttu-id="44d8e-103">Назначение «Необработанный файл» записывает необработанные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="44d8e-103">The Raw File destination writes raw data to a file.</span></span> <span data-ttu-id="44d8e-104">Так как формат данных является собственным для назначения, данные не требуют перевода и нуждаются лишь в небольшом анализе.</span><span class="sxs-lookup"><span data-stu-id="44d8e-104">Because the format of the data is native to the destination, the data requires no translation and little parsing.</span></span> <span data-ttu-id="44d8e-105">Это значит, что назначение «Необработанный файл» может записывать данные быстрее, чем другие назначения, такие как «Неструктурированный файл» или «OLE DB».</span><span class="sxs-lookup"><span data-stu-id="44d8e-105">This means that the Raw File destination can write data more quickly than other destinations such as the Flat File and the OLE DB destinations.</span></span>  
  
 <span data-ttu-id="44d8e-106">Помимо записи необработанных данных в файл, можно также использовать назначение «Необработанный файл» для создания пустого необработанного файла, содержащего только столбцы (файла только с метаданными), без необходимости запуска пакета.</span><span class="sxs-lookup"><span data-stu-id="44d8e-106">In addition to writing raw data to a file, you can also use the Raw File destination to generate an empty raw file that contains only the columns (metadata-only file), without having to run the package.</span></span> <span data-ttu-id="44d8e-107">Источник «Необработанный файл» используется для извлечения необработанных данных, записанных ранее одноименным назначением.</span><span class="sxs-lookup"><span data-stu-id="44d8e-107">You use the Raw File source to retrieve raw data that was previously written by the destination.</span></span> <span data-ttu-id="44d8e-108">Также в качестве источника «Необработанный файл» вы можете указать файл, который содержит только метаданные.</span><span class="sxs-lookup"><span data-stu-id="44d8e-108">You can also point the Raw File source to the metadata-only file.</span></span>  
  
 <span data-ttu-id="44d8e-109">В формате необработанного файла содержатся сведения о сортировке.</span><span class="sxs-lookup"><span data-stu-id="44d8e-109">The raw file format contains sort information.</span></span> <span data-ttu-id="44d8e-110">Назначение «Необработанный файл» сохраняет все сведения о сортировке, включая флаги сравнения для строковых столбцов.</span><span class="sxs-lookup"><span data-stu-id="44d8e-110">The Raw File Destination saves all the sort information including the comparison flags for string columns.</span></span> <span data-ttu-id="44d8e-111">Источник «Необработанный файл» считывает и учитывает сведения о сортировке.</span><span class="sxs-lookup"><span data-stu-id="44d8e-111">The Raw File source reads and honors the sort information.</span></span> <span data-ttu-id="44d8e-112">С помощью расширенного редактора можно настроить источник «Необработанный файл» так, что флаги сортировки в файле не будут учитываться.</span><span class="sxs-lookup"><span data-stu-id="44d8e-112">You do have the option of configuring the Raw File Source to ignore the sort flags in the file, using the Advanced Editor.</span></span> <span data-ttu-id="44d8e-113">Дополнительные сведения о флагах сравнения см. в разделе [Comparing String Data](comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="44d8e-113">For more information about comparison flags, see [Comparing String Data](comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="44d8e-114">Можно настроить назначение «Необработанный файл» следующим образом.</span><span class="sxs-lookup"><span data-stu-id="44d8e-114">You can configure the Raw File destination in the following ways:</span></span>  
  
-   <span data-ttu-id="44d8e-115">Задайте режим доступа, являющийся либо именем файла, либо переменной, содержащей имя файла, в который записывает данные назначение «Необработанный файл».</span><span class="sxs-lookup"><span data-stu-id="44d8e-115">Specify an access mode which is either the name of the file or a variable that contains the name of the file to which the Raw File destination writes.</span></span>  
  
-   <span data-ttu-id="44d8e-116">Укажите, будет ли назначение «Необработанный файл» дозаписывать данные в существующий файл с таким именем или создавать новый файл.</span><span class="sxs-lookup"><span data-stu-id="44d8e-116">Indicate whether the Raw File destination appends data to an existing file that has the same name or creates a new file.</span></span>  
  
 <span data-ttu-id="44d8e-117">Назначение «Необработанный файл» часто используется для записи промежуточных результатов частичной обработки данных между запусками пакетов.</span><span class="sxs-lookup"><span data-stu-id="44d8e-117">The Raw File destination is frequently used to write intermediary results of partly processed data between package executions.</span></span> <span data-ttu-id="44d8e-118">Хранение необработанных данных означает, что данные можно быстро считать с использованием источника «Необработанный файл», а затем преобразовать перед загрузкой в окончательное назначение.</span><span class="sxs-lookup"><span data-stu-id="44d8e-118">Storing raw data means that the data can be read quickly by a Raw File source and then further transformed before it is loaded into its final destination.</span></span> <span data-ttu-id="44d8e-119">Например, пакет может запускаться несколько раз, каждый раз записывая в файлы необработанные данные.</span><span class="sxs-lookup"><span data-stu-id="44d8e-119">For example, a package might run several times, and each time write raw data to files.</span></span> <span data-ttu-id="44d8e-120">Позднее другой пакет сможет использовать источник «Необработанный файл» для считывания из каждого файла, использовать преобразование «Объединить все» для слияния данных в один набор, а затем применить дополнительные преобразования, окончательно обрабатывающие данные перед загрузкой данных в окончательное назначение, такое как таблица [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="44d8e-120">Later, a different package can use the Raw File source to read from each file, use a Union All transformation to merge the data into one data set, and then apply additional transformations that summarize the data before loading the data into its final destination such as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="44d8e-121">Назначение «Необработанный файл» поддерживает данные типа NULL, но не поддерживает данные типа BLOB.</span><span class="sxs-lookup"><span data-stu-id="44d8e-121">The Raw File destination supports null data but not binary large object (BLOB) data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="44d8e-122">Назначение «Необработанный файл» не использует диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="44d8e-122">The Raw File destination does not use a connection manager.</span></span>  
  
 <span data-ttu-id="44d8e-123">Этот источник имеет один стандартный вход.</span><span class="sxs-lookup"><span data-stu-id="44d8e-123">This source has one regular input.</span></span> <span data-ttu-id="44d8e-124">Вывод ошибок не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="44d8e-124">It does not support an error output.</span></span>  
  
## <a name="append-and-new-file-options"></a><span data-ttu-id="44d8e-125">Параметры Append и New File</span><span class="sxs-lookup"><span data-stu-id="44d8e-125">Append and New File Options</span></span>  
 <span data-ttu-id="44d8e-126">Свойство WriteOption включает возможности дозаписи данных в существующий файл или создания нового файла.</span><span class="sxs-lookup"><span data-stu-id="44d8e-126">The WriteOption property includes options to append data to an existing file or create a new file.</span></span>  
  
 <span data-ttu-id="44d8e-127">В следующей таблице описаны доступные значения свойства WriteOption.</span><span class="sxs-lookup"><span data-stu-id="44d8e-127">The following table describes the available options for the WriteOption property.</span></span>  
  
|<span data-ttu-id="44d8e-128">Параметр</span><span class="sxs-lookup"><span data-stu-id="44d8e-128">Option</span></span>|<span data-ttu-id="44d8e-129">Description</span><span class="sxs-lookup"><span data-stu-id="44d8e-129">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="44d8e-130">Append</span><span class="sxs-lookup"><span data-stu-id="44d8e-130">Append</span></span>|<span data-ttu-id="44d8e-131">Дозаписывает данные в существующий файл.</span><span class="sxs-lookup"><span data-stu-id="44d8e-131">Appends data to an existing file.</span></span> <span data-ttu-id="44d8e-132">Метаданные присоединенных данных должны соответствовать формату файла.</span><span class="sxs-lookup"><span data-stu-id="44d8e-132">The metadata of the appended data must match the file format.</span></span>|  
|<span data-ttu-id="44d8e-133">Create always</span><span class="sxs-lookup"><span data-stu-id="44d8e-133">Create always</span></span>|<span data-ttu-id="44d8e-134">Всегда создает новый файл.</span><span class="sxs-lookup"><span data-stu-id="44d8e-134">Always creates a new file.</span></span>|  
|<span data-ttu-id="44d8e-135">Create once</span><span class="sxs-lookup"><span data-stu-id="44d8e-135">Create once</span></span>|<span data-ttu-id="44d8e-136">Создает новый файл.</span><span class="sxs-lookup"><span data-stu-id="44d8e-136">Creates a new file.</span></span> <span data-ttu-id="44d8e-137">Если файл существует, то работа компонента завершается аварийно.</span><span class="sxs-lookup"><span data-stu-id="44d8e-137">If the file exists, the component fails.</span></span>|  
|<span data-ttu-id="44d8e-138">Truncate and append</span><span class="sxs-lookup"><span data-stu-id="44d8e-138">Truncate and append</span></span>|<span data-ttu-id="44d8e-139">Усекает существующий файл и затем записывает данные.</span><span class="sxs-lookup"><span data-stu-id="44d8e-139">Truncates an existing file and then writes the data to the file.</span></span> <span data-ttu-id="44d8e-140">Метаданные присоединенных данных должны соответствовать формату файла.</span><span class="sxs-lookup"><span data-stu-id="44d8e-140">The metadata of the appended data must match the file format.</span></span>|  
  
 <span data-ttu-id="44d8e-141">Ниже приведены важные вопросы о добавлении данных.</span><span class="sxs-lookup"><span data-stu-id="44d8e-141">The following are important items about appending data:</span></span>  
  
-   <span data-ttu-id="44d8e-142">Добавление данных в существующий необработанный файл не приводит к повторной сортировке данных.</span><span class="sxs-lookup"><span data-stu-id="44d8e-142">Appending data to an existing raw file does not re-sort the data.</span></span>  
  
     <span data-ttu-id="44d8e-143">Необходимо убедиться, что ключи сортировки остаются в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="44d8e-143">You need to make certain that the sorted keys remain in the correct order.</span></span>  
  
-   <span data-ttu-id="44d8e-144">Добавление данных в существующий необработанный файл не меняет метаданные этого файла (сведения о сортировке).</span><span class="sxs-lookup"><span data-stu-id="44d8e-144">Appending data to an existing raw file does not change the file metadata (sort information).</span></span>  
  
 <span data-ttu-id="44d8e-145">Например, пакет считывает данные, отсортированные по ключу продукта (ProductKey, PK).</span><span class="sxs-lookup"><span data-stu-id="44d8e-145">For example, a package reads data sorted on the ProductKey (PK).</span></span> <span data-ttu-id="44d8e-146">Пакетный поток данных добавляет данные в существующий необработанный файл.</span><span class="sxs-lookup"><span data-stu-id="44d8e-146">The package data flow appends the data to an existing raw file.</span></span> <span data-ttu-id="44d8e-147">При первом запуске пакета будут получены три строки (PK 1000, 1100, 1200).</span><span class="sxs-lookup"><span data-stu-id="44d8e-147">The first time the package runs, three rows are received (PK 1000, 1100, 1200).</span></span> <span data-ttu-id="44d8e-148">Теперь необработанный файл содержит следующие данные.</span><span class="sxs-lookup"><span data-stu-id="44d8e-148">The raw file now contains the following data.</span></span>  
  
-   <span data-ttu-id="44d8e-149">1000, productA</span><span class="sxs-lookup"><span data-stu-id="44d8e-149">1000, productA</span></span>  
  
-   <span data-ttu-id="44d8e-150">1100, productB</span><span class="sxs-lookup"><span data-stu-id="44d8e-150">1100, productB</span></span>  
  
-   <span data-ttu-id="44d8e-151">1200, productC</span><span class="sxs-lookup"><span data-stu-id="44d8e-151">1200, productC</span></span>  
  
 <span data-ttu-id="44d8e-152">При втором запуске пакета будут получены две новые строки (PK 1001, 1300).</span><span class="sxs-lookup"><span data-stu-id="44d8e-152">The second time the package runs, two new rows are received (PK 1001, 1300).</span></span> <span data-ttu-id="44d8e-153">Теперь необработанный файл содержит следующие данные.</span><span class="sxs-lookup"><span data-stu-id="44d8e-153">The raw file now contains the following data.</span></span>  
  
-   <span data-ttu-id="44d8e-154">1000, productA</span><span class="sxs-lookup"><span data-stu-id="44d8e-154">1000, productA</span></span>  
  
-   <span data-ttu-id="44d8e-155">1100, productB</span><span class="sxs-lookup"><span data-stu-id="44d8e-155">1100, productB</span></span>  
  
-   <span data-ttu-id="44d8e-156">1200, productC</span><span class="sxs-lookup"><span data-stu-id="44d8e-156">1200, productC</span></span>  
  
-   <span data-ttu-id="44d8e-157">1001, productD</span><span class="sxs-lookup"><span data-stu-id="44d8e-157">1001, productD</span></span>  
  
-   <span data-ttu-id="44d8e-158">1300, productE</span><span class="sxs-lookup"><span data-stu-id="44d8e-158">1300, productE</span></span>  
  
 <span data-ttu-id="44d8e-159">Новые данные добавляются в конец необработанного файла, и порядок сортируемых ключей (PK) нарушается.</span><span class="sxs-lookup"><span data-stu-id="44d8e-159">The new data is appended to the end of the raw file, and the sorted keys (PK) are out of order.</span></span> <span data-ttu-id="44d8e-160">Кроме того, операция добавления не меняет метаданные файла (сведения о сортировке).</span><span class="sxs-lookup"><span data-stu-id="44d8e-160">In addition, the append operation didn't change the file metadata (sort information).</span></span> <span data-ttu-id="44d8e-161">Если файл был считан с использованием источника «Необработанный файл», компонент указывает, что файл все еще сортируется по PK, даже несмотря на то, что данные в файле больше не следуют в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="44d8e-161">If you read the file by using the Raw File source, the component indicates that the file is still sorted on PK even though the data in the file is no longer in the correct order.</span></span>  
  
 <span data-ttu-id="44d8e-162">Чтобы сохранить сортируемые ключи в правильном порядке после добавления данных, можно разработать пакетный поток данных следующим образом:</span><span class="sxs-lookup"><span data-stu-id="44d8e-162">To keep the sorted keys in the correct order while appending data, you can design the package data flow as follows:</span></span>  
  
1.  <span data-ttu-id="44d8e-163">Извлечение новых строк с использованием источника A.</span><span class="sxs-lookup"><span data-stu-id="44d8e-163">Retrieve new rows by using Source A.</span></span>  
  
2.  <span data-ttu-id="44d8e-164">Извлечение существующих строк из файла RawFile1 с помощью источника B.</span><span class="sxs-lookup"><span data-stu-id="44d8e-164">Retrieve existing rows from RawFile1 using Source B.</span></span>  
  
3.  <span data-ttu-id="44d8e-165">Объединение входных данных из источников A и B с помощью преобразования «Объединить все».</span><span class="sxs-lookup"><span data-stu-id="44d8e-165">Combine the inputs from Source A and Source B by using the Union All transformation.</span></span>  
  
4.  <span data-ttu-id="44d8e-166">Сортировка по PK.</span><span class="sxs-lookup"><span data-stu-id="44d8e-166">Sort on PK.</span></span>  
  
5.  <span data-ttu-id="44d8e-167">Запись в файл RawFile2 с использованием назначения «Необработанный файл».</span><span class="sxs-lookup"><span data-stu-id="44d8e-167">Write to RawFile2 by using the Raw File destination.</span></span>  
  
     <span data-ttu-id="44d8e-168">Файл RawFile1 заблокирован, поскольку из него выполняется чтение в потоке данных.</span><span class="sxs-lookup"><span data-stu-id="44d8e-168">RawFile1 is locked because it's being read from, in the data flow.</span></span>  
  
6.  <span data-ttu-id="44d8e-169">Замените RawFile1 на RawFile2.</span><span class="sxs-lookup"><span data-stu-id="44d8e-169">Replace RawFile1 with RawFile2.</span></span>  
  
### <a name="using-the-raw-file-destination-in-a-loop"></a><span data-ttu-id="44d8e-170">Использование назначения «Необработанный файл» в цикле</span><span class="sxs-lookup"><span data-stu-id="44d8e-170">Using the Raw File Destination in a Loop</span></span>  
 <span data-ttu-id="44d8e-171">Если поток данных, использующий назначение «Необработанный файл», является циклом, файл создается один раз, а затем данные дозаписываются в файл по мере повторения цикла.</span><span class="sxs-lookup"><span data-stu-id="44d8e-171">If the data flow that uses the Raw File destination is in a loop, you may want to create the file once and then append data to the file when the loop repeats.</span></span> <span data-ttu-id="44d8e-172">Чтобы добавить данные в файл, формат этих данных должен соответствовать формату существующего файла.</span><span class="sxs-lookup"><span data-stu-id="44d8e-172">To append data to the file, the data that is appended must match the format of the existing file.</span></span>  
  
 <span data-ttu-id="44d8e-173">Чтобы создать файл в первой итерации цикла, а затем в последующих итерациях цикла добавлять в него строки, в процессе разработки необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="44d8e-173">To create the file in the first iteration of the loop, and then append rows in the subsequent iterations of the loop, you need to do the following at design time:</span></span>  
  
1.  <span data-ttu-id="44d8e-174">Установите для свойства WriteOption значение **CreateOnce** или **CreateAlways**и запустите одну итерацию цикла.</span><span class="sxs-lookup"><span data-stu-id="44d8e-174">Set the WriteOption property to **CreateOnce** or **CreateAlways**and run one iteration of the loop.</span></span> <span data-ttu-id="44d8e-175">Файл будет создан.</span><span class="sxs-lookup"><span data-stu-id="44d8e-175">The file is created.</span></span> <span data-ttu-id="44d8e-176">Это будет гарантией того, что добавляемые метаданные и файл будут соответствовать друг другу.</span><span class="sxs-lookup"><span data-stu-id="44d8e-176">This ensures that the metadata of appended data and the file matches.</span></span>  
  
2.  <span data-ttu-id="44d8e-177">Сбросьте свойство WriteOption в значение **append** и задайте для свойства ValidateExternalMetadata значение `False` .</span><span class="sxs-lookup"><span data-stu-id="44d8e-177">Reset the WriteOption property to **Append** and set the ValidateExternalMetadata property to `False`.</span></span>  
  
 <span data-ttu-id="44d8e-178">Если используется параметр **TruncateAppend** вместо параметра **Append** , то строки, которые были добавлены в любой предыдущей итерации, будут усечены, и только затем будет добавлена новая строка.</span><span class="sxs-lookup"><span data-stu-id="44d8e-178">If you use the **TruncateAppend** option instead of the **Append** option, it will truncate rows that were added in any previous iteration, and then append new rows.</span></span> <span data-ttu-id="44d8e-179">Использование параметра **TruncateAppend** также требует, чтобы данные соответствовали формату файла.</span><span class="sxs-lookup"><span data-stu-id="44d8e-179">Using the **TruncateAppend** option also requires that the data matches the file format.</span></span>  
  
## <a name="configuration-of-the-raw-file-destination"></a><span data-ttu-id="44d8e-180">Настройка назначения «Необработанный файл»</span><span class="sxs-lookup"><span data-stu-id="44d8e-180">Configuration of the Raw File Destination</span></span>  
 <span data-ttu-id="44d8e-181">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="44d8e-181">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="44d8e-182">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="44d8e-182">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="44d8e-183">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="44d8e-183">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="44d8e-184">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="44d8e-184">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="44d8e-185">Пользовательские свойства необработанного файла</span><span class="sxs-lookup"><span data-stu-id="44d8e-185">Raw File Custom Properties</span></span>](raw-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="44d8e-186">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="44d8e-186">Related Tasks</span></span>  
 <span data-ttu-id="44d8e-187">Дополнительные сведения о настройке свойств компонента см. в разделе [Установление свойств компонента потока данных](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="44d8e-187">For information about how to set properties of the component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="44d8e-188">См. также</span><span class="sxs-lookup"><span data-stu-id="44d8e-188">Related Content</span></span>  
 <span data-ttu-id="44d8e-189">Запись в блоге [Необработанные файлы ― это здорово](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131)на сайте sqlservercentral.com.</span><span class="sxs-lookup"><span data-stu-id="44d8e-189">Blog entry, [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), on sqlservercentral.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44d8e-190">См. также:</span><span class="sxs-lookup"><span data-stu-id="44d8e-190">See Also</span></span>  
 <span data-ttu-id="44d8e-191">[Источник необработанного файла](raw-file-source.md) </span><span class="sxs-lookup"><span data-stu-id="44d8e-191">[Raw File Source](raw-file-source.md) </span></span>  
 [<span data-ttu-id="44d8e-192">Поток данных</span><span class="sxs-lookup"><span data-stu-id="44d8e-192">Data Flow</span></span>](data-flow.md)  
  
  
