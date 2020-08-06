---
title: Переименование компьютера, на который установлен изолированный экземпляр SQL Server | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- remote login errors [SQL Server]
- standalone computer names [SQL Server]
- names [SQL Server], standalone instances of SQL Server
- renaming standalone instances of SQL Server
- sysservers system table
- removing remote logins
- deleting remote logins
- dropping remote logins
ms.assetid: bbaf1445-b8a2-4ebf-babe-17d8cf20b037
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 079348921900a7cbf880027433280253df1a9e30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740286"
---
# <a name="rename-a-computer-that-hosts-a-stand-alone-instance-of-sql-server"></a><span data-ttu-id="00857-102">Переименование компьютера, на который установлен изолированный экземпляр SQL Server</span><span class="sxs-lookup"><span data-stu-id="00857-102">Rename a Computer that Hosts a Stand-Alone Instance of SQL Server</span></span>
  <span data-ttu-id="00857-103">Если изменить имя компьютера, на котором работает [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], новое имя будет распознано в момент следующего запуска [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00857-103">When you change the name of the computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the new name is recognized during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup.</span></span> <span data-ttu-id="00857-104">Не нужно заново запускать программу установки, чтобы изменить имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="00857-104">You do not have to run Setup again to reset the computer name.</span></span> <span data-ttu-id="00857-105">Вместо этого следует выполнить следующие шаги для обновления системных метаданных, хранимых в представлении каталога sys.servers и возвращаемых системной функцией @@SERVERNAME .</span><span class="sxs-lookup"><span data-stu-id="00857-105">Instead, use the following steps to update system metadata that is stored in sys.servers and reported by the system function @@SERVERNAME.</span></span> <span data-ttu-id="00857-106">Обновите системные метаданные таким образом, чтобы отразить в них изменения в именах компьютеров для удаленных соединений и приложений, в которых используется системная функция @@SERVERNAME или которые запрашивают имя сервера в представлении каталога sys.servers.</span><span class="sxs-lookup"><span data-stu-id="00857-106">Update system metadata to reflect computer name changes for remote connections and applications that use @@SERVERNAME, or that query the server name from sys.servers.</span></span>  
  
 <span data-ttu-id="00857-107">Следующие действия нельзя использовать для переименования экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00857-107">The following steps cannot be used to rename an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="00857-108">Ими можно воспользоваться только для изменения части имени экземпляра, соответствующей имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="00857-108">They can be used only to rename the part of the instance name that corresponds to the computer name.</span></span> <span data-ttu-id="00857-109">Например, можно изменить имя компьютера MB1, на котором расположен экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с именем Instance1, на другое имя, например MB2.</span><span class="sxs-lookup"><span data-stu-id="00857-109">For example, you can change a computer named MB1 that hosts an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] named Instance1 to another name, such as MB2.</span></span> <span data-ttu-id="00857-110">Однако часть имени, представляющая собой имя экземпляра (Instance1), останется неизменной.</span><span class="sxs-lookup"><span data-stu-id="00857-110">However, the instance part of the name, Instance1, will remain unchanged.</span></span> <span data-ttu-id="00857-111">В данном примере \\\\*ИмяКомпьютера*\\*ИмяЭкземпляра* изменится с \\\MB1\Instance1 на \\\MB2\Instance1.</span><span class="sxs-lookup"><span data-stu-id="00857-111">In this example, the \\\\*ComputerName*\\*InstanceName* would be changed from \\\MB1\Instance1 to \\\MB2\Instance1.</span></span>  
  
 <span data-ttu-id="00857-112">**Before you begin**</span><span class="sxs-lookup"><span data-stu-id="00857-112">**Before you begin**</span></span>  
  
 <span data-ttu-id="00857-113">Прежде чем приступить к процессу переименования, обратите внимание на следующее:</span><span class="sxs-lookup"><span data-stu-id="00857-113">Before you begin the renaming process, review the following information:</span></span>  
  
-   <span data-ttu-id="00857-114">Если экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] является частью отказоустойчивого кластера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , переименование компьютера выполняется не так, как для изолированного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="00857-114">When an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is part of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, the computer renaming process differs from a computer that hosts a stand-alone instance.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="00857-115">не поддерживает переименование компьютеров, участвующих в репликации, за исключением репликации с доставкой журналов.</span><span class="sxs-lookup"><span data-stu-id="00857-115">does not support renaming computers that are involved in replication, except when you use log shipping with replication.</span></span> <span data-ttu-id="00857-116">Компьютер-получатель в доставке журнала может быть переименован, если компьютер-источник окончательно потерян.</span><span class="sxs-lookup"><span data-stu-id="00857-116">The secondary computer in log shipping can be renamed if the primary computer is permanently lost.</span></span> <span data-ttu-id="00857-117">Дополнительные сведения см. в статье [Репликация и доставка журналов (SQL Server)](../log-shipping/log-shipping-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="00857-117">For more information, see [Log Shipping and Replication &#40;SQL Server&#41;](../log-shipping/log-shipping-and-replication-sql-server.md).</span></span>  
  
-   <span data-ttu-id="00857-118">После переименования компьютера, настроенного для использования служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] могут оказаться недоступными.</span><span class="sxs-lookup"><span data-stu-id="00857-118">When you rename a computer that is configured to use [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] might not be available after the computer name change.</span></span> <span data-ttu-id="00857-119">Дополнительные сведения см. в разделе [Переименование компьютера, на котором установлен сервер отчетов](../../reporting-services/report-server/rename-a-report-server-computer.md).</span><span class="sxs-lookup"><span data-stu-id="00857-119">For more information, see [Rename a Report Server Computer](../../reporting-services/report-server/rename-a-report-server-computer.md).</span></span>  
  
-   <span data-ttu-id="00857-120">Если компьютер настроен для использования зеркального отображения базы данных, перед его переименованием оно должно быть отключено.</span><span class="sxs-lookup"><span data-stu-id="00857-120">When you rename a computer that is configured to use database mirroring, you must turn off database mirroring before the renaming operation.</span></span> <span data-ttu-id="00857-121">После этого зеркальное отображение необходимо вновь установить для нового имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="00857-121">Then, re-establish database mirroring with the new computer name.</span></span> <span data-ttu-id="00857-122">Метаданные для зеркального отображения базы данных не будут обновлены автоматически для отражения нового имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="00857-122">Metadata for database mirroring will not be updated automatically to reflect the new computer name.</span></span> <span data-ttu-id="00857-123">Выполните следующие шаги, чтобы обновить системные метаданные.</span><span class="sxs-lookup"><span data-stu-id="00857-123">Use the following steps to update system metadata.</span></span>  
  
-   <span data-ttu-id="00857-124">Пользователи, которые подключаются к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] через группу Windows, в которой имя компьютера задано жестко, могут лишиться возможности подключения к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00857-124">Users who connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through a Windows group that uses a hard-coded reference to the computer name might not be able to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="00857-125">Это может произойти после переименования, если в группе Windows останется прежнее имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="00857-125">This can occur after the rename if the Windows group specifies the old computer name.</span></span> <span data-ttu-id="00857-126">Чтобы убедиться в том, что возможно соединение с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с использованием таких групп Windows после операции переименования, обновите группу Windows для указания нового имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="00857-126">To ensure that such Windows groups have [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connectivity following the renaming operation, update the Windows group to specify the new computer name.</span></span>  
  
 <span data-ttu-id="00857-127">Подключение к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью нового имени компьютера станет возможно после перезапуска [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00857-127">You can connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the new computer name after you have restarted [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="00857-128">Чтобы убедиться в том, что системная функция @@SERVERNAME возвращает новое имя локального экземпляра сервера, необходимо вручную выполнить следующую процедуру, применяющуюся в сценарии пользователя.</span><span class="sxs-lookup"><span data-stu-id="00857-128">To ensure that @@SERVERNAME returns the updated name of the local server instance, you should manually run the following procedure that applies to your scenario.</span></span> <span data-ttu-id="00857-129">Какая именно процедура должна быть выполнена, зависит от того, установлен ли на компьютере именованный экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]или экземпляр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="00857-129">The procedure you use depends on whether you are updating a computer that hosts a default or named instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-rename-a-computer-that-hosts-a-stand-alone-instance-of-ssnoversion"></a><span data-ttu-id="00857-130">Переименование компьютера, на котором расположен изолированный экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00857-130">To rename a computer that hosts a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="00857-131">Для компьютера с измененным именем, на котором установлен экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]по умолчанию, следует выполнить следующие процедуры.</span><span class="sxs-lookup"><span data-stu-id="00857-131">For a renamed computer that hosts a default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], run the following procedures:</span></span>  
  
    ```  
    sp_dropserver <old_name>;  
    GO  
    sp_addserver <new_name>, local;  
    GO  
    ```  
  
     <span data-ttu-id="00857-132">Повторно запустите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00857-132">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="00857-133">Для компьютера с измененным именем, на котором установлен именованный экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], следует выполнить следующие процедуры.</span><span class="sxs-lookup"><span data-stu-id="00857-133">For a renamed computer that hosts a named instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], run the following procedures:</span></span>  
  
    ```  
    sp_dropserver <old_name\instancename>;  
    GO  
    sp_addserver <new_name\instancename>, local;  
    GO  
    ```  
  
     <span data-ttu-id="00857-134">Повторно запустите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00857-134">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="after-the-renaming-operation"></a><span data-ttu-id="00857-135">После операции переименования</span><span class="sxs-lookup"><span data-stu-id="00857-135">After the Renaming Operation</span></span>  
 <span data-ttu-id="00857-136">После переименования компьютера все соединения, которые используют прежнее имя, должны подключаться с помощью нового имени.</span><span class="sxs-lookup"><span data-stu-id="00857-136">After a computer has been renamed, any connections that used the old computer name must connect by using the new name.</span></span>  
  
#### <a name="to-verify-that-the-renaming-operation-has-completed-successfully"></a><span data-ttu-id="00857-137">Подтверждение успешного завершения переименования</span><span class="sxs-lookup"><span data-stu-id="00857-137">To verify that the renaming operation has completed successfully</span></span>  
  
-   <span data-ttu-id="00857-138">Выберите данные из @@SERVERNAME или sys.servers.</span><span class="sxs-lookup"><span data-stu-id="00857-138">Select information from either @@SERVERNAME or sys.servers.</span></span> <span data-ttu-id="00857-139">Функция @@SERVERNAME возвращает новое имя, а в таблице sys.servers отображается новое имя.</span><span class="sxs-lookup"><span data-stu-id="00857-139">The @@SERVERNAME function will return the new name, and the sys.servers table will show the new name.</span></span> <span data-ttu-id="00857-140">В следующем примере показано использование @@SERVERNAME .</span><span class="sxs-lookup"><span data-stu-id="00857-140">The following example shows the use of @@SERVERNAME.</span></span>  
  
    ```  
    SELECT @@SERVERNAME AS 'Server Name';  
    ```  
  
## <a name="additional-considerations"></a><span data-ttu-id="00857-141">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="00857-141">Additional Considerations</span></span>  
 <span data-ttu-id="00857-142">**Удаленные имена входа** — если на компьютере имеются удаленные имена входа, при запуске хранимой процедуры **sp_dropserver** может возникнуть ошибка, аналогичная следующей:</span><span class="sxs-lookup"><span data-stu-id="00857-142">**Remote Logins** - If the computer has any remote logins, running **sp_dropserver** might generate an error similar to the following:</span></span>  
  
 `Server: Msg 15190, Level 16, State 1, Procedure sp_dropserver, Line 44 There are still remote logins for the server 'SERVER1'.`  
  
 <span data-ttu-id="00857-143">Чтобы исправить ошибку, необходимо удалить имена для удаленного входа в систему для этого сервера.</span><span class="sxs-lookup"><span data-stu-id="00857-143">To resolve the error, you must drop remote logins for this server.</span></span>  
  
#### <a name="to-drop-remote-logins"></a><span data-ttu-id="00857-144">Удаление удаленных входов в систему</span><span class="sxs-lookup"><span data-stu-id="00857-144">To drop remote logins</span></span>  
  
-   <span data-ttu-id="00857-145">В случае с экземпляром по умолчанию, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="00857-145">For a default instance, run the following procedure:</span></span>  
  
    ```  
    sp_dropremotelogin old_name;  
    GO  
    ```  
  
-   <span data-ttu-id="00857-146">В случае с именованным экземпляром, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="00857-146">For a named instance, run the following procedure:</span></span>  
  
    ```  
    sp_dropremotelogin old_name\instancename;  
    GO  
    ```  
  
 <span data-ttu-id="00857-147">**Конфигурации связанных серверов** . Операция переименования компьютера повлияет на конфигурации связанных серверов.</span><span class="sxs-lookup"><span data-stu-id="00857-147">**Linked Server Configurations** - Linked server configurations will be affected by the computer renaming operation.</span></span> <span data-ttu-id="00857-148">Используйте хранимые процедуры `sp_addlinkedserver` или `sp_setnetname` для обновления ссылок на имена компьютеров.</span><span class="sxs-lookup"><span data-stu-id="00857-148">Use `sp_addlinkedserver` or `sp_setnetname` to update computer name references.</span></span> <span data-ttu-id="00857-149">Дополнительные сведения см. в статье [sp_addlinkedserver (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) или [sp_setnetname (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-setnetname-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="00857-149">For more information, see the [sp_addlinkedserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) or [sp_setnetname &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-setnetname-transact-sql).</span></span>  
  
 <span data-ttu-id="00857-150">**Имена-псевдонимы клиентов**. Операция переименования компьютера повлияет на псевдонимы клиентов, в которых используются именованные каналы.</span><span class="sxs-lookup"><span data-stu-id="00857-150">**Client Alias Names** - Client aliases that use named pipes will be affected by the computer renaming operation.</span></span> <span data-ttu-id="00857-151">Например, если псевдоним «PROD_SRVR» указывает на SRVR1 и в нем используется протокол именованных каналов, то имя канала будет выглядеть следующим образом: `\\SRVR1\pipe\sql\query`.</span><span class="sxs-lookup"><span data-stu-id="00857-151">For example, if an alias "PROD_SRVR" was created to point to SRVR1 and uses the named pipes protocol, the pipe name will look like `\\SRVR1\pipe\sql\query`.</span></span> <span data-ttu-id="00857-152">После переименования компьютера путь именованного канала станет недействительным.</span><span class="sxs-lookup"><span data-stu-id="00857-152">After the computer is renamed, the path of the named pipe will no longer be valid and.</span></span> <span data-ttu-id="00857-153">Дополнительные сведения об именованных каналах см. в разделе [Создание допустимой строки подключения, использующей протокол именованных каналов](https://go.microsoft.com/fwlink/?LinkId=111063).</span><span class="sxs-lookup"><span data-stu-id="00857-153">For more information about named pipes, see the [Creating a Valid Connection String Using Named Pipes](https://go.microsoft.com/fwlink/?LinkId=111063).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00857-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="00857-154">See Also</span></span>  
 [<span data-ttu-id="00857-155">Установка SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="00857-155">Install SQL Server 2014</span></span>](../../database-engine/install-windows/install-sql-server.md)  
  
  
