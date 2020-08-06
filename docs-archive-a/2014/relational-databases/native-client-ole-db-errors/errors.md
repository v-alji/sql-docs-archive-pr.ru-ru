---
title: Ошибки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- OLE/COM errors
- errors [OLE DB]
- OLE DB error handling, about error handling
- OLE DB error handling
ms.assetid: bd0612f4-96ef-4919-b0f9-b5447210fe93
author: rothja
ms.author: jroth
ms.openlocfilehash: 0560a31b60a10e278f621aa53f1c7fa038fe8039
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667066"
---
# <a name="errors"></a><span data-ttu-id="f8dd4-102">ошибки</span><span class="sxs-lookup"><span data-stu-id="f8dd4-102">Errors</span></span>
  <span data-ttu-id="f8dd4-103">Объекты OLE/COM сообщают об ошибках с помощью кодов возврата HRESULT функций-членов объектов.</span><span class="sxs-lookup"><span data-stu-id="f8dd4-103">OLE/COM objects report errors through the HRESULT return code of object member functions.</span></span> <span data-ttu-id="f8dd4-104">Тип HRESULT в OLE/COM представляет собой структуру с битовой упаковкой.</span><span class="sxs-lookup"><span data-stu-id="f8dd4-104">An OLE/COM HRESULT is a bit-packed structure.</span></span> <span data-ttu-id="f8dd4-105">OLE предоставляет макросы для разыменования членов структуры.</span><span class="sxs-lookup"><span data-stu-id="f8dd4-105">OLE provides macros that dereference structure members.</span></span>  
  
 <span data-ttu-id="f8dd4-106">OLE/COM задает интерфейс **IErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="f8dd4-106">OLE/COM specifies the **IErrorInfo** interface.</span></span> <span data-ttu-id="f8dd4-107">Интерфейс предоставляет доступ к методам (например, **GetDescription**).</span><span class="sxs-lookup"><span data-stu-id="f8dd4-107">The interface exposes methods such as **GetDescription**.</span></span> <span data-ttu-id="f8dd4-108">Это позволяет клиентам получать подробную информацию об ошибках у серверов OLE/COM.</span><span class="sxs-lookup"><span data-stu-id="f8dd4-108">This allows clients to extract error details from OLE/COM servers.</span></span> <span data-ttu-id="f8dd4-109">В OLE DB к интерфейсу **IErrorInfo** добавлена поддержка возврата сразу нескольких пакетов информации об ошибках на один вызов метода.</span><span class="sxs-lookup"><span data-stu-id="f8dd4-109">OLE DB extends **IErrorInfo** to support the return of multiple error information packets on a single-member function execution.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f8dd4-110">может возвращать несколько ошибок.</span><span class="sxs-lookup"><span data-stu-id="f8dd4-110">can return multiple errors.</span></span> <span data-ttu-id="f8dd4-111">Приложение может получать ошибки сервера поочередно, вызывая метод [IMultipleResults::GetResult](https://go.microsoft.com/fwlink/?LinkId=129630) в сочетании с ISQLErrorInfo и IErrorRecords.</span><span class="sxs-lookup"><span data-stu-id="f8dd4-111">An application can retrieve server errors one at a time by calling [IMultipleResults::GetResult](https://go.microsoft.com/fwlink/?LinkId=129630) combined with ISQLErrorInfo and IErrorRecords.</span></span>  
  
 <span data-ttu-id="f8dd4-112">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента предоставляет OLE DB расширенный интерфейс **IErrorInfo**, настраиваемый `ISQLErrorInfo` объект и интерфейсы объекта ошибки [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) , относящиеся к поставщику.</span><span class="sxs-lookup"><span data-stu-id="f8dd4-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the OLE DB record-enhanced **IErrorInfo**, the custom `ISQLErrorInfo`, and the provider-specific [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) error object interfaces.</span></span>  
  
 <span data-ttu-id="f8dd4-113">Сведения об ошибках трассировки см. в статье [Отслеживание доступа к данным](https://go.microsoft.com/fwlink/?LinkId=125805).</span><span class="sxs-lookup"><span data-stu-id="f8dd4-113">For information about tracing errors, see [Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805).</span></span> <span data-ttu-id="f8dd4-114">См. сведения об улучшениях трассировки ошибок, добавленных в [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], в руководстве по [получению доступа к диагностическим сведениям в расширенном журнале событий](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span><span class="sxs-lookup"><span data-stu-id="f8dd4-114">For information about enhancements to error tracing added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], see [Accessing Diagnostic Information in the Extended Events Log](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f8dd4-115">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="f8dd4-115">In This Section</span></span>  
  
-   [<span data-ttu-id="f8dd4-116">Коды возврата</span><span class="sxs-lookup"><span data-stu-id="f8dd4-116">Return Codes</span></span>](return-codes.md)  
  
-   [<span data-ttu-id="f8dd4-117">Сведения в интерфейсах ошибок</span><span class="sxs-lookup"><span data-stu-id="f8dd4-117">Information in Error Interfaces</span></span>](information-in-error-interfaces.md)  
  
-   [<span data-ttu-id="f8dd4-118">Подробные сведения об ошибках SQL Server</span><span class="sxs-lookup"><span data-stu-id="f8dd4-118">SQL Server Error Detail</span></span>](sql-server-error-detail.md)  
  
-   [<span data-ttu-id="f8dd4-119">Получение информации об ошибке</span><span class="sxs-lookup"><span data-stu-id="f8dd4-119">Retrieving Error Information</span></span>](retrieving-error-information.md)  
  
-   [<span data-ttu-id="f8dd4-120">Результаты сообщения SQL Server</span><span class="sxs-lookup"><span data-stu-id="f8dd4-120">SQL Server Message Results</span></span>](sql-server-message-results.md)  
  
## <a name="see-also"></a><span data-ttu-id="f8dd4-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="f8dd4-121">See Also</span></span>  
 [<span data-ttu-id="f8dd4-122">SQL Server Native Client (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="f8dd4-122">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
