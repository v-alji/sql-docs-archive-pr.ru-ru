---
title: Включение следящего сервера (мастер настройки безопасности зеркального отображения баз данных) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.inclwitness.f1
ms.assetid: f04b38a4-f4e2-4d4c-bdac-7cc70e5a5684
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 314d2205463436e2182b8d1a4cc0cc972213bd5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655912"
---
# <a name="include-witness-server-configure-database-mirroring-security-wizard"></a><span data-ttu-id="9c800-102">Включить следящий сервер (мастер настройки безопасности зеркального отображения баз данных)</span><span class="sxs-lookup"><span data-stu-id="9c800-102">Include Witness Server (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="9c800-103">Используйте эту страницу, чтобы указать, включать ли следящий сервер в конфигурацию безопасности для зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="9c800-103">Use this page to specify whether you want to include a witness server in this security configuration for database mirroring.</span></span>  
  
 <span data-ttu-id="9c800-104">**Настройка зеркального отображения базы данных в среде SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="9c800-104">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="9c800-105">Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="9c800-105">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="9c800-106">Запуск мастера настройки безопасности зеркального отображения баз данных (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="9c800-106">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="9c800-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="9c800-107">Options</span></span>  
 <span data-ttu-id="9c800-108">**Да**</span><span class="sxs-lookup"><span data-stu-id="9c800-108">**Yes**</span></span>  
 <span data-ttu-id="9c800-109">Нажмите, чтобы включить экземпляр следящего сервера в конфигурацию безопасности.</span><span class="sxs-lookup"><span data-stu-id="9c800-109">Click to include a witness server instance in the security configuration.</span></span> <span data-ttu-id="9c800-110">Следящий сервер необходим для режима высокого уровня безопасности с автоматической отработкой отказа, который дает возможность автоматического перехода на экземпляр зеркального сервера при сбое в работе экземпляра основного сервера.</span><span class="sxs-lookup"><span data-stu-id="9c800-110">The witness is necessary for high-safety mode with automatic failover, which supports automatic failover to the mirror server instance if the principal server instance fails.</span></span>  
  
 <span data-ttu-id="9c800-111">**Нет**</span><span class="sxs-lookup"><span data-stu-id="9c800-111">**No**</span></span>  
 <span data-ttu-id="9c800-112">Нажмите, чтобы настроить безопасность без следящего сервера.</span><span class="sxs-lookup"><span data-stu-id="9c800-112">Click to configure security without a witness.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c800-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="9c800-113">See Also</span></span>  
 <span data-ttu-id="9c800-114">[Свойства базы данных (страница "Зеркальное отображение")](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="9c800-114">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="9c800-115">[Зеркальное отображение базы данных (SQL Server)](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9c800-115">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="9c800-116">Следящий сервер зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="9c800-116">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
