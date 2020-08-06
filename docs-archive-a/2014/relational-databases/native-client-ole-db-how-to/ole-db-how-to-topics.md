---
title: Инструкции по OLE DB | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, how-to topics
ms.assetid: fbfab1b0-433d-497e-ae07-9b21a5c6903c
author: rothja
ms.author: jroth
ms.openlocfilehash: 006962c1a28cc4a21f3e2efaa63b45b0871e208f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658688"
---
# <a name="ole-db-how-to-topics"></a><span data-ttu-id="d3b92-102">Инструкции по OLE DB</span><span class="sxs-lookup"><span data-stu-id="d3b92-102">OLE DB How-to Topics</span></span>
  <span data-ttu-id="d3b92-103">Чтобы использовать [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственный поставщик OLE DB клиента, необходимо понять, как установить соединение с сервером, выполнить команду и обработать результаты.</span><span class="sxs-lookup"><span data-stu-id="d3b92-103">To use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, you have to understand how to make a connection to the server, execute the command, and process the results.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d3b92-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="d3b92-104">In This Section</span></span>  
  
-   [<span data-ttu-id="d3b92-105">Инструкции по обработке результатов &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d3b92-105">Processing Results How-to Topics &#40;OLE DB&#41;</span></span>](results/processing-results-how-to-topics-ole-db.md)  
  
-   [<span data-ttu-id="d3b92-106">Задание данных большого объема (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="d3b92-106">Set Large Data &#40;OLE DB&#41;</span></span>](set-large-data-ole-db.md)  
  
-   [<span data-ttu-id="d3b92-107">Перечисление источников данных OLE DB &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d3b92-107">Enumerate OLE DB Data Sources &#40;OLE DB&#41;</span></span>](enumerate-ole-db-data-sources-ole-db.md)  
  
-   [<span data-ttu-id="d3b92-108">Выполнение массового копирования данных с использованием интерфейса IRowsetFastLoad &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d3b92-108">Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;</span></span>](../native-client-ole-db-interfaces/irowsetfastload-ole-db.md)  
  
-   [<span data-ttu-id="d3b92-109">Получение курсора FAST_FORWARD</span><span class="sxs-lookup"><span data-stu-id="d3b92-109">Obtain a FAST_FORWARD Cursor</span></span>](obtain-a-fast-forward-cursor.md)  
  
-   [<span data-ttu-id="d3b92-110">Получение строк с помощью закладок &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d3b92-110">Retrieve Rows Using Bookmarks &#40;OLE DB&#41;</span></span>](retrieve-rows-using-bookmarks-ole-db.md)  
  
-   [<span data-ttu-id="d3b92-111">Выбор столбцов с помощью метода IRow::GetColumns &#40;или IRow::Open&#41; и интерфейса ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="d3b92-111">Fetch Columns Using IRow::GetColumns &#40;or IRow::Open&#41; and ISequentialStream</span></span>](fetch-columns-using-irow-getcolumns-or-irow-open-and-isequentialstream.md)  
  
-   [<span data-ttu-id="d3b92-112">Выбор столбцов с помощью метода IRow::GetColumns &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d3b92-112">Fetch Columns Using IRow::GetColumns &#40;OLE DB&#41;</span></span>](fetch-columns-using-irow-getcolumns-ole-db.md)  
  
-   [<span data-ttu-id="d3b92-113">Изменения пароля проверки подлинности пользователя SQL Server &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d3b92-113">Change a SQL Server Authentication User Password &#40;OLE DB&#41;</span></span>](change-a-sql-server-authentication-user-password-ole-db.md)  
  
-   [<span data-ttu-id="d3b92-114">Использование улучшенных функций даты и времени &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d3b92-114">Use Enhanced Date and Time Features &#40;OLE DB&#41;</span></span>](use-enhanced-date-and-time-features-ole-db.md)  
  
-   [<span data-ttu-id="d3b92-115">Filestream и OLE DB</span><span class="sxs-lookup"><span data-stu-id="d3b92-115">Filestream and OLE DB</span></span>](filestream/filestream-and-ole-db.md)  
  
-   [<span data-ttu-id="d3b92-116">Отправка данных BLOB-объектов в SQL Server с помощью интерфейсов IROWSETFASTLOAD и ISEQUENTIALSTREAM &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d3b92-116">Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;</span></span>](send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md)  
  
-   [<span data-ttu-id="d3b92-117">Использование определяемых пользователем типов больших данных CLR (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="d3b92-117">Use Large CLR UDTs &#40;OLE DB&#41;</span></span>](use-large-clr-udts-ole-db.md)  
  
-   [<span data-ttu-id="d3b92-118">Отображение метаданных столбца и каталога для разреженных столбцов &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d3b92-118">Display Column and Catalog Metadata for Sparse Columns &#40;OLE DB&#41;</span></span>](display-column-and-catalog-metadata-for-sparse-columns-ole-db.md)  
  
-   [<span data-ttu-id="d3b92-119">Интегрированная проверка подлинности Kerberos &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d3b92-119">Integrated Kerberos Authentication &#40;OLE DB&#41;</span></span>](integrated-kerberos-authentication-ole-db.md)  
  
-   [<span data-ttu-id="d3b92-120">Использование возвращающих табличные значения параметров &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d3b92-120">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md)  
  
## <a name="see-also"></a><span data-ttu-id="d3b92-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="d3b92-121">See Also</span></span>  
 [<span data-ttu-id="d3b92-122">Программирование собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="d3b92-122">SQL Server Native Client Programming</span></span>](../native-client/sql-server-native-client-programming.md)  
  
  
