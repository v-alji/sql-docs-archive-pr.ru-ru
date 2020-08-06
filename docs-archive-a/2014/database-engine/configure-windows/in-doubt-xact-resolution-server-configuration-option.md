---
title: Параметр конфигурации сервера "in-doubt xact resolution" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- distributed transactions [SQL Server], unresolved transactions
- unresolved transactions
- in-doubt xact resolution option
ms.assetid: 3426fd32-cad2-4f2f-8ca9-e0296cc12703
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6b8db57ef2a4ee85d65e8c25de28ff7ada7994e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729825"
---
# <a name="in-doubt-xact-resolution-server-configuration-option"></a><span data-ttu-id="a973a-102">Параметр конфигурации сервера «in-doubt xact resolution»</span><span class="sxs-lookup"><span data-stu-id="a973a-102">in-doubt xact resolution Server Configuration Option</span></span>
  <span data-ttu-id="a973a-103">Результат по умолчанию для транзакций, которые не удалось разрешить координатору распределенных транзакций **(MS DTC), задается с помощью параметра** in-doubt xact resolution [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a973a-103">Use the **in-doubt xact resolution** option to control the default outcome of transactions that the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) is unable to resolve.</span></span> <span data-ttu-id="a973a-104">Невозможность разрешить транзакции может быть связана с простоем MS DTC или с неизвестным результатом транзакции на момент восстановления.</span><span class="sxs-lookup"><span data-stu-id="a973a-104">Inability to resolve transactions may be related to the MS DTC down time or an unknown transaction outcome at the time of recovery.</span></span>  
  
 <span data-ttu-id="a973a-105">В следующей таблице перечислены возможные значения результатов для разрешения сомнительных транзакций.</span><span class="sxs-lookup"><span data-stu-id="a973a-105">The following table lists the possible outcome values for resolving an in-doubt transaction.</span></span>  
  
|<span data-ttu-id="a973a-106">Значение результата</span><span class="sxs-lookup"><span data-stu-id="a973a-106">Outcome value</span></span>|<span data-ttu-id="a973a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a973a-107">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="a973a-108">0</span><span class="sxs-lookup"><span data-stu-id="a973a-108">0</span></span>|<span data-ttu-id="a973a-109">Без предположения.</span><span class="sxs-lookup"><span data-stu-id="a973a-109">No presumption.</span></span> <span data-ttu-id="a973a-110">Восстановление завершится неуспешно, если MS DTC не сможет разрешить хотя бы одну сомнительную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="a973a-110">Recovery fails if MS DTC cannot resolve any in-doubt transactions.</span></span>|  
|<span data-ttu-id="a973a-111">1</span><span class="sxs-lookup"><span data-stu-id="a973a-111">1</span></span>|<span data-ttu-id="a973a-112">Предположить фиксацию.</span><span class="sxs-lookup"><span data-stu-id="a973a-112">Presume commit.</span></span> <span data-ttu-id="a973a-113">Все сомнительные транзакции MS DTC считаются зафиксированными.</span><span class="sxs-lookup"><span data-stu-id="a973a-113">Any MS DTC in-doubt transactions are presumed to have committed.</span></span>|  
|<span data-ttu-id="a973a-114">2</span><span class="sxs-lookup"><span data-stu-id="a973a-114">2</span></span>|<span data-ttu-id="a973a-115">Предположить прерывание.</span><span class="sxs-lookup"><span data-stu-id="a973a-115">Presume abort.</span></span> <span data-ttu-id="a973a-116">Все сомнительные транзакции MS DTC считаются прерванными.</span><span class="sxs-lookup"><span data-stu-id="a973a-116">Any MS DTC in-doubt transactions are presumed to have aborted.</span></span>|  
  
 <span data-ttu-id="a973a-117">Чтобы свести к минимуму вероятность увеличения времени простоя, администратор может выбрать с помощью этого параметра либо предположительную фиксацию, либо предположительное прерывание, как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="a973a-117">To minimize the possibility of extended down time, an administrator might choose to configure this option either to presume commit or presume abort, as shown in the following example.</span></span>  
  
```  
sp_configure 'show advanced options', 1  
GO  
RECONFIGURE  
GO  
sp_configure 'in-doubt xact resolution', 2 -- presume abort  
GO  
RECONFIGURE  
GO  
sp_configure 'show advanced options', 0  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="a973a-118">Кроме того, администратор может не менять значение по умолчанию (без предположения) и допустить сбой восстановления, то есть, как показано в приведенном ниже примере, он будет узнавать о сбое DTC.</span><span class="sxs-lookup"><span data-stu-id="a973a-118">Alternatively, the administrator might want to leave the default (no presumption) and allow recovery to fail in order to be made aware of a DTC failure, as shown in the following example.</span></span>  
  
```  
sp_configure 'show advanced options', 1  
GO  
RECONFIGURE  
GO  
sp_configure 'in-doubt xact resolution', 1 -- presume commit  
GO  
reconfigure  
GO  
ALTER DATABASE pubs SET ONLINE -- run recovery again  
GO  
sp_configure 'in-doubt xact resolution', 0 -- back to no assumptions  
GO  
sp_configure 'show advanced options', 0  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="a973a-119">Параметр **in-doubt xact resolution** является дополнительным.</span><span class="sxs-lookup"><span data-stu-id="a973a-119">The **in-doubt xact resolution** option is an advanced option.</span></span> <span data-ttu-id="a973a-120">Если для изменения настроек используется системная хранимая процедура **sp_configure** , то изменить значение параметра **in-doubt xact resolution** можно только при условии, что параметр **show advanced options** равен 1.</span><span class="sxs-lookup"><span data-stu-id="a973a-120">If you are using the **sp_configure** system stored procedure to change the setting, you can change **in-doubt xact resolution** only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="a973a-121">Параметр вступает в силу сразу без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="a973a-121">The setting takes effect immediately without a server restart.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a973a-122">Последовательная настройка этого параметра во всех экземплярах [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые участвуют в распределенных транзакциях, поможет избежать несогласованности данных.</span><span class="sxs-lookup"><span data-stu-id="a973a-122">Consistent configuration of this option across all [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances involved in any distributed transactions will help avoid data inconsistencies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a973a-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="a973a-123">See Also</span></span>  
 <span data-ttu-id="a973a-124">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a973a-124">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="a973a-125">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a973a-125">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="a973a-126">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a973a-126">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
