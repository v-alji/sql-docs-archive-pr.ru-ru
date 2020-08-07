---
title: SQLEndTran | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLEndTran function
ms.assetid: 95cff841-c2d5-4e1e-a18d-f3d4696a5b85
author: rothja
ms.author: jroth
ms.openlocfilehash: e5d44756131b6133baec69e34da11055a965e2da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730662"
---
# <a name="sqlendtran"></a><span data-ttu-id="32222-102">SQLEndTran</span><span class="sxs-lookup"><span data-stu-id="32222-102">SQLEndTran</span></span>
  <span data-ttu-id="32222-103">По умолчанию драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] закрывает связанный с инструкцией курсор в момент фиксации или отката транзакции функцией **SQLEndTran** .</span><span class="sxs-lookup"><span data-stu-id="32222-103">By default, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver closes a statement's associated cursor when **SQLEndTran** commits or rolls back an operation.</span></span> <span data-ttu-id="32222-104">Серверные курсоры закрываются, если они не являются статическими.</span><span class="sxs-lookup"><span data-stu-id="32222-104">Server cursors are closed unless they are static.</span></span> <span data-ttu-id="32222-105">Когда **SQLEndTran** производит фиксацию или откат операции, поведение курсора, связанного с инструкцией, определяется значением определяемого драйвером соединения ODBC атрибута SQL_COPT_SS_PRESERVE_CURSORS, установленного при помощи функции [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="32222-105">When **SQLEndTran** commits or rolls back an operation, the behavior of the statement's associated cursor is determined by the value of the driver-specific ODBC connection attribute SQL_COPT_SS_PRESERVE_CURSORS, set by [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32222-106">См. также:</span><span class="sxs-lookup"><span data-stu-id="32222-106">See Also</span></span>  
 <span data-ttu-id="32222-107">[Сведения о реализации API ODBC](odbc-api-implementation-details.md) </span><span class="sxs-lookup"><span data-stu-id="32222-107">[ODBC API Implementation Details](odbc-api-implementation-details.md) </span></span>  
 [<span data-ttu-id="32222-108">Функция SQLEndTran</span><span class="sxs-lookup"><span data-stu-id="32222-108">SQLEndTran Function</span></span>](https://go.microsoft.com/fwlink/?LinkId=59342)  
  
  
