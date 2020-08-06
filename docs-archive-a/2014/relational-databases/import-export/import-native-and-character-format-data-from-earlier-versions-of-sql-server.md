---
title: Импорт данных в собственном и символьном формате из предыдущих версий SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- earlier versions [SQL Server], import and export data formats
- -V switch
- data formats [SQL Server], earlier versions
- previous versions [SQL Server], import and export data formats
ms.assetid: e644696f-9017-428e-a5b3-d445d1c630b3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 274c984d6ecec8af8f5bea27496450a45fc2f1df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666595"
---
# <a name="import-native-and-character-format-data-from-earlier-versions-of-sql-server"></a><span data-ttu-id="10dcc-102">Импорт данных в собственном и символьном формате из предыдущих версий SQL Server</span><span class="sxs-lookup"><span data-stu-id="10dcc-102">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>
  <span data-ttu-id="10dcc-103">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]можно с помощью программы **bcp** импортировать данные в собственном и символьном формате из [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]или [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , задав ключ **-V** .</span><span class="sxs-lookup"><span data-stu-id="10dcc-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can use **bcp** to import native and character format data from [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] by using the **-V** switch.</span></span> <span data-ttu-id="10dcc-104">Ключ **-V** указывает [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , что следует использовать типы данных из указанной более ранней версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]и что формат файла данных аналогичен формату в предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="10dcc-104">The **-V** switch causes [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to use data types from the specified earlier version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and the data file format are the same as the format in that earlier version.</span></span>  
  
 <span data-ttu-id="10dcc-105">Чтобы задать более раннюю версию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для файла данных, используйте параметр **-V** с одним из следующих квалификаторов:</span><span class="sxs-lookup"><span data-stu-id="10dcc-105">To specify an earlier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version for a data file, use the **-V** switch with one of the following qualifiers:</span></span>  
  
|<span data-ttu-id="10dcc-106">Версия SQL Server</span><span class="sxs-lookup"><span data-stu-id="10dcc-106">SQL Server version</span></span>|<span data-ttu-id="10dcc-107">Квалификатор</span><span class="sxs-lookup"><span data-stu-id="10dcc-107">Qualifier</span></span>|  
|------------------------|---------------|  
|[!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]|<span data-ttu-id="10dcc-108">**-V80**</span><span class="sxs-lookup"><span data-stu-id="10dcc-108">**-V80**</span></span>|  
|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|<span data-ttu-id="10dcc-109">**-V90**</span><span class="sxs-lookup"><span data-stu-id="10dcc-109">**-V90**</span></span>|  
|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|<span data-ttu-id="10dcc-110">**-V100**</span><span class="sxs-lookup"><span data-stu-id="10dcc-110">**-V100**</span></span>|  
|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]|<span data-ttu-id="10dcc-111">**-V 110**</span><span class="sxs-lookup"><span data-stu-id="10dcc-111">**-V 110**</span></span>|  
  
## <a name="interpretation-of-data-types"></a><span data-ttu-id="10dcc-112">Интерпретация типов данных</span><span class="sxs-lookup"><span data-stu-id="10dcc-112">Interpretation of Data Types</span></span>  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="10dcc-113">и более поздних версиях была добавлена поддержка некоторых новых типов данных.</span><span class="sxs-lookup"><span data-stu-id="10dcc-113">and later versions have support for some new types.</span></span> <span data-ttu-id="10dcc-114">Если нужно импортировать новый тип данных в более раннюю версию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , эти данные необходимо сохранить в формате, который могут прочитать старые клиенты **bcp** .</span><span class="sxs-lookup"><span data-stu-id="10dcc-114">When you want to import a new data type into an earlier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version, the data type must be stored in a format that readable by the older **bcp** clients.</span></span> <span data-ttu-id="10dcc-115">Следующая таблица содержит сведения о том, как новые типы данных преобразуются для совместимости с более ранними версиями [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10dcc-115">The following table summarizes how the new data types are converted for compatibility with the earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="10dcc-116">Новые типы данных в SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="10dcc-116">New data types in SQL Server 2005</span></span>|<span data-ttu-id="10dcc-117">Совместимые типы данных в версии 6*x*</span><span class="sxs-lookup"><span data-stu-id="10dcc-117">Compatible data types in version 6*x*</span></span>|<span data-ttu-id="10dcc-118">Совместимые типы данных в версии 70</span><span class="sxs-lookup"><span data-stu-id="10dcc-118">Compatible data types in version 70</span></span>|<span data-ttu-id="10dcc-119">Совместимые типы данных в версии 80</span><span class="sxs-lookup"><span data-stu-id="10dcc-119">Compatible data types in version 80</span></span>|  
|---------------------------------------|-------------------------------------------|-----------------------------------------|-----------------------------------------|  
|`bigint`|`decimal`|`decimal`|*|  
|`sql_variant`|`text`|`nvarchar(4000)`|*|  
|`varchar(max)`|`text`|`text`|`text`|  
|`nvarchar(max)`|`ntext`|`ntext`|`ntext`|  
|`varbinary(max)`|`image`|`image`|`image`|  
|<span data-ttu-id="10dcc-120">XML</span><span class="sxs-lookup"><span data-stu-id="10dcc-120">XML</span></span>|`ntext`|`ntext`|`ntext`|  
|<span data-ttu-id="10dcc-121">Определяемый пользователем тип<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="10dcc-121">UDT<sup>1</sup></span></span>|`image`|`image`|`image`|  
  
 <span data-ttu-id="10dcc-122">\*Этот тип поддерживается изначально.</span><span class="sxs-lookup"><span data-stu-id="10dcc-122">\* This type is natively supported.</span></span>  
  
 <span data-ttu-id="10dcc-123"><sup>1</sup> UDT обозначает определяемый пользователем тип.</span><span class="sxs-lookup"><span data-stu-id="10dcc-123"><sup>1</sup> UDT indicates a user defined type.</span></span>  
  
## <a name="exporting-using--v-80"></a><span data-ttu-id="10dcc-124">Экспорт с ключом -V 80</span><span class="sxs-lookup"><span data-stu-id="10dcc-124">Exporting using -V 80</span></span>  
 <span data-ttu-id="10dcc-125">При выполнении операций с массовым экспортом с помощью параметра **-V80** данные,,, `nvarchar(max)` `varchar(max)` `varbinary(max)` XML и определяемые пользователем типы данных в собственном режиме сохраняются с помощью 4-байтного префикса, например `text` , `image` и `ntext` данных, вместо 8-байтного префикса по умолчанию для [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="10dcc-125">When you bulk export data by using the **-V80** switch, `nvarchar(max)`, `varchar(max)`, `varbinary(max)`, XML, and UDT data in native mode are stored with a 4-byte prefix, like `text`, `image`, and `ntext` data, rather than with an 8-byte prefix, which is the default for [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span>  
  
## <a name="copying-date-values"></a><span data-ttu-id="10dcc-126">Копирование значений данных</span><span class="sxs-lookup"><span data-stu-id="10dcc-126">Copying Date Values</span></span>  
 <span data-ttu-id="10dcc-127">Программа**bcp** использует API-интерфейс массового копирования ODBC.</span><span class="sxs-lookup"><span data-stu-id="10dcc-127">**bcp** uses the ODBC bulk copy API.</span></span> <span data-ttu-id="10dcc-128">Таким образом, для импорта значений дат в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]программа **bcp** использует формат данных ODBC (*гггг-мм-дд чч:мм:сс*[ *.f...* ]).</span><span class="sxs-lookup"><span data-stu-id="10dcc-128">Therefore, to import date values into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], **bcp** uses the ODBC date format (*yyyy-mm-dd hh:mm:ss*[*.f...*]).</span></span>  
  
 <span data-ttu-id="10dcc-129">Команда **bcp** экспортирует файлы данных символьного формата, используя формат ODBC по умолчанию для `datetime` `smalldatetime` значений и.</span><span class="sxs-lookup"><span data-stu-id="10dcc-129">The **bcp** command exports character format data files using the ODBC default format for `datetime` and `smalldatetime` values.</span></span> <span data-ttu-id="10dcc-130">Например, столбец типа `datetime`, содержащий дату `12 Aug 1998`, копируется с помощью массового копирования в файл данных в качестве строки символов `1998-08-12 00:00:00.000`.</span><span class="sxs-lookup"><span data-stu-id="10dcc-130">For example, a `datetime` column containing the date `12 Aug 1998` is bulk copied to a data file as the character string `1998-08-12 00:00:00.000`.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="10dcc-131">При импорте данных в `smalldatetime` поле с помощью программы **bcp**убедитесь, что значение секунд равно 00,000; в противном случае операция завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="10dcc-131">When importing data into a `smalldatetime` field using **bcp**, be sure the value for seconds is 00.000; otherwise the operation will fail.</span></span> <span data-ttu-id="10dcc-132">Тип данных `smalldatetime` содержит значения только с точностью до минуты.</span><span class="sxs-lookup"><span data-stu-id="10dcc-132">The `smalldatetime` data type only holds values to the nearest minute.</span></span> <span data-ttu-id="10dcc-133">В данном случае инструкции BULK INSERT и INSERT ... SELECT \* FROM OPENROWSET(BULK...) не приведут к ошибке, но усекут значение секунд.</span><span class="sxs-lookup"><span data-stu-id="10dcc-133">BULK INSERT and INSERT ... SELECT \* FROM OPENROWSET(BULK...) will not fail in this instance but will truncate the seconds value.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="10dcc-134">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="10dcc-134">Related Tasks</span></span>  
 <span data-ttu-id="10dcc-135">**Использование форматов данных для массового импорта или экспорта**</span><span class="sxs-lookup"><span data-stu-id="10dcc-135">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="10dcc-136">Использование символьного формата для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="10dcc-136">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="10dcc-137">Использование собственного формата для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="10dcc-137">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="10dcc-138">Использование символьного формата Юникод для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="10dcc-138">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="10dcc-139">Использование собственного формата Юникод для импорта и экспорта данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="10dcc-139">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
 
  
## <a name="see-also"></a><span data-ttu-id="10dcc-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="10dcc-140">See Also</span></span>  
 <span data-ttu-id="10dcc-141">[bcp Utility](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="10dcc-141">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="10dcc-142">[BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="10dcc-142">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="10dcc-143">[OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="10dcc-143">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="10dcc-144">[Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="10dcc-144">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="10dcc-145">[Обратная совместимость компонента ядра СУБД SQL Server](../../database-engine/sql-server-database-engine-backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="10dcc-145">[SQL Server Database Engine Backward Compatibility](../../database-engine/sql-server-database-engine-backward-compatibility.md) </span></span>  
 [<span data-ttu-id="10dcc-146">Функции CAST и CONVERT (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="10dcc-146">CAST and CONVERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/cast-and-convert-transact-sql)  
  
  
