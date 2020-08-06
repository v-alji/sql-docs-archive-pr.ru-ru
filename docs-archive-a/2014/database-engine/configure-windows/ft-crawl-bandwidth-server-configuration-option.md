---
title: Параметр конфигурации сервера "ft crawl bandwidth" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- large memory buffers
- memory [SQL Server], buffers
- ft crawl bandwidth option
ms.assetid: e5864ad9-92f5-43b5-95de-46d68ded8694
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 33821ff1fdbc4248c71906d8307a8164a7f64d24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750136"
---
# <a name="ft-crawl-bandwidth-server-configuration-option"></a><span data-ttu-id="ef4da-102">Параметр конфигурации сервера «ft crawl bandwidth»</span><span class="sxs-lookup"><span data-stu-id="ef4da-102">ft crawl bandwidth Server Configuration Option</span></span>
  <span data-ttu-id="ef4da-103">Параметр **ft crawl bandwidth** используют для того, чтобы указать размер, до которого может расти пул больших буферов памяти.</span><span class="sxs-lookup"><span data-stu-id="ef4da-103">Use the **ft crawl bandwidth** option to specify the size to which the pool of large memory buffers can grow.</span></span> <span data-ttu-id="ef4da-104">Большие буферы памяти имеют размер 4 МБ.</span><span class="sxs-lookup"><span data-stu-id="ef4da-104">Large memory buffers are 4 megabytes (MB) in size.</span></span> <span data-ttu-id="ef4da-105">Значение параметра **max** указывает максимальное количество буферов, которое должен поддерживать диспетчер полнотекстовой памяти в большом буферном пуле.</span><span class="sxs-lookup"><span data-stu-id="ef4da-105">The **max** parameter value specifies the maximum number of buffers that the full-text memory manager should maintain in a large buffer pool.</span></span> <span data-ttu-id="ef4da-106">Если значение **max** нулевое, верхний предел числа буферных пулов отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ef4da-106">If the **max** value is zero, then there is no upper limit to the number of buffers that can be in a large buffer pool.</span></span>  
  
 <span data-ttu-id="ef4da-107">Параметр **min** указывает минимальное количество буферов памяти, которое нужно поддерживать в больших пулах буферов памяти.</span><span class="sxs-lookup"><span data-stu-id="ef4da-107">The **min** parameter specifies the minimum number of memory buffers that must be maintained in the pool of large memory buffers.</span></span> <span data-ttu-id="ef4da-108">По запросу диспетчера памяти [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] все дополнительные буферные пулы будут освобождены, однако это минимальное количество буферов сохранится.</span><span class="sxs-lookup"><span data-stu-id="ef4da-108">Upon request from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory manager, all extra buffer pools will be released but this minimum number of buffers will be maintained.</span></span> <span data-ttu-id="ef4da-109">Однако если указанное значение **min** равно нулю, то будут освобождены все буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="ef4da-109">If, however, the **min** value specified is zero, then all memory buffers are released.</span></span>  
  
 <span data-ttu-id="ef4da-110">При некоторых обстоятельствах число выделенных в данный момент буферов может быть меньше значения, указанного в параметре **min** .</span><span class="sxs-lookup"><span data-stu-id="ef4da-110">Under certain circumstances, the number of buffers currently allocated is less than the value specified by the **min** parameter.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ef4da-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="ef4da-111">See Also</span></span>  
 <span data-ttu-id="ef4da-112">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ef4da-112">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="ef4da-113">[Параметр конфигурации сервера "ft notify bandwidth"](ft-notify-bandwidth-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="ef4da-113">[ft notify bandwidth Server Configuration Option](ft-notify-bandwidth-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="ef4da-114">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ef4da-114">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
