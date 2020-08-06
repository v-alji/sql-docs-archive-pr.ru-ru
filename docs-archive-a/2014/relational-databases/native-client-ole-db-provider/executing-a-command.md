---
title: Выполнение команды | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- commands [SQL Server Native Client]
- OLE DB, executing commands
- sessions [SQL Server Native Client]
- OLE DB extensions for XML
- SQL Server Native Client OLE DB provider, command execution
ms.assetid: bb0b3cbf-fe45-46ba-b2ec-c5a39e3c7081
author: rothja
ms.author: jroth
ms.openlocfilehash: 41e8da036d5a4b6469a31213247ad7d4edb7dbfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667050"
---
# <a name="executing-a-command"></a><span data-ttu-id="4d60f-102">Выполнение команды</span><span class="sxs-lookup"><span data-stu-id="4d60f-102">Executing a Command</span></span>
  <span data-ttu-id="4d60f-103">После подключения с источнику данных потребитель вызывает метод **IDBCreateSession::CreateSession** для создания сеанса.</span><span class="sxs-lookup"><span data-stu-id="4d60f-103">After the connection to a data source is established, the consumer calls the **IDBCreateSession::CreateSession** method to create a session.</span></span> <span data-ttu-id="4d60f-104">Сеанс выступает в роли фабрики для команд, наборов строк и транзакций.</span><span class="sxs-lookup"><span data-stu-id="4d60f-104">The session acts as a command, rowset, or transaction factory.</span></span>  
  
 <span data-ttu-id="4d60f-105">Для непосредственной работы с отдельными таблицами и индексами потребитель запрашивает интерфейс `IOpenRowset`.</span><span class="sxs-lookup"><span data-stu-id="4d60f-105">To work directly with individual tables or indexes, the consumer requests the `IOpenRowset` interface.</span></span> <span data-ttu-id="4d60f-106">Метод `IOpenRowset::OpenRowset` открывает и возвращает набор строк, содержащий все строки из единой базовой таблицы или индекса.</span><span class="sxs-lookup"><span data-stu-id="4d60f-106">The `IOpenRowset::OpenRowset` method opens and returns a rowset that includes all rows from a single base table or index.</span></span>  
  
 <span data-ttu-id="4d60f-107">Чтобы выполнить команду (например \* , SELECT FROM Authors), потребитель запрашивает `IDBCreateCommand` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="4d60f-107">To execute a command (such as SELECT \* FROM Authors), the consumer requests the `IDBCreateCommand` interface.</span></span> <span data-ttu-id="4d60f-108">Потребитель может вызвать метод `IDBCreateCommand::CreateCommand`, чтобы создать командный объект и запросить интерфейс `ICommandText`.</span><span class="sxs-lookup"><span data-stu-id="4d60f-108">The consumer can execute the `IDBCreateCommand::CreateCommand` method to create a command object and request for the `ICommandText` interface.</span></span> <span data-ttu-id="4d60f-109">Метод `ICommandText::SetCommandText` используется для задания текста команды, которую надо выполнить.</span><span class="sxs-lookup"><span data-stu-id="4d60f-109">The `ICommandText::SetCommandText` method is used to specify the command that is to be executed.</span></span>  
  
 <span data-ttu-id="4d60f-110">Для выполнения команды используется команда `Execute`.</span><span class="sxs-lookup"><span data-stu-id="4d60f-110">The `Execute` command is used to execute the command.</span></span> <span data-ttu-id="4d60f-111">Командой может быть любая инструкция SQL или имя процедуры.</span><span class="sxs-lookup"><span data-stu-id="4d60f-111">The command can be any SQL statement or procedure name.</span></span> <span data-ttu-id="4d60f-112">Не все команды возвращают объект результирующего набора (набор строк).</span><span class="sxs-lookup"><span data-stu-id="4d60f-112">Not all commands produce a result set (rowset) object.</span></span> <span data-ttu-id="4d60f-113">Такие команды, как SELECT \* FROM Authors, возвращают результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="4d60f-113">Commands such as SELECT \* FROM Authors produce a result set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d60f-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="4d60f-114">See Also</span></span>  
 [<span data-ttu-id="4d60f-115">Создание приложения поставщика OLE DB для собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="4d60f-115">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
  
