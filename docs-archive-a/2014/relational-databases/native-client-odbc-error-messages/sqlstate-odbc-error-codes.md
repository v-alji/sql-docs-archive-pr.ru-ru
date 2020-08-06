---
title: SQLSTATE (коды ошибок ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, errors
- ODBC error handling, cause information
- messages [ODBC], cause information
- SQLSTATEs
- errors [ODBC], cause information
ms.assetid: 84cce528-edb0-473f-a85f-3eb87fbe2cf3
author: rothja
ms.author: jroth
ms.openlocfilehash: ff3ec0a5cdc8f24f34e42849f7c8f6d1d9d41478
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654254"
---
# <a name="sqlstate-odbc-error-codes"></a><span data-ttu-id="1274f-102">SQLSTATE (коды ошибок ODBC)</span><span class="sxs-lookup"><span data-stu-id="1274f-102">SQLSTATE (ODBC Error Codes)</span></span>
  <span data-ttu-id="1274f-103">Код SQLSTATE предоставляет подробные сведения о причине предупреждения или ошибки.</span><span class="sxs-lookup"><span data-stu-id="1274f-103">SQLSTATE provides detailed information about the cause of a warning or error.</span></span> <span data-ttu-id="1274f-104">Для ошибок, возникающих в источнике данных, обнаруженном и возвращенном [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента сопоставляет возвращенный номер собственной ошибки с соответствующим SQLSTATE.</span><span class="sxs-lookup"><span data-stu-id="1274f-104">For errors that occur in the data source detected and returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver maps the returned native error number to the appropriate SQLSTATE.</span></span> <span data-ttu-id="1274f-105">Если машинный номер ошибки не имеет кода ошибки ODBC для сопоставлений, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента возвращает значение SQLSTATE 42000 ("Синтаксическая ошибка или нарушение прав доступа").</span><span class="sxs-lookup"><span data-stu-id="1274f-105">If a native error number does not have an ODBC error code to map to, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns SQLSTATE 42000 ("syntax error or access violation").</span></span> <span data-ttu-id="1274f-106">Для ошибок, обнаруженных драйвером, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента создает соответствующее значение SQLSTATE.</span><span class="sxs-lookup"><span data-stu-id="1274f-106">For errors that are detected by the driver, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver generates the appropriate SQLSTATE.</span></span>  
  
 <span data-ttu-id="1274f-107">Дополнительные сведения о кодах ошибок состояния см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="1274f-107">For more information about the state error codes, see the following topics:</span></span>  
  
-   [<span data-ttu-id="1274f-108">Приложение А. Коды ошибок ODBC</span><span class="sxs-lookup"><span data-stu-id="1274f-108">Appendix A: ODBC Error Codes</span></span>](https://go.microsoft.com/fwlink/?LinkId=89356)  
  
-   [<span data-ttu-id="1274f-109">Сопоставления SQLSTATE</span><span class="sxs-lookup"><span data-stu-id="1274f-109">SQLSTATE Mappings</span></span>](https://go.microsoft.com/fwlink/?LinkId=89355)  
  
## <a name="see-also"></a><span data-ttu-id="1274f-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="1274f-110">See Also</span></span>  
 [<span data-ttu-id="1274f-111">Обработка ошибок и сообщений</span><span class="sxs-lookup"><span data-stu-id="1274f-111">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
