---
title: Параметры конфигурации сервера "access check cache" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- access check cache option
- access check cache bucket count
- access check cache quota
ms.assetid: 0a992ea8-3ec6-4a4d-97b5-460ae7326247
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: feed895eeb7b11b4c41c51c4c26859a1057d2733
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654500"
---
# <a name="access-check-cache-server-configuration-options"></a><span data-ttu-id="cf1c2-102">Параметры конфигурации сервера «access check cache»</span><span class="sxs-lookup"><span data-stu-id="cf1c2-102">access check cache Server Configuration Options</span></span>
<span data-ttu-id="cf1c2-103">При доступе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]к объектам базы данных проверка доступа кэшируется во внутренней структуре, которую называют **кэшем результатов проверки доступа**.</span><span class="sxs-lookup"><span data-stu-id="cf1c2-103">When database objects are accessed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the access check is cached in an internal structure called the **access check result cache**.</span></span> 
  
<span data-ttu-id="cf1c2-104">Параметр **доступ к счетчику контейнеров проверки кэша** контролирует количество сегментов хэша, используемых для кэша результатов проверки доступа.</span><span class="sxs-lookup"><span data-stu-id="cf1c2-104">The **access check cache bucket count** option controls the number of hash buckets that are used for the access check result cache.</span></span> 

<span data-ttu-id="cf1c2-105">Параметр **доступ к квоте кэша проверки** контролирует количество записей, хранящихся в кэше результатов проверки доступа.</span><span class="sxs-lookup"><span data-stu-id="cf1c2-105">The **access check cache quota** option controls the number of entries that are stored in the access check result cache.</span></span> <span data-ttu-id="cf1c2-106">При достижении максимального количества записей самые старые записи удаляются из кэша результатов проверки доступа.</span><span class="sxs-lookup"><span data-stu-id="cf1c2-106">When the maximum number of entries is reached, the oldest entries are removed from the access check result cache.</span></span>
  
<span data-ttu-id="cf1c2-107">Значение по умолчанию 0 указывает на то, что этими параметрами управляет [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cf1c2-107">The default values of 0 indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is managing these options.</span></span> <span data-ttu-id="cf1c2-108">Из [!INCLUDE[ssKatmai](../../includes/ssKatmai-md.md)] до [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] значения по умолчанию преобразуются в следующие внутренние конфигурации:</span><span class="sxs-lookup"><span data-stu-id="cf1c2-108">From [!INCLUDE[ssKatmai](../../includes/ssKatmai-md.md)] through [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], the default values translate to the following internal configurations:</span></span>
-   <span data-ttu-id="cf1c2-109">Для доступа к числу контейнеров проверки для кэша значение 0 задает значение по умолчанию 256 сегментов для архитектуры x86 и 2 048 для архитектур x64 и IA-64.</span><span class="sxs-lookup"><span data-stu-id="cf1c2-109">For access check cache bucket count, the value 0 sets a default value of 256 buckets for x86 architecture, and 2,048 buckets for x64 and IA-64 architectures.</span></span>
-   <span data-ttu-id="cf1c2-110">Для доступа к квоте проверки кэша значение 0 задает значение по умолчанию 1 024 записей для архитектуры x86 и 28 192 048 контейнеров для архитектур x64 и IA-64.</span><span class="sxs-lookup"><span data-stu-id="cf1c2-110">For access check cache quota, the value 0 sets a default value of 1,024 entries for x86 architecture, and 28,192,048 buckets for x64 and IA-64 architectures.</span></span>

<span data-ttu-id="cf1c2-111">В редких случаях можно добиться увеличения производительности, изменив эти параметры.</span><span class="sxs-lookup"><span data-stu-id="cf1c2-111">In rare circumstances, performance can be improved by changing these options.</span></span> <span data-ttu-id="cf1c2-112">Например, если используется слишком много памяти, возможно, придется уменьшить размер кэша результатов проверки доступа.</span><span class="sxs-lookup"><span data-stu-id="cf1c2-112">For example, you may want to reduce the size of the access check result cache if too much memory is used.</span></span> <span data-ttu-id="cf1c2-113">Также может потребоваться увеличить размер кэша результатов проверки доступа, если при пересчете разрешений возникнет высокая загрузка ЦП.</span><span class="sxs-lookup"><span data-stu-id="cf1c2-113">Or, you may want to increase the size of the access check result cache if you experience high CPU usage when permissions are recalculated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf1c2-114">Майкрософт рекомендует изменять эти параметры только под руководством службы поддержки пользователей Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cf1c2-114">Microsoft recommends only changing these options when directed by Microsoft Customer Support Services.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cf1c2-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="cf1c2-115">See Also</span></span>  
 <span data-ttu-id="cf1c2-116">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cf1c2-116">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="cf1c2-117">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cf1c2-117">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
