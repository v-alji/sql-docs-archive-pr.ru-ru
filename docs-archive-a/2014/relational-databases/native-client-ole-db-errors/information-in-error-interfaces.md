---
title: Сведения в интерфейсах обработки ошибок | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- IErrorRecords interface
- IErrorInfo interface
- OLE DB error handling, error interfaces
- ISQLErrorInfo interface
- errors [OLE DB], error interfaces
ms.assetid: 4620f03f-1193-43e7-ba19-ad022737d300
author: rothja
ms.author: jroth
ms.openlocfilehash: e9859ccbd804ba15685d84b98cbe74d4b096d98c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667062"
---
# <a name="information-in-error-interfaces"></a><span data-ttu-id="390fc-102">Сведения в интерфейсах обработки ошибок</span><span class="sxs-lookup"><span data-stu-id="390fc-102">Information in Error Interfaces</span></span>
  <span data-ttu-id="390fc-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента сообщает о некоторых ошибках и состоянии в определяемых OLE DB интерфейсах ошибок **IErrorInfo**, **IErrorRecords**и **ISQLErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="390fc-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider reports some error and status information in the OLE DB-defined error interfaces **IErrorInfo**, **IErrorRecords**, and **ISQLErrorInfo**.</span></span>  
  
 <span data-ttu-id="390fc-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента поддерживает функции членов **IErrorInfo** следующим образом.</span><span class="sxs-lookup"><span data-stu-id="390fc-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **IErrorInfo** member functions as follows.</span></span>  
  
|<span data-ttu-id="390fc-105">Функция-член</span><span class="sxs-lookup"><span data-stu-id="390fc-105">Member function</span></span>|<span data-ttu-id="390fc-106">Описание</span><span class="sxs-lookup"><span data-stu-id="390fc-106">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="390fc-107">**GetDescription**</span><span class="sxs-lookup"><span data-stu-id="390fc-107">**GetDescription**</span></span>|<span data-ttu-id="390fc-108">Строка описательного сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="390fc-108">Descriptive error message string.</span></span>|  
|<span data-ttu-id="390fc-109">**GetGUID**</span><span class="sxs-lookup"><span data-stu-id="390fc-109">**GetGUID**</span></span>|<span data-ttu-id="390fc-110">Идентификатор GUID интерфейса, в котором была определена ошибка.</span><span class="sxs-lookup"><span data-stu-id="390fc-110">GUID of the interface that defined the error.</span></span>|  
|<span data-ttu-id="390fc-111">**GetHelpContext**</span><span class="sxs-lookup"><span data-stu-id="390fc-111">**GetHelpContext**</span></span>|<span data-ttu-id="390fc-112">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="390fc-112">Not supported.</span></span> <span data-ttu-id="390fc-113">Всегда возвращает значение 0.</span><span class="sxs-lookup"><span data-stu-id="390fc-113">Always returns zero.</span></span>|  
|<span data-ttu-id="390fc-114">**GetHelpFile**</span><span class="sxs-lookup"><span data-stu-id="390fc-114">**GetHelpFile**</span></span>|<span data-ttu-id="390fc-115">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="390fc-115">Not supported.</span></span> <span data-ttu-id="390fc-116">Всегда возвращает значение NULL.</span><span class="sxs-lookup"><span data-stu-id="390fc-116">Always returns NULL.</span></span>|  
|<span data-ttu-id="390fc-117">**GetSource**</span><span class="sxs-lookup"><span data-stu-id="390fc-117">**GetSource**</span></span>|<span data-ttu-id="390fc-118">Строка «Собственный клиент Microsoft SQL Server».</span><span class="sxs-lookup"><span data-stu-id="390fc-118">String "Microsoft SQL Server Native Client".</span></span>|  
  
 <span data-ttu-id="390fc-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента поддерживает функции-члены **IErrorRecords** , доступные для потребителей, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="390fc-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports consumer-available **IErrorRecords** member functions as follows.</span></span>  
  
|<span data-ttu-id="390fc-120">Функция-член</span><span class="sxs-lookup"><span data-stu-id="390fc-120">Member function</span></span>|<span data-ttu-id="390fc-121">Описание</span><span class="sxs-lookup"><span data-stu-id="390fc-121">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="390fc-122">**GetBasicErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="390fc-122">**GetBasicErrorInfo**</span></span>|<span data-ttu-id="390fc-123">Заполняет структуру ERRORINFO основными сведениями об ошибке.</span><span class="sxs-lookup"><span data-stu-id="390fc-123">Fills an ERRORINFO structure with basic information about an error.</span></span> <span data-ttu-id="390fc-124">Структура ERRORINFO содержит элементы, которые идентифицируют возвращаемое значение HRESULT для ошибки, поставщика и интерфейс, к которому относится ошибка.</span><span class="sxs-lookup"><span data-stu-id="390fc-124">An ERRORINFO structure contains members that identify the HRESULT return value for the error, and the provider and interface to which the error applies.</span></span>|  
|<span data-ttu-id="390fc-125">**GetCustomErrorObject**</span><span class="sxs-lookup"><span data-stu-id="390fc-125">**GetCustomErrorObject**</span></span>|<span data-ttu-id="390fc-126">Возвращает ссылку на интерфейсы **ISQLErrorInfo** и [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="390fc-126">Returns a reference on interfaces **ISQLErrorInfo,** and [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span></span>|  
|<span data-ttu-id="390fc-127">**GetErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="390fc-127">**GetErrorInfo**</span></span>|<span data-ttu-id="390fc-128">Возвращает ссылку на интерфейс **IErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="390fc-128">Returns a reference on an **IErrorInfo** interface.</span></span>|  
|<span data-ttu-id="390fc-129">**GetErrorParameters**</span><span class="sxs-lookup"><span data-stu-id="390fc-129">**GetErrorParameters**</span></span>|<span data-ttu-id="390fc-130">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента не возвращает параметры потребителю через **жетеррорпараметерс**.</span><span class="sxs-lookup"><span data-stu-id="390fc-130">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not return parameters to the consumer through **GetErrorParameters**.</span></span>|  
|<span data-ttu-id="390fc-131">**GetRecordCount**</span><span class="sxs-lookup"><span data-stu-id="390fc-131">**GetRecordCount**</span></span>|<span data-ttu-id="390fc-132">Число доступных записей ошибок.</span><span class="sxs-lookup"><span data-stu-id="390fc-132">Count of error records available.</span></span>|  
  
 <span data-ttu-id="390fc-133">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента поддерживает параметры **ISQLErrorInfo:: GetSQLInfo** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="390fc-133">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **ISQLErrorInfo::GetSQLInfo** parameters as follows.</span></span>  
  
|<span data-ttu-id="390fc-134">Параметр</span><span class="sxs-lookup"><span data-stu-id="390fc-134">Parameter</span></span>|<span data-ttu-id="390fc-135">Описание</span><span class="sxs-lookup"><span data-stu-id="390fc-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="390fc-136">*pbstrSQLState*</span><span class="sxs-lookup"><span data-stu-id="390fc-136">*pbstrSQLState*</span></span>|<span data-ttu-id="390fc-137">Возвращает значение SQLSTATE для ошибки.</span><span class="sxs-lookup"><span data-stu-id="390fc-137">Returns a SQLSTATE value for the error.</span></span> <span data-ttu-id="390fc-138">Значения SQLSTATE определены в стандартах SQL-92, ODBC и ISO SQL, а также спецификациях API-интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="390fc-138">SQLSTATE values are defined in the SQL-92, ODBC and ISO SQL, and API specifications.</span></span> <span data-ttu-id="390fc-139">Ни [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик собственного клиента OLE DB не ОПРЕДЕЛИЛ значения SQLSTATE, специфичные для реализации.</span><span class="sxs-lookup"><span data-stu-id="390fc-139">Neither [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nor the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defined implementation-specific SQLSTATE values.</span></span>|  
|<span data-ttu-id="390fc-140">*plNativeError*</span><span class="sxs-lookup"><span data-stu-id="390fc-140">*plNativeError*</span></span>|<span data-ttu-id="390fc-141">Возвращает номер ошибки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из системной таблицы **master.dbo.sysmessages**, если он доступен.</span><span class="sxs-lookup"><span data-stu-id="390fc-141">Returns the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error number from **master.dbo.sysmessages** when available.</span></span> <span data-ttu-id="390fc-142">Собственные ошибки доступны после успешной попытки инициализации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] источника данных поставщика OLE DB собственного клиента.</span><span class="sxs-lookup"><span data-stu-id="390fc-142">Native errors are available after a successful attempt to initialize a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source.</span></span> <span data-ttu-id="390fc-143">Прежде чем пытаться, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик собственного клиента OLE DB всегда возвращает ноль.</span><span class="sxs-lookup"><span data-stu-id="390fc-143">Prior to the attempt, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider always returns zero.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="390fc-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="390fc-144">See Also</span></span>  
 [<span data-ttu-id="390fc-145">ошибки</span><span class="sxs-lookup"><span data-stu-id="390fc-145">Errors</span></span>](errors.md)  
  
  
