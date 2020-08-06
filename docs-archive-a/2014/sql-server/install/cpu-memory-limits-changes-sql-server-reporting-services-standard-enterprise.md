---
title: Изменения в ограничениях ресурсов ЦП и памяти для SQL Server Reporting Services Standard и Enterprise | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: dd553715-2b95-4119-8f58-d01de388d9ab
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: bd889344f5b0bc72320ff8467ebd6ecc654872f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657492"
---
# <a name="changes-to-cpu-and-memory-limits-for-sql-server-reporting-services-standard-and-enterprise"></a><span data-ttu-id="0a461-102">Изменения ограничений ЦП и памяти для выпусков служб SQL Server Reporting Services Standard Edition и Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="0a461-102">Changes to CPU and memory limits for SQL Server Reporting Services Standard and Enterprise</span></span>
  <span data-ttu-id="0a461-103">Начиная с версии [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], выпуски служб Reporting Services Standard и Enterprise поддерживают до 64 ГБ системной памяти.</span><span class="sxs-lookup"><span data-stu-id="0a461-103">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Reporting Services Standard and Enterprise supports a maximum of 64 gigabytes of system memory.</span></span>  
  
## <a name="component"></a><span data-ttu-id="0a461-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="0a461-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
### <a name="description"></a><span data-ttu-id="0a461-105">Описание</span><span class="sxs-lookup"><span data-stu-id="0a461-105">Description</span></span>  
 <span data-ttu-id="0a461-106">Начиная с версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], выпуски служб Reporting Services Standard и Enterprise поддерживают до 64 ГБ системной памяти.</span><span class="sxs-lookup"><span data-stu-id="0a461-106">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Reporting Services Standard and Enterprise supports a maximum of 64 gigabytes of system memory.</span></span> <span data-ttu-id="0a461-107">Может потребоваться повторно настроить параметры системы, чтобы поддерживать обновленные ограничения.</span><span class="sxs-lookup"><span data-stu-id="0a461-107">You may need to reconfigure your current system settings to align with the new limits.</span></span>  
  
 <span data-ttu-id="0a461-108">Дополнительные сведения об ограничениях ЦП и памяти для других выпусков [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в разделе [ограничения вычислительной мощности по выпуску SQL Server](../compute-capacity-limits-by-edition-of-sql-server.md)и [память, поддерживаемая выпусками SQL Server](https://go.microsoft.com/fwlink/?LinkId=212633).</span><span class="sxs-lookup"><span data-stu-id="0a461-108">For more information about CPU and memory limits for other editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Compute Capacity Limits by Edition of SQL Server](../compute-capacity-limits-by-edition-of-sql-server.md), and [Memory Supported by the Editions of SQL Server](https://go.microsoft.com/fwlink/?LinkId=212633).</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="0a461-109">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="0a461-109">Corrective Action</span></span>  
 <span data-ttu-id="0a461-110">Может потребоваться повторно настроить параметры системы, чтобы поддерживать обновленные ограничения.</span><span class="sxs-lookup"><span data-stu-id="0a461-110">You may need to reconfigure your current system settings to align with the new CPU and memory limits.</span></span> <span data-ttu-id="0a461-111">Дополнительные сведения см. в статье [Параметры конфигурации сервера](../../database-engine/configure-windows/server-memory-server-configuration-options.md) [ALTER Server Configuration &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-server-configuration-transact-sql)и Server Memory.</span><span class="sxs-lookup"><span data-stu-id="0a461-111">For more information, see [ALTER SERVER CONFIGURATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-server-configuration-transact-sql), and [Server Memory Server Configuration Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a461-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="0a461-112">See Also</span></span>  
 <span data-ttu-id="0a461-113">[Функции, поддерживаемые различными выпусками SQL Server 2014](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="0a461-113">[Features Supported by the Editions of SQL Server 2014](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 [<span data-ttu-id="0a461-114">Обратная совместимость</span><span class="sxs-lookup"><span data-stu-id="0a461-114">Backward Compatibility</span></span>](../../../2014/getting-started/backward-compatibility.md)  
  
  
