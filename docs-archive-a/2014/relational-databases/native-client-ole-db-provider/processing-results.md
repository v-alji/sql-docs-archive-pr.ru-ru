---
title: Обработка результатов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, results processing
- OLE DB, processing results
- rowsets [SQL Server], results processing
- results [SQL Server Native Client]
ms.assetid: 20887ac4-f649-4e7f-92e6-f929e2e70952
author: rothja
ms.author: jroth
ms.openlocfilehash: b9e5bf00b4d2e554536c9f2ba1a328390b93a8a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667049"
---
# <a name="processing-results"></a><span data-ttu-id="2cd19-102">Обработка результатов</span><span class="sxs-lookup"><span data-stu-id="2cd19-102">Processing Results</span></span>
  <span data-ttu-id="2cd19-103">Если объект набора строк создан в результате выполнения команды или его формирования непосредственно из поставщика, то пользователю необходимо иметь возможность доступа к данным набора строк и их получения.</span><span class="sxs-lookup"><span data-stu-id="2cd19-103">If a rowset object is produced by either the execution of a command or the generation of a rowset object directly from the provider, the consumer needs to retrieve and access data in the rowset.</span></span>  
  
 <span data-ttu-id="2cd19-104">Наборы строк являются важными объектами, позволяющими поставщику OLE DB для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] обеспечивать доступ к данным в табличной форме.</span><span class="sxs-lookup"><span data-stu-id="2cd19-104">Rowsets are the central objects that enable the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider to expose data in tabular form.</span></span> <span data-ttu-id="2cd19-105">С концептуальной точки зрения объект набора строк — это набор строк, в котором каждая строка содержит данные столбцов.</span><span class="sxs-lookup"><span data-stu-id="2cd19-105">Conceptually, a rowset is a set of rows in which each row has column data.</span></span> <span data-ttu-id="2cd19-106">Объект набора строк предоставляет доступ к интерфейсам, таким как **IRowset** (содержит методы последовательного получения строк из набора), **IAccessor** (обеспечивает определение группы привязок столбцов, описывающих привязку табличных данных к переменным пользовательской программы), **IColumnsInfo** (предоставляет информацию о столбцах набора строк) и **IRowsetInfo** (предоставляет информацию о наборе строк).</span><span class="sxs-lookup"><span data-stu-id="2cd19-106">A rowset object exposes interfaces such as **IRowset** (contains methods for fetching rows from the rowset sequentially), **IAccessor** (permits the definition of a group of column bindings describing the way tabular data is bound to consumer program variables), **IColumnsInfo** (provides information about columns in the rowset), and **IRowsetInfo** (provides information about rowset).</span></span>  
  
 <span data-ttu-id="2cd19-107">Пользователь может вызывать метод **IRowset::GetData** для получения строки данных из набора строк в буфер.</span><span class="sxs-lookup"><span data-stu-id="2cd19-107">A consumer can call the **IRowset::GetData** method to retrieve a row of data from the rowset into a buffer.</span></span> <span data-ttu-id="2cd19-108">Перед вызовом функции **GetData** пользователь описывает буфер с помощью набора структур DBBINDING.</span><span class="sxs-lookup"><span data-stu-id="2cd19-108">Before **GetData** is called, the consumer describes the buffer using a set of DBBINDING structures.</span></span> <span data-ttu-id="2cd19-109">Каждая привязка описывает способ сохранения столбца набора строк в буфере пользователя и содержит следующее.</span><span class="sxs-lookup"><span data-stu-id="2cd19-109">Each binding describes how a column in a rowset is stored in a consumer buffer and contains the following:</span></span>  
  
-   <span data-ttu-id="2cd19-110">Порядковый номер столбца (или параметра), к которому относится привязка.</span><span class="sxs-lookup"><span data-stu-id="2cd19-110">Ordinal of the column (or parameter) to which the binding applies.</span></span>  
  
-   <span data-ttu-id="2cd19-111">Информация о том объекте, для которого выполняется привязка (например, значение данных, длина данных, состояние привязки).</span><span class="sxs-lookup"><span data-stu-id="2cd19-111">Information about what is bound (for example, data value, length of the data, and its binding status).</span></span>  
  
-   <span data-ttu-id="2cd19-112">Информация о смещении в буфере для каждой из этих частей.</span><span class="sxs-lookup"><span data-stu-id="2cd19-112">Information about what is offset in the buffer to each of these parts.</span></span>  
  
-   <span data-ttu-id="2cd19-113">Длина и тип значений данных, которые имеются в буфере пользователя.</span><span class="sxs-lookup"><span data-stu-id="2cd19-113">Length and type of the data values as they exist in the consumer buffer.</span></span>  
  
 <span data-ttu-id="2cd19-114">При получении данных поставщик использует информацию каждой привязки, чтобы определить, куда и как получить данные из буфера пользователя.</span><span class="sxs-lookup"><span data-stu-id="2cd19-114">When getting the data, the provider uses information in each binding to determine where and how to retrieve data from the consumer buffer.</span></span> <span data-ttu-id="2cd19-115">При задании значений данных в буфере пользователя поставщик использует информацию каждой привязки, чтобы определить, куда и как вернуть данные в буфер пользователя.</span><span class="sxs-lookup"><span data-stu-id="2cd19-115">When setting data in the consumer buffer, the provider uses information in each binding to determine where and how to return data in the consumer's buffer.</span></span>  
  
 <span data-ttu-id="2cd19-116">После задания структур DBBINDING создается метод доступа (**IAccessor::CreateAccessor**).</span><span class="sxs-lookup"><span data-stu-id="2cd19-116">After the DBBINDING structures are specified, an accessor is created (**IAccessor::CreateAccessor**).</span></span> <span data-ttu-id="2cd19-117">Метод доступа представляет собой коллекцию привязок и используется для получения данных из буфера пользователя или задания значений данных в буфере.</span><span class="sxs-lookup"><span data-stu-id="2cd19-117">An accessor is a collection of bindings and is used to get or set the data in the consumer buffer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cd19-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="2cd19-118">See Also</span></span>  
 <span data-ttu-id="2cd19-119">[Создание приложения поставщика SQL Server Native Client OLE DB](creating-a-sql-server-native-client-ole-db-provider-application.md) </span><span class="sxs-lookup"><span data-stu-id="2cd19-119">[Creating a SQL Server Native Client OLE DB Provider Application](creating-a-sql-server-native-client-ole-db-provider-application.md) </span></span>  
 [<span data-ttu-id="2cd19-120">Инструкции по OLE DB</span><span class="sxs-lookup"><span data-stu-id="2cd19-120">OLE DB How-to Topics</span></span>](../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
  
