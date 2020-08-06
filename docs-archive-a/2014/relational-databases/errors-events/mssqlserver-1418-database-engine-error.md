---
title: MSSQLSERVER_1418 | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1418 (Database Engine error)
ms.assetid: 6e9c7241-0201-44e0-9f8b-b3c4e293f0f6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1fcac03f044aacce5e907824862eb589c97a07d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734113"
---
# <a name="mssqlserver_1418"></a><span data-ttu-id="b27ef-102">MSSQLSERVER_1418</span><span class="sxs-lookup"><span data-stu-id="b27ef-102">MSSQLSERVER_1418</span></span>
    
## <a name="details"></a><span data-ttu-id="b27ef-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="b27ef-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b27ef-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="b27ef-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="b27ef-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="b27ef-105">Event ID</span></span>|<span data-ttu-id="b27ef-106">1418</span><span class="sxs-lookup"><span data-stu-id="b27ef-106">1418</span></span>|  
|<span data-ttu-id="b27ef-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="b27ef-107">Event Source</span></span>|<span data-ttu-id="b27ef-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b27ef-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b27ef-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="b27ef-109">Component</span></span>|<span data-ttu-id="b27ef-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b27ef-110">SQLEngine</span></span>|  
|<span data-ttu-id="b27ef-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="b27ef-111">Symbolic Name</span></span>|<span data-ttu-id="b27ef-112">DBM_PARTNERNOTFOUND</span><span class="sxs-lookup"><span data-stu-id="b27ef-112">DBM_PARTNERNOTFOUND</span></span>|  
|<span data-ttu-id="b27ef-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="b27ef-113">Message Text</span></span>|<span data-ttu-id="b27ef-114">Не удалось подключиться к сетевому адресу «%.\*ls» сервера, или адрес не существует.</span><span class="sxs-lookup"><span data-stu-id="b27ef-114">The server network address "%.\*ls" can not be reached or does not exist.</span></span> <span data-ttu-id="b27ef-115">Проверьте имя сетевого адреса и работоспособность портов для локальных и удаленных конечных точек.</span><span class="sxs-lookup"><span data-stu-id="b27ef-115">Check the network address name and that the ports for the local and remote endpoints are operational.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b27ef-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="b27ef-116">Explanation</span></span>  
 <span data-ttu-id="b27ef-117">Сетевая конечная точка сервера не ответила, так как указанный сетевой адрес сервера недоступен или не существует.</span><span class="sxs-lookup"><span data-stu-id="b27ef-117">The server network endpoint did not respond because the specified server network address cannot be reached or does not exist.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b27ef-118">По умолчанию операционная система [!INCLUDE[msCoName](../../includes/msconame-md.md)] блокирует все порты.</span><span class="sxs-lookup"><span data-stu-id="b27ef-118">By default, [!INCLUDE[msCoName](../../includes/msconame-md.md)] operating system blocks all ports.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b27ef-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="b27ef-119">User Action</span></span>  
 <span data-ttu-id="b27ef-120">Проверьте имя сетевого адреса и повторите команду.</span><span class="sxs-lookup"><span data-stu-id="b27ef-120">Verify the network address name and reissue the command.</span></span>  
  
 <span data-ttu-id="b27ef-121">Действия по исправлению могут потребоваться на обоих участниках.</span><span class="sxs-lookup"><span data-stu-id="b27ef-121">Corrective action might be required on both partners.</span></span> <span data-ttu-id="b27ef-122">Например, если это сообщение об ошибке появилось при попытке выполнить инструкцию SET PARTNER на экземпляре основного сервера, то может подразумеваться, что действия по исправлению требуются только на экземпляре зеркального сервера.</span><span class="sxs-lookup"><span data-stu-id="b27ef-122">For example, if this message is raised when you are trying to run SET PARTNER on the principal server instance, the message might imply that you only have to take corrective action on the mirror server instance.</span></span> <span data-ttu-id="b27ef-123">Однако на самом деле их нужно выполнить на обоих участниках.</span><span class="sxs-lookup"><span data-stu-id="b27ef-123">However, corrective actions might be required on both partners.</span></span>  
  
### <a name="additional-corrective-actions"></a><span data-ttu-id="b27ef-124">Дополнительные действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="b27ef-124">Additional Corrective Actions</span></span>  
  
-   <span data-ttu-id="b27ef-125">Убедитесь, что зеркальная база данных готова к зеркальному отображению.</span><span class="sxs-lookup"><span data-stu-id="b27ef-125">Make sure that the mirror database is ready for mirroring.</span></span>  
  
-   <span data-ttu-id="b27ef-126">Убедитесь, что имя и порт экземпляра зеркального сервера указаны правильно.</span><span class="sxs-lookup"><span data-stu-id="b27ef-126">Make sure that the name and port of the mirror server instance are correct.</span></span>  
  
-   <span data-ttu-id="b27ef-127">Убедитесь, что целевой экземпляр зеркального сервера не защищен брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="b27ef-127">Make sure that the destination mirror server instance is not behind a firewall.</span></span>  
  
-   <span data-ttu-id="b27ef-128">Убедитесь, что экземпляр основного сервера не защищен брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="b27ef-128">Make sure that the principal server instance is not behind a firewall.</span></span>  
  
-   <span data-ttu-id="b27ef-129">По столбцу **state** или **state_desc** представления каталога **sys.database_mirroring_endpoints** проверьте, запущены ли на участниках конечные точки.</span><span class="sxs-lookup"><span data-stu-id="b27ef-129">Verify that the endpoints are started on the partners by using the **state** or **state_desc** column the of the **sys.database_mirroring_endpoints** catalog view.</span></span> <span data-ttu-id="b27ef-130">Если нет, то запустите их с помощью инструкции ALTER ENDPOINT.</span><span class="sxs-lookup"><span data-stu-id="b27ef-130">If either endpoint is not started, execute an ALTER ENDPOINT statement to start it.</span></span>  
  
-   <span data-ttu-id="b27ef-131">Убедитесь, что экземпляр основного сервера прослушивает порт, назначенный его конечной точке зеркального отображения базы данных, и что экземпляр зеркального сервера прослушивает свой порт.</span><span class="sxs-lookup"><span data-stu-id="b27ef-131">Make sure that the principal server instance is listening on the port assigned to its database mirroring endpoint and that and the mirror server instance is listening on its port.</span></span> <span data-ttu-id="b27ef-132">Дополнительные сведения см. в подразделе «Проверка доступности порта» далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b27ef-132">For more information, see "Verifying Port Availability," later in this topic.</span></span> <span data-ttu-id="b27ef-133">Если участник не прослушивает назначенный порт, перенастройте конечную точку зеркального отображения на другой порт.</span><span class="sxs-lookup"><span data-stu-id="b27ef-133">If a partner is not listening on its assigned port, modify the database mirroring endpoint to listen on a different port.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b27ef-134">Неправильно настроенные параметры безопасности могут вызвать сообщение об общей ошибке установки.</span><span class="sxs-lookup"><span data-stu-id="b27ef-134">Improperly configured security can cause a general setup error message.</span></span> <span data-ttu-id="b27ef-135">Обычно экземпляр сервера удаляет неверный запрос на соединение, не отвечая на него.</span><span class="sxs-lookup"><span data-stu-id="b27ef-135">Typically, the server instance drops the bad connection request without responding.</span></span> <span data-ttu-id="b27ef-136">Поэтому вызывающей стороне может показаться, что ошибка настройки безопасности вызвана какими-либо другими причинами (например, неверным состоянием зеркальной базы данных или ее отсутствием, недопустимыми разрешениями и т.д.).</span><span class="sxs-lookup"><span data-stu-id="b27ef-136">To the caller, a security-configuration error could appear to have occurred for a variety of other reasons, such as the mirror database in a bad state or does not exist, incorrect permissions, and so on.</span></span>  
  
### <a name="using-the-error-log-file-for-diagnosis"></a><span data-ttu-id="b27ef-137">Диагностика при помощи журнала ошибок</span><span class="sxs-lookup"><span data-stu-id="b27ef-137">Using the Error Log File for Diagnosis</span></span>  
 <span data-ttu-id="b27ef-138">В некоторых случаях для изучения доступны только файлы журнала ошибок.</span><span class="sxs-lookup"><span data-stu-id="b27ef-138">In some cases, only error log files are available for investigation.</span></span> <span data-ttu-id="b27ef-139">В этих условиях следует проверить, содержится ли в журнале ошибок сообщение об ошибке 26023 для порта TCP конечной точки зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="b27ef-139">In these cases, determine whether the error log contains error message 26023 for the TCP port of the database mirroring endpoint.</span></span> <span data-ttu-id="b27ef-140">Данная ошибка, уровень серьезности которой равен 16, может указывать на то, что не запущена конечная точка зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="b27ef-140">This error, which is severity 16, might indicate that the database mirroring endpoint is not started.</span></span> <span data-ttu-id="b27ef-141">Это сообщение может появиться даже в том случае, если представление каталога **sys.database_mirroring_endpoints** показывает, что конечная точка работает.</span><span class="sxs-lookup"><span data-stu-id="b27ef-141">This message can occur even if **sys.database_mirroring_endpoints** shows the endpoint state as started.</span></span>  
  
 <span data-ttu-id="b27ef-142">После устранения всех проблем повторно выполните на основном сервере команду ALTER DATABASE *имя_базы_данных* SET PARTNER.</span><span class="sxs-lookup"><span data-stu-id="b27ef-142">After resolving any issues that you encounter, rerun the ALTER DATABASE *database_name* SET PARTNER statement on the principal server.</span></span>  
  
### <a name="verifying-port-availability"></a><span data-ttu-id="b27ef-143">Проверка доступности порта</span><span class="sxs-lookup"><span data-stu-id="b27ef-143">Verifying Port Availability</span></span>  
 <span data-ttu-id="b27ef-144">При настройке сети для сеанса зеркального отображения базы данных убедитесь, что конечная точка зеркального отображения на каждом экземпляре сервера используется только процессом зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="b27ef-144">When you are configuring the network for a database mirroring session, make sure the database mirroring endpoint of each server instance is used by only the database mirroring process.</span></span> <span data-ttu-id="b27ef-145">Если порт, назначенный зеркальному отображению базы данных, прослушивается другим процессом, то процессы зеркального отображения других экземпляров сервера не смогут подключиться к этой конечной точке.</span><span class="sxs-lookup"><span data-stu-id="b27ef-145">If another process is listening on the port assigned to a database mirroring endpoint, the database mirroring processes of the other server instances cannot connect to the endpoint.</span></span>  
  
 <span data-ttu-id="b27ef-146">Для отображения всех портов, которые прослушивает сервер Windows, можно воспользоваться программой командной строки **netstat**.</span><span class="sxs-lookup"><span data-stu-id="b27ef-146">To display all the ports on which a Windows-based server is listening, use the **netstat** command-prompt utility.</span></span> <span data-ttu-id="b27ef-147">Синтаксис программы **netstat** зависит от версии операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="b27ef-147">The syntax for **netstat** depends on the version of the Windows operating system.</span></span> <span data-ttu-id="b27ef-148">Дополнительные сведения см. в документации по операционной системе.</span><span class="sxs-lookup"><span data-stu-id="b27ef-148">For more information, see the operating system documentation.</span></span>  
  
#### <a name="windows-server-2003-service-pack-1-sp1"></a><span data-ttu-id="b27ef-149">Windows Server 2003 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="b27ef-149">Windows Server 2003 Service Pack 1 (SP1)</span></span>  
 <span data-ttu-id="b27ef-150">Для просмотра прослушиваемых портов и открывших их процессов введите в командной строке Windows следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b27ef-150">To list listening ports and the processes that have those ports opened, enter the following command at the Windows command prompt:</span></span>  
  
 <span data-ttu-id="b27ef-151">**netstat -abn**</span><span class="sxs-lookup"><span data-stu-id="b27ef-151">**netstat -abn**</span></span>  
  
#### <a name="windows-server-2003-pre-sp1"></a><span data-ttu-id="b27ef-152">Windows Server 2003 (до пакета обновления SP1)</span><span class="sxs-lookup"><span data-stu-id="b27ef-152">Windows Server 2003 (pre-SP1)</span></span>  
 <span data-ttu-id="b27ef-153">Для просмотра прослушиваемых портов и открывших их процессов выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b27ef-153">To identify the listening ports and the processes that have those ports opened, follow these steps:</span></span>  
  
1.  <span data-ttu-id="b27ef-154">Получите идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="b27ef-154">Obtain the process ID.</span></span>  
  
     <span data-ttu-id="b27ef-155">Чтобы получить идентификатор процесса для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], подключитесь к экземпляру и выполните следующую инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b27ef-155">To learn the process ID of an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], connect to that instance and use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    SELECT SERVERPROPERTY('ProcessID')   
    ```  
  
     <span data-ttu-id="b27ef-156">Дополнительные сведения см. в разделе «SERVERPROPERTY (Transact-SQL)» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b27ef-156">For more information, see "SERVERPROPERTY (Transact-SQL)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="b27ef-157">Сопоставьте идентификатор процесса с данными, полученными командой **netstat**:</span><span class="sxs-lookup"><span data-stu-id="b27ef-157">Match the process ID with the output of the following **netstat** command:</span></span>  
  
     <span data-ttu-id="b27ef-158">**netstat -ano**</span><span class="sxs-lookup"><span data-stu-id="b27ef-158">**netstat -ano**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b27ef-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="b27ef-159">See Also</span></span>  
 <span data-ttu-id="b27ef-160">[ALTER ENDPOINT (Transact-SQL)](/sql/t-sql/statements/alter-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b27ef-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="b27ef-161">[Конечная точка зеркального отображения базы данных (SQL Server)](../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b27ef-161">[The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="b27ef-162">[Подготовка зеркальной базы данных к зеркальному отображению (SQL Server)](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b27ef-162">[Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="b27ef-163">[SERVERPROPERTY (Transact-SQL)](/sql/t-sql/functions/serverproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b27ef-163">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span></span>  
 <span data-ttu-id="b27ef-164">[Указание сетевого адреса сервера (зеркальное отображение базы данных)](../../database-engine/database-mirroring/specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="b27ef-164">[Specify a Server Network Address &#40;Database Mirroring&#41;](../../database-engine/database-mirroring/specify-a-server-network-address-database-mirroring.md) </span></span>  
 <span data-ttu-id="b27ef-165">[sys.database_mirroring_endpoints (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b27ef-165">[sys.database_mirroring_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql) </span></span>  
 [<span data-ttu-id="b27ef-166">Диагностика конфигурации зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b27ef-166">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/troubleshoot-database-mirroring-configuration-sql-server.md)  
  
  
