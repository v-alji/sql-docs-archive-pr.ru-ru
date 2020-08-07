---
title: Собственные номера ошибок | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC error handling, native error numbers
- SQL Server Native Client ODBC driver, errors
- native error numbers [SQL Server Native Client]
- messages [ODBC], native error numbers
- errors [ODBC], native error numbers
ms.assetid: 77cbc826-f47f-4803-8e7a-223d6df069b1
author: rothja
ms.author: jroth
ms.openlocfilehash: 7232a921027246c3ceb7d0ae1ffd5efbd3672895
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730661"
---
# <a name="native-error-numbers"></a><span data-ttu-id="a6270-102">Собственные коды ошибок</span><span class="sxs-lookup"><span data-stu-id="a6270-102">Native Error Numbers</span></span>
  <span data-ttu-id="a6270-103">Для ошибок, возникающих в источнике данных (возвращенном [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента возвращает номер собственной ошибки, возвращенный ей [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6270-103">For errors that occur in the data source (returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns the native error number returned to it by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a6270-104">Для ошибок, обнаруженных драйвером, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента возвращает номер собственной ошибки, равный 0.</span><span class="sxs-lookup"><span data-stu-id="a6270-104">For errors detected by the driver, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns a native error number of 0.</span></span> <span data-ttu-id="a6270-105">Дополнительные сведения о списке машинных номеров ошибок см. в столбце "ошибка" системной таблицы **sysmessages** в базе данных **master** в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6270-105">For more information about a list of native error numbers, see the error column of the **sysmessages** system table in the **master** database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a6270-106">Сведения о кодах ошибок состояния см. в разделе [SQLSTATE &#40;коды ошибок ODBC&#41;](sqlstate-odbc-error-codes.md).</span><span class="sxs-lookup"><span data-stu-id="a6270-106">For information about the state error codes, see [SQLSTATE &#40;ODBC Error Codes&#41;](sqlstate-odbc-error-codes.md).</span></span> <span data-ttu-id="a6270-107">В случае ошибок, возвращаемых библиотекой Net-Library, собственный код ошибки можно получить из базового сетевого программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="a6270-107">For errors returned by the Net-Library, the native error number is from the underlying network software.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6270-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="a6270-108">See Also</span></span>  
 [<span data-ttu-id="a6270-109">Обработка ошибок и сообщений</span><span class="sxs-lookup"><span data-stu-id="a6270-109">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
