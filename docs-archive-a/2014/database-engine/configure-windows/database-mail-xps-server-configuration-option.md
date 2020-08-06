---
title: Параметр конфигурации сервера "Database Mail XPs" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Database Mail XPs option
- Database Mail [SQL Server], enabling
ms.assetid: e22c4e63-1792-473b-af11-14a7931ca9ed
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 33ee15e862e0992f39373ec30275040c4fcacc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665538"
---
# <a name="database-mail-xps-server-configuration-option"></a><span data-ttu-id="b3223-102">Параметр конфигурации сервера «Database Mail XPs»</span><span class="sxs-lookup"><span data-stu-id="b3223-102">Database Mail XPs Server Configuration Option</span></span>
  <span data-ttu-id="b3223-103">Используйте параметр **Расширенные хранимые процедуры компонента Database Mail** для включения компонента Database Mail на сервере.</span><span class="sxs-lookup"><span data-stu-id="b3223-103">Use the **DatabaseMail XPs** option to enable Database Mail on this server.</span></span> <span data-ttu-id="b3223-104">Вы можете выбрать</span><span class="sxs-lookup"><span data-stu-id="b3223-104">The possible values are:</span></span>  
  
-   <span data-ttu-id="b3223-105">**0** означает, что компонент Database Mail не доступен (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b3223-105">**0** indicating Database Mail is not available (default).</span></span>  
  
-   <span data-ttu-id="b3223-106">**1** означает, что компонент Database Mail доступен.</span><span class="sxs-lookup"><span data-stu-id="b3223-106">**1** indicating Database Mail is available.</span></span>  
  
 <span data-ttu-id="b3223-107">Новые настройки вступают в силу сразу же, без остановки или перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="b3223-107">The setting takes effect immediately without a server stop and restart.</span></span>  
  
 <span data-ttu-id="b3223-108">После активации компонента Database Mail необходимо настроить базу данных обслуживания почты, чтобы использовать службу Database Mail.</span><span class="sxs-lookup"><span data-stu-id="b3223-108">After enabling Database Mail, you must configure a Database Mail host database to use Database Mail.</span></span>  
  
 <span data-ttu-id="b3223-109">Настройка компонента Database Mail при помощи **мастера настройки компонента Database Mail** разрешает использование расширенных хранимых процедур компонента Database Mail в базе данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="b3223-109">Configuring Database Mail using the **Database Mail Configuration Wizard** enables the Database Mail extended stored procedures in the **msdb** database.</span></span> <span data-ttu-id="b3223-110">При использовании **мастера настройки компонента Database Mail**можно не применять пример с **sp_configure** , приведенный ниже.</span><span class="sxs-lookup"><span data-stu-id="b3223-110">If you use the **Database Mail Configuration Wizard**, you do not have to use the **sp_configure** example below.</span></span>  
  
 <span data-ttu-id="b3223-111">Установка параметра **Database Mail XPs** в 0 не допускает запуска компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="b3223-111">Setting the **Database Mail XPs** option to 0 prevents Database Mail from starting.</span></span> <span data-ttu-id="b3223-112">Если же в момент установки параметра в 0 этот компонент уже запущен, он продолжает работать и отсылать письма до начала периода простоя, указанного в параметре **DatabaseMailExeMinimumLifeTime** .</span><span class="sxs-lookup"><span data-stu-id="b3223-112">If it is running when the option is set to 0, it continues to run and send mail until it is idle for the time configured in the **DatabaseMailExeMinimumLifeTime** option.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b3223-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="b3223-113">Examples</span></span>  
 <span data-ttu-id="b3223-114">В следующем примере активируются расширенные хранимые процедуры компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="b3223-114">The following example enables the Database Mail extended stored procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Database Mail XPs', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3223-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="b3223-115">See Also</span></span>  
 [<span data-ttu-id="b3223-116">Database Mail</span><span class="sxs-lookup"><span data-stu-id="b3223-116">Database Mail</span></span>](../../relational-databases/database-mail/database-mail.md)  
  
  
