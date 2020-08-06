---
title: Размер сетевого пакета не должен превышать 8060 байт | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 86db5da1-afe4-4fbb-8bf8-33cedc7e4361
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 01b500cbe65107767d73bc2901b6d5e028b94ee9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657714"
---
# <a name="network-packet-size-should-not-exceed-8060-bytes"></a><span data-ttu-id="0466d-102">Размер сетевого пакета не должен превышать 8060 байт</span><span class="sxs-lookup"><span data-stu-id="0466d-102">Network Packet Size Should Not Exceed 8060 Bytes</span></span>
  <span data-ttu-id="0466d-103">Если значение, заданное для параметра хранимой процедуры sp_configure 'network packet size', или размер пакета любого вошедшего в систему пользователя превышает 8 060 байт, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняет другие операции выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="0466d-103">If the value specified for sp_configure 'network packet size' or if the network packet size of any logged-in user is more than 8060 bytes, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs different memory allocation operations.</span></span> <span data-ttu-id="0466d-104">Это может привести к увеличению виртуального адресного пространства процессов, которое не зарезервировано для буферного пула.</span><span class="sxs-lookup"><span data-stu-id="0466d-104">This can cause an increase in the process virtual address space that is not reserved for the buffer pool.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="0466d-105">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="0466d-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="0466d-106">Размер сетевого пакета не должен превышать 8 060 байт.</span><span class="sxs-lookup"><span data-stu-id="0466d-106">The network packet size should not exceed 8060 bytes.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="0466d-107">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="0466d-107">For More Information</span></span>  
 [<span data-ttu-id="0466d-108">Статья 903002 базы знаний Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0466d-108">Microsoft Knowledge Base article 903002</span></span>](https://go.microsoft.com/fwlink/?linkid=117749)  
  
## <a name="see-also"></a><span data-ttu-id="0466d-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="0466d-109">See Also</span></span>  
 [<span data-ttu-id="0466d-110">Наблюдение с помощью управления на основе политик и принудительное применение рекомендаций с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="0466d-110">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
