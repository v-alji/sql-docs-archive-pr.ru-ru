---
title: bcp_done | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_done
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_done function
ms.assetid: e59b3f16-5b59-40da-880f-f3edf657d1ee
author: rothja
ms.author: jroth
ms.openlocfilehash: cb9b0cbcc927fcd10c2d81b3c5c3d39bb80a8e9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654246"
---
# <a name="bcp_done"></a><span data-ttu-id="3b138-102">bcp_done</span><span class="sxs-lookup"><span data-stu-id="3b138-102">bcp_done</span></span>
  <span data-ttu-id="3b138-103">Завершает массовое копирование переменных программы в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , выполненное с помощью функции [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="3b138-103">Ends a bulk copy from program variables to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performed with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b138-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b138-104">Syntax</span></span>  
  
```  
  
DBINT bcp_done (  
    HDBC   
hdbc  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="3b138-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3b138-105">Arguments</span></span>  
 <span data-ttu-id="3b138-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="3b138-106">*hdbc*</span></span>  
 <span data-ttu-id="3b138-107">Дескриптор соединения ODBC с поддержкой массового копирования.</span><span class="sxs-lookup"><span data-stu-id="3b138-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="3b138-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3b138-108">Returns</span></span>  
 <span data-ttu-id="3b138-109">Число строк окончательно сохраняется после последнего вызова функции [bcp_batch](bcp-batch.md) или -1 в случае ошибки.</span><span class="sxs-lookup"><span data-stu-id="3b138-109">The number of rows permanently saved after the last call to [bcp_batch](bcp-batch.md) or -1 in case of error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b138-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="3b138-110">Remarks</span></span>  
 <span data-ttu-id="3b138-111">Вызов функции **bcp_done** после последнего вызова [bcp_sendrow](bcp-sendrow.md) или [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="3b138-111">Call **bcp_done** after the last call to [bcp_sendrow](bcp-sendrow.md) or [bcp_moretext](bcp-moretext.md).</span></span> <span data-ttu-id="3b138-112">Сбой вызова функции **bcp_done** после копирования всех результатов данных в ошибки.</span><span class="sxs-lookup"><span data-stu-id="3b138-112">Failure to call **bcp_done** after copying all data results in errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b138-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="3b138-113">See Also</span></span>  
 [<span data-ttu-id="3b138-114">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="3b138-114">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
