---
title: bcp_batch | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_batch
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_batch function
ms.assetid: 0bda489e-86bc-4a7e-80f6-96047e03f281
author: rothja
ms.author: jroth
ms.openlocfilehash: 24cdf6e2934c2b80a55d8fa1fcc572a976b636ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664156"
---
# <a name="bcp_batch"></a><span data-ttu-id="ba7f4-102">bcp_batch</span><span class="sxs-lookup"><span data-stu-id="ba7f4-102">bcp_batch</span></span>
  <span data-ttu-id="ba7f4-103">Фиксирует все строки, которые ранее были скопированы из переменных программы с использованием массовой операции и переданы в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью функции [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="ba7f4-103">Commits all rows previously bulk copied from program variables and sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba7f4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba7f4-104">Syntax</span></span>  
  
```  
  
DBINT bcp_batch (HDBC  
hdbc  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="ba7f4-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ba7f4-105">Arguments</span></span>  
 <span data-ttu-id="ba7f4-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="ba7f4-106">*hdbc*</span></span>  
 <span data-ttu-id="ba7f4-107">Дескриптор соединения ODBC с поддержкой массового копирования.</span><span class="sxs-lookup"><span data-stu-id="ba7f4-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="ba7f4-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ba7f4-108">Returns</span></span>  
 <span data-ttu-id="ba7f4-109">Количество строк, сохраненных после последнего вызова **bcp_batch**, или -1 в случае ошибки.</span><span class="sxs-lookup"><span data-stu-id="ba7f4-109">The number of rows saved after the last call to **bcp_batch**, or -1 in case of error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba7f4-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="ba7f4-110">Remarks</span></span>  
 <span data-ttu-id="ba7f4-111">Пакеты массового копирования определяют транзакции.</span><span class="sxs-lookup"><span data-stu-id="ba7f4-111">Bulk copy batches define transactions.</span></span> <span data-ttu-id="ba7f4-112">Если приложение использует функции [bcp_bind](bcp-bind.md) и **bcp_sendrow** для массового копирования строк из переменных программы в таблицы SQL Server, то строки фиксируются только при вызове программой функций **bcp_batch** или [bcp_done](bcp-done.md).</span><span class="sxs-lookup"><span data-stu-id="ba7f4-112">When an application uses [bcp_bind](bcp-bind.md) and **bcp_sendrow** to bulk copy rows from program variables to SQL Server tables, the rows are committed only when the program calls **bcp_batch** or [bcp_done](bcp-done.md).</span></span>  
  
 <span data-ttu-id="ba7f4-113">Функцию **bcp_batch** можно вызывать один раз для каждых *n* строк или при приостановке поступления данных (например, в телеметрических приложениях).</span><span class="sxs-lookup"><span data-stu-id="ba7f4-113">You can call **bcp_batch** once every *n* rows or when there is a lull in incoming data (as in a telemetry application).</span></span> <span data-ttu-id="ba7f4-114">Если приложение не вызывает функцию **bcp_batch** , то строки, для которых выполнено массовое копирование, фиксируются только при вызове функции **bcp_done** .</span><span class="sxs-lookup"><span data-stu-id="ba7f4-114">If an application does not call **bcp_batch** the bulk copied rows are committed only when **bcp_done** is called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba7f4-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="ba7f4-115">See Also</span></span>  
 [<span data-ttu-id="ba7f4-116">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="ba7f4-116">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
