---
title: Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows (Transact-SQL) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- database mirroring [SQL Server], endpoint
- endpoints [SQL Server], database mirroring
- Windows authentication [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: baf1a4b1-6790-4275-b261-490bca33bdb9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5558bc5684f2eb9053c935543db0c05d6225daf7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657288"
---
# <a name="create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql"></a><span data-ttu-id="dcddf-102">Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dcddf-102">Create a Database Mirroring Endpoint for Windows Authentication (Transact-SQL)</span></span>
  <span data-ttu-id="dcddf-103">В этом разделе описывается создание конечной точки зеркального отображения базы данных, использующей проверку подлинности Windows, в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dcddf-103">This topic describes how to create a database mirroring endpoint that uses Windows Authentication in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="dcddf-104">Для поддержки зеркального отображения баз данных или [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] , каждому экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] требуется конечная точка зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="dcddf-104">To support database mirroring or [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires a database mirroring endpoint.</span></span> <span data-ttu-id="dcddf-105">На экземпляре сервера может быть только одна конечная точка зеркального отображения базы данных, которой назначен только один порт.</span><span class="sxs-lookup"><span data-stu-id="dcddf-105">A server instance can have only one database mirroring endpoint, which has a single port.</span></span> <span data-ttu-id="dcddf-106">Конечная точка зеркального отображения базы данных может использовать любой доступный порт на локальной системе, на которой эта точка создана.</span><span class="sxs-lookup"><span data-stu-id="dcddf-106">A database mirroring endpoint can use any port that is available on the local system when the endpoint is created.</span></span> <span data-ttu-id="dcddf-107">Все сеансы зеркального отображения базы данных на экземпляре сервера прослушивают этот порт, и все входящие соединения для зеркального отображения базы данных используют этот порт.</span><span class="sxs-lookup"><span data-stu-id="dcddf-107">All database mirroring sessions on a server instance listen on that port, and all incoming connections for database mirroring use that port.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dcddf-108">Если конечная точка зеркального отображения базы данных существует и уже используется, рекомендуется использовать именно эту конечную точку.</span><span class="sxs-lookup"><span data-stu-id="dcddf-108">If a database mirroring endpoint exists and is already in use, we recommend that you use that endpoint.</span></span> <span data-ttu-id="dcddf-109">Удаление используемой конечной точки нарушает работу существующих сеансов.</span><span class="sxs-lookup"><span data-stu-id="dcddf-109">Dropping an in-use endpoint disrupts existing sessions.</span></span>  
  
 <span data-ttu-id="dcddf-110">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="dcddf-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="dcddf-111">**Перед началом работы**  [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="dcddf-111">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="dcddf-112">**Создание конечной точки зеркального отображения базы данных с помощью различных средств.**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="dcddf-112">**To create a database mirroring endpoint, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dcddf-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="dcddf-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dcddf-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="dcddf-114">Security</span></span>  
 <span data-ttu-id="dcddf-115">Методы проверки подлинности и шифрования для каждого экземпляра сервера устанавливаются администратором системы.</span><span class="sxs-lookup"><span data-stu-id="dcddf-115">The authentication and encryption methods of the server instance are established by the system administrator.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dcddf-116">Алгоритм RC4 устарел.</span><span class="sxs-lookup"><span data-stu-id="dcddf-116">The RC4 algorithm is deprecated.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="dcddf-117">Вместо этого рекомендуется использовать алгоритм AES.</span><span class="sxs-lookup"><span data-stu-id="dcddf-117">We recommend that you use AES.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dcddf-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="dcddf-118">Permissions</span></span>  
 <span data-ttu-id="dcddf-119">Требуется разрешение CREATE ENDPOINT или членство в предопределенной роли сервера sysadmin.</span><span class="sxs-lookup"><span data-stu-id="dcddf-119">Requires CREATE ENDPOINT permission, or membership in the sysadmin fixed server role.</span></span> <span data-ttu-id="dcddf-120">Дополнительные сведения см. в разделе [GRANT, предоставление разрешений на конечную точку (Transact-SQL)](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dcddf-120">For more information, see [GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="dcddf-121">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dcddf-121">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-database-mirroring-endpoint-that-uses-windows-authentication"></a><span data-ttu-id="dcddf-122">Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="dcddf-122">To Create a Database Mirroring Endpoint That Uses Windows Authentication</span></span>  
  
1.  <span data-ttu-id="dcddf-123">Подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , для которого требуется создать конечную точку зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="dcddf-123">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on which you want to create a database mirroring endpoint.</span></span>  
  
2.  <span data-ttu-id="dcddf-124">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="dcddf-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dcddf-125">Определите, не существует ли уже конечная точка зеркального отображения, с помощью следующей инструкции:</span><span class="sxs-lookup"><span data-stu-id="dcddf-125">Determine if a database mirroring endpoint already exists by using the following statement:</span></span>  
  
    ```sql
    SELECT name, role_desc, state_desc FROM sys.database_mirroring_endpoints;
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="dcddf-126">Если конечная точка зеркального отображения уже существует для данного экземпляра сервера, используйте ее для всех сеансов, устанавливаемых с этим экземпляром.</span><span class="sxs-lookup"><span data-stu-id="dcddf-126">If a database mirroring endpoint already exists for the server instance, use that endpoint for any other sessions you establish on the server instance.</span></span>  
  
4.  <span data-ttu-id="dcddf-127">Чтобы создать конечную точку с проверкой подлинности Windows на языке Transact-SQL, выполните инструкцию CREATE ENDPOINT.</span><span class="sxs-lookup"><span data-stu-id="dcddf-127">To use Transact-SQL to create an endpoint to use with Windows Authentication, use a CREATE ENDPOINT statement.</span></span> <span data-ttu-id="dcddf-128">Эта инструкция выглядит так:</span><span class="sxs-lookup"><span data-stu-id="dcddf-128">The statement takes the following general form:</span></span>  
  
     <span data-ttu-id="dcddf-129">CREATE ENDPOINT *\<endpointName>*</span><span class="sxs-lookup"><span data-stu-id="dcddf-129">CREATE ENDPOINT *\<endpointName>*</span></span>  
  
     <span data-ttu-id="dcddf-130">STATE=STARTED</span><span class="sxs-lookup"><span data-stu-id="dcddf-130">STATE=STARTED</span></span>  
  
     <span data-ttu-id="dcddf-131">AS TCP ( LISTENER_PORT = *\<listenerPortList>* )</span><span class="sxs-lookup"><span data-stu-id="dcddf-131">AS TCP ( LISTENER_PORT = *\<listenerPortList>* )</span></span>  
  
     <span data-ttu-id="dcddf-132">ДЛЯ DATABASE_MIRRORING</span><span class="sxs-lookup"><span data-stu-id="dcddf-132">FOR DATABASE_MIRRORING</span></span>  
  
     <span data-ttu-id="dcddf-133">(</span><span class="sxs-lookup"><span data-stu-id="dcddf-133">(</span></span>  
  
     <span data-ttu-id="dcddf-134">[ AUTHENTICATION = **WINDOWS** [ *\<authorizationMethod>* ]</span><span class="sxs-lookup"><span data-stu-id="dcddf-134">[ AUTHENTICATION = **WINDOWS** [ *\<authorizationMethod>* ]</span></span>  
  
     <span data-ttu-id="dcddf-135">]</span><span class="sxs-lookup"><span data-stu-id="dcddf-135">]</span></span>  
  
     <span data-ttu-id="dcddf-136">[ [ **,** ] ENCRYPTION = **REQUIRED**</span><span class="sxs-lookup"><span data-stu-id="dcddf-136">[ [**,**] ENCRYPTION = **REQUIRED**</span></span>  
  
     <span data-ttu-id="dcddf-137">[ ALGORITHM { *\<algorithm>* } ]</span><span class="sxs-lookup"><span data-stu-id="dcddf-137">[ ALGORITHM { *\<algorithm>* } ]</span></span>  
  
     <span data-ttu-id="dcddf-138">]</span><span class="sxs-lookup"><span data-stu-id="dcddf-138">]</span></span>  
  
     <span data-ttu-id="dcddf-139">[ **,** ] ROLE = *\<role>*</span><span class="sxs-lookup"><span data-stu-id="dcddf-139">[**,**] ROLE = *\<role>*</span></span>  
  
     <span data-ttu-id="dcddf-140">)</span><span class="sxs-lookup"><span data-stu-id="dcddf-140">)</span></span>  
  
     <span data-ttu-id="dcddf-141">где</span><span class="sxs-lookup"><span data-stu-id="dcddf-141">where</span></span>  
  
    -   <span data-ttu-id="dcddf-142">*\<endpointName>*  — уникальное имя для конечной точки зеркального отображения базы данных экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="dcddf-142">*\<endpointName>* is a unique name for the database mirroring endpoint of the server instance.</span></span>  
  
    -   <span data-ttu-id="dcddf-143">STARTED указывает, что конечная точка должна запуститься и начать ожидать соединения.</span><span class="sxs-lookup"><span data-stu-id="dcddf-143">STARTED specifies that the endpoint is to be started and to begin listening for connections.</span></span> <span data-ttu-id="dcddf-144">Обычно конечные точки зеркального отображения базы данных создаются в состоянии STARTED.</span><span class="sxs-lookup"><span data-stu-id="dcddf-144">A database mirroring endpoint typically is created in the STARTED state.</span></span> <span data-ttu-id="dcddf-145">Можно также начать сеанс в состоянии STOPPED (по умолчанию) или DISABLED.</span><span class="sxs-lookup"><span data-stu-id="dcddf-145">Alternatively, you can start a session in a STOPPED state (the default) or DISABLED state.</span></span>  
  
    -   <span data-ttu-id="dcddf-146">*\<listenerPortList>*  — номер одного порта (*nnnn*), по которому сервер должен прослушивать сообщения зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="dcddf-146">*\<listenerPortList>* is a single port number (*nnnn*) on which you want the server to listen for database mirroring messages.</span></span> <span data-ttu-id="dcddf-147">Разрешается только протокол TCP; использование другого протокола приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="dcddf-147">Only TCP is allowed; specifying any other protocol causes an error.</span></span>  
  
         <span data-ttu-id="dcddf-148">Номер порта на одном компьютере может использоваться только один раз.</span><span class="sxs-lookup"><span data-stu-id="dcddf-148">A port number can be used only once per computer system.</span></span> <span data-ttu-id="dcddf-149">Конечная точка зеркального отображения базы данных может использовать любой доступный порт на локальной системе, на которой эта точка создана.</span><span class="sxs-lookup"><span data-stu-id="dcddf-149">A database mirroring endpoint can use any port that is available on the local system when the endpoint is created.</span></span> <span data-ttu-id="dcddf-150">Чтобы определить, какие порты в данный момент используются в системе конечными точками протокола TCP, выполните следующую инструкцию Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="dcddf-150">To identify the ports currently being used by TCP endpoints on the system, use the following Transact-SQL statement:</span></span>  
  
        ```  
        SELECT name, port FROM sys.tcp_endpoints;  
        ```  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="dcddf-151">У каждого экземпляра сервера должен быть один и только один уникальный прослушиваемый порт.</span><span class="sxs-lookup"><span data-stu-id="dcddf-151">Each server instance requires one and only one unique listener port.</span></span>  
  
    -   <span data-ttu-id="dcddf-152">Для проверки подлинности Windows параметр AUTHENTICATION является необязательным, если не требуется, чтобы в конечной точке использовались только NTLM или Kerberos для проверки подлинности соединений.</span><span class="sxs-lookup"><span data-stu-id="dcddf-152">For Windows Authentication, the AUTHENTICATION option is optional, unless you want the endpoint to use only NTLM or Kerberos to authenticate connections.</span></span> <span data-ttu-id="dcddf-153">*\<authorizationMethod>* указывает метод, используемый для проверки подлинности соединений как один из следующих: NTLM, KERBEROS или NEGOTIATE.</span><span class="sxs-lookup"><span data-stu-id="dcddf-153">*\<authorizationMethod>* specifies the method used to authenticate connections as one of the following: NTLM, KERBEROS, or NEGOTIATE.</span></span> <span data-ttu-id="dcddf-154">Значение по умолчанию NEGOTIATE соответствует тому, что конечная точка будет использовать протокол согласования Windows для выбора NTLM либо Kerberos.</span><span class="sxs-lookup"><span data-stu-id="dcddf-154">The default, NEGOTIATE, causes the endpoint to use the Windows negotiation protocol to choose either NTLM or Kerberos.</span></span> <span data-ttu-id="dcddf-155">Согласование разрешает соединения без проверки подлинности или с ней, в зависимости от уровня проверки подлинности противоположной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="dcddf-155">Negotiation enables connections with or without authentication, depending on the authentication level of the opposite endpoint.</span></span>  
  
    -   <span data-ttu-id="dcddf-156">По умолчанию параметр ENCRYPTION имеет значение REQUIRED.</span><span class="sxs-lookup"><span data-stu-id="dcddf-156">ENCRYPTION is set to REQUIRED by default.</span></span> <span data-ttu-id="dcddf-157">Это означает, что все соединения с этой конечной точкой должны использовать шифрование.</span><span class="sxs-lookup"><span data-stu-id="dcddf-157">This means that all connections to this endpoint must use encryption.</span></span> <span data-ttu-id="dcddf-158">Однако можно отключить шифрование или сделать его необязательным.</span><span class="sxs-lookup"><span data-stu-id="dcddf-158">However, you can disable encryption or make it optional on an endpoint.</span></span> <span data-ttu-id="dcddf-159">Существуют следующие варианты.</span><span class="sxs-lookup"><span data-stu-id="dcddf-159">The alternatives are as follows:</span></span>  
  
        |<span data-ttu-id="dcddf-160">Значение</span><span class="sxs-lookup"><span data-stu-id="dcddf-160">Value</span></span>|<span data-ttu-id="dcddf-161">Определение</span><span class="sxs-lookup"><span data-stu-id="dcddf-161">Definition</span></span>|  
        |-----------|----------------|  
        |<span data-ttu-id="dcddf-162">DISABLED</span><span class="sxs-lookup"><span data-stu-id="dcddf-162">DISABLED</span></span>|<span data-ttu-id="dcddf-163">Указывает на то, что данные, передаваемые через соединение, не будут зашифрованы.</span><span class="sxs-lookup"><span data-stu-id="dcddf-163">Specifies that data sent over a connection is not encrypted.</span></span>|  
        |<span data-ttu-id="dcddf-164">SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="dcddf-164">SUPPORTED</span></span>|<span data-ttu-id="dcddf-165">Указывает на то, что данные будут зашифрованы только в случае, если у противоположной конечной точки этот аргумент принял значение SUPPORTED или REQUIRED.</span><span class="sxs-lookup"><span data-stu-id="dcddf-165">Specifies that the data is encrypted only if the opposite endpoint specifies either SUPPORTED or REQUIRED.</span></span>|  
        |<span data-ttu-id="dcddf-166">REQUIRED</span><span class="sxs-lookup"><span data-stu-id="dcddf-166">REQUIRED</span></span>|<span data-ttu-id="dcddf-167">Указывает на то, что данные, передаваемые через соединение, шифруются.</span><span class="sxs-lookup"><span data-stu-id="dcddf-167">Specifies that data sent over a connection must be encrypted.</span></span>|  
  
         <span data-ttu-id="dcddf-168">Если конечная точка требует шифрования, у другой конечной точки значением параметра ENCRYPTION может быть SUPPORTED или REQUIRED.</span><span class="sxs-lookup"><span data-stu-id="dcddf-168">If an endpoint requires encryption, the other endpoint must have ENCRYPTION set to either SUPPORTED or REQUIRED.</span></span>  
  
    -   <span data-ttu-id="dcddf-169">*\<algorithm>* предоставляет параметр определения стандартов шифрования для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="dcddf-169">*\<algorithm>* provides the option of specifying the encryption standards for the endpoint.</span></span> <span data-ttu-id="dcddf-170">Значение *\<algorithm>* может указывать один из следующих алгоритмов или сочетание алгоритмов: RC4, AES, AES RC4 или RC4 AES.</span><span class="sxs-lookup"><span data-stu-id="dcddf-170">The value of *\<algorithm>* can be one following algorithms or combinations of algorithms: RC4, AES, AES RC4, or RC4 AES.</span></span>  
  
         <span data-ttu-id="dcddf-171">Алгоритм AES RC4 определяет, что данная конечная точка будет согласовывать алгоритм шифрования, отдавая предпочтение алгоритму AES.</span><span class="sxs-lookup"><span data-stu-id="dcddf-171">AES RC4 specifies that this endpoint will negotiate for the encryption algorithm, giving preference to the AES algorithm.</span></span> <span data-ttu-id="dcddf-172">Алгоритм RC4 AES определяет, что данная конечная точка будет согласовывать алгоритм шифрования, отдавая предпочтение алгоритму RC4.</span><span class="sxs-lookup"><span data-stu-id="dcddf-172">RC4 AES specifies that this endpoint will negotiate for the encryption algorithm, giving preference to the RC4 algorithm.</span></span> <span data-ttu-id="dcddf-173">Если обе конечные точки указывают оба алгоритма, но в разной последовательности, то используется та, которая указана на принимающей стороне.</span><span class="sxs-lookup"><span data-stu-id="dcddf-173">If both endpoints specify both algorithms but in different orders, the endpoint accepting the connection wins.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="dcddf-174">Алгоритм RC4 устарел.</span><span class="sxs-lookup"><span data-stu-id="dcddf-174">The RC4 algorithm is deprecated.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="dcddf-175">Вместо этого рекомендуется использовать алгоритм AES.</span><span class="sxs-lookup"><span data-stu-id="dcddf-175">We recommend that you use AES.</span></span>  
  
    -   <span data-ttu-id="dcddf-176">*\<role>* определяет роль или роли, которые может выполнять сервер.</span><span class="sxs-lookup"><span data-stu-id="dcddf-176">*\<role>* defines the role or roles that the server can perform.</span></span> <span data-ttu-id="dcddf-177">Указание параметра ROLE необходимо.</span><span class="sxs-lookup"><span data-stu-id="dcddf-177">Specifying ROLE is required.</span></span> <span data-ttu-id="dcddf-178">Однако роль конечной точки является значимой только для зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="dcddf-178">However, the role of the endpoint is relevant only for database mirroring.</span></span> <span data-ttu-id="dcddf-179">Для [!INCLUDE[ssHADR](../../includes/sshadr-md.md)]роль конечной точки игнорируется.</span><span class="sxs-lookup"><span data-stu-id="dcddf-179">For [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], the role of the endpoint is ignored.</span></span>  
  
         <span data-ttu-id="dcddf-180">Чтобы сервер мог выполнять одну роль в одном сеансе зеркального отображения базы данных и другую — в другом, укажите ROLE=ALL.</span><span class="sxs-lookup"><span data-stu-id="dcddf-180">To allow a server instance to serve as one role for one database mirroring session and different role for another session, specify ROLE=ALL.</span></span> <span data-ttu-id="dcddf-181">Чтобы ограничить роль сервера только участником или следящим, укажите ROLE=PARTNER или ROLE=WITNESS соответственно.</span><span class="sxs-lookup"><span data-stu-id="dcddf-181">To restrict a server instance to being either a partner or a witness, specify ROLE=PARTNER or ROLE=WITNESS, respectively.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="dcddf-182">Дополнительные сведения о параметрах зеркального отображения баз данных для различных выпусков [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. [в разделе функции, поддерживаемые различными выпусками SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="dcddf-182">For more information about Database Mirroring options for different editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
     <span data-ttu-id="dcddf-183">Полное описание синтаксиса инструкции CREATE ENDPOINT см. в разделе [CREATE ENDPOINT (Transact-SQL)](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dcddf-183">For a complete description of the CREATE ENDPOINT syntax, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dcddf-184">Чтобы изменить существующую конечную точку, используйте [ALTER ENDPOINT (Transact-SQL)](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dcddf-184">To change an existing endpoint, use [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
###  <a name="example-creating-endpoints-to-support-for-database-mirroring-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="dcddf-185">Пример. Создание конечных точек для поддержки функции зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dcddf-185">Example: Creating Endpoints to Support for Database Mirroring (Transact-SQL)</span></span>  
 <span data-ttu-id="dcddf-186">В следующем примере создаются конечные точки зеркального отображения базы данных для экземпляров сервера по умолчанию на трех разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="dcddf-186">The following example creates database mirroring endpoints for the default server instances on three separate computer systems:</span></span>  
  
|<span data-ttu-id="dcddf-187">Роль экземпляра сервера</span><span class="sxs-lookup"><span data-stu-id="dcddf-187">Role of server instance</span></span>|<span data-ttu-id="dcddf-188">Имя главного компьютера</span><span class="sxs-lookup"><span data-stu-id="dcddf-188">Name of host computer</span></span>|  
|-----------------------------|---------------------------|  
|<span data-ttu-id="dcddf-189">Участник (изначально в роли основного сервера)</span><span class="sxs-lookup"><span data-stu-id="dcddf-189">Partner (initially in the principal role)</span></span>|`SQLHOST01\.`|  
|<span data-ttu-id="dcddf-190">Участник (изначально в роли зеркального сервера)</span><span class="sxs-lookup"><span data-stu-id="dcddf-190">Partner (initially in the mirror role)</span></span>|`SQLHOST02\.`|  
|<span data-ttu-id="dcddf-191">Свидетель</span><span class="sxs-lookup"><span data-stu-id="dcddf-191">Witness</span></span>|`SQLHOST03\.`|  
  
 <span data-ttu-id="dcddf-192">В этом примере все три конечные точки используют порт с номером 7022, хотя можно было бы использовать номер любого доступного порта.</span><span class="sxs-lookup"><span data-stu-id="dcddf-192">In this example, all three endpoints use port number 7022, though any available port number would work.</span></span> <span data-ttu-id="dcddf-193">Параметр AUTHENTICATION необязателен, так как все конечные точки используют тип по умолчанию, проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="dcddf-193">The AUTHENTICATION option is unnecessary, because the endpoints use the default type, Windows Authentication.</span></span> <span data-ttu-id="dcddf-194">Параметр ENCRYPTION также необязателен, так как все конечные точки намереваются согласовывать метод проверки подлинности соединения, а это поведение по умолчанию — для проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="dcddf-194">The ENCRYPTION option is also unnecessary, because the endpoints are all intended to negotiate the authentication method for a connection, which is the default behavior for Windows Authentication.</span></span> <span data-ttu-id="dcddf-195">Также все конечные точки требуют шифрование, что также является поведением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dcddf-195">Also, all of the endpoints require the encryption, which is the default behavior.</span></span>  
  
 <span data-ttu-id="dcddf-196">Каждый сервер ограничен ролью или участника, или следящего, и конечная точка каждого сервера явно задает эту роль (ROLE=PARTNER или ROLE=WITNESS).</span><span class="sxs-lookup"><span data-stu-id="dcddf-196">Each server instance is limited to serving as either a partner or a witness, and the endpoint of each server expressly specifies which role (ROLE=PARTNER or ROLE=WITNESS).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dcddf-197">У каждого экземпляра сервера может быть только одна конечная точка.</span><span class="sxs-lookup"><span data-stu-id="dcddf-197">Each server instance can have only one endpoint.</span></span> <span data-ttu-id="dcddf-198">Поэтому, если нужно, чтобы экземпляр сервера был в некоторых сеансах участником, а в некоторых — следящим, укажите ROLE=ALL.</span><span class="sxs-lookup"><span data-stu-id="dcddf-198">Therefore, if you want a server instance to be a partner in some sessions and the witness in others, specify ROLE=ALL.</span></span>  
  
```sql
--Endpoint for initial principal server instance, which  
--is the only server instance running on SQLHOST01.  
CREATE ENDPOINT endpoint_mirroring  
    STATE = STARTED  
    AS TCP ( LISTENER_PORT = 7022 )  
    FOR DATABASE_MIRRORING (ROLE=PARTNER);  
GO  
--Endpoint for initial mirror server instance, which  
--is the only server instance running on SQLHOST02.  
CREATE ENDPOINT endpoint_mirroring  
    STATE = STARTED  
    AS TCP ( LISTENER_PORT = 7022 )  
    FOR DATABASE_MIRRORING (ROLE=PARTNER);  
GO  
--Endpoint for witness server instance, which  
--is the only server instance running on SQLHOST03.  
CREATE ENDPOINT endpoint_mirroring  
    STATE = STARTED  
    AS TCP ( LISTENER_PORT = 7022 )  
    FOR DATABASE_MIRRORING (ROLE=WITNESS);  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="dcddf-199">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="dcddf-199">Related Tasks</span></span>  

### <a name="to-configure-a-database-mirroring-endpoint"></a><span data-ttu-id="dcddf-200">Настройка конечной точки зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="dcddf-200">To Configure a Database Mirroring Endpoint</span></span>
  
-   [<span data-ttu-id="dcddf-201">Создание конечной точки зеркального отображения базы данных для группы доступности AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="dcddf-201">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](../availability-groups/windows/database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="dcddf-202">Использование сертификатов для конечной точки зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dcddf-202">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [<span data-ttu-id="dcddf-203">Включение использования сертификатов для исходящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dcddf-203">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [<span data-ttu-id="dcddf-204">Включение использования сертификатов для входящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dcddf-204">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="dcddf-205">Указание сетевого адреса сервера (зеркальное отображение базы данных)</span><span class="sxs-lookup"><span data-stu-id="dcddf-205">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](specify-a-server-network-address-database-mirroring.md)  
  
-   [<span data-ttu-id="dcddf-206">Укажите URL-адрес конечной точки при добавлении или изменении реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="dcddf-206">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](../availability-groups/windows/specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="dcddf-207">**Просмотр сведений о конечной точке зеркального отображения базы данных**</span><span class="sxs-lookup"><span data-stu-id="dcddf-207">**To View Information About the Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="dcddf-208">sys.database_mirroring_endpoints (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dcddf-208">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="dcddf-209">См. также:</span><span class="sxs-lookup"><span data-stu-id="dcddf-209">See Also</span></span>  
 <span data-ttu-id="dcddf-210">[ALTER ENDPOINT (Transact-SQL)](/sql/t-sql/statements/alter-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dcddf-210">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="dcddf-211">[Выбор алгоритма шифрования](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="dcddf-211">[Choose an Encryption Algorithm](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span></span>  
 <span data-ttu-id="dcddf-212">[CREATE ENDPOINT (Transact-SQL)](/sql/t-sql/statements/create-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dcddf-212">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="dcddf-213">[Указание сетевого адреса сервера (зеркальное отображение базы данных)](specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="dcddf-213">[Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md) </span></span>  
 <span data-ttu-id="dcddf-214">[Пример. Настройка зеркального отображения базы данных с помощью проверки подлинности Windows (Transact-SQL)](example-setting-up-database-mirroring-using-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="dcddf-214">[Example: Setting Up Database Mirroring Using Windows Authentication &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-windows-authentication-transact-sql.md) </span></span>  
 [<span data-ttu-id="dcddf-215">Конечная точка зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="dcddf-215">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](the-database-mirroring-endpoint-sql-server.md)  
