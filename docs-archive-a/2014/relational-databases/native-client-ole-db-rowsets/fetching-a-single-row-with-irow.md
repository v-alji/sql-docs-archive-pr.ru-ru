---
title: Выборка одной строки через IRow | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fetching rows
- IRow interface
- single row fetching [SQL Server Native Client]
- OLE DB rowsets, fetching
- rowsets [OLE DB], fetching
- SQL Server Native Client OLE DB provider, fetching
ms.assetid: 07c803ca-299a-42c5-ba02-360b9631d15f
author: rothja
ms.author: jroth
ms.openlocfilehash: b5573fe1fef39f29329e373323f5f8aaf15f2c58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667048"
---
# <a name="fetching-a-single-row-with-irow"></a><span data-ttu-id="4a84b-102">Выборка одной строки при помощи интерфейса IRow</span><span class="sxs-lookup"><span data-stu-id="4a84b-102">Fetching a Single Row with IRow</span></span>
  <span data-ttu-id="4a84b-103">Реализация интерфейса **IRow** в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственном поставщике OLE DB клиента упрощена для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="4a84b-103">The **IRow** interface implementation in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider is simplified to increase performance.</span></span> <span data-ttu-id="4a84b-104">Интерфейс **IRow** предоставляет прямой доступ к столбцам одного объекта, представляющего собой строку.</span><span class="sxs-lookup"><span data-stu-id="4a84b-104">**IRow** allows direct access to columns of a single row object.</span></span> <span data-ttu-id="4a84b-105">Если заранее известно, что результатом выполнения команды будет ровно одна строка, **IRow** даст возможность получить столбцы этой строки.</span><span class="sxs-lookup"><span data-stu-id="4a84b-105">If you know beforehand that the result of a command execution will produce exactly one row, **IRow** will retrieve the columns of that row.</span></span> <span data-ttu-id="4a84b-106">Если в результирующий набор входит несколько строк, интерфейс **IRow** предоставит доступ только к первой.</span><span class="sxs-lookup"><span data-stu-id="4a84b-106">If the result set includes multiple rows, **IRow** will expose only the first row.</span></span>  
  
 <span data-ttu-id="4a84b-107">Реализация интерфейса **IRow** не позволяет перемещаться по строке.</span><span class="sxs-lookup"><span data-stu-id="4a84b-107">The **IRow** implementation does not allow any navigation of the row.</span></span> <span data-ttu-id="4a84b-108">Доступ к каждому столбцу в строке осуществляется только один раз с одним исключением: доступ к столбцу можно получить один раз, чтобы найти размер столбца и снова получить данные.</span><span class="sxs-lookup"><span data-stu-id="4a84b-108">Each column in the row is accessed only one time with one exception: A column can be accessed one time to find the column size and again to fetch the data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a84b-109">Метод **IRow::Open** поддерживает открытие только объектов типа DBGUID_STREAM или DBGUID_NULL.</span><span class="sxs-lookup"><span data-stu-id="4a84b-109">**IRow::Open** supports only DBGUID_STREAM and DBGUID_NULL type of objects to be opened.</span></span>  
  
 <span data-ttu-id="4a84b-110">Для получения объекта строки с помощью метода **ICommand::Execute** нужно передать в качестве параметра идентификатор IID_IRow.</span><span class="sxs-lookup"><span data-stu-id="4a84b-110">To obtain a row object using **ICommand::Execute** method, IID_IRow must be passed.</span></span> <span data-ttu-id="4a84b-111">Обработка нескольких результирующих наборов производится с помощью интерфейса **IMultipleResults**.</span><span class="sxs-lookup"><span data-stu-id="4a84b-111">The **IMultipleResults** interface must be used to handle multiple result sets.</span></span> <span data-ttu-id="4a84b-112">Интерфейс **IMultipleResults** поддерживает интерфейсы **IRow** и **IRowset**.</span><span class="sxs-lookup"><span data-stu-id="4a84b-112">**IMultipleResults** supports **IRow** and **IRowset**.</span></span> <span data-ttu-id="4a84b-113">Интерфейс **IRowset** используется для массовых операций.</span><span class="sxs-lookup"><span data-stu-id="4a84b-113">**IRowset** is used for bulk operations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4a84b-114">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="4a84b-114">In This Section</span></span>  
  
-   [<span data-ttu-id="4a84b-115">Использование метода IRow::GetColumns</span><span class="sxs-lookup"><span data-stu-id="4a84b-115">Using IRow::GetColumns</span></span>](using-irow-getcolumns.md)  
  
-   [<span data-ttu-id="4a84b-116">Выборка данных большого двоичного объекта при помощи интерфейса IRow</span><span class="sxs-lookup"><span data-stu-id="4a84b-116">Fetching BLOB Data Using IRow</span></span>](../../database-engine/dev-guide/fetching-blob-data-using-irow.md)  
  
## <a name="see-also"></a><span data-ttu-id="4a84b-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="4a84b-117">See Also</span></span>  
 [<span data-ttu-id="4a84b-118">Наборы строк</span><span class="sxs-lookup"><span data-stu-id="4a84b-118">Rowsets</span></span>](rowsets.md)  
  
  
