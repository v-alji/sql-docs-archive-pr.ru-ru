---
title: Параметр конфигурации сервера "cross db ownership chaining" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cross-database ownership chaining
- cross db ownership chaining option
- chaining ownership
ms.assetid: 7b2d49f2-b91c-4aee-a52b-6cc49bed03af
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cfb768065cc0aa2aaa7aed0f996b18e46f1da7ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665121"
---
# <a name="cross-db-ownership-chaining-server-configuration-option"></a><span data-ttu-id="3a05a-102">Параметр конфигурации сервера «cross db ownership chaining»</span><span class="sxs-lookup"><span data-stu-id="3a05a-102">cross db ownership chaining Server Configuration Option</span></span>
  <span data-ttu-id="3a05a-103">Используйте параметр **cross db ownership chaining**, чтобы настроить межбазовые цепочки владения для экземпляра [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a05a-103">Use the **cross db ownership chaining** option to configure cross-database ownership chaining for an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="3a05a-104">Этот серверный параметр позволяет управлять межбазовыми цепочками владения на уровне базы данных и обеспечивает применение межбазовых цепочек владения для всех баз данных:</span><span class="sxs-lookup"><span data-stu-id="3a05a-104">This server option allows you to control cross-database ownership chaining at the database level or to allow cross-database ownership chaining for all databases:</span></span>  
  
-   <span data-ttu-id="3a05a-105">Если параметр **cross db ownership chaining** отключен для экземпляра (0), межбазовые цепочки владения выключены для всех баз данных.</span><span class="sxs-lookup"><span data-stu-id="3a05a-105">When **cross db ownership chaining** is off (0) for the instance, cross-database ownership chaining is disabled for all databases.</span></span>  
  
-   <span data-ttu-id="3a05a-106">Если параметр **cross db ownership chaining** включен для экземпляра (1), межбазовые цепочки владения включены для всех баз данных.</span><span class="sxs-lookup"><span data-stu-id="3a05a-106">When **cross db ownership chaining** is on (1) for the instance, cross-database ownership chaining is on for all databases.</span></span>  
  
-   <span data-ttu-id="3a05a-107">Межбазовые цепочки владения для отдельных баз данных можно установить с помощью предложения SET инструкции ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="3a05a-107">You can set cross-database ownership chaining for individual databases using the SET clause of the ALTER DATABASE statement.</span></span> <span data-ttu-id="3a05a-108">При создании новой базы данных параметр cross db ownership chaining можно установить с использованием инструкции CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="3a05a-108">If you are creating a new database, you can set the cross-database ownership chaining option for the new database using the CREATE DATABASE statement.</span></span>  
  
     <span data-ttu-id="3a05a-109">Не рекомендуется присваивать параметру **cross db ownership chaining** значение "1", за исключением ситуаций, когда все базы данных, размещенные на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , должны участвовать в межбазовой цепочке владения и известно влияние данного значения на безопасность.</span><span class="sxs-lookup"><span data-stu-id="3a05a-109">Setting **cross db ownership chaining** to 1 is not recommended unless all of the databases hosted by the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must participate in cross-database ownership chaining and you are aware of the security implications of this setting.</span></span>  
  
## <a name="controlling-cross-database-ownership-chaining"></a><span data-ttu-id="3a05a-110">Управление межбазовыми цепочками владения</span><span class="sxs-lookup"><span data-stu-id="3a05a-110">Controlling Cross-Database Ownership Chaining</span></span>  
 <span data-ttu-id="3a05a-111">Прежде чем включить или выключить межбазовые цепочки владения, следует учесть следующие факторы:</span><span class="sxs-lookup"><span data-stu-id="3a05a-111">Before turning cross-database ownership chaining on or off, consider the following:</span></span>  
  
-   <span data-ttu-id="3a05a-112">Для включения и выключения межбазовых цепочек владения необходимо быть членом предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="3a05a-112">You must be a member of the **sysadmin** fixed server role to turn cross-database ownership chaining on or off.</span></span>  
  
-   <span data-ttu-id="3a05a-113">Прежде чем отключить межбазовые цепочки владения на производственном сервере, проведите полное тестирование всех приложений, в том числе приложений от сторонних поставщиков, чтобы убедиться, что изменения не влияют на функциональность приложений.</span><span class="sxs-lookup"><span data-stu-id="3a05a-113">Before turning off cross-database ownership chaining on a production server, fully test all applications, including third-party applications, to ensure that the changes do not affect application functionality.</span></span>  
  
-   <span data-ttu-id="3a05a-114">Можно изменить параметр **cross db ownership chaining** на активном сервере, если указать RECONFIGURE как хранимую процедуру **sp_configure**.</span><span class="sxs-lookup"><span data-stu-id="3a05a-114">You can change the **cross db ownership chaining** option while the server is running if you specify RECONFIGURE with **sp_configure**.</span></span>  
  
-   <span data-ttu-id="3a05a-115">При работе с базами данных, требующими межбазовых цепочек владения, рекомендуется отключить параметр **cross db ownership chaining** для экземпляра с помощью хранимой процедуры **sp_configure**; затем с помощью инструкции ALTER DATABASE следует включить межбазовые цепочки владения для отдельных баз данных, если это требуется.</span><span class="sxs-lookup"><span data-stu-id="3a05a-115">If you have databases that require cross-database ownership chaining, the recommended practice is to turn off the **cross db ownership chaining** option for the instance using **sp_configure**; then turn on cross-database ownership chaining for individual databases that require it using the ALTER DATABASE statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a05a-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="3a05a-116">See Also</span></span>  
 <span data-ttu-id="3a05a-117">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3a05a-117">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="3a05a-118">[CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3a05a-118">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="3a05a-119">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3a05a-119">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="3a05a-120">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3a05a-120">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="3a05a-121">RECONFIGURE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3a05a-121">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
