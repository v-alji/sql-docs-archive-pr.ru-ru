---
title: Форматы данных для массового экспорта или импорта (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- data formats [SQL Server], choosing
- bulk importing [SQL Server], data formats
ms.assetid: 73fe6741-9437-4b26-b030-28b863e74399
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b92ac8c038362ff18a1459a8bf3c55b6b596a17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654273"
---
# <a name="data-formats-for-bulk-import-or-bulk-export-sql-server"></a><span data-ttu-id="08a2c-102">Форматы данных для массового экспорта или импорта (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="08a2c-102">Data Formats for Bulk Import or Bulk Export (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="08a2c-103">может принимать данные в символьном или исходном двоичном формате.</span><span class="sxs-lookup"><span data-stu-id="08a2c-103">can accept data in character data format or native binary data format.</span></span> <span data-ttu-id="08a2c-104">Символьный формат применяется при перемещении данных между [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и другим приложением (например [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel) или другим сервером базы данных (например Oracle или [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="08a2c-104">Use character format when you move data between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and another application (such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel) or another database server (such as Oracle or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]).</span></span> <span data-ttu-id="08a2c-105">Собственный формат может применяться только при переносе данных между экземплярами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08a2c-105">You can use native format only when you transfer data between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="08a2c-106">**В этом разделе.**</span><span class="sxs-lookup"><span data-stu-id="08a2c-106">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="08a2c-107">Форматы данных для массового импорта или экспорта</span><span class="sxs-lookup"><span data-stu-id="08a2c-107">Data Formats for Bulk Import or Export</span></span>](#ComponentsAndConcepts)  
  
-   [<span data-ttu-id="08a2c-108">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="08a2c-108">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="data-formats-for-bulk-import-or-export"></a><a name="ComponentsAndConcepts"></a> <span data-ttu-id="08a2c-109">Форматы данных для массового импорта или экспорта</span><span class="sxs-lookup"><span data-stu-id="08a2c-109">Data Formats for Bulk Import or Export</span></span>  
 <span data-ttu-id="08a2c-110">В следующей таблице приведены общие правила выбора формата данных в зависимости от того, как представлены данные, а также от источника или назначения операции.</span><span class="sxs-lookup"><span data-stu-id="08a2c-110">The following table indicates what data format is generally appropriate to use depending on how the data is represented and the source or target of the operation.</span></span>  
  
|<span data-ttu-id="08a2c-111">Операция</span><span class="sxs-lookup"><span data-stu-id="08a2c-111">Operation</span></span>|<span data-ttu-id="08a2c-112">Собственный</span><span class="sxs-lookup"><span data-stu-id="08a2c-112">Native</span></span>|<span data-ttu-id="08a2c-113">собственный формат Юникода</span><span class="sxs-lookup"><span data-stu-id="08a2c-113">Unicode native</span></span>|<span data-ttu-id="08a2c-114">Символ</span><span class="sxs-lookup"><span data-stu-id="08a2c-114">Character</span></span>|<span data-ttu-id="08a2c-115">символьный формат Юникода</span><span class="sxs-lookup"><span data-stu-id="08a2c-115">Unicode character</span></span>|  
|---------------|------------|--------------------|---------------|-----------------------|  
|<span data-ttu-id="08a2c-116">Массовый перенос данных между несколькими экземплярами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при помощи файла данных, не содержащего символы расширенной или двухбайтовой кодировки (DBCS).</span><span class="sxs-lookup"><span data-stu-id="08a2c-116">Bulk transfers of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that does not contain any extended or double-byte character set (DBCS) characters.</span></span> <span data-ttu-id="08a2c-117">Если не используется файл форматирования, эти таблицы должны быть определены одинаково.</span><span class="sxs-lookup"><span data-stu-id="08a2c-117">Unless a format file is used, these tables must be identically defined.</span></span>|<span data-ttu-id="08a2c-118">Да<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="08a2c-118">Yes<sup>1</sup></span></span>|-|-|-|  
|<span data-ttu-id="08a2c-119">Для столбцов типа `sql_variant` наилучшим образом подходит собственный формат данных, так как в отличие от символьного и формата Юникода, собственный формат сохраняет метаданные для каждого значения типа `sql_variant`.</span><span class="sxs-lookup"><span data-stu-id="08a2c-119">For `sql_variant` columns, use of native data format is best, because native data format preserves the metadata for each `sql_variant` value, unlike character or Unicode formats.</span></span>|<span data-ttu-id="08a2c-120">Да</span><span class="sxs-lookup"><span data-stu-id="08a2c-120">Yes</span></span>|-|-|-|  
|<span data-ttu-id="08a2c-121">Массовая передача данных между несколькими экземплярами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при помощи файла данных, содержащего символы расширенной или двухбайтовой кодировки (DBCS).</span><span class="sxs-lookup"><span data-stu-id="08a2c-121">Bulk transfers of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended or DBCS characters.</span></span>|-|<span data-ttu-id="08a2c-122">Да</span><span class="sxs-lookup"><span data-stu-id="08a2c-122">Yes</span></span>|-|-|  
|<span data-ttu-id="08a2c-123">Массовый импорт данных из текстового файла, формируемого другой программой.</span><span class="sxs-lookup"><span data-stu-id="08a2c-123">Bulk import of data from a text file that is generated by another program.</span></span>|-|-|<span data-ttu-id="08a2c-124">Да</span><span class="sxs-lookup"><span data-stu-id="08a2c-124">Yes</span></span>|-|  
|<span data-ttu-id="08a2c-125">Массовый экспорт данных в текстовый файл, который должен использоваться другой программой.</span><span class="sxs-lookup"><span data-stu-id="08a2c-125">Bulk export of data to a text file that is to be used in another program.</span></span>|-|-|<span data-ttu-id="08a2c-126">Да</span><span class="sxs-lookup"><span data-stu-id="08a2c-126">Yes</span></span>|-|  
|<span data-ttu-id="08a2c-127">Массовая передача данных между несколькими экземплярами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при помощи файла данных, содержащего данные Юникода и не содержащего символы расширенной или двухбайтовой кодировки (DBCS).</span><span class="sxs-lookup"><span data-stu-id="08a2c-127">Bulk transfers of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains Unicode data and does not contain any extended or DBCS characters.</span></span>|-|-|-|<span data-ttu-id="08a2c-128">Да</span><span class="sxs-lookup"><span data-stu-id="08a2c-128">Yes</span></span>|  
  
 <span data-ttu-id="08a2c-129"><sup>1</sup> самый быстрый способ для полного экспорта данных из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при использовании программы **bcp**.</span><span class="sxs-lookup"><span data-stu-id="08a2c-129"><sup>1</sup> Fastest method for the bulk export of data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] when using **bcp**.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="08a2c-130">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="08a2c-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="08a2c-131">Использование собственного формата для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="08a2c-131">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="08a2c-132">Использование символьного формата для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="08a2c-132">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="08a2c-133">Использование собственного формата Юникод для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="08a2c-133">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="08a2c-134">Использование символьного формата Юникод для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="08a2c-134">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="08a2c-135">Импорт данных в собственном и символьном формате из предыдущих версий SQL Server</span><span class="sxs-lookup"><span data-stu-id="08a2c-135">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="08a2c-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="08a2c-136">See Also</span></span>  
 <span data-ttu-id="08a2c-137">[Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="08a2c-137">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 [<span data-ttu-id="08a2c-138">Указание форматов данных для совместимости с помощью программы bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="08a2c-138">Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;</span></span>](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md)  
  
  
