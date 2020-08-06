---
title: Взаимодействие с SQL Server (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, communicating with SQL Server
- ODBC applications, communicating with SQL Server
- ODBC, communicating with SQL Server
ms.assetid: cca3dcf0-2a7e-465a-84de-7ce055360eb6
author: rothja
ms.author: jroth
ms.openlocfilehash: c41ac2dcce9c5bdbdd351148d16bcaa8f067d22f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738369"
---
# <a name="communicating-with-sql-server-odbc"></a><span data-ttu-id="a9fb6-102">Взаимодействие с SQL Server (ODBC)</span><span class="sxs-lookup"><span data-stu-id="a9fb6-102">Communicating with SQL Server (ODBC)</span></span>
  <span data-ttu-id="a9fb6-103">Чтобы приложение ODBC было взаимодействовать с экземпляром [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , оно должно выделить среду и дескрипторы соединения и подключиться к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-103">For an ODBC application to communicate with an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it must allocate environment and connection handles and connect to the data source.</span></span> <span data-ttu-id="a9fb6-104">После установки соединения приложение может отправлять запросы на сервер и обрабатывать любые результирующие наборы.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-104">After a connection is established, the application can send queries to the server and process any result sets.</span></span> <span data-ttu-id="a9fb6-105">После завершения использования источника данных приложение отсоединяется от источника и освобождает дескриптор соединения.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-105">When the application has finished using the data source, it disconnects from the data source and frees the connection handle.</span></span> <span data-ttu-id="a9fb6-106">Когда приложение освободит все дескрипторы соединения, оно освобождает дескриптор среды.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-106">When the application has freed all its connection handles, it frees the environment handle.</span></span>  
  
 <span data-ttu-id="a9fb6-107">Приложение может соединяться с любым количеством источников данных.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-107">An application can connect to any number of data sources.</span></span> <span data-ttu-id="a9fb6-108">Приложение может использовать различные сочетания драйверов и источников данных, один драйвер и различные источники данных, или даже один драйвер для многих соединений к одному и тому же источнику данных.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-108">The application can use a combination of drivers and data sources, the same driver and a combination of data sources, or even the same driver and multiple connections to the same data source.</span></span>  
  
 <span data-ttu-id="a9fb6-109">Вы можете скачать [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] образцы ODBC для собственного клиента на странице [загрузки SQL Server](https://go.microsoft.com/fwlink/?LinkId=62796) на сайте MSDN.</span><span class="sxs-lookup"><span data-stu-id="a9fb6-109">You can download [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC samples from the [SQL Server Downloads](https://go.microsoft.com/fwlink/?LinkId=62796) page on MSDN.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a9fb6-110">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="a9fb6-110">In This Section</span></span>  
  
-   [<span data-ttu-id="a9fb6-111">Выделение дескриптора среды</span><span class="sxs-lookup"><span data-stu-id="a9fb6-111">Allocating an Environment Handle</span></span>](allocating-an-environment-handle.md)  
  
-   [<span data-ttu-id="a9fb6-112">Выделение дескриптора соединения</span><span class="sxs-lookup"><span data-stu-id="a9fb6-112">Allocating a Connection Handle</span></span>](allocating-a-connection-handle.md)  
  
-   [<span data-ttu-id="a9fb6-113">Источники данных ODBC собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="a9fb6-113">SQL Server Native Client ODBC Data Sources</span></span>](../../integration-services/connection-manager/data-sources.md)  
  
-   [<span data-ttu-id="a9fb6-114">Подключение к источнику данных &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a9fb6-114">Connecting to a Data Source &#40;ODBC&#41;</span></span>](connecting-to-a-data-source-odbc.md)  
  
-   [<span data-ttu-id="a9fb6-115">Отсоединение от источника данных</span><span class="sxs-lookup"><span data-stu-id="a9fb6-115">Disconnecting from a Data Source</span></span>](disconnecting-from-a-data-source.md)  
  
## <a name="see-also"></a><span data-ttu-id="a9fb6-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="a9fb6-116">See Also</span></span>  
 <span data-ttu-id="a9fb6-117">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="a9fb6-117">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="a9fb6-118">SQLSetEnvAttr</span><span class="sxs-lookup"><span data-stu-id="a9fb6-118">SQLSetEnvAttr</span></span>](../native-client-odbc-api/sqlsetenvattr.md)  
  
  
