---
title: bcp_sendrow | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_sendrow
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_sendrow function
ms.assetid: ddbdb4bd-ad4e-4bf1-9a75-656aa26ce10a
author: rothja
ms.author: jroth
ms.openlocfilehash: 3d2f55486ba57101ffc7b1903de5d19ac8eaaca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657760"
---
# <a name="bcp_sendrow"></a><span data-ttu-id="2bd48-102">bcp_sendrow</span><span class="sxs-lookup"><span data-stu-id="2bd48-102">bcp_sendrow</span></span>
  <span data-ttu-id="2bd48-103">Отправляет строку данных из переменных программы в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bd48-103">Sends a row of data from program variables to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bd48-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2bd48-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_sendrow (  
    HDBC   
hdbc  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="2bd48-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2bd48-105">Arguments</span></span>  
 <span data-ttu-id="2bd48-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="2bd48-106">*hdbc*</span></span>  
 <span data-ttu-id="2bd48-107">Дескриптор соединения ODBC с поддержкой массового копирования.</span><span class="sxs-lookup"><span data-stu-id="2bd48-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="2bd48-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2bd48-108">Returns</span></span>  
 <span data-ttu-id="2bd48-109">SUCCEED или FAIL.</span><span class="sxs-lookup"><span data-stu-id="2bd48-109">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bd48-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="2bd48-110">Remarks</span></span>  
 <span data-ttu-id="2bd48-111">Функция **bcp_sendrow** формирует строку из переменных программы и отправляет ее в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bd48-111">The **bcp_sendrow** function builds a row from program variables and sends it to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2bd48-112">Перед вызовом функции **bcp_sendrow**необходимо вызвать функцию [bcp_bind](bcp-bind.md) , чтобы указать переменные программы, содержащие данные строки.</span><span class="sxs-lookup"><span data-stu-id="2bd48-112">Before calling **bcp_sendrow**, you must make calls to [bcp_bind](bcp-bind.md) to specify the program variables containing row data.</span></span>  
  
 <span data-ttu-id="2bd48-113">Если функция **bcp_bind** вызывается с указанием типа данных большого объема переменной длины, например параметра *eDataType* SQLTEXT и параметра *pData* , отличного от значения NULL, функция **bcp_sendrow** отправляет все данные значения, также как и для любого другого типа данных.</span><span class="sxs-lookup"><span data-stu-id="2bd48-113">If **bcp_bind** is called specifying a long, variable-length data type, for example, an *eDataType* parameter of SQLTEXT and a nonNULL *pData* parameter, **bcp_sendrow** sends the entiredata value, just as it does for any other data type.</span></span> <span data-ttu-id="2bd48-114">Однако, если в функции **bcp_bind** параметр *pData* имеет значение NULL, функция **bcp_sendrow** возвращает управление приложению сразу после того, как все указанные столбцы с данными отправляются в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bd48-114">If, however, **bcp_bind** has a NULL *pData* parameter, **bcp_sendrow** returns control to the application immediately after all columns with data specified are sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2bd48-115">Затем приложение может повторно вызывать функцию [bcp_moretext](bcp-moretext.md) , чтобы отправлять данные большого объема переменной длины в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]по одному фрагменту данных за раз.</span><span class="sxs-lookup"><span data-stu-id="2bd48-115">The application can then call [bcp_moretext](bcp-moretext.md) repeatedly to send the long, variable-length data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a chunk at a time.</span></span> <span data-ttu-id="2bd48-116">Дополнительные сведения см. в разделе [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="2bd48-116">For more information, see [bcp_moretext](bcp-moretext.md).</span></span>  
  
 <span data-ttu-id="2bd48-117">Если функция **bcp_sendrow** используется для массового копирования строк из переменных программы в таблицы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , строки фиксируются только при вызове пользователем функции [bcp_batch](bcp-batch.md) или [bcp_done](bcp-done.md).</span><span class="sxs-lookup"><span data-stu-id="2bd48-117">When **bcp_sendrow** is used to bulk copy rows from program variables into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables, rows are committed only when the user calls [bcp_batch](bcp-batch.md) or [bcp_done](bcp-done.md).</span></span> <span data-ttu-id="2bd48-118">Пользователь может вызывать функцию **bcp_batch** один раз для каждой из *n* строк или во время перерыва между периодами поступления данных.</span><span class="sxs-lookup"><span data-stu-id="2bd48-118">The user can choose to call **bcp_batch** once every *n* rows or when there is a lull between periods of incoming data.</span></span> <span data-ttu-id="2bd48-119">Если функция **bcp_batch** никогда не вызывается, то строки фиксируются при вызове функции **bcp_done** .</span><span class="sxs-lookup"><span data-stu-id="2bd48-119">If **bcp_batch** is never called, the rows are committed when **bcp_done** is called.</span></span>  
  
 <span data-ttu-id="2bd48-120">Дополнительные сведения о критическом изменении в разделе Выполнение операций с массовым копированием, начиная с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , см. в статье [осуществление операции копирования &#40;&#41;ODBC ](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="2bd48-120">For information about a breaking change in bulk-copying beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], see [Performing Bulk Copy Operations &#40;ODBC&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bd48-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="2bd48-121">See Also</span></span>  
 [<span data-ttu-id="2bd48-122">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="2bd48-122">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
