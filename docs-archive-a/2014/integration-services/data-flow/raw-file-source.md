---
title: Источник "Необработанный файл" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfilesource.f1
helpviewer_keywords:
- sources [Integration Services], Raw File
- raw data [Integration Services]
- Raw File source
ms.assetid: 5b4daea5-7f76-4674-aa77-0a79f9f97f7d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4cbc5800c4fb2b90b74e66b6ff161118b2b550f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657175"
---
# <a name="raw-file-source"></a><span data-ttu-id="a51c4-102">источник «Необработанный файл»</span><span class="sxs-lookup"><span data-stu-id="a51c4-102">Raw File Source</span></span>
  <span data-ttu-id="a51c4-103">Источник «Необработанный файл» считывает необработанные данные из файла.</span><span class="sxs-lookup"><span data-stu-id="a51c4-103">The Raw File source reads raw data from a file.</span></span> <span data-ttu-id="a51c4-104">Поскольку данные представлены в собственном формате источника, их преобразование не требуется. Также практически не требуется синтаксический анализ.</span><span class="sxs-lookup"><span data-stu-id="a51c4-104">Because the representation of the data is native to the source, the data requires no translation and almost no parsing.</span></span> <span data-ttu-id="a51c4-105">Это означает, что источник необработанных файлов в состоянии считывать данные быстрее, чем другие источники, такие как источник «Неструктурированный файл» и источник «OLE DB».</span><span class="sxs-lookup"><span data-stu-id="a51c4-105">This means that the Raw File source can read data more quickly than other sources such as the Flat File and the OLE DB sources.</span></span>  
  
 <span data-ttu-id="a51c4-106">Источник «Необработанный файл» используется для извлечения необработанных данных, записанных ранее назначением «Необработанный файл».</span><span class="sxs-lookup"><span data-stu-id="a51c4-106">The Raw File source is used to retrieve raw data that was previously written by the Raw File destination.</span></span> <span data-ttu-id="a51c4-107">Вы можете также указать источник «Необработанный файл», указывающий на пустой необработанный файл, содержащий только столбцы (файл только с метаданными).</span><span class="sxs-lookup"><span data-stu-id="a51c4-107">You can also point the Raw File source to an empty raw file that contains only the columns (metadata-only file).</span></span> <span data-ttu-id="a51c4-108">Можно использовать назначение «Необработанный файл» для создания файла только с метаданными без необходимости запускать пакет.</span><span class="sxs-lookup"><span data-stu-id="a51c4-108">You use the Raw File destination to generate the metadata-only file without having to run the package.</span></span> <span data-ttu-id="a51c4-109">Дополнительные сведения см. в статье [Raw File Destination](raw-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="a51c4-109">For more information, see [Raw File Destination](raw-file-destination.md).</span></span>  
  
 <span data-ttu-id="a51c4-110">В формате необработанного файла содержатся сведения о сортировке.</span><span class="sxs-lookup"><span data-stu-id="a51c4-110">The raw file format contains sort information.</span></span> <span data-ttu-id="a51c4-111">Назначение «Необработанный файл» сохраняет все сведения о сортировке, включая флаги сравнения для строковых столбцов.</span><span class="sxs-lookup"><span data-stu-id="a51c4-111">The Raw File Destination saves all the sort information including the comparison flags for string columns.</span></span> <span data-ttu-id="a51c4-112">Источник «Необработанный файл» считывает и учитывает сведения о сортировке.</span><span class="sxs-lookup"><span data-stu-id="a51c4-112">The Raw File source reads and honors the sort information.</span></span> <span data-ttu-id="a51c4-113">С помощью расширенного редактора можно настроить источник «Необработанный файл» так, что флаги сортировки в файле не будут учитываться.</span><span class="sxs-lookup"><span data-stu-id="a51c4-113">You do have the option of configuring the Raw File Source to ignore the sort flags in the file, using the Advanced Editor.</span></span> <span data-ttu-id="a51c4-114">Дополнительные сведения о флагах сравнения см. в разделе [Comparing String Data](comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="a51c4-114">For more information about comparison flags, see [Comparing String Data](comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="a51c4-115">Для настройки необработанного файла необходимо указать имя файла, который считывается источником «Необработанный файл».</span><span class="sxs-lookup"><span data-stu-id="a51c4-115">You configure the Raw File by specifying the name of the name of the file that the Raw File source reads.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a51c4-116">Данный источник не использует диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="a51c4-116">This source does not use a connection manager.</span></span>  
  
 <span data-ttu-id="a51c4-117">Этот источник имеет один выход.</span><span class="sxs-lookup"><span data-stu-id="a51c4-117">This source has one output.</span></span> <span data-ttu-id="a51c4-118">Вывод ошибок не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a51c4-118">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-raw-file-source"></a><span data-ttu-id="a51c4-119">Настройка источника «Необработанный файл»</span><span class="sxs-lookup"><span data-stu-id="a51c4-119">Configuration of the Raw File Source</span></span>  
 <span data-ttu-id="a51c4-120">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="a51c4-120">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="a51c4-121">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="a51c4-121">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="a51c4-122">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="a51c4-122">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="a51c4-123">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="a51c4-123">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="a51c4-124">Пользовательские свойства необработанного файла</span><span class="sxs-lookup"><span data-stu-id="a51c4-124">Raw File Custom Properties</span></span>](raw-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="a51c4-125">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="a51c4-125">Related Tasks</span></span>  
 <span data-ttu-id="a51c4-126">Дополнительные сведения о настройке свойств компонента см. в разделе [Установление свойств компонента потока данных](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="a51c4-126">For information about how to set the properties of the component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="a51c4-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a51c4-127">Related Content</span></span>  
  
-   <span data-ttu-id="a51c4-128">Запись в блоге [Необработанные файлы ― это здорово](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131)на сайте sqlservercentral.com</span><span class="sxs-lookup"><span data-stu-id="a51c4-128">Blog entry, [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), on sqlservercentral.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a51c4-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="a51c4-129">See Also</span></span>  
 <span data-ttu-id="a51c4-130">[Назначение «Необработанный файл»](raw-file-destination.md) </span><span class="sxs-lookup"><span data-stu-id="a51c4-130">[Raw File Destination](raw-file-destination.md) </span></span>  
 [<span data-ttu-id="a51c4-131">Поток данных</span><span class="sxs-lookup"><span data-stu-id="a51c4-131">Data Flow</span></span>](data-flow.md)  
  
  
