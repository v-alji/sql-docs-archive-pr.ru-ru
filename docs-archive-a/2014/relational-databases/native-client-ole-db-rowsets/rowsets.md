---
title: Наборы строк | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowsets [OLE DB], about rowsets
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets
- OLE DB rowsets, about rowsets
- rowsets [OLE DB]
ms.assetid: 5e7b3cbe-3670-4e18-8172-2226e0b6b142
author: rothja
ms.author: jroth
ms.openlocfilehash: 1245d17dc0f3757b3c212146c8c162de6e48a483
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657090"
---
# <a name="rowsets"></a><span data-ttu-id="4f35a-102">Наборы строк</span><span class="sxs-lookup"><span data-stu-id="4f35a-102">Rowsets</span></span>
  <span data-ttu-id="4f35a-103">Набор строк — это несколько строк, содержащих столбцы данных.</span><span class="sxs-lookup"><span data-stu-id="4f35a-103">A rowset is a set of rows that contain columns of data.</span></span> <span data-ttu-id="4f35a-104">Наборы строк — это основные объекты, позволяющие всем поставщикам данных OLE DB представлять данные результирующих наборов в виде таблиц.</span><span class="sxs-lookup"><span data-stu-id="4f35a-104">Rowsets are central objects that enable all OLE DB data providers to expose result set data in tabular form.</span></span>  
  
 <span data-ttu-id="4f35a-105">После создания сеанса с помощью метода **IDBCreateSession::CreateSession** потребитель может использовать интерфейс **IOpenRowset** или **IDBCreateCommand** этого сеанса для создания набора строк.</span><span class="sxs-lookup"><span data-stu-id="4f35a-105">After a consumer creates a session by using the **IDBCreateSession::CreateSession** method, the consumer can use either the **IOpenRowset** or **IDBCreateCommand** interface on the session to create a rowset.</span></span> <span data-ttu-id="4f35a-106">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента поддерживает оба этих интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4f35a-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports both of these interfaces.</span></span> <span data-ttu-id="4f35a-107">Оба эти метода описаны здесь.</span><span class="sxs-lookup"><span data-stu-id="4f35a-107">Both of these methods are described here.</span></span>  
  
-   <span data-ttu-id="4f35a-108">Создайте набор строк, вызвав метод **IOpenRowset::OpenRowset**.</span><span class="sxs-lookup"><span data-stu-id="4f35a-108">Create a rowset by calling the **IOpenRowset::OpenRowset** method.</span></span>  
  
     <span data-ttu-id="4f35a-109">Это эквивалентно созданию набора строк из одной таблицы.</span><span class="sxs-lookup"><span data-stu-id="4f35a-109">This is equivalent to creating a rowset over a single table.</span></span> <span data-ttu-id="4f35a-110">Этот метод открывает и возвращает набор строк, включающий все строки одной базовой таблицы.</span><span class="sxs-lookup"><span data-stu-id="4f35a-110">This method opens and returns a rowset that includes all of the rows from a single base table.</span></span> <span data-ttu-id="4f35a-111">Одним из аргументов метода **OpenRowset** является идентификатор таблицы, указывающий таблицу, на основе которой создается набор строк.</span><span class="sxs-lookup"><span data-stu-id="4f35a-111">One of the arguments to **OpenRowset** is a table ID that identifies the table from which to create the rowset.</span></span>  
  
-   <span data-ttu-id="4f35a-112">Создайте объект команд с помощью метода **IDBCreateCommand::CreateCommand**.</span><span class="sxs-lookup"><span data-stu-id="4f35a-112">Create a command object by calling the **IDBCreateCommand::CreateCommand** method.</span></span>  
  
     <span data-ttu-id="4f35a-113">Объект команд выполняет команды, поддерживаемые поставщиком.</span><span class="sxs-lookup"><span data-stu-id="4f35a-113">The command object executes commands that the provider supports.</span></span> <span data-ttu-id="4f35a-114">С помощью поставщика OLE DB для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] потребитель может указать любую инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)], например SELECT, или вызов хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="4f35a-114">With the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the consumer can specify any [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, such as a SELECT statement or a call to a stored procedure.</span></span> <span data-ttu-id="4f35a-115">Создание набора строк с помощью объекта команд включает следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="4f35a-115">The steps for creating a rowset by using a command object are:</span></span>  
  
    1.  <span data-ttu-id="4f35a-116">Потребитель вызывает метод **IDBCreateCommand::CreateCommand** для сеанса, чтобы получить объект команд, запрашивающий интерфейс **ICommandText** для объекта команд.</span><span class="sxs-lookup"><span data-stu-id="4f35a-116">The consumer calls the **IDBCreateCommand::CreateCommand** method on the session to get a command object requesting the **ICommandText** interface on the command object.</span></span> <span data-ttu-id="4f35a-117">Этот интерфейс **ICommandText** задает и получает действительный текст команды.</span><span class="sxs-lookup"><span data-stu-id="4f35a-117">This **ICommandText** interface sets and retrieves the actual command text.</span></span> <span data-ttu-id="4f35a-118">Потребитель заполняет текст команды путем вызова метода **ICommandText::SetCommandText**.</span><span class="sxs-lookup"><span data-stu-id="4f35a-118">The consumer fills in the text command by calling the **ICommandText::SetCommandText** method.</span></span>  
  
    2.  <span data-ttu-id="4f35a-119">Пользователь вызывает метод **ICommand::Execute** для команды.</span><span class="sxs-lookup"><span data-stu-id="4f35a-119">The user calls the **ICommand::Execute** method on the command.</span></span> <span data-ttu-id="4f35a-120">Объект набора строк, создаваемый во время выполнения команды, содержит результирующий набор этой команды.</span><span class="sxs-lookup"><span data-stu-id="4f35a-120">The rowset object built when the command executes contains the result set from the command.</span></span>  
  
 <span data-ttu-id="4f35a-121">Потребитель может использовать интерфейс **ICommandProperties** для получения или задания свойств набора строк, возвращаемого командой, которая выполняется интерфейсом **ICommand::Execute**.</span><span class="sxs-lookup"><span data-stu-id="4f35a-121">The consumer can use the **ICommandProperties** interface to get or set the properties for the rowset returned by the command executed by the **ICommand::Execute** interfaces.</span></span> <span data-ttu-id="4f35a-122">Наиболее часто запрашиваемыми свойствами являются интерфейсы, которые должны поддерживаться набором строк.</span><span class="sxs-lookup"><span data-stu-id="4f35a-122">The most commonly requested properties are the interfaces the rowset must support.</span></span> <span data-ttu-id="4f35a-123">Кроме интерфейсов, потребитель может запросить свойства, изменяющие поведение набора строк или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4f35a-123">In addition to interfaces, the consumer can request properties that modify the behavior of the rowset or interface.</span></span>  
  
 <span data-ttu-id="4f35a-124">Потребители освобождают наборы строк с помощью метода **IRowset::Release**.</span><span class="sxs-lookup"><span data-stu-id="4f35a-124">Consumers release rowsets with the **IRowset::Release** method.</span></span> <span data-ttu-id="4f35a-125">При освобождении набора строк освобождаются все дескрипторы строк, удерживаемые потребителем для данного набора строк.</span><span class="sxs-lookup"><span data-stu-id="4f35a-125">Releasing a rowset releases any row handles held by the consumer on that rowset.</span></span> <span data-ttu-id="4f35a-126">При освобождении набора строк методы доступа не освобождаются.</span><span class="sxs-lookup"><span data-stu-id="4f35a-126">Releasing a rowset does not release the accessors.</span></span> <span data-ttu-id="4f35a-127">Если используется интерфейс **IAccessor**, его нужно освободить отдельно.</span><span class="sxs-lookup"><span data-stu-id="4f35a-127">If you have an **IAccessor** interface, it still has to be released.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f35a-128">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="4f35a-128">In This Section</span></span>  
  
-   [<span data-ttu-id="4f35a-129">Создание набора строк с помощью интерфейса IOpenRowset</span><span class="sxs-lookup"><span data-stu-id="4f35a-129">Creating a Rowset with IOpenRowset</span></span>](creating-a-rowset-with-iopenrowset.md)  
  
-   [<span data-ttu-id="4f35a-130">Создание наборов строк с помощью метода ICommand::Execute</span><span class="sxs-lookup"><span data-stu-id="4f35a-130">Creating Rowsets with ICommand::Execute</span></span>](creating-rowsets-with-icommand-execute.md)  
  
-   [<span data-ttu-id="4f35a-131">Свойства и поведение наборов строк</span><span class="sxs-lookup"><span data-stu-id="4f35a-131">Rowset Properties and Behaviors</span></span>](rowset-properties-and-behaviors.md)  
  
-   [<span data-ttu-id="4f35a-132">Наборы строк и курсоры SQL Server</span><span class="sxs-lookup"><span data-stu-id="4f35a-132">Rowsets and SQL Server Cursors</span></span>](rowsets-and-sql-server-cursors.md)  
  
-   [<span data-ttu-id="4f35a-133">Выборка строк</span><span class="sxs-lookup"><span data-stu-id="4f35a-133">Fetching Rows</span></span>](fetching-rows.md)  
  
-   [<span data-ttu-id="4f35a-134">Выборка одной строки с помощью интерфейса IRow</span><span class="sxs-lookup"><span data-stu-id="4f35a-134">Fetching a Single Row with IRow</span></span>](fetching-a-single-row-with-irow.md)  
  
-   [<span data-ttu-id="4f35a-135">Закладки</span><span class="sxs-lookup"><span data-stu-id="4f35a-135">Bookmarks</span></span>](bookmarks.md)  
  
-   [<span data-ttu-id="4f35a-136">Обновление данных в наборах строк</span><span class="sxs-lookup"><span data-stu-id="4f35a-136">Updating Data in Rowsets</span></span>](updating-data-in-rowsets.md)  
  
## <a name="see-also"></a><span data-ttu-id="4f35a-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="4f35a-137">See Also</span></span>  
 [<span data-ttu-id="4f35a-138">SQL Server Native Client (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="4f35a-138">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
