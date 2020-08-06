---
title: Подробные сведения об ошибках SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- errors [OLE DB], error details
- IErrorRecords interface
- IErrorInfo interface
- OLE DB error handling, error details
- ISQLServerErrorInfo interface
ms.assetid: 51500ee3-3d78-47ec-b90f-ebfc55642e06
author: rothja
ms.author: jroth
ms.openlocfilehash: 4c03cf62dd274f9bcca213d33fb8969b26c9d980
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667057"
---
# <a name="sql-server-error-detail"></a><span data-ttu-id="c306f-102">Подробные сведения об ошибках SQL Server</span><span class="sxs-lookup"><span data-stu-id="c306f-102">SQL Server Error Detail</span></span>
  <span data-ttu-id="c306f-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента определяет определяемый поставщиком интерфейс ошибок [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="c306f-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the provider-specific error interface [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span></span> <span data-ttu-id="c306f-104">Интерфейс возвращает более подробные сведения об ошибке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и полезен, если выполнение команды или операции работы с наборами строк завершились с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c306f-104">The interface returns more detail about a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error and is valuable when command execution or rowset operations fail.</span></span>  
  
 <span data-ttu-id="c306f-105">Существует два способа получения доступа к интерфейсу **ISQLServerErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="c306f-105">There are two ways to obtain access to **ISQLServerErrorInfo** interface.</span></span>  
  
 <span data-ttu-id="c306f-106">Как показано в приведенном ниже образце кода, потребитель может вызвать метод **IErrorRecords::GetCustomerErrorObject**, чтобы получить указатель на интерфейс **ISQLServerErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="c306f-106">The consumer may call **IErrorRecords::GetCustomerErrorObject** to obtain an **ISQLServerErrorInfo** pointer, as shown in the following code sample.</span></span> <span data-ttu-id="c306f-107">(Нет необходимости получать интерфейс **ISQLErrorInfo**.) Интерфейсы **ISQLErrorInfo** и **ISQLServerErrorInfo** представляют собой пользовательские объекты ошибок OLE DB. При этом объект **ISQLServerErrorInfo** является интерфейсом для получения информации об ошибках на сервере, включая такие данные, как имя процедуры и номера строк.</span><span class="sxs-lookup"><span data-stu-id="c306f-107">(There is no need to obtain **ISQLErrorInfo.**) Both **ISQLErrorInfo** and **ISQLServerErrorInfo** are custom OLE DB error objects, with **ISQLServerErrorInfo** being the interface to use to obtain information of server errors, including such details as procedure name and line numbers.</span></span>  
  
```  
// Get the SQL Server custom error object.  
if(FAILED(hr=pIErrorRecords->GetCustomErrorObject(  
   nRec, IID_ISQLServerErrorInfo,  
   (IUnknown**)&pISQLServerErrorErrorInfo)))  
```  
  
 <span data-ttu-id="c306f-108">Другой способ получить указатель на интерфейс **ISQLServerErrorInfo** состоит в вызове метода **QueryInterface** для уже полученного указателя на интерфейс **ISQLErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="c306f-108">Another way to get an **ISQLServerErrorInfo** pointer is to call the **QueryInterface** method on an already-obtained **ISQLErrorInfo** pointer.</span></span> <span data-ttu-id="c306f-109">Обратите внимание на то, что так как интерфейс **ISQLServerErrorInfo** содержит надмножество информации, доступной из интерфейса **ISQLErrorInfo**, имеет смысл получить непосредственно интерфейс **ISQLServerErrorInfo** с помощью метода **GetCustomerErrorObject**.</span><span class="sxs-lookup"><span data-stu-id="c306f-109">Note that because **ISQLServerErrorInfo** contains a superset of the information available from **ISQLErrorInfo**, it makes sense to go directly to **ISQLServerErrorInfo** through **GetCustomerErrorObject**.</span></span>  
  
 <span data-ttu-id="c306f-110">Интерфейс **ISQLServerErrorInfo** предоставляет одну функцию-член [ISQLServerErrorInfo::GetErrorInfo](../native-client-ole-db-interfaces/isqlservererrorinfo-geterrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="c306f-110">The **ISQLServerErrorInfo** interface exposes one member function, [ISQLServerErrorInfo::GetErrorInfo](../native-client-ole-db-interfaces/isqlservererrorinfo-geterrorinfo-ole-db.md).</span></span> <span data-ttu-id="c306f-111">Функция возвращает указатель на структуру SSERRORINFO и указатель на буфер строк.</span><span class="sxs-lookup"><span data-stu-id="c306f-111">The function returns a pointer to an SSERRORINFO structure and a pointer to a string buffer.</span></span> <span data-ttu-id="c306f-112">Оба указателя ссылаются на память, которую потребитель должен освободить с помощью метода **IMalloc::Free**.</span><span class="sxs-lookup"><span data-stu-id="c306f-112">Both pointers reference memory the consumer must deallocate by using the **IMalloc::Free** method.</span></span>  
  
 <span data-ttu-id="c306f-113">Элементы структуры SSERRORINFO обрабатываются потребителем следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c306f-113">SSERRORINFO structure members are interpreted by the consumer as follows.</span></span>  
  
|<span data-ttu-id="c306f-114">Член</span><span class="sxs-lookup"><span data-stu-id="c306f-114">Member</span></span>|<span data-ttu-id="c306f-115">Описание</span><span class="sxs-lookup"><span data-stu-id="c306f-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c306f-116">*pwszMessage*</span><span class="sxs-lookup"><span data-stu-id="c306f-116">*pwszMessage*</span></span>|<span data-ttu-id="c306f-117">Сообщение об ошибке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c306f-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message.</span></span> <span data-ttu-id="c306f-118">Идентично строке, возвращаемой методом **IErrorInfo::GetDescription**.</span><span class="sxs-lookup"><span data-stu-id="c306f-118">Identical to the string returned in **IErrorInfo::GetDescription**.</span></span>|  
|<span data-ttu-id="c306f-119">*pwszServer*</span><span class="sxs-lookup"><span data-stu-id="c306f-119">*pwszServer*</span></span>|<span data-ttu-id="c306f-120">Имя экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для сеанса.</span><span class="sxs-lookup"><span data-stu-id="c306f-120">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the session.</span></span>|  
|<span data-ttu-id="c306f-121">*pwszProcedure*</span><span class="sxs-lookup"><span data-stu-id="c306f-121">*pwszProcedure*</span></span>|<span data-ttu-id="c306f-122">При необходимости, имя процедуры, в которой произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="c306f-122">If appropriate, the name of the procedure in which the error originated.</span></span> <span data-ttu-id="c306f-123">Пустая строка в противном случае.</span><span class="sxs-lookup"><span data-stu-id="c306f-123">An empty string otherwise.</span></span>|  
|<span data-ttu-id="c306f-124">*lNative*</span><span class="sxs-lookup"><span data-stu-id="c306f-124">*lNative*</span></span>|<span data-ttu-id="c306f-125">Номер собственной ошибки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c306f-125">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native error number.</span></span> <span data-ttu-id="c306f-126">Идентичен значению, возвращаемому в параметре *plNativeError* метода **ISQLErrorInfo::GetSQLInfo**.</span><span class="sxs-lookup"><span data-stu-id="c306f-126">Identical to the value returned in the *plNativeError* parameter of **ISQLErrorInfo::GetSQLInfo**.</span></span>|  
|<span data-ttu-id="c306f-127">*bState*</span><span class="sxs-lookup"><span data-stu-id="c306f-127">*bState*</span></span>|<span data-ttu-id="c306f-128">Состояние сообщения об ошибке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c306f-128">State of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message.</span></span>|  
|<span data-ttu-id="c306f-129">*bClass*</span><span class="sxs-lookup"><span data-stu-id="c306f-129">*bClass*</span></span>|<span data-ttu-id="c306f-130">Серьезность сообщения об ошибке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c306f-130">Severity of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message.</span></span>|  
|<span data-ttu-id="c306f-131">*wLineNumber*</span><span class="sxs-lookup"><span data-stu-id="c306f-131">*wLineNumber*</span></span>|<span data-ttu-id="c306f-132">Если применимо, номер строки хранимой процедуры, в которой возникла ошибка.</span><span class="sxs-lookup"><span data-stu-id="c306f-132">When applicable, the line number of a stored procedure on which the error occurred.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c306f-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="c306f-133">See Also</span></span>  
 <span data-ttu-id="c306f-134">[Наличии](errors.md) </span><span class="sxs-lookup"><span data-stu-id="c306f-134">[Errors](errors.md) </span></span>  
 [<span data-ttu-id="c306f-135">RAISERROR (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c306f-135">RAISERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/raiserror-transact-sql)  
  
  
