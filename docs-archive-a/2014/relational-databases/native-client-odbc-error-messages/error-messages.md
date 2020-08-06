---
title: Сообщения об ошибках | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, errors
- messages [ODBC], types
- ODBC error handling, message types
- errors [ODBC], types
ms.assetid: 46c0c22e-d105-4d5b-bb9d-5694472e8651
author: rothja
ms.author: jroth
ms.openlocfilehash: d004ba320b50896b6f57c5de335d7f7b3d33e87a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738321"
---
# <a name="error-messages"></a><span data-ttu-id="f929a-102">сообщения об ошибках</span><span class="sxs-lookup"><span data-stu-id="f929a-102">Error Messages</span></span>
  <span data-ttu-id="f929a-103">Текст сообщений, возвращаемых [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвером ODBC для собственного клиента, помещается в параметр *MessageText* объекта **SQLGetDiagRec**.</span><span class="sxs-lookup"><span data-stu-id="f929a-103">The text of messages returned by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver is placed in the *MessageText* parameter of **SQLGetDiagRec**.</span></span> <span data-ttu-id="f929a-104">На источник ошибки указывает заголовок сообщения.</span><span class="sxs-lookup"><span data-stu-id="f929a-104">The source of an error is indicated by the header of the message:</span></span>  
  
 <span data-ttu-id="f929a-105">[Майкрософт][Диспетчер драйверов ODBC]</span><span class="sxs-lookup"><span data-stu-id="f929a-105">[Microsoft][ODBC Driver Manager]</span></span>  
 <span data-ttu-id="f929a-106">Эти ошибки формируются диспетчером драйверов ODBC.</span><span class="sxs-lookup"><span data-stu-id="f929a-106">These errors are raised by the ODBC Driver Manager.</span></span>  
  
 <span data-ttu-id="f929a-107">[Майкрософт][Библиотека курсоров ODBC]</span><span class="sxs-lookup"><span data-stu-id="f929a-107">[Microsoft][ODBC Cursor Library]</span></span>  
 <span data-ttu-id="f929a-108">Эти ошибки формируются библиотекой курсоров ODBC.</span><span class="sxs-lookup"><span data-stu-id="f929a-108">These errors are raised by the ODBC cursor library.</span></span>  
  
 <span data-ttu-id="f929a-109">[Майкрософт][Собственный клиент SQL Server]</span><span class="sxs-lookup"><span data-stu-id="f929a-109">[Microsoft][SQL Server Native Client]</span></span>  
 <span data-ttu-id="f929a-110">Эти ошибки вызываются [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвером ODBC для собственного клиента.</span><span class="sxs-lookup"><span data-stu-id="f929a-110">These errors are raised by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="f929a-111">Если не существует других узлов с именем сетевой библиотеки или [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], то ошибка произошла в драйвере.</span><span class="sxs-lookup"><span data-stu-id="f929a-111">If there are no other nodes with either the name of a Net-Library or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], then the error was encountered in the driver.</span></span>  
  
 <span data-ttu-id="f929a-112">NNTP [SQL Server Native Client] [*Net-транспорта*]</span><span class="sxs-lookup"><span data-stu-id="f929a-112">[Microsoft][SQL Server Native Client][*Net-Transportname*]</span></span>  
 <span data-ttu-id="f929a-113">Эти ошибки вызываются [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] сетевой библиотекой, где *net-транспорта* — отображаемое имя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] сетевого транспорта клиента (например, именованные каналы, Общая память, сокеты TCP/IP или Via).</span><span class="sxs-lookup"><span data-stu-id="f929a-113">These errors are raised by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Net-Library, where *Net-Transportname* is the display name of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client network transport (for example, Named Pipes, Shared Memory, TCP/IP Sockets, or VIA).</span></span> <span data-ttu-id="f929a-114">Остальная часть сообщения об ошибке содержит вызванную функцию сетевой библиотеки и функцию, вызванную в базовом сетевом API-интерфейсе функцией потока табличных данных.</span><span class="sxs-lookup"><span data-stu-id="f929a-114">The remainder of the error message contains the Net-Library function called and the function called in the underlying network API by the TDS function.</span></span> <span data-ttu-id="f929a-115">Код ошибки *pfNative* , возвращенный с этими ошибками, является кодом ошибки из базового стека сетевых протоколов.</span><span class="sxs-lookup"><span data-stu-id="f929a-115">The *pfNative* error code returned with these errors is the error code from the underlying network protocol stack.</span></span>  
  
 <span data-ttu-id="f929a-116">[Майкрософт] [Собственный клиент SQL Server][[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]]</span><span class="sxs-lookup"><span data-stu-id="f929a-116">[Microsoft][SQL Server Native Client][[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]]</span></span>  
 <span data-ttu-id="f929a-117">Эти ошибки формируются в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f929a-117">These errors are raised by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f929a-118">Остальная часть сообщения об ошибке — текст сообщения об ошибке из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f929a-118">The remainder of the error message is the text of the error message from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f929a-119">Код *pfNative* , возвращенный с этими ошибками, является номером ошибки из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f929a-119">The *pfNative* code returned with these errors is the error number from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f929a-120">Дополнительные сведения о списке сообщений об ошибках (и их номерах), которые могут быть возвращены [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , см. в столбцах Description и Error системной таблицы **sysmessages** в базе данных **master** в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f929a-120">For more information about a list of error messages (and their numbers) that can be returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see the description and error columns of the **sysmessages** system table in the **master** database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f929a-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="f929a-121">See Also</span></span>  
 [<span data-ttu-id="f929a-122">Обработка ошибок и сообщений</span><span class="sxs-lookup"><span data-stu-id="f929a-122">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
