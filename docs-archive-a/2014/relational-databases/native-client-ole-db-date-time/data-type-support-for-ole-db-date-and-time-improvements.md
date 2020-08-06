---
title: Улучшения поддержки типов данных даты и времени OLE DB | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- date/time [OLE DB], data type support
- OLE DB, date/time improvements
ms.assetid: d40e3fd6-9057-4371-8236-95cef300603e
author: rothja
ms.author: jroth
ms.openlocfilehash: 834583fdec63a8f613e623c239f9c3a1c9398950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738258"
---
# <a name="data-type-support-for-ole-db-date-and-time-improvements"></a><span data-ttu-id="f8e55-102">Улучшения поддержки типов данных даты и времени OLE DB</span><span class="sxs-lookup"><span data-stu-id="f8e55-102">Data Type Support for OLE DB Date and Time Improvements</span></span>
  <span data-ttu-id="f8e55-103">В этом разделе содержатся сведения о типах OLE DB (собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), которые поддерживают типы данных даты-времени [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8e55-103">This topic provides information about OLE DB ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) types that support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date/time data types.</span></span>  
  
## <a name="data-type-mapping-in-rowsets-and-parameters"></a><span data-ttu-id="f8e55-104">Сопоставление типов данных в наборах строк и параметрах</span><span class="sxs-lookup"><span data-stu-id="f8e55-104">Data Type Mapping in Rowsets and Parameters</span></span>  
 <span data-ttu-id="f8e55-105">OLE DB предоставляет два новых типа данных для поддержки новых типов серверов: DBTYPE_DBTIME2 и DBTYPE_DBTIMESTAMPOFFSET.</span><span class="sxs-lookup"><span data-stu-id="f8e55-105">OLE DB provides two new data types to support the new server types: DBTYPE_DBTIME2 and DBTYPE_DBTIMESTAMPOFFSET.</span></span> <span data-ttu-id="f8e55-106">Следующая таблица отображает полное сопоставление типов серверов.</span><span class="sxs-lookup"><span data-stu-id="f8e55-106">The following table shows the complete server type mapping:</span></span>  
  
|<span data-ttu-id="f8e55-107">Тип данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8e55-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type</span></span>|<span data-ttu-id="f8e55-108">Тип данных OLE DB</span><span class="sxs-lookup"><span data-stu-id="f8e55-108">OLE DB data type</span></span>|<span data-ttu-id="f8e55-109">Значение</span><span class="sxs-lookup"><span data-stu-id="f8e55-109">Value</span></span>|  
|-----------------------------------------|----------------------|-----------|  
|<span data-ttu-id="f8e55-110">DATETIME</span><span class="sxs-lookup"><span data-stu-id="f8e55-110">datetime</span></span>|<span data-ttu-id="f8e55-111">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="f8e55-111">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="f8e55-112">135 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="f8e55-112">135 (oledb.h)</span></span>|  
|<span data-ttu-id="f8e55-113">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="f8e55-113">smalldatetime</span></span>|<span data-ttu-id="f8e55-114">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="f8e55-114">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="f8e55-115">135 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="f8e55-115">135 (oledb.h)</span></span>|  
|<span data-ttu-id="f8e55-116">Дата</span><span class="sxs-lookup"><span data-stu-id="f8e55-116">date</span></span>|<span data-ttu-id="f8e55-117">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="f8e55-117">DBTYPE_DBDATE</span></span>|<span data-ttu-id="f8e55-118">133 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="f8e55-118">133 (oledb.h)</span></span>|  
|<span data-ttu-id="f8e55-119">time</span><span class="sxs-lookup"><span data-stu-id="f8e55-119">time</span></span>|<span data-ttu-id="f8e55-120">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="f8e55-120">DBTYPE_DBTIME2</span></span>|<span data-ttu-id="f8e55-121">145 (sqlncli. h)</span><span class="sxs-lookup"><span data-stu-id="f8e55-121">145 (sqlncli.h)</span></span>|  
|<span data-ttu-id="f8e55-122">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="f8e55-122">datetimeoffset</span></span>|<span data-ttu-id="f8e55-123">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="f8e55-123">DBTYPE_DBTIMESTAMPOFFSET</span></span>|<span data-ttu-id="f8e55-124">146 (sqlncli. h)</span><span class="sxs-lookup"><span data-stu-id="f8e55-124">146 (sqlncli.h)</span></span>|  
|<span data-ttu-id="f8e55-125">datetime2</span><span class="sxs-lookup"><span data-stu-id="f8e55-125">datetime2</span></span>|<span data-ttu-id="f8e55-126">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="f8e55-126">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="f8e55-127">135 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="f8e55-127">135 (oledb.h)</span></span>|  
  
## <a name="data-formats-strings-and-literals"></a><span data-ttu-id="f8e55-128">Форматы данных: строки и литералы</span><span class="sxs-lookup"><span data-stu-id="f8e55-128">Data Formats: Strings and Literals</span></span>  
  
|<span data-ttu-id="f8e55-129">Тип данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8e55-129">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type</span></span>|<span data-ttu-id="f8e55-130">Тип данных OLE DB</span><span class="sxs-lookup"><span data-stu-id="f8e55-130">OLE DB data type</span></span>|<span data-ttu-id="f8e55-131">Формат строки для клиентских преобразований</span><span class="sxs-lookup"><span data-stu-id="f8e55-131">String format for client conversions</span></span>|  
|-----------------------------------------|----------------------|------------------------------------------|  
|<span data-ttu-id="f8e55-132">DATETIME</span><span class="sxs-lookup"><span data-stu-id="f8e55-132">datetime</span></span>|<span data-ttu-id="f8e55-133">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="f8e55-133">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="f8e55-134">'гггг-мм-дд чч:мм:сс:[.999]'</span><span class="sxs-lookup"><span data-stu-id="f8e55-134">'yyyy-mm-dd hh:mm:ss[.999]'</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f8e55-135">для типа Datetime поддерживает значения долей секунды, состоящие из не более чем трех цифр.</span><span class="sxs-lookup"><span data-stu-id="f8e55-135">supports up to three fractional second digits for Datetime.</span></span>|  
|<span data-ttu-id="f8e55-136">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="f8e55-136">smalldatetime</span></span>|<span data-ttu-id="f8e55-137">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="f8e55-137">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="f8e55-138">'гггг-мм-дд чч:мм:сс'</span><span class="sxs-lookup"><span data-stu-id="f8e55-138">'yyyy-mm-dd hh:mm:ss'</span></span><br /><br /> <span data-ttu-id="f8e55-139">Точность этого типа данных составляет одну минуту.</span><span class="sxs-lookup"><span data-stu-id="f8e55-139">This data type has an accuracy of one minute.</span></span> <span data-ttu-id="f8e55-140">При выводе данных секунды будут равны нулю, а при вводе данных они округляются сервером.</span><span class="sxs-lookup"><span data-stu-id="f8e55-140">The seconds component will be zero on output and will be rounded by the server on input.</span></span>|  
|<span data-ttu-id="f8e55-141">Дата</span><span class="sxs-lookup"><span data-stu-id="f8e55-141">date</span></span>|<span data-ttu-id="f8e55-142">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="f8e55-142">DBTYPE_DBDATE</span></span>|<span data-ttu-id="f8e55-143">'гггг-мм-дд'</span><span class="sxs-lookup"><span data-stu-id="f8e55-143">'yyyy-mm-dd'</span></span>|  
|<span data-ttu-id="f8e55-144">time</span><span class="sxs-lookup"><span data-stu-id="f8e55-144">time</span></span>|<span data-ttu-id="f8e55-145">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="f8e55-145">DBTYPE_DBTIME2</span></span>|<span data-ttu-id="f8e55-146">'чч:мм:сс[.9999999]'</span><span class="sxs-lookup"><span data-stu-id="f8e55-146">'hh:mm:ss[.9999999]'</span></span><br /><br /> <span data-ttu-id="f8e55-147">Дополнительно можно указывать доли секунд до семи цифр.</span><span class="sxs-lookup"><span data-stu-id="f8e55-147">Fractional seconds can optionally be specified using up to seven digits.</span></span>|  
|<span data-ttu-id="f8e55-148">datetime2</span><span class="sxs-lookup"><span data-stu-id="f8e55-148">datetime2</span></span>|<span data-ttu-id="f8e55-149">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="f8e55-149">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="f8e55-150">'гггг-мм-дд чч:мм:сс[.еееееее]'</span><span class="sxs-lookup"><span data-stu-id="f8e55-150">'yyyy-mm-dd hh:mm:ss[.fffffff]'</span></span><br /><br /> <span data-ttu-id="f8e55-151">Дополнительно можно указывать доли секунд до семи цифр.</span><span class="sxs-lookup"><span data-stu-id="f8e55-151">Fractional seconds can optionally be specified using up to seven digits.</span></span>|  
|<span data-ttu-id="f8e55-152">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="f8e55-152">datetimeoffset</span></span>|<span data-ttu-id="f8e55-153">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="f8e55-153">DBTYPE_DBTIMESTAMPOFFSET</span></span>|<span data-ttu-id="f8e55-154">'гггг-мм-дд чч:мм:сс[.еееееее] +/-чч:мм'</span><span class="sxs-lookup"><span data-stu-id="f8e55-154">'yyyy-mm-dd hh:mm:ss[.fffffff] +/-hh:mm'</span></span><br /><br /> <span data-ttu-id="f8e55-155">Дополнительно можно указывать доли секунд до семи цифр.</span><span class="sxs-lookup"><span data-stu-id="f8e55-155">Fractional seconds can optionally be specified using up to seven digits.</span></span>|  
  
 <span data-ttu-id="f8e55-156">В escape-последовательностях для литералов даты и времени изменений нет.</span><span class="sxs-lookup"><span data-stu-id="f8e55-156">There are no changes to the escape sequences for date/time literals.</span></span>  
  
 <span data-ttu-id="f8e55-157">Для долей секунды в результатах используется точка (.), а не двоеточие (:).</span><span class="sxs-lookup"><span data-stu-id="f8e55-157">Fractional seconds in results use a dot (.) rather than a colon (:).</span></span>  
  
 <span data-ttu-id="f8e55-158">Строковые значения, возвращаемые в приложения, всегда будут иметь одинаковую длину для данного столбца.</span><span class="sxs-lookup"><span data-stu-id="f8e55-158">String values returned to applications will always be the same length for a given column.</span></span> <span data-ttu-id="f8e55-159">Компоненты года, месяца, дня, часа, минуты и секунды дополняются ведущими нулями до максимальной длины.</span><span class="sxs-lookup"><span data-stu-id="f8e55-159">Year, month, day, hour, minute, and second components will be padded with leading zeros to their maximum width.</span></span> <span data-ttu-id="f8e55-160">Между значениями даты и времени имеется точно один пробел, а также предусмотрен точно один пробел между значением времени и смещением часового пояса.</span><span class="sxs-lookup"><span data-stu-id="f8e55-160">There will be exactly one space between date and time and exactly one space between the time and timezone offset.</span></span> <span data-ttu-id="f8e55-161">Перед смещением часового пояса всегда должен стоять знак.</span><span class="sxs-lookup"><span data-stu-id="f8e55-161">A timezone offset will always be preceded by a sign.</span></span> <span data-ttu-id="f8e55-162">Это знак «плюс» (+), если смещение равен нулю.</span><span class="sxs-lookup"><span data-stu-id="f8e55-162">This sign will be a plus (+) when the offset is zero.</span></span> <span data-ttu-id="f8e55-163">Пробелы между знаком и значением смещения отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="f8e55-163">There will be no white space between the sign and the offset value.</span></span> <span data-ttu-id="f8e55-164">Доли секунды дополняются замыкающими нулями при необходимости до заданной точности столбца, но не более.</span><span class="sxs-lookup"><span data-stu-id="f8e55-164">Fractional seconds will be padded with trailing zeros, if necessary, up to the defined precision for the column, but no further.</span></span> <span data-ttu-id="f8e55-165">Для столбцов datetime количество цифр с обозначением долей секунды равно трем.</span><span class="sxs-lookup"><span data-stu-id="f8e55-165">For datetime columns, there will be three fractional seconds digits.</span></span> <span data-ttu-id="f8e55-166">Для столбцов smalldatetime цифры с обозначением долей секунды отсутствуют, а секунды всегда равны нулю.</span><span class="sxs-lookup"><span data-stu-id="f8e55-166">For smalldatetime columns, there will be no fractional seconds digits and the seconds will always be zero.</span></span>  
  
 <span data-ttu-id="f8e55-167">Приложения позволяют применять более гибкие преобразования из строковых значений, а также обеспечивают возможность использования значений компонентов с меньшей шириной по сравнению с максимальной.</span><span class="sxs-lookup"><span data-stu-id="f8e55-167">Conversions from string values provided by the application will be more flexible and will allow component values less than maximum width.</span></span> <span data-ttu-id="f8e55-168">Годы могут быть представлены цифрами в количестве от 1 до 4.</span><span class="sxs-lookup"><span data-stu-id="f8e55-168">Years can be 1-4 digits.</span></span> <span data-ttu-id="f8e55-169">Месяцы, дни, часы, минуты и секунды могут быть представлены 1 или 2 цифрами.</span><span class="sxs-lookup"><span data-stu-id="f8e55-169">Months, days, hours, minutes, and seconds can be 1 or 2 digits.</span></span> <span data-ttu-id="f8e55-170">Между значениями даты и времени, а также значением времени и смещением часового пояса может находиться произвольное число пробелов.</span><span class="sxs-lookup"><span data-stu-id="f8e55-170">There can be arbitrary white space between date/time and time/timezone offsets.</span></span> <span data-ttu-id="f8e55-171">Смещение, равное нулю часов и нулю минут, может иметь знак плюс или минус.</span><span class="sxs-lookup"><span data-stu-id="f8e55-171">The sign of an offset with zero hours and zero minutes can be plus or minus.</span></span> <span data-ttu-id="f8e55-172">Допускается использование замыкающих нулей для долей секунд вплоть до максимального количества цифр, равного 9.</span><span class="sxs-lookup"><span data-stu-id="f8e55-172">Trailing zeros are allowed for fractional seconds up to a maximum of 9 digits.</span></span> <span data-ttu-id="f8e55-173">Время может завершаться десятичной запятой без указания цифр долей секунды.</span><span class="sxs-lookup"><span data-stu-id="f8e55-173">A time component can terminate with a decimal point and no fractional seconds digits.</span></span>  
  
 <span data-ttu-id="f8e55-174">Пустая строка не является допустимым литералом даты-времени, она не представляет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="f8e55-174">An empty string is not a valid date/time literal and it does not represent a NULL value.</span></span> <span data-ttu-id="f8e55-175">Попытка преобразовать пустую строку в значение даты-времени приведет к ошибкам со значением SQLState, равным 22018, и сообщением «Недопустимое символьное значение для спецификации приведения».</span><span class="sxs-lookup"><span data-stu-id="f8e55-175">An attempt to convert an empty string to a date/time value will result in errors with SQLState 22018 and the message "Invalid character value for cast specification".</span></span>  
  
## <a name="data-formats-data-structures"></a><span data-ttu-id="f8e55-176">Форматы данных: структуры данных</span><span class="sxs-lookup"><span data-stu-id="f8e55-176">Data Formats: Data Structures</span></span>  
 <span data-ttu-id="f8e55-177">В структурах, зависящих от поставщика OLE DB, на OLE DB налагаются те же ограничения, что и на ODBC.</span><span class="sxs-lookup"><span data-stu-id="f8e55-177">In the OLE DB-specific structures described below, OLE DB conforms to the same constraints as ODBC.</span></span> <span data-ttu-id="f8e55-178">Следующие определения взяты из описания григорианского календаря.</span><span class="sxs-lookup"><span data-stu-id="f8e55-178">These are taken from the Gregorian calendar:</span></span>  
  
-   <span data-ttu-id="f8e55-179">Диапазон месяцев — от 1 до 12 включительно.</span><span class="sxs-lookup"><span data-stu-id="f8e55-179">Month range is 1 through 12.</span></span>  
  
-   <span data-ttu-id="f8e55-180">Диапазон поля даты — от 1 до количества дней в месяце включительно, он должен быть согласован с полями года и месяца с учетом високосного года.</span><span class="sxs-lookup"><span data-stu-id="f8e55-180">Day field range is 1 through the number of days in the month, and must be consistent with year and month fields, taking account of leap years.</span></span>  
  
-   <span data-ttu-id="f8e55-181">Диапазон часов — от 0 до 23 включительно.</span><span class="sxs-lookup"><span data-stu-id="f8e55-181">Hour range is 0 through 23.</span></span>  
  
-   <span data-ttu-id="f8e55-182">Диапазон минут — от 0 до 59 включительно.</span><span class="sxs-lookup"><span data-stu-id="f8e55-182">Minute range is 0 through 59.</span></span>  
  
-   <span data-ttu-id="f8e55-183">Диапазон секунд — от 0 до 59.</span><span class="sxs-lookup"><span data-stu-id="f8e55-183">Seconds range from 0 through 59.</span></span> <span data-ttu-id="f8e55-184">Это позволяет использовать до двух корректировочных секунд для синхронизации со звездным временем.</span><span class="sxs-lookup"><span data-stu-id="f8e55-184">This allows up to two leap seconds to maintain synchronization with sidereal time.</span></span>  
  
 <span data-ttu-id="f8e55-185">Реализации следующих существующих структур OLE DB были изменены в целях совместимости с новыми типами данных даты и времени [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8e55-185">Implementations for the following existing OLE DB structs have been modified to support the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date and time data types.</span></span> <span data-ttu-id="f8e55-186">При этом определения не изменились.</span><span class="sxs-lookup"><span data-stu-id="f8e55-186">The definitions, however, have not changed.</span></span>  
  
-   <span data-ttu-id="f8e55-187">DBTYPE_DATE (Тип автоматизации DATE.</span><span class="sxs-lookup"><span data-stu-id="f8e55-187">DBTYPE_DATE (This is an automation DATE type.</span></span> <span data-ttu-id="f8e55-188">Имеет внутреннее представление `double`.</span><span class="sxs-lookup"><span data-stu-id="f8e55-188">It is internally represented as a `double`..</span></span> <span data-ttu-id="f8e55-189">Целая часть числа равна числу дней, прошедшему с 30 декабря 1899 г., а десятичная часть равна части дня.</span><span class="sxs-lookup"><span data-stu-id="f8e55-189">The whole part is the number of days since December 30, 1899 and the fractional part is the fraction of a day.</span></span> <span data-ttu-id="f8e55-190">Точность этого типа составляет 1 секунду, поэтому значение масштаба фактически равно 0.)</span><span class="sxs-lookup"><span data-stu-id="f8e55-190">This type has an accuracy of 1 second, so has an effective scale of 0.)</span></span>  
  
-   <span data-ttu-id="f8e55-191">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="f8e55-191">DBTYPE_DBDATE</span></span>  
  
-   <span data-ttu-id="f8e55-192">DBTYPE_DBTIME</span><span class="sxs-lookup"><span data-stu-id="f8e55-192">DBTYPE_DBTIME</span></span>  
  
-   <span data-ttu-id="f8e55-193">DBTYPE_DBTIMESTAMP (Поле дробной части определяется в OLE DB как число миллиардных долей секунды (наносекунд) и имеет диапазон от 0 до 999 999 999.)</span><span class="sxs-lookup"><span data-stu-id="f8e55-193">DBTYPE_DBTIMESTAMP (the fraction field is defined by OLE DB as the number of billionths of a second (nanoseconds) and ranges from 0-999,999,999)</span></span>  
  
-   <span data-ttu-id="f8e55-194">DBTYPE_FILETIME</span><span class="sxs-lookup"><span data-stu-id="f8e55-194">DBTYPE_FILETIME</span></span>  
  
### <a name="dbtype_dbtime2"></a><span data-ttu-id="f8e55-195">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="f8e55-195">DBTYPE_DBTIME2</span></span>  
 <span data-ttu-id="f8e55-196">Эта структура дополняется до 12 байт как в 32-разрядных, так и в 64-разрядных операционных системах.</span><span class="sxs-lookup"><span data-stu-id="f8e55-196">This struct is padded to 12 bytes on both 32-bit and 64-bit operating systems.</span></span>  
  
```  
typedef struct tagDBTIME2 {  
    USHORT hour;  
    USHORT minute;  
    USHORT second;  
    ULONG fraction;  
    } DBTIME2;  
```  
  
### <a name="dbtype_-dbtimestampoffset"></a><span data-ttu-id="f8e55-197">DBTYPE_ DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="f8e55-197">DBTYPE_ DBTIMESTAMPOFFSET</span></span>  
  
```  
typedef struct tagDBTIMESTAMPOFFSET {  
    SHORT year;  
    USHORT month;  
    USHORT day;  
    USHORT hour;  
    USHORT minute;  
    USHORT second;  
    ULONG fraction;  
    SHORT timezone_hour;  
    SHORT timezone_minute;  
    } DBTIMESTAMPOFFSET;  
```  
  
 <span data-ttu-id="f8e55-198">Если значение `timezone_hour` отрицательно, значение `timezone_minute` должно быть отрицательным или нулевым.</span><span class="sxs-lookup"><span data-stu-id="f8e55-198">If `timezone_hour` is negative, `timezone_minute` must be negative or zero.</span></span> <span data-ttu-id="f8e55-199">Если значение `timezone_hour` положительно, значение `timezone minute` должно быть положительным или нулевым.</span><span class="sxs-lookup"><span data-stu-id="f8e55-199">If `timezone_hour` is positive, `timezone minute` must be positive or zero.</span></span> <span data-ttu-id="f8e55-200">Если значение `timezone_hour` равно нулю, `timezone minute` может содержать значение от -59 до +59.</span><span class="sxs-lookup"><span data-stu-id="f8e55-200">If `timezone_hour` is zero, `timezone minute` can hold a value between -59 and +59.</span></span>  
  
### <a name="ssvariant"></a><span data-ttu-id="f8e55-201">SSVARIANT</span><span class="sxs-lookup"><span data-stu-id="f8e55-201">SSVARIANT</span></span>  
 <span data-ttu-id="f8e55-202">Эта структура изменена и теперь содержит новые типы DBTYPE_DBTIME2 и DBTYPE_DBTIMESTAMPOFFSET, а также шкалу дробных долей секунды для соответствующих типов.</span><span class="sxs-lookup"><span data-stu-id="f8e55-202">This struct now includes the new structures, DBTYPE_DBTIME2 and DBTYPE_DBTIMESTAMPOFFSET, and adds fractional seconds scale for appropriate types.</span></span>  
  
```  
struct SSVARIANT {  
   SSVARTYPE vt;  
   DWORD dwReserved1;  
   DWORD dwReserved2;  
   union {  
// ...  
      DBTIMESTAMP tsDateTimeVal;  
      DBDATE dDateVal;  
      struct _Time2Val {  
         DBTIME2 tTime2Val;  
         BYTE bScale;  
      } Time2Val;  
      struct _DateTimeVal {  
         DBTIMESTAMP tsDateTimeVal;  
         BYTE bScale;  
      } DateTimeVal;  
      struct _DateTimeOffsetVal {   
         DBTIMESTAMPOFFSET tsoDateTimeOffsetVal;  
         BYTE bScale;  
      } DateTimeOffsetVal;  
// ...  
   };  
};  
```  
  
 <span data-ttu-id="f8e55-203">Кроме того, перечисление, связанное с типом шифрования SSVARIANT, который определяет тип перечисления, будет расширено следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f8e55-203">In addition, the enum associated with SSVARIANT type encoding, which determines the type of the enum, will be extended as follows:</span></span>  
  
```  
enum SQLVARENUM {  
// ...  
   // Datetime  
   VT_SS_DATETIME      = DBTYPE_DBTIMESTAMP,  
   VT_SS_SMALLDATETIME = 206,  
  
   VT_SS_DATE = DBTYPE_DBDATE,  
   VT_SS_TIME2 = DBTYPE_DBTIME2,  
   VT_SS_DATETIME2 = 212  
   VT_SS_DATETIMEOFFSET = DBTYPE_DBTIMESTAMPOFFSET  
};  
```  
  
 <span data-ttu-id="f8e55-204">Приложения, переводимые на использование собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], которые используют тип данных `sql_variant` и ограниченную точность `datetime`, должны быть обновлены, если базовая схема обновлена для использования типа данных `datetime2` вместо `datetime`.</span><span class="sxs-lookup"><span data-stu-id="f8e55-204">Applications migrating to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client that use `sql_variant` and rely on the limited precision of `datetime` will have to be updated if the underlying schema is updated to use `datetime2` rather than `datetime`.</span></span>  
  
 <span data-ttu-id="f8e55-205">Макрос доступа SSVARIANT также расширен с помощью следующего дополнения:</span><span class="sxs-lookup"><span data-stu-id="f8e55-205">The access macros for SSVARIANT have also been extended with the addition of the following:</span></span>  
  
```  
#define V_SS_DATETIME2(X)       V_SS_UNION(X, DateTimeVal)  
#define V_SS_TIME2(X)           V_SS_UNION(X, Time2Val)  
#define V_SS_DATE(X)            V_SS_UNION(X, dDateVal)  
#define V_SS_DATETIMEOFFSET(X)  V_SS_UNION(X, DateTimeOffsetVal)  
```  
  
## <a name="data-type-mapping-in-itabledefinitioncreatetable"></a><span data-ttu-id="f8e55-206">Сопоставление типов данных в методе ITableDefinition::CreateTable</span><span class="sxs-lookup"><span data-stu-id="f8e55-206">Data Type Mapping in ITableDefinition::CreateTable</span></span>  
 <span data-ttu-id="f8e55-207">Следующее сопоставление типов используется со структурами DBCOLUMNDESC в ITableDefinition::CreateTable:</span><span class="sxs-lookup"><span data-stu-id="f8e55-207">The following type mapping is used with DBCOLUMNDESC structures used by ITableDefinition::CreateTable:</span></span>  
  
|<span data-ttu-id="f8e55-208">Тип данных OLE DB (*wType*)</span><span class="sxs-lookup"><span data-stu-id="f8e55-208">OLE DB data type (*wType*)</span></span>|<span data-ttu-id="f8e55-209">Тип данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8e55-209">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type</span></span>|<span data-ttu-id="f8e55-210">Примечания</span><span class="sxs-lookup"><span data-stu-id="f8e55-210">Notes</span></span>|  
|----------------------------------|-----------------------------------------|-----------|  
|<span data-ttu-id="f8e55-211">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="f8e55-211">DBTYPE_DBDATE</span></span>|<span data-ttu-id="f8e55-212">Дата</span><span class="sxs-lookup"><span data-stu-id="f8e55-212">date</span></span>||  
|<span data-ttu-id="f8e55-213">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="f8e55-213">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="f8e55-214">`datetime2`(p)</span><span class="sxs-lookup"><span data-stu-id="f8e55-214">`datetime2`(p)</span></span>|<span data-ttu-id="f8e55-215">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента проверяет элемент *bScale* дбколумдеск, чтобы определить точность доли секунды.</span><span class="sxs-lookup"><span data-stu-id="f8e55-215">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider inspects the DBCOLUMDESC *bScale* member to determine the fractional seconds precision.</span></span>|  
|<span data-ttu-id="f8e55-216">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="f8e55-216">DBTYPE_DBTIME2</span></span>|<span data-ttu-id="f8e55-217">`time`(p)</span><span class="sxs-lookup"><span data-stu-id="f8e55-217">`time`(p)</span></span>|<span data-ttu-id="f8e55-218">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента проверяет элемент *bScale* дбколумдеск, чтобы определить точность доли секунды.</span><span class="sxs-lookup"><span data-stu-id="f8e55-218">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider inspects the DBCOLUMDESC *bScale* member to determine the fractional seconds precision.</span></span>|  
|<span data-ttu-id="f8e55-219">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="f8e55-219">DBTYPE_DBTIMESTAMPOFFSET</span></span>|<span data-ttu-id="f8e55-220">`datetimeoffset`(p)</span><span class="sxs-lookup"><span data-stu-id="f8e55-220">`datetimeoffset`(p)</span></span>|<span data-ttu-id="f8e55-221">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента проверяет элемент *bScale* дбколумдеск, чтобы определить точность доли секунды.</span><span class="sxs-lookup"><span data-stu-id="f8e55-221">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider inspects the DBCOLUMDESC *bScale* member to determine the fractional seconds precision.</span></span>|  
  
 <span data-ttu-id="f8e55-222">Если приложение указывает DBTYPE_DBTIMESTAMP в *wType*, оно может переопределить сопоставление `datetime2` , указав имя типа в *pwszTypeName*.</span><span class="sxs-lookup"><span data-stu-id="f8e55-222">When an application specifies DBTYPE_DBTIMESTAMP in *wType*, it can override the mapping to `datetime2` by supplying a type name in *pwszTypeName*.</span></span> <span data-ttu-id="f8e55-223">Если `datetime` указан, *bScale* должен иметь значение 3.</span><span class="sxs-lookup"><span data-stu-id="f8e55-223">If `datetime` is specified, *bScale* must be 3.</span></span> <span data-ttu-id="f8e55-224">Если `smalldatetime` указан, *bScale* должен быть равен 0.</span><span class="sxs-lookup"><span data-stu-id="f8e55-224">If `smalldatetime` is specified, *bScale* must be 0.</span></span> <span data-ttu-id="f8e55-225">Если *bScale* не согласуется с *wType* и *pwszTypeName*, возвращается DB_E_BADSCALE.</span><span class="sxs-lookup"><span data-stu-id="f8e55-225">If *bScale* is not consistent with *wType* and *pwszTypeName*,DB_E_BADSCALE is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8e55-226">См. также:</span><span class="sxs-lookup"><span data-stu-id="f8e55-226">See Also</span></span>  
 [<span data-ttu-id="f8e55-227">Улучшения функций даты и времени &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f8e55-227">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
