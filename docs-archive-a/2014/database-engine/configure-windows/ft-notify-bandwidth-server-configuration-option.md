---
title: Параметр конфигурации сервера "ft notify bandwidth" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- ft notify bandwidth opion
- small memory buffers
- memory [SQL Server], buffers
ms.assetid: 9ca284c5-f3e0-4a67-a132-fff376ff0ffe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dc5839f699d55edf86c5e3e3f0eb001089a0a5dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738756"
---
# <a name="ft-notify-bandwidth-server-configuration-option"></a><span data-ttu-id="29e7c-102">Параметр конфигурации сервера «ft notify bandwidth»</span><span class="sxs-lookup"><span data-stu-id="29e7c-102">ft notify bandwidth Server Configuration Option</span></span>
  <span data-ttu-id="29e7c-103">Используйте параметр **ft notify bandwidth** для указания предельного размера роста пула малых буферов памяти.</span><span class="sxs-lookup"><span data-stu-id="29e7c-103">Use the **ft notify bandwidth** option to specify the size to which the pool of small memory buffers can grow.</span></span> <span data-ttu-id="29e7c-104">Малые буферы памяти занимают 64 килобайта (KБ).</span><span class="sxs-lookup"><span data-stu-id="29e7c-104">Small memory buffers are 64 kilobytes (KB) in size.</span></span> <span data-ttu-id="29e7c-105">Значение параметра *max* указывает максимальное количество буферов для управления диспетчером полнотекстовой памяти в малом буферном пуле.</span><span class="sxs-lookup"><span data-stu-id="29e7c-105">The *max* parameter value specifies the maximum number of buffers that the full-text memory manager should maintain in a small buffer pool.</span></span> <span data-ttu-id="29e7c-106">Если `max` значение равно нулю, верхний предел числа буферов, которые могут находиться в небольшом буферном пуле, отсутствует.</span><span class="sxs-lookup"><span data-stu-id="29e7c-106">If the `max` value is zero, then there is no upper limit to the number of buffers that can be in a small buffer pool.</span></span>  
  
 <span data-ttu-id="29e7c-107">Параметр **min** указывает минимальное количество пулов буферов для малого пула буферов памяти.</span><span class="sxs-lookup"><span data-stu-id="29e7c-107">The **min** parameter specifies the minimum number of memory buffers that must be maintained in the pool of small memory buffers.</span></span> <span data-ttu-id="29e7c-108">По запросу диспетчера памяти [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] все дополнительные буферные пулы будут освобождены, однако это минимальное количество буферов сохранится.</span><span class="sxs-lookup"><span data-stu-id="29e7c-108">Upon request from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory manager, all extra buffer pools will be released but this minimum number of buffers will be maintained.</span></span> <span data-ttu-id="29e7c-109">Однако если указанное значение **min** равно нулю, то будут освобождены все буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="29e7c-109">If, however, the **min** value specified is zero, then all memory buffers are released.</span></span>  
  
 <span data-ttu-id="29e7c-110">В определенных обстоятельствах количество буферов, распределенных в настоящий момент, может быть меньше значения, указанного параметром **min** .</span><span class="sxs-lookup"><span data-stu-id="29e7c-110">Under certain circumstances the number of buffers currently allocated is less than the value specified by the **min** parameter.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="29e7c-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="29e7c-111">See Also</span></span>  
 <span data-ttu-id="29e7c-112">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="29e7c-112">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="29e7c-113">[Параметр конфигурации сервера "ft crawl bandwidth"](ft-crawl-bandwidth-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="29e7c-113">[ft crawl bandwidth Server Configuration Option](ft-crawl-bandwidth-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="29e7c-114">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="29e7c-114">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
