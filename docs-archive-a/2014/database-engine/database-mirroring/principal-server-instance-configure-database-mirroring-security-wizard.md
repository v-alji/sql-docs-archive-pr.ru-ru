---
title: Экземпляр основного сервера (мастер настройки безопасности зеркального отображения баз данных) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.principalsrvr.f1
ms.assetid: 58af27d7-c5dd-4669-be6b-b472bc2c8ef4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2632b5ffd5355065b4b5c1f905b3b6e5c5b6204d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733101"
---
# <a name="principal-server-instance-configure-database-mirroring-security-wizard"></a><span data-ttu-id="3a119-102">Экземпляр основного сервера (мастер настройки безопасности зеркального отображения баз данных)</span><span class="sxs-lookup"><span data-stu-id="3a119-102">Principal Server Instance (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="3a119-103">Используйте данную страницу для задания данных об экземпляре сервера основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="3a119-103">Use this page to specify information about the server instance of the principal database.</span></span> <span data-ttu-id="3a119-104">Основная база данных представляет собой копию базы данных, начинающую сеанс зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="3a119-104">The principal database is the copy of the database that begins the mirroring session.</span></span> <span data-ttu-id="3a119-105">После начала сеанса основная база данных является копией базы данных, принимающей пользовательские изменения.</span><span class="sxs-lookup"><span data-stu-id="3a119-105">After the session has begun, the principal database is the copy of the database that accepts user changes.</span></span> <span data-ttu-id="3a119-106">(При отработке отказа основная роль и роль зеркального отображения меняются местами, следовательно, первоначальная основная база данных может не остаться основной.)</span><span class="sxs-lookup"><span data-stu-id="3a119-106">(When a failover occurs, the principal and mirroring roles are swapped; therefore, the initial principal database might not remain the principal database.)</span></span>  
  
 <span data-ttu-id="3a119-107">**Настройка зеркального отображения базы данных в среде SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="3a119-107">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="3a119-108">Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="3a119-108">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="3a119-109">Запуск мастера настройки безопасности зеркального отображения баз данных (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="3a119-109">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="3a119-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="3a119-110">Options</span></span>  
 <span data-ttu-id="3a119-111">**Экземпляр основного сервера**</span><span class="sxs-lookup"><span data-stu-id="3a119-111">**Principal server instance**</span></span>  
 <span data-ttu-id="3a119-112">Поскольку зеркальное отображение базы данных в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] всегда настраивается с основного сервера, то текущим экземпляром сервера всегда будет экземпляр основного сервера.</span><span class="sxs-lookup"><span data-stu-id="3a119-112">Because database mirroring in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is always configured from the principal server, the current server instance is always the principal server instance.</span></span>  
  
 <span data-ttu-id="3a119-113">**Listener Port** (Порт прослушивателя)</span><span class="sxs-lookup"><span data-stu-id="3a119-113">**Listener Port**</span></span>  
 <span data-ttu-id="3a119-114">Поведение этого параметра зависит от того, существует ли конечная точка зеркального отображения для этого экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="3a119-114">The behavior of this option depends on whether the mirroring endpoint exists for this server instance, as follows:</span></span>  
  
-   <span data-ttu-id="3a119-115">Если прослушиваемый порт не существует для данного экземпляра сервера, то в текстовом поле **Порт** отображается номер порта 5022.</span><span class="sxs-lookup"><span data-stu-id="3a119-115">If the listener port does not exist for this server instance, port number 5022 is displayed in the **Port** text box.</span></span> <span data-ttu-id="3a119-116">Можно использовать любой допустимый номер порта, например 7022.</span><span class="sxs-lookup"><span data-stu-id="3a119-116">You can use any available port number, such as, 7022.</span></span>  
  
-   <span data-ttu-id="3a119-117">Если конечная точка зеркального отображения уже существует, отображается номер порта конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3a119-117">When the mirroring endpoint already exists, the port number from the endpoint is displayed.</span></span> <span data-ttu-id="3a119-118">Если необходимо изменить порт, используйте команду ALTER ENDPOINT.</span><span class="sxs-lookup"><span data-stu-id="3a119-118">If you need to change the port, use an ALTER ENDPOINT command.</span></span> <span data-ttu-id="3a119-119">Дополнительные сведения см. в статье [ALTER ENDPOINT (Transact-SQL)](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3a119-119">For more information, see [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a119-120">Номер порта обязателен.</span><span class="sxs-lookup"><span data-stu-id="3a119-120">A port number is required.</span></span>  
  
 <span data-ttu-id="3a119-121">**Имя конечной точки**</span><span class="sxs-lookup"><span data-stu-id="3a119-121">**Endpoint name**</span></span>  
 <span data-ttu-id="3a119-122">Если для данного экземпляра сервера существует конечная точка зеркального отображения, то здесь отображается имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3a119-122">If the mirroring endpoint exists for this server instance, the endpoint name is displayed here.</span></span> <span data-ttu-id="3a119-123">Если конечная точка отсутствует, можно задать имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3a119-123">If the endpoint does not exist, you can specify the name of the endpoint.</span></span>  
  
 <span data-ttu-id="3a119-124">**Шифровать данные, проходящие через эту конечную точку**</span><span class="sxs-lookup"><span data-stu-id="3a119-124">**Encrypt data sent through this endpoint**</span></span>  
 <span data-ttu-id="3a119-125">По умолчанию шифрование включено.</span><span class="sxs-lookup"><span data-stu-id="3a119-125">By default, encryption is enabled.</span></span> <span data-ttu-id="3a119-126">Если этот параметр включен, шифрование обязательно (а не просто поддерживается), а для всех параметров шифрования используются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3a119-126">When enabled, encryption is required (not merely supported) and uses the default values for all of the encryption options.</span></span> <span data-ttu-id="3a119-127">Дополнительные сведения см. в разделе [CREATE ENDPOINT (Transact-SQL)](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3a119-127">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
 <span data-ttu-id="3a119-128">Снимите этот флажок для выключения шифрования.</span><span class="sxs-lookup"><span data-stu-id="3a119-128">To disable encryption, clear the check box.</span></span> <span data-ttu-id="3a119-129">Установите этот флажок, чтобы вновь включить шифрование.</span><span class="sxs-lookup"><span data-stu-id="3a119-129">To re-enable encryption, select the check box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a119-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="3a119-130">See Also</span></span>  
 <span data-ttu-id="3a119-131">[Конечная точка зеркального отображения базы данных (SQL Server)](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3a119-131">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="3a119-132">[Свойства базы данных (страница "Зеркальное отображение")](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="3a119-132">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="3a119-133">[Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows (Transact-SQL)](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="3a119-133">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="3a119-134">[Запуск монитора зеркального отображения баз данных (среда SQL Server Management Studio)](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="3a119-134">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="3a119-135">Зеркальное отображение базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3a119-135">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
