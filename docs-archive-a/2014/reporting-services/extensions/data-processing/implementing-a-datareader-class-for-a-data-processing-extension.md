---
title: Реализация класса DataReader для модуля обработки данных | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], data readers
- data readers [Reporting Services]
- DataReader class
- read-only data
ms.assetid: 23e286e7-6074-4fbe-be29-203420d6c3d0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7c9e55741c72d624b7149435ced90550135d8b4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750491"
---
# <a name="implementing-a-datareader-class-for-a-data-processing-extension"></a><span data-ttu-id="7da79-102">Реализация класса DataReader для модуля обработки данных</span><span class="sxs-lookup"><span data-stu-id="7da79-102">Implementing a DataReader Class for a Data Processing Extension</span></span>
  <span data-ttu-id="7da79-103">Объект **DataReader** позволяет клиенту принимать доступный только для чтения однопроходный поток данных из источника данных.</span><span class="sxs-lookup"><span data-stu-id="7da79-103">The **DataReader** object enables a client to retrieve a read-only, forward-only stream of data from a data source.</span></span> <span data-ttu-id="7da79-104">Результаты возвращаются после выполнения запроса и хранятся в сетевом буфере на клиенте до тех пор, пока не будут запрошены с помощью метода **Read** класса **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="7da79-104">Results are returned as the query executes and are stored in the network buffer on the client until you request them using the **Read** method of the **DataReader** class.</span></span> <span data-ttu-id="7da79-105">Чтобы создать класс **DataReader**, следует реализовать <xref:Microsoft.ReportingServices.DataProcessing.IDataReader> и, возможно, реализовать <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension>.</span><span class="sxs-lookup"><span data-stu-id="7da79-105">To create a **DataReader** class, implement <xref:Microsoft.ReportingServices.DataProcessing.IDataReader> and optionally implement <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension>.</span></span> <span data-ttu-id="7da79-106">Объект **DataReader** позволяет увеличить производительность приложения двумя способами: путем получения данных, как только они становятся доступны, вместо ожидания возвращения всех результатов запроса, а также (по умолчанию) путем сохранения в памяти только одной строки за один раз, что снижает нагрузку на системные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="7da79-106">Using a **DataReader** object increases application performance both by retrieving data as soon as it is available, rather than waiting for the entire results of the query to be returned, and (by default) storing only one row at a time in memory, reducing system overhead.</span></span>  
  
 <span data-ttu-id="7da79-107">После создания экземпляра класса **Command** создайте объект **DataReader**, вызвав **Command.ExecuteReader** для получения строк из источника данных.</span><span class="sxs-lookup"><span data-stu-id="7da79-107">After creating an instance of your **Command** class, you create a **DataReader** object by calling **Command.ExecuteReader** to retrieve rows from the data source.</span></span> <span data-ttu-id="7da79-108">Реализация **DataReader** должна предоставлять две основные возможности: однопроходный доступ к результирующим наборам, полученным при выполнении команды, и доступ к типам столбцов, именам и значениям в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="7da79-108">The **DataReader** implementation must provide two basic capabilities: forward-only access over the result sets obtained by executing a command and access to the column types, names, and values within each row.</span></span> <span data-ttu-id="7da79-109">Клиенты используют метод **Read** объекта **DataReader** для получения строки из результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="7da79-109">Clients use the **Read** method of the **DataReader** object to obtain a row from the results of the query.</span></span>  
  
 <span data-ttu-id="7da79-110">В конструкторе отчетов объект **DataReader** используется для получения списка полей, а также сведений о схеме для результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="7da79-110">In Report Designer, your **DataReader** object is used to retrieve a list of fields as well as schema information about the result set.</span></span> <span data-ttu-id="7da79-111">Это достигается путем реализации методов **GetName**, **GetValue**, **GetFieldType** и **GetOrdinal** экземпляра <xref:Microsoft.ReportingServices.DataProcessing.IDataReader>.</span><span class="sxs-lookup"><span data-stu-id="7da79-111">This is accomplished by implementing the **GetName**, **GetValue**, **GetFieldType,** and **GetOrdinal** methods of the <xref:Microsoft.ReportingServices.DataProcessing.IDataReader> interface.</span></span>  
  
 <span data-ttu-id="7da79-112">Экземпляр <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension> позволяет предоставлять конкретные сведения статистической обработки результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="7da79-112">The <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension> interface allows you to supply specific aggregation information about your result set.</span></span> <span data-ttu-id="7da79-113">Пример реализации класса **DataReader** см. в разделе [Образцы продуктов служб SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="7da79-113">For a sample **DataReader** class implementation, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7da79-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="7da79-114">See Also</span></span>  
 <span data-ttu-id="7da79-115">[Модули служб Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="7da79-115">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="7da79-116">[Реализация модуля обработки данных](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="7da79-116">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="7da79-117">Библиотека модулей Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7da79-117">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
