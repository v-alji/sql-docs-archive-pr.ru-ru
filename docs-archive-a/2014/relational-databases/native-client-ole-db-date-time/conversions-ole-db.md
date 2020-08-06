---
title: Привязки и преобразования (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- conversions [OLE DB]
- bindings [OLE DB]
- OLE DB, bindings and conversions
ms.assetid: c187df58-a8c8-4c74-a76f-663abbc5f0c1
author: rothja
ms.author: jroth
ms.openlocfilehash: 95c73bdad80b5f948a45235ad208ab307fcceff3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667724"
---
# <a name="bindings-and-conversions-ole-db"></a><span data-ttu-id="3f6a9-102">Привязки и преобразования (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="3f6a9-102">Bindings and Conversions (OLE DB)</span></span>
  <span data-ttu-id="3f6a9-103">В этом разделе описано преобразование между типами `datetime` и `datetimeoffset`.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-103">This section discusses how to convert between `datetime` and `datetimeoffset` values.</span></span> <span data-ttu-id="3f6a9-104">Преобразования, описанные в этом разделе, либо уже предоставлены OLE DB, либо являются согласованным расширением OLE DB.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-104">The conversions described in this section are either already provided by OLE DB or are a consistent extension of OLE DB.</span></span>  
  
 <span data-ttu-id="3f6a9-105">Формат литералов и строк для дат и времени в OLE DB обычно соответствует ISO и не зависит от локали, установленной на клиенте.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-105">The format of literals and strings for dates and times in OLE DB generally follows ISO, and is not dependent on the client locale.</span></span> <span data-ttu-id="3f6a9-106">Единственное исключение — DBTYPE_DATE, для которого стандартом является OLE-автоматизация.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-106">One exception is DBTYPE_DATE, where the standard is OLE Automation.</span></span> <span data-ttu-id="3f6a9-107">Однако, поскольку собственный клиент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] проводит преобразования из одного типа в другой только при передаче данных с клиента или на клиент, приложение никак не может заставить собственный клиент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] проводить преобразования между типом DBTYPE_DATE и строковыми форматами.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-107">However, because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client only converts between types when data is transmitted to or from the client, there is no way for an application to force [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client to convert between DBTYPE_DATE and string formats.</span></span> <span data-ttu-id="3f6a9-108">Во всех остальных случаях строки используют следующие форматы (скобками отмечены необязательные элементы).</span><span class="sxs-lookup"><span data-stu-id="3f6a9-108">Otherwise, strings use the following formats (text in brackets indicates an optional element):</span></span>  
  
-   <span data-ttu-id="3f6a9-109">Формат строк `datetime` и `datetimeoffset`:</span><span class="sxs-lookup"><span data-stu-id="3f6a9-109">The format of `datetime` and `datetimeoffset` strings is:</span></span>  
  
     <span data-ttu-id="3f6a9-110">*гггг* - *mm* - *дд*[ *чч*:*мм*:*СС*[.\* 9999999\*] [??</span><span class="sxs-lookup"><span data-stu-id="3f6a9-110">*yyyy*-*mm*-*dd*[ *hh*:*mm*:*ss*[.*9999999*][ ??</span></span> <span data-ttu-id="3f6a9-111">*чч*:*мм*]]</span><span class="sxs-lookup"><span data-stu-id="3f6a9-111">*hh*:*mm*]]</span></span>  
  
-   <span data-ttu-id="3f6a9-112">Формат строк `time`:</span><span class="sxs-lookup"><span data-stu-id="3f6a9-112">The format of `time` strings is:</span></span>  
  
     <span data-ttu-id="3f6a9-113">*чч*:*мм*:*сс*[.*9999999*]</span><span class="sxs-lookup"><span data-stu-id="3f6a9-113">*hh*:*mm*:*ss*[.*9999999*]</span></span>  
  
-   <span data-ttu-id="3f6a9-114">Формат строк `date`:</span><span class="sxs-lookup"><span data-stu-id="3f6a9-114">The format of `date` strings is:</span></span>  
  
     <span data-ttu-id="3f6a9-115">*гггг*-*мм*-*дд*</span><span class="sxs-lookup"><span data-stu-id="3f6a9-115">*yyyy*-*mm*-*dd*</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f6a9-116">Предыдущие версии собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и SQLOLEDB реализовали преобразования OLE в случаях, когда стандартные преобразования возвращали ошибку.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-116">Earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client and SQLOLEDB implemented OLE conversions, in case standard conversions failed.</span></span> <span data-ttu-id="3f6a9-117">В результате некоторые преобразования, проводимые собственным клиентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] версии 10.0 и более поздних версий, отличаются от спецификации OLE DB.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-117">As a result, some conversions performed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 10.0 and later differ from the OLE DB specification.</span></span>  
  
 <span data-ttu-id="3f6a9-118">Преобразования из строк обеспечивают гибкость в отношении пробелов и ширины полей.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-118">Conversions from strings allow flexibility in white space and field width.</span></span> <span data-ttu-id="3f6a9-119">Дополнительные сведения см. в разделе "форматы данных: строки и литералы" статьи [Поддержка типов данных для OLE DB улучшения даты и времени](data-type-support-for-ole-db-date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="3f6a9-119">For more information, see the "Data Formats: Strings and Literals" section in [Data Type Support for OLE DB Date and Time Improvements](data-type-support-for-ole-db-date-and-time-improvements.md).</span></span>  
  
 <span data-ttu-id="3f6a9-120">Далее приведены общие правила преобразования.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-120">The following are general conversion rules:</span></span>  
  
-   <span data-ttu-id="3f6a9-121">При преобразовании строки в тип данных даты-времени строка сначала проходит синтаксический анализ как литерал ISO.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-121">When a string is converted to a date/time type, the string is first parsed as an ISO literal.</span></span> <span data-ttu-id="3f6a9-122">Если анализ завершился неудачей, строка проходит синтаксический анализ как литерал даты OLE, содержащий компонент времени.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-122">If this fails, the string is parsed as an OLE date literal, which has time components.</span></span>  
  
-   <span data-ttu-id="3f6a9-123">Если время отсутствует, но получатель способен его хранить, оно устанавливается в нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-123">If no time is present but the receiver can store time, the time is set to zero.</span></span> <span data-ttu-id="3f6a9-124">Если дата отсутствует, но принимающий объект может хранить дату, этой дате присваивается значение сегодняшней даты при использовании преобразования ISO и 30 декабря 1899 года при использовании преобразования OLE.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-124">If no date is present but the receiver can store a date, the date is set to the current date when ISO conversions are used and to 1899-12-30 when OLE conversions are used.</span></span>  
  
-   <span data-ttu-id="3f6a9-125">Если клиент использует тип даты, в котором не указан часовой пояс, но сервер может хранить информацию о часовом поясе, предполагается, что данные клиента используют часовой пояс клиента.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-125">If no timezone is present in the data type that the client is using, but the server can store timezone, the data on the client is assumed to be in the client timezone.</span></span>  
  
-   <span data-ttu-id="3f6a9-126">Если клиент содержит информацию о часовом поясе, но на сервере данных часового пояса нет, предполагается, что часовой пояс задан в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-126">If no timezone is present at the server but the client has timezone information, the UTC timezone is assumed.</span></span> <span data-ttu-id="3f6a9-127">Это отличается от поведения сервера.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-127">This differs from server behavior.</span></span>  
  
-   <span data-ttu-id="3f6a9-128">Если время присутствует, но получатель не способен его хранить, компонент времени пропускается.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-128">If the time is present but the receiver cannot store time, the time component is ignored.</span></span>  
  
-   <span data-ttu-id="3f6a9-129">Если дата присутствует, но получатель не способен ее хранить, компонент даты пропускается.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-129">If the date is present but the receiver cannot store the date, the date component is ignored.</span></span>  
  
-   <span data-ttu-id="3f6a9-130">Если при преобразовании с клиента на сервер происходит усечение секунд или долей секунд, возвращается значение DB_E_ERRORSOCCURRED и устанавливается состояние DBSTATUS_E_DATAOVERFLOW.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-130">If truncation of seconds or fractional seconds occurs when converting from client to server, DB_E_ERRORSOCCURRED is returned and the status DBSTATUS_E_DATAOVERFLOW is set.</span></span>  
  
-   <span data-ttu-id="3f6a9-131">Если усечение секунд или долей секунд происходит при преобразовании с клиента на сервер, устанавливается состояние DBSTATUS_S_TRUNCATED.</span><span class="sxs-lookup"><span data-stu-id="3f6a9-131">If truncation of seconds or fractional seconds occurs when converting from server to client, DBSTATUS_S_TRUNCATED is set</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3f6a9-132">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="3f6a9-132">In This Section</span></span>  
 [<span data-ttu-id="3f6a9-133">Преобразования, выполняемые при передаче от клиента к серверу</span><span class="sxs-lookup"><span data-stu-id="3f6a9-133">Conversions Performed from Client to Server</span></span>](conversions-performed-from-client-to-server.md)  
 <span data-ttu-id="3f6a9-134">Описывает преобразования даты-времени, проводимые между клиентским приложением, написанным с помощью собственного клиента OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], и [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (или более поздней версией).</span><span class="sxs-lookup"><span data-stu-id="3f6a9-134">Describes date/time conversions performed between a client application written with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later).</span></span>  
  
 [<span data-ttu-id="3f6a9-135">Преобразования, выполняемые при передаче от сервера к клиенту</span><span class="sxs-lookup"><span data-stu-id="3f6a9-135">Conversions Performed from Server to Client</span></span>](conversions-performed-from-server-to-client.md)  
 <span data-ttu-id="3f6a9-136">Описывает преобразования даты-времени, проводимые между [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (или более поздней версией) и клиентским приложением, написанным с помощью собственного клиента OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f6a9-136">Describes date/time conversions performed between [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later) and a client application written with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f6a9-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="3f6a9-137">See Also</span></span>  
 [<span data-ttu-id="3f6a9-138">Улучшения функций даты и времени &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="3f6a9-138">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
