---
title: Включение интеграции со средой CLR | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- clr enabled option
- common language runtime [SQL Server], enabling
ms.assetid: eb3e9c64-7486-42e7-baf6-c956fb311a2c
author: rothja
ms.author: jroth
ms.openlocfilehash: d7187906f1376deb81ca7ff4770af7b12b63c022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735317"
---
# <a name="enabling-clr-integration"></a><span data-ttu-id="c37eb-102">Включение интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="c37eb-102">Enabling CLR Integration</span></span>
  <span data-ttu-id="c37eb-103">Функция интеграции со средой CLR отключена по умолчанию, поэтому ее нужно включить, чтобы использовать объекты, использующие интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="c37eb-103">The common language runtime (CLR) integration feature is off by default, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="c37eb-104">Чтобы включить интеграцию со средой CLR, используйте параметр **clr enabled** хранимой процедуры **sp_configure** .</span><span class="sxs-lookup"><span data-stu-id="c37eb-104">To enable CLR integration, use the **clr enabled** option of the **sp_configure** stored procedure:</span></span>  
  
```  
  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'clr enabled', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="c37eb-105">Вы можете отключить интеграцию со средой CLR, задав для параметра **clr enabled** значение 0.</span><span class="sxs-lookup"><span data-stu-id="c37eb-105">You can disable CLR integration by setting the **clr enabled** option to 0.</span></span> <span data-ttu-id="c37eb-106">При отключении интеграции со средой CLR [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] прекращает выполнение всех подпрограмм CLR и выгружает все домены приложений.</span><span class="sxs-lookup"><span data-stu-id="c37eb-106">When you disable CLR integration, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stops executing all CLR routines and unloads all application domains.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c37eb-107">Чтобы включить интеграцию со средой CLR, необходимо иметь разрешение ALTER SETTINGS на уровне сервера, которое неявно удерживается членами предопределенных ролей сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="c37eb-107">To enable CLR integration, you must have ALTER SETTINGS server level permission, which is implicitly held by members of the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c37eb-108">Компьютеры, сконфигурированные для работы с большим объемом памяти и большим числом процессоров, при запуске сервера могут отказаться загружать функцию интеграции со средой CLR SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c37eb-108">Computers configured with large amounts of memory and a large number of processors may fail to load the CLR integration feature of SQL Server when starting the server.</span></span> <span data-ttu-id="c37eb-109">Чтобы устранить эту неполадку, запустите сервер с помощью параметра запуска службы **-gmemory_to_reserve** [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и укажите достаточно большое значение памяти.</span><span class="sxs-lookup"><span data-stu-id="c37eb-109">To address this issue, start the server by using the **-gmemory_to_reserve**[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service startup option, and specify a memory value large enough.</span></span> <span data-ttu-id="c37eb-110">Дополнительные сведения см. в разделе [Параметры запуска службы Database Engine](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="c37eb-110">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c37eb-111">Выполнение в среде CLR не поддерживается при использовании упрощенных пулов.</span><span class="sxs-lookup"><span data-stu-id="c37eb-111">Common language runtime (CLR) execution is not supported under lightweight pooling.</span></span> <span data-ttu-id="c37eb-112">Перед включением интеграции со средой CLR необходимо отключить функцию использования упрощенных пулов.</span><span class="sxs-lookup"><span data-stu-id="c37eb-112">Before enabling CLR integration, you must disable lightweight pooling.</span></span> <span data-ttu-id="c37eb-113">Дополнительные сведения см. в разделе [Параметр конфигурации сервера «использование упрощенных пулов»](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="c37eb-113">For more information, see [lightweight pooling Server Configuration Option](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c37eb-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="c37eb-114">See Also</span></span>  
 <span data-ttu-id="c37eb-115">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c37eb-115">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="c37eb-116">[Параметр конфигурации сервера «clr enabled»](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="c37eb-116">[clr enabled Server Configuration Option](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) </span></span>  
 <span data-ttu-id="c37eb-117">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c37eb-117">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="c37eb-118">[GRANT (Transact-SQL)](/sql/t-sql/statements/grant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c37eb-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span></span>  
 [<span data-ttu-id="c37eb-119">Роли уровня сервера</span><span class="sxs-lookup"><span data-stu-id="c37eb-119">Server-Level Roles</span></span>](../security/authentication-access/server-level-roles.md)  
  
  
