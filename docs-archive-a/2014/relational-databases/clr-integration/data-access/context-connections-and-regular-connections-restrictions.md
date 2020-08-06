---
title: Ограничения для обычных и контекстных подключений | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: 0c6fe4cb-d846-40b5-8884-35a9c770f5e8
author: rothja
ms.author: jroth
ms.openlocfilehash: 52f50347a27cdaffe83b252d86c56382b5ef4f31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665385"
---
# <a name="restrictions-on-regular-and-context-connections"></a><span data-ttu-id="938b8-102">Ограничения обычных и контекстных соединений</span><span class="sxs-lookup"><span data-stu-id="938b8-102">Restrictions on Regular and Context Connections</span></span>
  <span data-ttu-id="938b8-103">В этом разделе содержатся сведения об ограничениях, связанных с кодом, выполняемым в процессе [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] через контекстные и обычные соединения.</span><span class="sxs-lookup"><span data-stu-id="938b8-103">This topic discusses the restrictions associated with code executing in the [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] process through context and regular connections.</span></span>  
  
## <a name="restrictions-on-context-connections"></a><span data-ttu-id="938b8-104">Ограничения контекстных соединений</span><span class="sxs-lookup"><span data-stu-id="938b8-104">Restrictions on Context Connections</span></span>  
 <span data-ttu-id="938b8-105">При проектировании приложения учитывайте следующие ограничения, которые применяются к контекстным соединениям.</span><span class="sxs-lookup"><span data-stu-id="938b8-105">When developing your application, take into account the following restrictions that apply to context connections:</span></span>  
  
-   <span data-ttu-id="938b8-106">В определенное время для заданного соединения может существовать только одно открытое контекстное соединение.</span><span class="sxs-lookup"><span data-stu-id="938b8-106">You can have only one context connection open at a given time for a given connection.</span></span> <span data-ttu-id="938b8-107">Если имеется несколько инструкций, параллельно выполняемых в отдельных соединениях, каждая из них может иметь собственное контекстное соединение.</span><span class="sxs-lookup"><span data-stu-id="938b8-107">If you have multiple statements running concurrently in separate connections, each one of them can get their own context connection.</span></span> <span data-ttu-id="938b8-108">Ограничение не влияет на параллельные запросы из различных соединений, оно влияет только на конкретный запрос в отдельном соединении.</span><span class="sxs-lookup"><span data-stu-id="938b8-108">The restriction does not affect concurrent requests from different connections; it only affects a given request on a given connection.</span></span>  
  
-   <span data-ttu-id="938b8-109">Режим MARS не поддерживается в контекстных соединениях.</span><span class="sxs-lookup"><span data-stu-id="938b8-109">Multiple Active Result Sets (MARS) is not supported in a context connection.</span></span>  
  
-   <span data-ttu-id="938b8-110">Класс `SqlBulkCopy` не работает в контекстных соединениях.</span><span class="sxs-lookup"><span data-stu-id="938b8-110">The `SqlBulkCopy` class does not operate in a context connection.</span></span>  
  
-   <span data-ttu-id="938b8-111">Пакетное обновление не поддерживается в контекстных соединениях.</span><span class="sxs-lookup"><span data-stu-id="938b8-111">Update batching in a context connection is not supported</span></span>  
  
-   <span data-ttu-id="938b8-112">`SqlNotificationRequest` нельзя использовать с командами, применяемыми в контекстном соединении.</span><span class="sxs-lookup"><span data-stu-id="938b8-112">`SqlNotificationRequest` cannot be used with commands that execute against a context connection.</span></span>  
  
-   <span data-ttu-id="938b8-113">Отмена команд, применяемых в контекстном соединении, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="938b8-113">Canceling commands that are running against the context connection is not supported.</span></span> <span data-ttu-id="938b8-114">Метод `SqlCommand.Cancel` не учитывает запрос, не сообщая об этом.</span><span class="sxs-lookup"><span data-stu-id="938b8-114">The `SqlCommand.Cancel` method silently ignores the request.</span></span>  
  
-   <span data-ttu-id="938b8-115">Никакие другие ключевые слова строки соединения не могут использоваться при использовании «context connection=true».</span><span class="sxs-lookup"><span data-stu-id="938b8-115">No other connection string keywords can be used when you use "context connection=true".</span></span>  
  
-   <span data-ttu-id="938b8-116">Свойство `SqlConnection.DataSource` возвращает вместо имени экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] значение NULL, если строка соединения для `SqlConnection` равна «context connection=true».</span><span class="sxs-lookup"><span data-stu-id="938b8-116">The `SqlConnection.DataSource` property returns null if the connection string for the `SqlConnection` is "context connection=true", instead of the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="938b8-117">Установка свойства `SqlCommand.CommandTimeout` не имеет значения, если команда выполняется в контекстном соединении.</span><span class="sxs-lookup"><span data-stu-id="938b8-117">Setting the `SqlCommand.CommandTimeout` property has no effect when the command is executed against a context connection.</span></span>  
  
## <a name="restrictions-on-regular-connections"></a><span data-ttu-id="938b8-118">Ограничения обычных соединений</span><span class="sxs-lookup"><span data-stu-id="938b8-118">Restrictions on Regular Connections</span></span>  
 <span data-ttu-id="938b8-119">При проектировании приложения учитывайте следующие ограничения, которые применяются к обычным соединениям.</span><span class="sxs-lookup"><span data-stu-id="938b8-119">When developing your application, take into account the following restrictions that apply to regular connections:</span></span>  
  
-   <span data-ttu-id="938b8-120">Асинхронное применение команд к внутренним серверам не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="938b8-120">Asynchronous command execution against internal servers is not supported.</span></span> <span data-ttu-id="938b8-121">Если в строке соединения содержится «async=true», по при последующем выполнении команды возникает исключение `System.NotSupportedException`.</span><span class="sxs-lookup"><span data-stu-id="938b8-121">Including "async=true" in the connection string of a command, and then executing the command, results in `System.NotSupportedException` being thrown.</span></span> <span data-ttu-id="938b8-122">Отображается сообщение: «Асинхронная обработка не поддерживается при выполнении в процессе [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ».</span><span class="sxs-lookup"><span data-stu-id="938b8-122">This message appears: "Asynchronous processing is not supported when running inside the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process."</span></span>  
  
-   <span data-ttu-id="938b8-123">Объект `SqlDependency` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="938b8-123">`SqlDependency` object is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="938b8-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="938b8-124">See Also</span></span>  
 [<span data-ttu-id="938b8-125">Контекстное соединение</span><span class="sxs-lookup"><span data-stu-id="938b8-125">Context Connection</span></span>](context-connection.md)  
  
  
