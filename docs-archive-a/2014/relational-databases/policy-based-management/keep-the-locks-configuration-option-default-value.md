---
title: Сохранение предусмотренного по умолчанию значения для параметра конфигурации блокировок | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: f214f05b-5f0b-4786-b2ad-b8b4b6e58d72
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a1d1dcf82d9cd0ef8ef2c15cb68ef78b53a8a54a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655683"
---
# <a name="keep-the-locks-configuration-option-default-value"></a><span data-ttu-id="a4414-102">Сохранение предусмотренного по умолчанию значения параметра конфигурации блокировок</span><span class="sxs-lookup"><span data-stu-id="a4414-102">Keep the Locks Configuration Option Default Value</span></span>
  <span data-ttu-id="a4414-103">Это правило проверяет значение параметра конфигурации «locks».</span><span class="sxs-lookup"><span data-stu-id="a4414-103">This rule checks the value of the locks configuration option.</span></span> <span data-ttu-id="a4414-104">Параметр определяет максимальное количество доступных блокировок.</span><span class="sxs-lookup"><span data-stu-id="a4414-104">This option determines the maximum number of available locks.</span></span> <span data-ttu-id="a4414-105">Тем самым ограничивается объем памяти, который компонент [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] использует для блокировок.</span><span class="sxs-lookup"><span data-stu-id="a4414-105">This limits how much memory the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses for locks.</span></span> <span data-ttu-id="a4414-106">Значение по умолчанию 0 позволяет компоненту [!INCLUDE[ssDE](../../includes/ssde-md.md)] выделять и освобождать структуры блокировок динамически в соответствии с изменяющимися требования к системе.</span><span class="sxs-lookup"><span data-stu-id="a4414-106">The default setting of 0 enables the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to allocate and deallocate lock structures dynamically based on changing system requirements.</span></span>  
  
 <span data-ttu-id="a4414-107">Если значение параметра отлично от нуля, то в случае превышения указанного числа блокировок выполнение пакетных заданий будет остановлено и появится сообщение об ошибке, извещающее о недостатке памяти для блокировок.</span><span class="sxs-lookup"><span data-stu-id="a4414-107">If locks is nonzero, batch jobs will stop, and an "out of locks" error message will be generated, if the value specified is exceeded.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="a4414-108">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="a4414-108">Best Practices Recommendations</span></span>  
 <span data-ttu-id="a4414-109">Для присвоения параметру конфигурации «locks» значения по умолчанию используется системная хранимая процедура sp_configure в следующей инструкции:</span><span class="sxs-lookup"><span data-stu-id="a4414-109">Use the sp_configure system stored procedure to change the value of locks to its default setting by using the following statement:</span></span>  
  
```  
EXEC sp_configure 'locks', 0;  
```  
  
## <a name="for-more-information"></a><span data-ttu-id="a4414-110">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="a4414-110">For More Information</span></span>  
 [<span data-ttu-id="a4414-111">Настройка параметра конфигурации сервера locks</span><span class="sxs-lookup"><span data-stu-id="a4414-111">Configure the locks Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-locks-server-configuration-option.md)  
  
 [<span data-ttu-id="a4414-112">sys.dm_tran_locks (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a4414-112">sys.dm_tran_locks &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql)  
  
 [<span data-ttu-id="a4414-113">sys.dm_os_wait_stats (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a4414-113">sys.dm_os_wait_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-wait-stats-transact-sql)  
  
 [<span data-ttu-id="a4414-114">Статья 271509 базы знаний Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a4414-114">Microsoft Knowledge Base article 271509</span></span>](https://go.microsoft.com/fwlink/?linkid=117788)  
  
## <a name="see-also"></a><span data-ttu-id="a4414-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="a4414-115">See Also</span></span>  
 [<span data-ttu-id="a4414-116">Наблюдение с помощью управления на основе политик и принудительное применение рекомендаций с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="a4414-116">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
