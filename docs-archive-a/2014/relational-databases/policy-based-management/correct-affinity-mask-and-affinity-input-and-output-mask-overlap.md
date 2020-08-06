---
title: Правильное перекрытие маски схожести и привязки входных данных сходства | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 1a0da6df-57ff-4f3f-aae9-2fbc4897508c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 486b4441a20db7630082344fb1f277bba053f3ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752120"
---
# <a name="correct-affinity-mask-and-affinity-input-output-mask-overlap"></a><span data-ttu-id="b1ed4-102">Правильное перекрытие маски сходства и привязки входных данных сходства</span><span class="sxs-lookup"><span data-stu-id="b1ed4-102">Correct Affinity Mask and Affinity Input Output Mask Overlap</span></span>
  <span data-ttu-id="b1ed4-103">Это правило проверяет, имеет ли экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] один или несколько процессоров, назначенных для использования как с параметром «affinity mask», так и с параметром «affinity I/O mask».</span><span class="sxs-lookup"><span data-stu-id="b1ed4-103">This rule checks whether the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has one or more processors that are assigned to be used with both the affinity mask and the affinity I/O mask options.</span></span> <span data-ttu-id="b1ed4-104">На многопроцессорном компьютере параметры «affinity mask» и «affinity I/O mask» используются для определения процессоров, работающих с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1ed4-104">On a computer that has more than one processor, the affinity mask and the affinity I/O mask options are used to designate which CPUs are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b1ed4-105">Если для ЦП включены оба параметра, то это может привести к снижению производительности, поскольку вызовет перегрузку процессора.</span><span class="sxs-lookup"><span data-stu-id="b1ed4-105">Enabling a CPU with both the affinity mask and the affinity I/O mask can slow performance by forcing the processor to be overused.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="b1ed4-106">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="b1ed4-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="b1ed4-107">Необходимо указывать оба параметра, «affinity mask» и «affinity I/O mask», но включать каждый ЦП только для одного параметра.</span><span class="sxs-lookup"><span data-stu-id="b1ed4-107">When you specify either the affinity mask or the affinity I/O mask options, you should specify both, but only enable each CPU no more than once.</span></span>  
  
 <span data-ttu-id="b1ed4-108">Не допускайте, чтобы один и тот же ЦП оказывался задействованным для обоих параметров.</span><span class="sxs-lookup"><span data-stu-id="b1ed4-108">Do not enable the same CPU in both the affinity mask option and the affinity I/O mask option.</span></span> <span data-ttu-id="b1ed4-109">Биты, относящиеся к каждому ЦП, должны находиться в одном из следующих состояний:</span><span class="sxs-lookup"><span data-stu-id="b1ed4-109">The bits that correspond to each CPU should be in one of the following states:</span></span>  
  
-   <span data-ttu-id="b1ed4-110">значение 0 для обоих параметров, «affinity mask» и «affinity I/O mask»;</span><span class="sxs-lookup"><span data-stu-id="b1ed4-110">0 in both the affinity mask option and the affinity I/O mask option</span></span>  
  
-   <span data-ttu-id="b1ed4-111">значение 0 для параметра «affinity mask» и 1 для параметра «affinity I/O mask»;</span><span class="sxs-lookup"><span data-stu-id="b1ed4-111">0 in the affinity mask option and 1 in the affinity I/O mask option</span></span>  
  
-   <span data-ttu-id="b1ed4-112">значение 1 для параметра «affinity mask» и 0 для параметра «affinity I/O mask».</span><span class="sxs-lookup"><span data-stu-id="b1ed4-112">1 in the affinity mask option and 0 in the affinity I/O mask option</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="b1ed4-113">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="b1ed4-113">For More Information</span></span>  
 [<span data-ttu-id="b1ed4-114">Параметр конфигурации сервера «affinity mask»</span><span class="sxs-lookup"><span data-stu-id="b1ed4-114">affinity mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity-mask-server-configuration-option.md)  
  
 [<span data-ttu-id="b1ed4-115">Параметр конфигурации сервера "affinity Input-Output mask"</span><span class="sxs-lookup"><span data-stu-id="b1ed4-115">affinity Input-Output mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity-input-output-mask-server-configuration-option.md)  
  
 [<span data-ttu-id="b1ed4-116">Параметр конфигурации сервера «affinity64 mask»</span><span class="sxs-lookup"><span data-stu-id="b1ed4-116">affinity64 mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity64-mask-server-configuration-option.md)  
  
 [<span data-ttu-id="b1ed4-117">Параметр конфигурации сервера "affinity64 Input-Output mask"</span><span class="sxs-lookup"><span data-stu-id="b1ed4-117">affinity64 Input-Output mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity64-input-output-mask-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="b1ed4-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="b1ed4-118">See Also</span></span>  
 [<span data-ttu-id="b1ed4-119">Наблюдение с помощью управления на основе политик и принудительное применение рекомендаций с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="b1ed4-119">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
