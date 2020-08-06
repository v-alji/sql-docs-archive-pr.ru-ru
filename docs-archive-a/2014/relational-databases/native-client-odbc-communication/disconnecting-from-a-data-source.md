---
title: Отключение от источника данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC data sources, connections
- data sources [SQL Server Native Client]
- disconnecting [ODBC]
- ODBC applications, disconnecting
- SQLDisconnect function
- ODBC applications, data sources
- connections [SQL Server Native Client]
- SQLFreeHandle function
- ODBC data sources, disconnecting
- SQL Server Native Client ODBC driver, data sources
- ODBC functions
- SQL Server Native Client ODBC driver, connections
ms.assetid: 65b0267d-b2ab-4a59-83f2-436d90cfbf79
author: rothja
ms.author: jroth
ms.openlocfilehash: 5db3b83ab65d854f3a4d2182d9a4a1314e097681
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664164"
---
# <a name="disconnecting-from-a-data-source"></a><span data-ttu-id="c11e0-102">Отсоединение от источника данных</span><span class="sxs-lookup"><span data-stu-id="c11e0-102">Disconnecting from a Data Source</span></span>
  <span data-ttu-id="c11e0-103">Когда приложение завершило работу с источником данных, оно вызывает **SQLDisconnect**.</span><span class="sxs-lookup"><span data-stu-id="c11e0-103">When an application has finished using a data source, it calls **SQLDisconnect**.</span></span> <span data-ttu-id="c11e0-104">**SQLDisconnect** освобождает все инструкции, выделенные для соединения, и отключает драйвер от источника данных.</span><span class="sxs-lookup"><span data-stu-id="c11e0-104">**SQLDisconnect** frees any statements that are allocated on the connection and disconnects the driver from the data source.</span></span> <span data-ttu-id="c11e0-105">После отключения приложение может вызвать [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) , чтобы освободить маркер подключения.</span><span class="sxs-lookup"><span data-stu-id="c11e0-105">After disconnecting, the application can call [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) to free the connection handle.</span></span> <span data-ttu-id="c11e0-106">Перед выходом приложение также вызывает **SQLFreeHandle** , чтобы освободить обработчик среды.</span><span class="sxs-lookup"><span data-stu-id="c11e0-106">Before exiting, an application also calls **SQLFreeHandle** to free the environment handle.</span></span>  
  
 <span data-ttu-id="c11e0-107">После отсоединения приложение может повторно использовать выделенный дескриптор соединения, либо для соединения с другим источником данных, либо для повторного соединения с тем же.</span><span class="sxs-lookup"><span data-stu-id="c11e0-107">After disconnecting, an application can reuse the allocated connection handle, either to connect to a different data source or reconnect to the same data source.</span></span> <span data-ttu-id="c11e0-108">Для принятия решения о сохранении соединения или отсоединении и повторном соединении, разработчик приложения должен рассмотреть сравнительную стоимость каждого варианта.</span><span class="sxs-lookup"><span data-stu-id="c11e0-108">The decision to remain connected instead of disconnecting and reconnecting later requires that the application writer consider the relative costs of each option.</span></span> <span data-ttu-id="c11e0-109">Соединение с источником данных и сохранение соединения в различных окружениях могут оказаться в разной степени затратными.</span><span class="sxs-lookup"><span data-stu-id="c11e0-109">Connecting to a data source and remaining connected can be relatively costly, depending on the connection medium.</span></span> <span data-ttu-id="c11e0-110">Чтобы сделать выбор, следует также проанализировать вероятность и временные затраты других операций в том же источнике данных.</span><span class="sxs-lookup"><span data-stu-id="c11e0-110">In making a trade-off, the application must also make assumptions about the probability and timing of additional operations on the same data source.</span></span> <span data-ttu-id="c11e0-111">Также приложению может потребоваться более одного соединения.</span><span class="sxs-lookup"><span data-stu-id="c11e0-111">An application may also have to use more than one connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c11e0-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="c11e0-112">See Also</span></span>  
 [<span data-ttu-id="c11e0-113">Взаимодействие с SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c11e0-113">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
