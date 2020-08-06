---
title: Разделы руководства по ODBC | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 151f2066-1c37-410f-88f4-b27dfca66031
author: rothja
ms.author: jroth
ms.openlocfilehash: cfeb120b9fa1fedb5358b5e12dabed7835f9a6b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738306"
---
# <a name="odbc-how-to-topics"></a><span data-ttu-id="4f5d8-102">ODBC How-to Topics</span><span class="sxs-lookup"><span data-stu-id="4f5d8-102">ODBC How-to Topics</span></span>
  <span data-ttu-id="4f5d8-103">Для использования драйвера ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] необходимо предусмотреть возможность создания источников данных ODBC и убедиться в том, что на сервере находится правильная версия хранимых процедур каталога.</span><span class="sxs-lookup"><span data-stu-id="4f5d8-103">To use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver, you must be able to create ODBC data sources and ensure that the server has the correct version of the catalog stored procedures.</span></span> <span data-ttu-id="4f5d8-104">Для написания приложения ODBC, в котором используется SQL Server, необходимо знать, как выделять дескрипторы ODBC, устанавливать атрибуты, соединяться с экземпляром SQL Server, выполнять запросы и вычислять результаты.</span><span class="sxs-lookup"><span data-stu-id="4f5d8-104">To code an ODBC application that uses SQL Server, you must know how to allocate ODBC handles, set attributes, connect to an instance of SQL Server, execute queries, and process results.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f5d8-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="4f5d8-105">In This Section</span></span>  
  
-   [<span data-ttu-id="4f5d8-106">Инструкции по настройке драйвера ODBC SQL Server</span><span class="sxs-lookup"><span data-stu-id="4f5d8-106">Configuring the SQL Server ODBC Driver How-to Topics</span></span>](../../database-engine/dev-guide/configuring-the-sql-server-odbc-driver-how-to-topics.md)  
  
-   [<span data-ttu-id="4f5d8-107">Выделение дескрипторов и подключение к SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="4f5d8-107">Allocate Handles and Connect to SQL Server &#40;ODBC&#41;</span></span>](allocate-handles-and-connect-to-sql-server-odbc.md)  
  
-   [<span data-ttu-id="4f5d8-108">Инструкции по выполнению запросов &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="4f5d8-108">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](execute-queries/executing-queries-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="4f5d8-109">Разделы руководства по обработке результатов &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="4f5d8-109">Processing Results How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="4f5d8-110">Инструкции по использованию курсоров &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="4f5d8-110">Using Cursors How-to Topics &#40;ODBC&#41;</span></span>](cursors/using-cursors-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="4f5d8-111">Использование Microsoft координатор распределенных транзакций &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="4f5d8-111">Use Microsoft Distributed Transaction Coordinator &#40;ODBC&#41;</span></span>](use-microsoft-distributed-transaction-coordinator-odbc.md)  
  
-   [<span data-ttu-id="4f5d8-112">Разделы руководства по выполнению хранимых процедур &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="4f5d8-112">Running Stored Procedures How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="4f5d8-113">Разделы руководства по управлению столбцами Text и Image &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="4f5d8-113">Managing text and image Columns How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/managing-text-and-image-columns-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="4f5d8-114">Инструкции по профилированию производительности драйвера ODBC &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="4f5d8-114">Profiling ODBC Driver Performance How-to Topics &#40;ODBC&#41;</span></span>](profiling-odbc-driver-performance-odbc.md)  
  
-   [<span data-ttu-id="4f5d8-115">Обработка ошибок ODBC &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="4f5d8-115">Process ODBC Errors &#40;ODBC&#41;</span></span>](process-odbc-errors-odbc.md)  
  
-   [<span data-ttu-id="4f5d8-116">Инструкции по групповому копированию с помощью драйвера ODBC SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="4f5d8-116">Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;</span></span>](bulk-copy/bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="4f5d8-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="4f5d8-117">See Also</span></span>  
 [<span data-ttu-id="4f5d8-118">SQL Server Native Client (ODBC)</span><span class="sxs-lookup"><span data-stu-id="4f5d8-118">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
