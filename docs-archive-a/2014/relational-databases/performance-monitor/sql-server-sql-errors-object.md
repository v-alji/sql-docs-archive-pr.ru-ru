---
title: SQL Server, объект SQL Errors | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQL Errors object
- SQLServer:SQL Errors
ms.assetid: 6e5273ca-29cb-4618-88a2-70b9b8d6cf76
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 11bfb728e79b4fc175fb8a2fe16c9f1662a205ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729397"
---
# <a name="sql-server-sql-errors-object"></a><span data-ttu-id="78092-102">SQL Server, объект SQL Errors</span><span class="sxs-lookup"><span data-stu-id="78092-102">SQL Server, SQL Errors Object</span></span>
  <span data-ttu-id="78092-103">Объект **SQLServer: ошибки SQL** в Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] обеспечивает счетчики для контроля работы **SQL Errors**.</span><span class="sxs-lookup"><span data-stu-id="78092-103">The **SQLServer:SQL Errors** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor **SQL Errors**.</span></span>  
  
 <span data-ttu-id="78092-104">В этой таблице описаны счетчики [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Ошибки SQL**.</span><span class="sxs-lookup"><span data-stu-id="78092-104">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **SQL Errors** counters.</span></span>  
  
|<span data-ttu-id="78092-105">Счетчики SQL Server SQL Errors</span><span class="sxs-lookup"><span data-stu-id="78092-105">SQL Server SQL Errors counters</span></span>|<span data-ttu-id="78092-106">Описание</span><span class="sxs-lookup"><span data-stu-id="78092-106">Description</span></span>|  
|------------------------------------|-----------------|  
|<span data-ttu-id="78092-107">**Ошибок/с**</span><span class="sxs-lookup"><span data-stu-id="78092-107">**Errors/sec**</span></span>|<span data-ttu-id="78092-108">Количество ошибок в секунду.</span><span class="sxs-lookup"><span data-stu-id="78092-108">Number of errors/sec.</span></span>|  
  
 <span data-ttu-id="78092-109">Каждый из счетчиков объекта содержит следующие экземпляры.</span><span class="sxs-lookup"><span data-stu-id="78092-109">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="78092-110">Item</span><span class="sxs-lookup"><span data-stu-id="78092-110">Item</span></span>|<span data-ttu-id="78092-111">Определение</span><span class="sxs-lookup"><span data-stu-id="78092-111">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="78092-112">**_Total**</span><span class="sxs-lookup"><span data-stu-id="78092-112">**_Total**</span></span>|<span data-ttu-id="78092-113">Сведения обо всех ошибках.</span><span class="sxs-lookup"><span data-stu-id="78092-113">Information for all errors.</span></span>|  
|<span data-ttu-id="78092-114">**Ошибки DB в режиме «вне сети»**</span><span class="sxs-lookup"><span data-stu-id="78092-114">**DB Offline Errors**</span></span>|<span data-ttu-id="78092-115">Отслеживает серьезные ошибки, которые заставляют [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] переключать текущую базу данных в режим «вне сети».</span><span class="sxs-lookup"><span data-stu-id="78092-115">Tracks severe errors that cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to take the current database offline.</span></span>|  
|<span data-ttu-id="78092-116">**Информационные ошибки**</span><span class="sxs-lookup"><span data-stu-id="78092-116">**Info Errors**</span></span>|<span data-ttu-id="78092-117">Сведения, связанные с сообщениями об ошибках, которые предоставляют данные пользователям, но не вызывают ошибок.</span><span class="sxs-lookup"><span data-stu-id="78092-117">Information related to error messages that provide information to users but do not cause errors.</span></span>|  
|<span data-ttu-id="78092-118">**Ошибки разрыва соединения**</span><span class="sxs-lookup"><span data-stu-id="78092-118">**Kill Connection Errors**</span></span>|<span data-ttu-id="78092-119">Отслеживает ошибки, которые заставляют [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] разорвать текущее соединение.</span><span class="sxs-lookup"><span data-stu-id="78092-119">Tracks severe errors that cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to kill the current connection.</span></span>|  
|<span data-ttu-id="78092-120">**Пользовательские ошибки**</span><span class="sxs-lookup"><span data-stu-id="78092-120">**User Errors**</span></span>|<span data-ttu-id="78092-121">Сведения об ошибках пользователя.</span><span class="sxs-lookup"><span data-stu-id="78092-121">Information about user errors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78092-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="78092-122">See Also</span></span>  
 [<span data-ttu-id="78092-123">Наблюдение за использованием ресурсов (системный монитор)</span><span class="sxs-lookup"><span data-stu-id="78092-123">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
