---
title: Использование сертификатов для конечной точки зеркального отображения базы данных (Transact-SQL) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- certificates [SQL Server], database mirroring
- authentication [SQL Server], database mirroring
- database mirroring [SQL Server], security
ms.assetid: f7c23cc2-48dc-4b78-b441-89ca29a0bd9e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c159e66e798524c41bf6e653283c299cc8393be5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658392"
---
# <a name="use-certificates-for-a-database-mirroring-endpoint-transact-sql"></a><span data-ttu-id="dda58-102">Использование сертификатов для конечной точки зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dda58-102">Use Certificates for a Database Mirroring Endpoint (Transact-SQL)</span></span>
  <span data-ttu-id="dda58-103">Для обеспечения возможности выполнения проверки подлинности при помощи сертификата при зеркальном отображении базы данных на данном экземпляре сервера, системный администратор должен настроить каждый экземпляр сервера для использования сертификатов, как для входящих, так и для исходящих соединений.</span><span class="sxs-lookup"><span data-stu-id="dda58-103">To enable certificate authentication for database mirroring on a given server instance, the system administrator must configure each server instance to use certificates on both outbound and inbound connections.</span></span> <span data-ttu-id="dda58-104">Вначале должны быть настроены исходящие соединения.</span><span class="sxs-lookup"><span data-stu-id="dda58-104">Outbound connections must be configured first.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dda58-105">Все соединения зеркального отображения экземпляра сервера используют одну и ту же конечную точку зеркального отображения базы данных, и при ее создании необходимо задать метод проверки подлинности экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="dda58-105">All mirroring connections on a server instance use a single database mirroring endpoint, and you must specify the authentication method of the server instance when you create the endpoint.</span></span> <span data-ttu-id="dda58-106">Таким образом, экземпляр сервера может использовать только одну форму проверки подлинности при зеркальном отображении базы данных.</span><span class="sxs-lookup"><span data-stu-id="dda58-106">Therefore, you can use only one form of authentication per server instance for database mirroring.</span></span>  
  
## <a name="configuring-outbound-connections"></a><span data-ttu-id="dda58-107">Настройка исходящих соединений</span><span class="sxs-lookup"><span data-stu-id="dda58-107">Configuring Outbound Connections</span></span>  
 <span data-ttu-id="dda58-108">На каждом экземпляре сервера, настраиваемом для зеркального отображения базы данных, должны быть выполнены следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="dda58-108">Follow these steps on each server instance that you are configuring for database mirroring:</span></span>  
  
1.  <span data-ttu-id="dda58-109">В базе данных **master** создайте главный ключ базы данных.</span><span class="sxs-lookup"><span data-stu-id="dda58-109">In the **master** database, create a database master key.</span></span>  
  
2.  <span data-ttu-id="dda58-110">В базе данных **master** создайте зашифрованный сертификат для экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="dda58-110">In the **master** database, create an encrypted certificate on the server instance.</span></span>  
  
3.  <span data-ttu-id="dda58-111">Создайте конечную точку для экземпляра сервера при использовании его сертификата.</span><span class="sxs-lookup"><span data-stu-id="dda58-111">Create an endpoint for the server instance using its certificate.</span></span>  
  
4.  <span data-ttu-id="dda58-112">Создайте резервную копию сертификата в файле и защищенным образом скопируйте этот файл на другие системы.</span><span class="sxs-lookup"><span data-stu-id="dda58-112">Back up the certificate to a file and securely copy it to the other system or systems.</span></span>  
  
 <span data-ttu-id="dda58-113">Все эти этапы необходимо выполнить для каждого из участников, а также для следящего сервера, если он есть.</span><span class="sxs-lookup"><span data-stu-id="dda58-113">You must complete these steps for each partner and the witness, if there is one.</span></span>  
  
 <span data-ttu-id="dda58-114">Дополнительные сведения см. в разделе [Включение использования сертификатов для исходящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="dda58-114">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
## <a name="configuring-inbound-connections"></a><span data-ttu-id="dda58-115">Настройка входящих соединений</span><span class="sxs-lookup"><span data-stu-id="dda58-115">Configuring Inbound Connections</span></span>  
 <span data-ttu-id="dda58-116">Для каждого из участников, настраиваемых для зеркального отображения базы данных, выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="dda58-116">Next, follow these steps for each partner that you are configuring for database mirroring.</span></span> <span data-ttu-id="dda58-117">В базе данных **master** :</span><span class="sxs-lookup"><span data-stu-id="dda58-117">In the **master** database:</span></span>  
  
1.  <span data-ttu-id="dda58-118">Создайте имя входа для другой системы.</span><span class="sxs-lookup"><span data-stu-id="dda58-118">Create a login for the other system.</span></span>  
  
2.  <span data-ttu-id="dda58-119">Создайте пользователя для этого имени входа.</span><span class="sxs-lookup"><span data-stu-id="dda58-119">Create a user for that login.</span></span>  
  
3.  <span data-ttu-id="dda58-120">Получите сертификат для конечной точки зеркального отображения другого экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="dda58-120">Obtain the certificate for the mirroring endpoint of the other server instance.</span></span>  
  
4.  <span data-ttu-id="dda58-121">Свяжите сертификат с пользователем, созданным на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="dda58-121">Associate the certificate with the user created in step 2.</span></span>  
  
5.  <span data-ttu-id="dda58-122">Предоставьте этому имени входа разрешение CONNECT на эту конечную точку зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="dda58-122">Grant CONNECT permission on the login for that mirroring endpoint.</span></span>  
  
 <span data-ttu-id="dda58-123">Если имеется следящий сервер, для него также необходимо настроить входящие соединения.</span><span class="sxs-lookup"><span data-stu-id="dda58-123">If there is a witness, you must also set up inbound connections for it.</span></span> <span data-ttu-id="dda58-124">Для этого нужно настроить имена входа, пользователей и сертификаты для следящего сервера на обоих участниках, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="dda58-124">This requires setting up logins, users, and certificates for the witness on both of the partners, and vice versa.</span></span>  
  
 <span data-ttu-id="dda58-125">Дополнительные сведения см. в разделе [Включение использования сертификатов для входящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="dda58-125">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="dda58-126">безопасность</span><span class="sxs-lookup"><span data-stu-id="dda58-126">Security</span></span>  
 <span data-ttu-id="dda58-127">За исключением случаев, когда сеть гарантированно защищена, рекомендуется для соединений зеркального отображения базы данных применять шифрование.</span><span class="sxs-lookup"><span data-stu-id="dda58-127">Unless you can guarantee that your network is secure, we recommend that you use encryption for database mirroring connections.</span></span> <span data-ttu-id="dda58-128">Дополнительные сведения см. в разделе [Конечная точка зеркального отображения базы данных (SQL Server)](the-database-mirroring-endpoint-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dda58-128">For more information, see [The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md).</span></span>  
  
 <span data-ttu-id="dda58-129">При копировании сертификата на другую систему используйте безопасный метод копирования.</span><span class="sxs-lookup"><span data-stu-id="dda58-129">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="dda58-130">Отнеситесь с особым вниманием к хранению сертификатов в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="dda58-130">Be extremely careful to keep all of your certificates secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dda58-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="dda58-131">See Also</span></span>  
 <span data-ttu-id="dda58-132">[Создание главного ключа базы данных](../../relational-databases/security/encryption/create-a-database-master-key.md) </span><span class="sxs-lookup"><span data-stu-id="dda58-132">[Create a Database Master Key](../../relational-databases/security/encryption/create-a-database-master-key.md) </span></span>  
 <span data-ttu-id="dda58-133">[CREATE MASTER KEY (Transact-SQL)](/sql/t-sql/statements/create-master-key-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dda58-133">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span></span>  
 <span data-ttu-id="dda58-134">[Безопасность транспорта для зеркального отображения базы данных и группы доступности AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="dda58-134">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="dda58-135">[Центр обеспечения безопасности для базы данных Azure SQL и SQL Server Database Engine](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md) </span><span class="sxs-lookup"><span data-stu-id="dda58-135">[Security Center for SQL Server Database Engine and Azure SQL Database](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md) </span></span>  
 [<span data-ttu-id="dda58-136">Конечная точка зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="dda58-136">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](the-database-mirroring-endpoint-sql-server.md)  
  
  
