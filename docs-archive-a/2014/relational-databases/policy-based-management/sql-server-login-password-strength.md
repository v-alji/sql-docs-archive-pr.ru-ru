---
title: Стойкость пароля для входа (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: b0862c3a-926b-490c-a37f-382e50146a3e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5534748fbbf810539f2dcfc22239e4b987cf0f77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729357"
---
# <a name="sql-server-login-password-strength"></a><span data-ttu-id="76d36-102">Стойкость пароля имени входа SQL Server</span><span class="sxs-lookup"><span data-stu-id="76d36-102">SQL Server Login Password Strength</span></span>
  <span data-ttu-id="76d36-103">Это правило проверяет, установлен ли флажок «Требовать использование политики паролей» для каждого имени входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76d36-103">This rule checks whether "Enforce password policy" of each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is enabled.</span></span> <span data-ttu-id="76d36-104">Если включена проверка подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , а версия операционной системы младше [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], злоумышленник может многократно использовать известный ему пароль имени входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76d36-104">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is enabled and if the operating system version is earlier than [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], an attacker could repeatedly exploit a known [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login password.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="76d36-105">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="76d36-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="76d36-106">Рекомендуется обновить операционную систему до [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76d36-106">We recommend that you upgrade the operating system to [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)].</span></span>  
  
 <span data-ttu-id="76d36-107">Если в определенной среде не требуется проверка подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , следует использовать проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="76d36-107">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is not required in your environment, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="76d36-108">Следует установить флажок «Требовать использование политики паролей» для всех имен входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76d36-108">Enable "Enforce password policy" for all the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins.</span></span> <span data-ttu-id="76d36-109">Для настройки политики паролей для имени входа [используется инструкция](/sql/t-sql/statements/alter-login-transact-sql) ALTER LOGIN [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76d36-109">Use [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) to configure the password policy for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="76d36-110">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="76d36-110">For More Information</span></span>  
 [<span data-ttu-id="76d36-111">Политика паролей</span><span class="sxs-lookup"><span data-stu-id="76d36-111">Password Policy</span></span>](../security/password-policy.md)  
  
## <a name="see-also"></a><span data-ttu-id="76d36-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="76d36-112">See Also</span></span>  
 [<span data-ttu-id="76d36-113">Наблюдение с помощью управления на основе политик и принудительное применение рекомендаций с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="76d36-113">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
