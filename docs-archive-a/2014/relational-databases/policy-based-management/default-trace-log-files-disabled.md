---
title: Отключение предусмотренных по умолчанию файлов журнала трассировки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: c27761e6-75ed-4ee4-a236-0cbc42e500a1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0fed8fb006427b4dda9d99c57cbabca8538efcad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657719"
---
# <a name="default-trace-log-files-disabled"></a><span data-ttu-id="24821-102">Отключение предусмотренных по умолчанию файлов журнала трассировки</span><span class="sxs-lookup"><span data-stu-id="24821-102">Default Trace Log Files Disabled</span></span>
  <span data-ttu-id="24821-103">Это правило проверяет значение хранимой процедуры sp_configure «default trace enabled», чтобы определить, включена ли трассировка по умолчанию (значение ON (1)) или отключена (значение OFF (0)).</span><span class="sxs-lookup"><span data-stu-id="24821-103">This rule checks the value of the sp_configure stored procedure default trace enabled option to determine whether default trace is set ON (1) or OFF (0).</span></span> <span data-ttu-id="24821-104">Если параметр включен, трассировка по умолчанию предоставляет [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]данные о конфигурации и изменениях DDL.</span><span class="sxs-lookup"><span data-stu-id="24821-104">When this option is enabled, default tracing provides information about configuration and DDL changes to the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="24821-105">В некоторых случаях эти сведения могут оказаться полезными для клиентов и службы поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)] при устранении неполадок с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24821-105">In some cases, this information can be helpful for customers and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support when they troubleshooting issues with the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="24821-106">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="24821-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="24821-107">Для установки значения параметра «default trace enabled» равным 1 используется хранимая процедура sp_configure.</span><span class="sxs-lookup"><span data-stu-id="24821-107">Use the sp_configure stored procedure to enable tracing by setting the value of default trace enabled to 1.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="24821-108">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="24821-108">For More Information</span></span>  
 [<span data-ttu-id="24821-109">Параметры конфигурации сервера (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="24821-109">Server Configuration Options &#40;SQL Server&#41;</span></span>](../../database-engine/configure-windows/server-configuration-options-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="24821-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="24821-110">See Also</span></span>  
 [<span data-ttu-id="24821-111">Наблюдение с помощью управления на основе политик и принудительное применение рекомендаций с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="24821-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
