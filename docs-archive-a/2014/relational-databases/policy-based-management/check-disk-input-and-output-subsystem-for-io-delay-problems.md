---
title: Проверка на наличие проблем с задержками ввода-вывода в подсистеме дискового ввода-вывода | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 23863340-d8e0-48d6-928b-462745885d37
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a0ae8dc0d1a93f8150ccbeab73ed8aa918d1f495
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731525"
---
# <a name="check-disk-input-and-output-subsystem-for-io-delay-problems"></a><span data-ttu-id="c836a-102">Проверка на наличие проблем задержки ввода-вывода в подсистеме дискового ввода-вывода</span><span class="sxs-lookup"><span data-stu-id="c836a-102">Check Disk Input and Output Subsystem for IO Delay Problems</span></span>
  <span data-ttu-id="c836a-103">Это правило проверяет журнал событий на наличие сообщения об ошибке 833.</span><span class="sxs-lookup"><span data-stu-id="c836a-103">This rule checks the event log for error message 833.</span></span> <span data-ttu-id="c836a-104">Это сообщение указывает, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] издал запрос чтения или записи на диск, и выполнение запроса заняло более 15 секунд.</span><span class="sxs-lookup"><span data-stu-id="c836a-104">This message indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has issued a read or write request from disk, and that the request has taken longer than 15 seconds to return.</span></span> <span data-ttu-id="c836a-105">Эта ошибка выдается [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и указывает на проблему в подсистеме дискового ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="c836a-105">This error is reported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and indicates a problem with the disk I/O subsystem.</span></span> <span data-ttu-id="c836a-106">Такие долгие задержки могут существенно снизить производительность среды [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c836a-106">Delays this long can severely damage the performance of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environment.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="c836a-107">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="c836a-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="c836a-108">Для устранения этой ошибки найдите в журнале системных событий сообщения об ошибках, связанных с оборудованием.</span><span class="sxs-lookup"><span data-stu-id="c836a-108">Troubleshoot this error by examining the system event log for hardware-related error messages.</span></span> <span data-ttu-id="c836a-109">Также изучите журналы оборудования, если они доступны.</span><span class="sxs-lookup"><span data-stu-id="c836a-109">Also, examine hardware-specific logs if they are available.</span></span>  
  
 <span data-ttu-id="c836a-110">При помощи системного монитора проверьте следующие счетчики.</span><span class="sxs-lookup"><span data-stu-id="c836a-110">Use Performance Monitor to examine the following counters:</span></span>  
  
-   <span data-ttu-id="c836a-111">Среднее время обращения к диску (сек)</span><span class="sxs-lookup"><span data-stu-id="c836a-111">Average Disk Sec/Transfer</span></span>  
  
-   <span data-ttu-id="c836a-112">Средняя длина очереди диска</span><span class="sxs-lookup"><span data-stu-id="c836a-112">Average Disk Queue Length</span></span>  
  
-   <span data-ttu-id="c836a-113">Текущая длина очереди диска</span><span class="sxs-lookup"><span data-stu-id="c836a-113">Current Disk Queue Length</span></span>  
  
 <span data-ttu-id="c836a-114">Например, значение Average Disk Sec/Transfer на компьютере, где выполняется [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , обычно не превышает 15 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="c836a-114">For example, the Average Disk Sec/Transfer time on a computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is typically less than 15 milliseconds.</span></span> <span data-ttu-id="c836a-115">Если значение счетчика Average Disk Sec/Transfer увеличивается, это указывает на то, что подсистема ввода-вывода диска не справляется с запросами на операции ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="c836a-115">If the Average Disk Sec/Transfer value increases, this indicates that the disk I/O subsystem is not optimally keeping up with the I/O demand.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="c836a-116">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="c836a-116">For More Information</span></span>  
 [<span data-ttu-id="c836a-117">MSSQLSERVER_833</span><span class="sxs-lookup"><span data-stu-id="c836a-117">MSSQLSERVER_833</span></span>](../errors-events/mssqlserver-833-database-engine-error.md)  
  
 [<span data-ttu-id="c836a-118">Статья 897284 базы знаний Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c836a-118">Microsoft Knowledge Base article 897284</span></span>](https://go.microsoft.com/fwlink/?linkid=117743)  
  
 <span data-ttu-id="c836a-119">[Основные операции ввода-вывода в SQL Server, раздел 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="c836a-119">[SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span></span>  
  
  
