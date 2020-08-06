---
title: Параметр конфигурации сервера "max full-text crawl range" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- crawls [full-text search]
- max full-text crawl range option
ms.assetid: a49de86b-0891-4dcd-89c0-ead30aab00e0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e1dbd9e44518b6e849a06a76e21fc605172fd2ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728689"
---
# <a name="max-full-text-crawl-range-server-configuration-option"></a><span data-ttu-id="a9dfe-102">Параметр конфигурации сервера max full-text crawl range</span><span class="sxs-lookup"><span data-stu-id="a9dfe-102">max full-text crawl range Server Configuration Option</span></span>
  <span data-ttu-id="a9dfe-103">Параметр **max full-text crawl range** применяется для оптимизации использования ЦП, что позволяет улучшить производительность полнотекстового сканирования.</span><span class="sxs-lookup"><span data-stu-id="a9dfe-103">Use the **max full-text crawl range** option to optimize CPU utilization, which improves crawl performance during a full crawl.</span></span> <span data-ttu-id="a9dfe-104">С помощью этого параметра можно указать количество секций, которые [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] будет использовать при полном сканировании индекса.</span><span class="sxs-lookup"><span data-stu-id="a9dfe-104">Using this option, you can specify the number of partitions that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should use during a full index crawl.</span></span> <span data-ttu-id="a9dfe-105">Например, при неоптимальном использовании нескольких ЦП значение этого параметра можно увеличить до максимума.</span><span class="sxs-lookup"><span data-stu-id="a9dfe-105">For example, if there are many CPUs and their utilization is not optimal, you can increase the maximum value of this option.</span></span> <span data-ttu-id="a9dfe-106">Помимо этого параметра, определение фактического числа используемых секций в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] производится с учетом ряда других факторов, например количества строк в таблице или количества ЦП.</span><span class="sxs-lookup"><span data-stu-id="a9dfe-106">In addition to this option, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses a number of other factors, such as the number of rows in the table and the number of CPUs, to determine the actual number of partitions used.</span></span>  
  
 <span data-ttu-id="a9dfe-107">Значение этого параметра по умолчанию равно 4, минимальное значение равно 1, а максимальное значение равно 256.</span><span class="sxs-lookup"><span data-stu-id="a9dfe-107">The default value of this option is 4; the minimum value is 1, and the maximum value is 256.</span></span> <span data-ttu-id="a9dfe-108">Изменения этого параметра влияют только на последующие процессы сканирования.</span><span class="sxs-lookup"><span data-stu-id="a9dfe-108">Changes made to this option affect only subsequent crawls.</span></span> <span data-ttu-id="a9dfe-109">Изменение этого параметра не влияет на еще незавершенные процессы сканирования.</span><span class="sxs-lookup"><span data-stu-id="a9dfe-109">Crawls in process will not be affected by a change in this option setting.</span></span>  
  
 <span data-ttu-id="a9dfe-110">Параметр **max full-text crawl range** относится к дополнительным параметрам.</span><span class="sxs-lookup"><span data-stu-id="a9dfe-110">The **max full-text crawl range** option is an advanced option.</span></span> <span data-ttu-id="a9dfe-111">При вызове системной хранимой процедуры **sp_configure** параметр **max full-text crawl range** может быть изменен только в том случае, если параметр **show advanced options** установлен в значение 1.</span><span class="sxs-lookup"><span data-stu-id="a9dfe-111">If you are using the **sp_configure** system stored procedure to change the setting, you can change **max full-text crawl range** only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="a9dfe-112">Параметр вступает в силу сразу без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="a9dfe-112">The setting takes effect immediately without a server restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9dfe-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="a9dfe-113">See Also</span></span>  
 <span data-ttu-id="a9dfe-114">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a9dfe-114">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="a9dfe-115">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a9dfe-115">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="a9dfe-116">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a9dfe-116">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
