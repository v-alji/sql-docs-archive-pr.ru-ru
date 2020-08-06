---
title: Преобразования типов данных DateTime (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- conversions [ODBC]
- bindings [ODBC]
- ODBC, bindings and conversions
ms.assetid: 66b9d282-c88d-40e5-93c2-fd5499a74458
author: rothja
ms.author: jroth
ms.openlocfilehash: 142e4388cb87055ddbc6faa7d5b1a92a627738c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666551"
---
# <a name="datetime-data-type-conversions-odbc"></a><span data-ttu-id="46385-102">Преобразования типа данных datetime (ODBC)</span><span class="sxs-lookup"><span data-stu-id="46385-102">datetime Data Type Conversions (ODBC)</span></span>
  <span data-ttu-id="46385-103">Следующие привязки либо уже определены в ODBC, либо являются согласованными с расширением ODBC.</span><span class="sxs-lookup"><span data-stu-id="46385-103">The following conversions are either already defined by ODBC or are a consistent extension of ODBC.</span></span> <span data-ttu-id="46385-104">Преобразования, поддерживаемые каждым поставщиком, определяются сообществом, обслуживаемым поставщиком; в результате — часто возникают несоответствия между поставщиками.</span><span class="sxs-lookup"><span data-stu-id="46385-104">The conversions supplied by each provider are determined by the community served by the provider, and there are often inconsistencies between providers as a result.</span></span> <span data-ttu-id="46385-105">Значения в квадратных скобках необязательны.</span><span class="sxs-lookup"><span data-stu-id="46385-105">Values in square brackets are optional.</span></span>  
  
-   <span data-ttu-id="46385-106">Формат строк типа datetime — «гггг-мм-дд[ чч:мм:сс[.9999999][ плюс/минус чч:мм]]».</span><span class="sxs-lookup"><span data-stu-id="46385-106">The format of datetime strings is 'yyyy-mm-dd[ hh:mm:ss[.9999999][ plus/minus hh:mm]]'</span></span>  
  
-   <span data-ttu-id="46385-107">Формат строк типа time — «чч:мм:сс[.9999999]».</span><span class="sxs-lookup"><span data-stu-id="46385-107">The format of time strings is 'hh:mm:ss[.9999999]'</span></span>  
  
-   <span data-ttu-id="46385-108">Формат строк типа date — «гггг-мм-дд».</span><span class="sxs-lookup"><span data-stu-id="46385-108">The format of date strings is 'yyyy-mm-dd'</span></span>  
  
 <span data-ttu-id="46385-109">Преобразования из строк обеспечивают гибкость в отношении пробелов и ширины полей.</span><span class="sxs-lookup"><span data-stu-id="46385-109">Conversions from strings allow flexibility in white space and field width.</span></span> <span data-ttu-id="46385-110">Дополнительные сведения см. в подразделе «форматы данных: строки и литералы» статьи [Поддержка типов данных для улучшений даты и времени ODBC](data-type-support-for-odbc-date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="46385-110">For more information, see the "Data Formats: Strings and Literals" section of [Data Type Support for ODBC Date and Time Improvements](data-type-support-for-odbc-date-and-time-improvements.md).</span></span>  
  
 <span data-ttu-id="46385-111">Далее приведены общие правила преобразования.</span><span class="sxs-lookup"><span data-stu-id="46385-111">The following are general conversion rules:</span></span>  
  
-   <span data-ttu-id="46385-112">Если время отсутствует, но получатель способен его хранить, оно устанавливается в нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="46385-112">If no time is present but the receiver can store time, the time is set to zero.</span></span>  
  
-   <span data-ttu-id="46385-113">Если дата отсутствует, но получатель может ее хранить, используется текущая дата.</span><span class="sxs-lookup"><span data-stu-id="46385-113">If no date is present but the receiver can store date, the current date is used.</span></span>  
  
-   <span data-ttu-id="46385-114">Если в типе данных, используемых клиентом, отсутствует часовой пояс, но сервер может его хранить, дата сохраняется в часовом поясе клиента.</span><span class="sxs-lookup"><span data-stu-id="46385-114">If no timezone is present in the data type that the client is using but the server can store timezone, the date is stored in the client timezone.</span></span> <span data-ttu-id="46385-115">Обратите внимание на отличие от поведения сервера.</span><span class="sxs-lookup"><span data-stu-id="46385-115">Note that this differs from the server behavior.</span></span>  
  
-   <span data-ttu-id="46385-116">Если в типе сервера отсутствует часовой пояс, а в типе клиента он есть, то перед сохранением на сервере время преобразуется в формат UTC.</span><span class="sxs-lookup"><span data-stu-id="46385-116">If no timezone is present in the server type but the client type has a timezone, time is converted to UTC before being stored on the server.</span></span>  
  
-   <span data-ttu-id="46385-117">Если время присутствует, но получатель не может его хранить, то компонент времени не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="46385-117">If time is present but the receiver cannot store time, the time component is ignored.</span></span>  
  
-   <span data-ttu-id="46385-118">Если дата присутствует, но получатель не может ее хранить, то компонент даты не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="46385-118">If a date is present but the receiver cannot store the date, the date component is ignored.</span></span>  
  
-   <span data-ttu-id="46385-119">Если при преобразовании из C в SQL возникает усечение секунд или долей секунд, то создается запись диагностики с кодом SQLSTATE 22008 и сообщением «Переполнение поля Datetime».</span><span class="sxs-lookup"><span data-stu-id="46385-119">If truncation of seconds or fractional seconds occurs when converting from C to SQL, a diagnostic record is generated with SQLSTATE 22008 and the message "Datetime field overflow".</span></span>  
  
-   <span data-ttu-id="46385-120">Если при преобразовании из SQL в C возникает усечение секунд или долей секунд, то создается запись диагностики с кодом SQLSTATE 01S07 и сообщением «Частичное усечение».</span><span class="sxs-lookup"><span data-stu-id="46385-120">If truncation of seconds or fractional seconds occurs when converting from SQL to C, a diagnostic record is generated with SQLSTATE 01S07 and the message "Fractional truncation".</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="46385-121">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="46385-121">In This Section</span></span>  
 [<span data-ttu-id="46385-122">Преобразования из C в SQL</span><span class="sxs-lookup"><span data-stu-id="46385-122">Conversions from C to SQL</span></span>](datetime-data-type-conversions-from-c-to-sql.md)  
 <span data-ttu-id="46385-123">Перечисляет проблемы, которые необходимо решить при преобразовании типов C в типы даты-времени [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46385-123">Lists issues to consider when you convert from C types to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data/time types.</span></span>  
  
 [<span data-ttu-id="46385-124">Преобразования из SQL в C</span><span class="sxs-lookup"><span data-stu-id="46385-124">Conversions from SQL to C</span></span>](datetime-data-type-conversions-from-sql-to-c.md)  
 <span data-ttu-id="46385-125">Перечисляет проблемы, которые необходимо решить при преобразовании типов даты и времени [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в типы C.</span><span class="sxs-lookup"><span data-stu-id="46385-125">Lists issues to consider when you convert from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data/time types to C types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46385-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="46385-126">See Also</span></span>  
 [<span data-ttu-id="46385-127">Улучшения даты и времени &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="46385-127">Date and Time Improvements &#40;ODBC&#41;</span></span>](date-and-time-improvements-odbc.md)  
  
  
