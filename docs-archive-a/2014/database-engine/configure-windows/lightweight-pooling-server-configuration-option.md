---
title: Параметр конфигурации сервера "lightweight pooling" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default lightweight pooling
- decreasing overhead
- lightweight pooling option
- system overhead [SQL Server]
- performance [SQL Server], lightweight pooling
- context switching [SQL Server], lightweight pooling option
- excessive context switching [SQL Server]
- reducing overhead
- overhead [SQL Server]
ms.assetid: 2dc11b61-d065-4126-8e00-acf40390f9fb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 549ff7451a31b48459b5a290b94ad406c3768a91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665119"
---
# <a name="lightweight-pooling-server-configuration-option"></a><span data-ttu-id="6e2ae-102">Параметр конфигурации сервера «использование упрощенных пулов»</span><span class="sxs-lookup"><span data-stu-id="6e2ae-102">lightweight pooling Server Configuration Option</span></span>
  <span data-ttu-id="6e2ae-103">Чтобы обеспечить уменьшение системных издержек, связанных с излишним переключением контекста, что иногда случается при симметричной многопроцессорной обработке, воспользуйтесь параметром **lightweight pooling** .</span><span class="sxs-lookup"><span data-stu-id="6e2ae-103">Use the **lightweight pooling** option to provide a means of reducing the system overhead associated with the excessive context switching sometimes seen in symmetric multiprocessing (SMP) environments.</span></span> <span data-ttu-id="6e2ae-104">В случае, когда наблюдается излишнее переключение контекста, использование упрощенных пулов, может обеспечить лучшую производительность за счет встроенного переключения контекстов, помогая таким образом уменьшить количество переходов пользователь/ядро.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-104">When excessive context switching is present, lightweight pooling can provide better throughput by performing the context switching inline, thus helping to reduce user/kernel ring transitions.</span></span>  
  
 <span data-ttu-id="6e2ae-105">Режим волокон предназначен для ситуаций, когда главным фактором, ограничивающим производительность, является переключение контекста рабочих потоков UMS.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-105">Fiber mode is intended for certain situations in which the context switching of the UMS workers are the critical bottleneck in performance.</span></span> <span data-ttu-id="6e2ae-106">Поскольку такая ситуация является нестандартной, использование режима волокон редко увеличивает производительность или масштабируемость типичной системы.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-106">Because this is rare, fiber mode rarely enhances performance or scalability on the typical system.</span></span> <span data-ttu-id="6e2ae-107">Улучшенное переключение контекста в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] также снижает потребность в режиме волокон.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-107">Improved context switching in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] has also reduced the need for fiber mode.</span></span> <span data-ttu-id="6e2ae-108">Использовать планирование в режиме волокон для выполнения распространенных операций не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-108">We do not recommend that you use fiber mode scheduling for routine operation.</span></span> <span data-ttu-id="6e2ae-109">Это может привести к снижению производительности, мешая нормальной работе переключения контекста. Кроме того, некоторые компоненты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые используют локальное хранилище потоков (TLS) или объекты, принадлежащие потокам, такие как мьютексы (тип объекта ядра Win32), не выполняются правильно в режиме волокон.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-109">This is because it can decrease performance by inhibiting the regular benefits of context switching, and because some components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that use Thread Local Storage (TLS) or thread-owned objects, such as mutexes (a type of Win32 kernel object), cannot function correctly in fiber mode.</span></span>  
  
 <span data-ttu-id="6e2ae-110">Значение параметра **использование упрощенных пулов** , равное 1, приводит к переключению [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на расписание режима волокон.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-110">Setting **lightweight pooling** to 1 causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to switch to fiber mode scheduling.</span></span> <span data-ttu-id="6e2ae-111">Значение этого свойства по умолчанию равно 0.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-111">The default value for this option is 0.</span></span>  
  
 <span data-ttu-id="6e2ae-112">Параметр **использование упрощенных пулов** является дополнительным.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-112">The **lightweight pooling** option is an advanced option.</span></span> <span data-ttu-id="6e2ae-113">При вызове системной хранимой процедуры **sp_configure** параметр **lightweight pooling** может быть изменен только в том случае, если параметр **show advanced options** установлен равным 1.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-113">If you are using the **sp_configure** system stored procedure to change the setting, you can change **lightweight pooling** only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="6e2ae-114">Установка параметра вступает в силу после перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-114">The setting takes effect after the server is restarted.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6e2ae-115">Использование упрощенных пулов не поддерживается операционными системами [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2000 и [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows XP.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-115">Lightweight pooling is not supported for [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2000 and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows XP.</span></span> [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] <span data-ttu-id="6e2ae-116">обеспечивает полную поддержку использования упрощенных пулов.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-116">provides full support for lightweight pooling.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6e2ae-117">Выполнение в среде CLR не поддерживается при использовании упрощенных пулов.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-117">Common language runtime (CLR) execution is not supported under lightweight pooling.</span></span> <span data-ttu-id="6e2ae-118">Отключите один из двух параметров: clr enabled или lightweight pooling.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-118">Disable one of two options: "clr enabled" or "lightweight pooling".</span></span> <span data-ttu-id="6e2ae-119">Функции, зависящие от среды CLR и неправильно работающие в режиме волокон, включают иерархический тип данных, репликацию и управление на основе политик.</span><span class="sxs-lookup"><span data-stu-id="6e2ae-119">Features that rely upon CLR and that do not work properly in fiber mode include the hierarchy data type, replication, and Policy-Based Management.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e2ae-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="6e2ae-120">See Also</span></span>  
 <span data-ttu-id="6e2ae-121">[Параметр конфигурации сервера «clr enabled»](clr-enabled-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="6e2ae-121">[clr enabled Server Configuration Option](clr-enabled-server-configuration-option.md) </span></span>  
 <span data-ttu-id="6e2ae-122">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6e2ae-122">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="6e2ae-123">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6e2ae-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="6e2ae-124">Параметр конфигурации сервера «clr enabled»</span><span class="sxs-lookup"><span data-stu-id="6e2ae-124">clr enabled Server Configuration Option</span></span>](clr-enabled-server-configuration-option.md)  
  
  
