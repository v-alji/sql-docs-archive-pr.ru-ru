---
title: Доступ к данным из объектов базы данных CLR | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], data access
- routines [CLR integration]
- data access [CLR integration]
- ADO.NET [CLR integration]
- internal data access [CLR integration]
- common language runtime [SQL Server], ADO.NET
- database objects [CLR integration], data access
- managed code [SQL Server], database objects
- .NET Data Access Provider for SQL Server [CLR integration]
- managed code [SQL Server], data access
- SqlClient provider
- in-process data access providers [CLR integration]
ms.assetid: 9a0f4dee-71c1-42e9-a85e-52382807010f
author: rothja
ms.author: jroth
ms.openlocfilehash: d229d490a9f3a7bc6f613259ee0535218de47975
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667732"
---
# <a name="data-access-from-clr-database-objects"></a><span data-ttu-id="be042-102">Доступ к данным из объектов среды CLR для работы с базами данных</span><span class="sxs-lookup"><span data-stu-id="be042-102">Data Access from CLR Database Objects</span></span>
  <span data-ttu-id="be042-103">Подпрограммы среды CLR могут легко обращаться к данным, хранящимся в экземпляре служб [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] , в котором она выполняется, а также к данным, хранящимся в удаленных экземплярах.</span><span class="sxs-lookup"><span data-stu-id="be042-103">A common language runtime (CLR) routine may easily access data stored in the instance of [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] in which it runs, as well as data stored in remote instances.</span></span> <span data-ttu-id="be042-104">Какие именно это данные — определяет контекст пользователя, в котором выполняется код.</span><span class="sxs-lookup"><span data-stu-id="be042-104">Which particular data the routine can access is determined by the user context in which the code is running.</span></span> <span data-ttu-id="be042-105">Доступ к данным из объекта базы данных CLR с помощью .NET Framework поставщика данных для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] данных из управляемого клиента и приложений среднего уровня.</span><span class="sxs-lookup"><span data-stu-id="be042-105">Access data from within a CLR database object by using the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data from managed client and middle-tier applications.</span></span> <span data-ttu-id="be042-106">Это позволяет эффективно использовать опыт работы с ADO.NET и `SqlClient` как в клиентских приложениях, так и в приложениях среднего уровня.</span><span class="sxs-lookup"><span data-stu-id="be042-106">Because of this, you can leverage your knowledge of ADO.NET and `SqlClient` in client and middle-tier applications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be042-107">По умолчанию методы определяемых пользователем типов и определяемые пользователем функции не могут производить доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="be042-107">User-defined type methods and user-defined functions are not allowed to perform data access by default.</span></span> <span data-ttu-id="be042-108">Чтобы разрешить такой доступ, необходимо присвоить свойству `DataAccess` объекта `SqlMethodAttribute` или `SqlFunctionAttribute` значение `DataAccessKind.Read`.</span><span class="sxs-lookup"><span data-stu-id="be042-108">You must set the `DataAccess` property of `SqlMethodAttribute` or `SqlFunctionAttribute` to `DataAccessKind.Read` to enable read-only data access from user-defined type (UDT) methods or user-defined functions.</span></span> <span data-ttu-id="be042-109">Операции изменения данных из методов определяемых пользователем типов и определяемых пользователем функций не разрешены. При попытке выполнить такую операцию будет вызвано исключение времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="be042-109">Data modification operations are not allowed from UDTs or user-defined functions, and throws exceptions at execution time if attempted.</span></span>  
  
 <span data-ttu-id="be042-110">В этом разделе приведены лишь особые функциональные и поведенческие различия при доступе к данным из объекта базы данных CLR.</span><span class="sxs-lookup"><span data-stu-id="be042-110">This section discusses only the specific functional and behavioral differences when accessing data from within a CLR database object.</span></span> <span data-ttu-id="be042-111">Дополнительные сведения о функциях и возможностях ADO.NET см. в документации по ADO.NET, включенной в пакет разработчика .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="be042-111">For more information about the features and functionality of ADO.NET, see the ADO.NET documentation included in the .NET Framework SDK.</span></span>  
  
 <span data-ttu-id="be042-112">В следующей таблице приводится список подразделов данного раздела.</span><span class="sxs-lookup"><span data-stu-id="be042-112">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="be042-113">Контекстное соединение</span><span class="sxs-lookup"><span data-stu-id="be042-113">Context Connection</span></span>](context-connection.md)  
 <span data-ttu-id="be042-114">Содержит сведения о контекстном соединении с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="be042-114">Describes the context connection to SQL Server.</span></span>  
  
 [<span data-ttu-id="be042-115">Олицетворение и учетные данные для соединений</span><span class="sxs-lookup"><span data-stu-id="be042-115">Impersonation and Credentials for Connections</span></span>](impersonation-and-credentials-for-connections.md)  
 <span data-ttu-id="be042-116">Содержит сведения об олицетворенных соединениях и учетных данных соединения.</span><span class="sxs-lookup"><span data-stu-id="be042-116">Describes impersonating connections and connection credentials.</span></span>  
  
 [<span data-ttu-id="be042-117">Внутрипроцессные расширения SQL Server для ADO.NET</span><span class="sxs-lookup"><span data-stu-id="be042-117">SQL Server In-Process Specific Extensions to ADO.NET</span></span>](../../clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md)  
 <span data-ttu-id="be042-118">Содержит описание внутрипроцессных объектов `SqlPipe`, `SqlContext`, `SqlTriggerContext` и `SqlDataRecord`.</span><span class="sxs-lookup"><span data-stu-id="be042-118">Discusses the in-process specific `SqlPipe`, `SqlContext`, `SqlTriggerContext`, and `SqlDataRecord` objects.</span></span>  
  
 [<span data-ttu-id="be042-119">Интеграция со средой CLR и транзакции</span><span class="sxs-lookup"><span data-stu-id="be042-119">CLR Integration and Transactions</span></span>](../../native-client-ole-db-transactions/transactions.md)  
 <span data-ttu-id="be042-120">Содержит описание интеграции с ADO.NET и [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] CLR новой платформы транзакций, представленной в пространстве имен System.Transactions.</span><span class="sxs-lookup"><span data-stu-id="be042-120">Describes how the new transaction framework provided in the System.Transactions namespace integrates with ADO.NET and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] CLR integration.</span></span>  
  
 [<span data-ttu-id="be042-121">Сериализация XML из объектов базы данных CLR</span><span class="sxs-lookup"><span data-stu-id="be042-121">XML Serialization from CLR Database Objects</span></span>](../../../database-engine/dev-guide/xml-serialization-from-clr-database-objects.md)  
 <span data-ttu-id="be042-122">Объясняет, как задействовать сценарии сериализации XML объектов базы данных CLR в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be042-122">Explains how to enable XML serialization scenarios of CLR database objects inside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
  
