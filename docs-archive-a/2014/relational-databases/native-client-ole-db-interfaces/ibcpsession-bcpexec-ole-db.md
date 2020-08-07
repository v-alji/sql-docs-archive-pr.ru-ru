---
title: IBCPSession::BCPExec (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPExec (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPExec method
ms.assetid: 0f4ebb63-cf03-4e53-846e-6c3021cde007
author: rothja
ms.author: jroth
ms.openlocfilehash: 1452888e046b6223c64a6cdf6fe09b074b815702
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729441"
---
# <a name="ibcpsessionbcpexec-ole-db"></a><span data-ttu-id="729f4-102">IBCPSession::BCPExec (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="729f4-102">IBCPSession::BCPExec (OLE DB)</span></span>
  <span data-ttu-id="729f4-103">Выполняет операцию массового копирования.</span><span class="sxs-lookup"><span data-stu-id="729f4-103">Performs the bulk copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="729f4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="729f4-104">Syntax</span></span>  
  
```  
  
HRESULT BCPExec(   
DBROWCOUNT *pRowsCopied);  
```  
  
## <a name="remarks"></a><span data-ttu-id="729f4-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="729f4-105">Remarks</span></span>  
 <span data-ttu-id="729f4-106">Метод **BCPExec** копирует данные из пользовательского файла в таблицу базы данных или наоборот, в зависимости от значения параметра *eDirection*, используемого в методе [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="729f4-106">The **BCPExec** method copies data from a user file to a database table or vice versa, depending on the value of the *eDirection* parameter used with the [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) method.</span></span>  
  
 <span data-ttu-id="729f4-107">Перед вызовом **BCPExec**вызовите метод **BCPInit** , передав ему допустимое имя файла пользователя.</span><span class="sxs-lookup"><span data-stu-id="729f4-107">Before calling **BCPExec**, call the **BCPInit** method with a valid user file name.</span></span> <span data-ttu-id="729f4-108">Несоблюдение этого правила приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="729f4-108">Failure to do so results in an error.</span></span> <span data-ttu-id="729f4-109">Единственное исключение — использование запроса для операции массового копирования из базы данных.</span><span class="sxs-lookup"><span data-stu-id="729f4-109">The only exception is if a query is to be used for a bulk copy out operation.</span></span> <span data-ttu-id="729f4-110">В этом случае указывается имя таблицы NULL в методе **BCPInit** , а затем задается запрос, использующий параметр BCP_OPTION_HINTS.</span><span class="sxs-lookup"><span data-stu-id="729f4-110">In that case specify NULL for the table name in the **BCPInit** method and then specify the query using the BCP_OPTION_HINTS option.</span></span>  
  
 <span data-ttu-id="729f4-111">Метод **BCPExec** — единственный метод массового копирования, который с большой вероятностью может ожидать выполнения в течение любого периода времени.</span><span class="sxs-lookup"><span data-stu-id="729f4-111">The **BCPExec** method is the only bulk copy method that is likely to be outstanding for any length of time.</span></span> <span data-ttu-id="729f4-112">Таким образом, это единственный метод массового копирования, который поддерживает асинхронный режим.</span><span class="sxs-lookup"><span data-stu-id="729f4-112">It is therefore the only bulk copy method that supports asynchronous mode.</span></span> <span data-ttu-id="729f4-113">Чтобы использовать асинхронный режим, задайте для свойства сеанса конкретного поставщика SSPROP_ASYNCH_BULKCOPY значение VARIANT_TRUE перед вызовом метода **BCPExec** .</span><span class="sxs-lookup"><span data-stu-id="729f4-113">To use asynchronous mode, set the provider specific session property SSPROP_ASYNCH_BULKCOPY to VARIANT_TRUE before calling the **BCPExec** method.</span></span> <span data-ttu-id="729f4-114">Это свойство доступно в наборе свойств DBPROPSET_SQLSERVERSESSION.</span><span class="sxs-lookup"><span data-stu-id="729f4-114">This property is available in the DBPROPSET_SQLSERVERSESSION property set.</span></span> <span data-ttu-id="729f4-115">Чтобы проверить завершение операции, вызовите метод **BCPExec** с теми же параметрами.</span><span class="sxs-lookup"><span data-stu-id="729f4-115">To test for completion, call the **BCPExec** method with the same parameters.</span></span> <span data-ttu-id="729f4-116">Если массовое копирование еще не завершено, метод **BCPExec** возвращает DB_S_ASYNCHRONOUS.</span><span class="sxs-lookup"><span data-stu-id="729f4-116">If the bulk copy has not yet completed, the **BCPExec** method returns DB_S_ASYNCHRONOUS.</span></span> <span data-ttu-id="729f4-117">Он также возвращает в аргументе *pRowsCopied* состояние счетчика строк, переданных на сервер или полученных от него.</span><span class="sxs-lookup"><span data-stu-id="729f4-117">It also returns in the *pRowsCopied* argument a status count of the number of rows that have been sent to or received from the server.</span></span> <span data-ttu-id="729f4-118">Строки, отправленные на сервер, не фиксируются до тех пор, пока не будет достигнут конец пакета.</span><span class="sxs-lookup"><span data-stu-id="729f4-118">Rows sent to the server are not committed until the end of a batch has been reached.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="729f4-119">Аргументы</span><span class="sxs-lookup"><span data-stu-id="729f4-119">Arguments</span></span>  
 <span data-ttu-id="729f4-120">*pRowsCopied*[out]</span><span class="sxs-lookup"><span data-stu-id="729f4-120">*pRowsCopied*[out]</span></span>  
 <span data-ttu-id="729f4-121">Указатель на значение типа DWORD.</span><span class="sxs-lookup"><span data-stu-id="729f4-121">A pointer to a DWORD.</span></span> <span data-ttu-id="729f4-122">Метод **BCPExec** записывает в значение DWORD количество успешно скопированных строк.</span><span class="sxs-lookup"><span data-stu-id="729f4-122">The **BCPExec** method fills the DWORD with the number of rows successfully copied.</span></span> <span data-ttu-id="729f4-123">Если для аргумента *pRowsCopied* задано значение NULL, то он пропускается методом **BCPExec** .</span><span class="sxs-lookup"><span data-stu-id="729f4-123">If the *pRowsCopied* argument is set to NULL, it is ignored by the **BCPExec** method.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="729f4-124">Значения кода возврата</span><span class="sxs-lookup"><span data-stu-id="729f4-124">Return Code Values</span></span>  
 <span data-ttu-id="729f4-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="729f4-125">S_OK</span></span>  
 <span data-ttu-id="729f4-126">Метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="729f4-126">The method succeeded.</span></span>  
  
 <span data-ttu-id="729f4-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="729f4-127">E_FAIL</span></span>  
 <span data-ttu-id="729f4-128">Произошла ошибка конкретного поставщика; для получения дополнительных сведений используйте интерфейс [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="729f4-128">A provider-specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="729f4-129">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="729f4-129">E_UNEXPECTED</span></span>  
 <span data-ttu-id="729f4-130">Непредвиденный вызов метода.</span><span class="sxs-lookup"><span data-stu-id="729f4-130">The call to the method was unexpected.</span></span> <span data-ttu-id="729f4-131">Например, перед вызовом этого метода не был вызван метод **BCPInit** .</span><span class="sxs-lookup"><span data-stu-id="729f4-131">For example, the **BCPInit** method was not called before calling this method.</span></span> <span data-ttu-id="729f4-132">Также возникает, если операция была прервана с использованием параметра BCP_OPTION_ABORT, а затем был вызван метод **BCPExec** .</span><span class="sxs-lookup"><span data-stu-id="729f4-132">Also occurs if the operation has been aborted through using the BCP_OPTION_ABORT option, and the **BCPExec** method was called afterwards.</span></span>  
  
 <span data-ttu-id="729f4-133">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="729f4-133">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="729f4-134">Недостаточно памяти.</span><span class="sxs-lookup"><span data-stu-id="729f4-134">Out-of-memory error.</span></span>  
  
 <span data-ttu-id="729f4-135">DB_S_ENDOFROWSET</span><span class="sxs-lookup"><span data-stu-id="729f4-135">DB_S_ENDOFROWSET</span></span>  
 <span data-ttu-id="729f4-136">Операция массового копирования завершена, и вся передача всех данных выполнена.</span><span class="sxs-lookup"><span data-stu-id="729f4-136">The bulk copy operation finished, and all the data transfer was completed.</span></span>  
  
 <span data-ttu-id="729f4-137">DB_S_ASYNCHRONOUS</span><span class="sxs-lookup"><span data-stu-id="729f4-137">DB_S_ASYNCHRONOUS</span></span>  
 <span data-ttu-id="729f4-138">Текущий пакет строк скопирован.</span><span class="sxs-lookup"><span data-stu-id="729f4-138">The current batch of rows has been copied.</span></span> <span data-ttu-id="729f4-139">Вновь вызовите метод **BCPExec** , чтобы передать следующий пакет.</span><span class="sxs-lookup"><span data-stu-id="729f4-139">Call the **BCPExec** method again to transfer the next batch.</span></span>  
  
 <span data-ttu-id="729f4-140">DB_S_ERRORSOCCURRED</span><span class="sxs-lookup"><span data-stu-id="729f4-140">DB_S_ERRORSOCCURRED</span></span>  
 <span data-ttu-id="729f4-141">Во время операции массового копирования произошли ошибки, и некоторые строки могли быть не скопированы.</span><span class="sxs-lookup"><span data-stu-id="729f4-141">Errors occurred during the bulk copy operation, and some rows might not have been copied.</span></span> <span data-ttu-id="729f4-142">Количество ошибок все еще меньше минимально допустимого числа ошибок.</span><span class="sxs-lookup"><span data-stu-id="729f4-142">The number of errors is still less than the maximum errors allowed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="729f4-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="729f4-143">See Also</span></span>  
 <span data-ttu-id="729f4-144">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="729f4-144">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="729f4-145">Выполнение операций массового копирования</span><span class="sxs-lookup"><span data-stu-id="729f4-145">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
