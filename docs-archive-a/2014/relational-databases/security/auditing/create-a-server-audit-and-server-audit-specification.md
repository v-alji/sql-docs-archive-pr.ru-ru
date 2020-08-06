---
title: Создание аудита сервера и спецификации аудита сервера | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.SQLAUDIT.FILTER.F1
- sql12.swb.sqlaudit.srvaudit.general.f1
- sql12.swb.sqlaudit.general.f1
helpviewer_keywords:
- server audit [SQL Server]
- audits [SQL Server], specification
ms.assetid: 6624b1ab-7ec8-44ce-8292-397edf644394
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: a648a975ae9f2c4139a8ebd584f6998f4d0fa1a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732514"
---
# <a name="create-a-server-audit-and-server-audit-specification"></a><span data-ttu-id="ace29-102">Создание аудита сервера и спецификации аудита сервера</span><span class="sxs-lookup"><span data-stu-id="ace29-102">Create a Server Audit and Server Audit Specification</span></span>
  <span data-ttu-id="ace29-103">В данном разделе описывается процесс создания аудита сервера и спецификации аудита сервера в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ace29-103">This topic describes how to create a server audit and server audit specification in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ace29-104">*Аудит* экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] или базы данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] включает в себя отслеживание и протоколирование событий, происходящих в системе.</span><span class="sxs-lookup"><span data-stu-id="ace29-104">*Auditing* an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database involves tracking and logging events that occur on the system.</span></span> <span data-ttu-id="ace29-105">Объект *Подсистема аудита SQL Server* объединяет отдельные экземпляры действий или групп действий уровня сервера или базы данных, за которыми нужно проводить наблюдение.</span><span class="sxs-lookup"><span data-stu-id="ace29-105">The *SQL Server Audit* object collects a single instance of server- or database-level actions and groups of actions to monitor.</span></span> <span data-ttu-id="ace29-106">Аудит работает на уровне экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ace29-106">The audit is at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance level.</span></span> <span data-ttu-id="ace29-107">На одном экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] может существовать несколько аудитов.</span><span class="sxs-lookup"><span data-stu-id="ace29-107">You can have multiple audits per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="ace29-108">Объект *Спецификация аудита сервера* принадлежит аудиту.</span><span class="sxs-lookup"><span data-stu-id="ace29-108">The *Server Audit Specification* object belongs to an audit.</span></span> <span data-ttu-id="ace29-109">Для каждого аудита вы можете создать один объект спецификации аудита сервера, поскольку они оба создаются в области экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ace29-109">You can create one server audit specification per audit, because both are created at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance scope.</span></span> <span data-ttu-id="ace29-110">Дополнительные сведения см. в статье [Подсистема аудита SQL Server (ядро СУБД)](sql-server-audit-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="ace29-110">For more information, see [SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md).</span></span>  
  
 <span data-ttu-id="ace29-111">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="ace29-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ace29-112">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="ace29-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ace29-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="ace29-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ace29-114">Безопасность</span><span class="sxs-lookup"><span data-stu-id="ace29-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ace29-115">**Создание аудита сервера и спецификации аудита сервера с помощью:**</span><span class="sxs-lookup"><span data-stu-id="ace29-115">**To create a server audit and server audit specification, using:**</span></span>  
  
     [<span data-ttu-id="ace29-116">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ace29-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ace29-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ace29-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ace29-118">Перед началом</span><span class="sxs-lookup"><span data-stu-id="ace29-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ace29-119">Ограничения</span><span class="sxs-lookup"><span data-stu-id="ace29-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ace29-120">Аудит должен существовать, прежде чем для него будет создана спецификация аудита сервера.</span><span class="sxs-lookup"><span data-stu-id="ace29-120">An audit must exist before creating a server audit specification for it.</span></span> <span data-ttu-id="ace29-121">Спецификация аудита сервера после создания находится в отключенном состоянии.</span><span class="sxs-lookup"><span data-stu-id="ace29-121">When a server audit specification is created, it is in a disabled state.</span></span>  
  
-   <span data-ttu-id="ace29-122">Инструкция CREATE SERVER AUDIT относится к области транзакции.</span><span class="sxs-lookup"><span data-stu-id="ace29-122">The CREATE SERVER AUDIT statement is in a transaction's scope.</span></span> <span data-ttu-id="ace29-123">Если выполняется откат транзакции, происходит также откат этой инструкции.</span><span class="sxs-lookup"><span data-stu-id="ace29-123">If the transaction is rolled back, the statement is also rolled back.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ace29-124">безопасность</span><span class="sxs-lookup"><span data-stu-id="ace29-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ace29-125">Permissions</span><span class="sxs-lookup"><span data-stu-id="ace29-125">Permissions</span></span>  
  
-   <span data-ttu-id="ace29-126">Чтобы создать, изменить или удалить аудит сервера, участникам требуется разрешение ALTER ANY SERVER AUDIT или CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="ace29-126">To create, alter, or drop a server audit, principals require the ALTER ANY SERVER AUDIT or the CONTROL SERVER permission.</span></span>  
  
-   <span data-ttu-id="ace29-127">Пользователи с разрешением ALTER ANY SERVER AUDIT могут создавать спецификации аудита сервера и привязывать их к любому аудиту.</span><span class="sxs-lookup"><span data-stu-id="ace29-127">Users with the ALTER ANY SERVER AUDIT permission can create server audit specifications and bind them to any audit.</span></span>  
  
-   <span data-ttu-id="ace29-128">После того как создана спецификация аудита сервера, ее могут просмотреть участники с разрешениями CONTROL SERVER или ALTER ANY SERVER AUDIT, учетная запись sysadmin или участники, имеющие явный доступ к аудиту.</span><span class="sxs-lookup"><span data-stu-id="ace29-128">After a server audit specification is created, it can be viewed by principals with the CONTROL SERVER or ALTER ANY SERVER AUDIT permissions, the sysadmin account, or principals having explicit access to the audit.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ace29-129">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ace29-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="ace29-130">Создание аудита сервера</span><span class="sxs-lookup"><span data-stu-id="ace29-130">To create a server audit</span></span>  
  
1.  <span data-ttu-id="ace29-131">В обозревателе объектов раскройте папку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="ace29-131">In Object Explorer, expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="ace29-132">Щелкните правой кнопкой мыши папку **Аудиты** и выберите пункт **Создать аудит...** .</span><span class="sxs-lookup"><span data-stu-id="ace29-132">Right-click the **Audits** folder and select **New Audit...**.</span></span>  
  
     <span data-ttu-id="ace29-133">На странице **Общие** диалогового окна **Создание аудита** доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="ace29-133">The following options are available on the **General** page of the **Create Audit** dialog box.</span></span>  
  
     <span data-ttu-id="ace29-134">**Имя аудита**</span><span class="sxs-lookup"><span data-stu-id="ace29-134">**Audit name**</span></span>  
     <span data-ttu-id="ace29-135">Имя аудита.</span><span class="sxs-lookup"><span data-stu-id="ace29-135">The name of the audit.</span></span> <span data-ttu-id="ace29-136">Формируется автоматически при создании нового аудита, но может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="ace29-136">This is generated automatically when you create a new audit but is editable.</span></span>  
  
     <span data-ttu-id="ace29-137">**Задержка очереди (в миллисекундах)**</span><span class="sxs-lookup"><span data-stu-id="ace29-137">**Queue delay (in milliseconds)**</span></span>  
     <span data-ttu-id="ace29-138">Определяет задержку в миллисекундах, после которой продолжается выполнение действий аудита.</span><span class="sxs-lookup"><span data-stu-id="ace29-138">Specifies the amount of time in milliseconds that can elapse before audit actions are forced to be processed.</span></span>  <span data-ttu-id="ace29-139">Значение 0 соответствует синхронной доставке.</span><span class="sxs-lookup"><span data-stu-id="ace29-139">A value of 0 indicates synchronous delivery.</span></span> <span data-ttu-id="ace29-140">Минимальное значение по умолчанию — **1000** (1 секунда).</span><span class="sxs-lookup"><span data-stu-id="ace29-140">The default minimum value is **1000** (1 second).</span></span> <span data-ttu-id="ace29-141">Максимальное значение составляет 2 147 483 647 (2 147 483,647 секунд или 24 дня, 20 часов, 31 минута и 23,647 секунд).</span><span class="sxs-lookup"><span data-stu-id="ace29-141">The maximum is 2,147,483,647 (2,147,483.647 seconds or 24 days, 20 hours, 31 minutes, 23.647 seconds).</span></span>  
  
     <span data-ttu-id="ace29-142">**При сбое журнала аудита:**</span><span class="sxs-lookup"><span data-stu-id="ace29-142">**On Audit Log Failure:**</span></span>  
     <span data-ttu-id="ace29-143">**Продолжить**</span><span class="sxs-lookup"><span data-stu-id="ace29-143">**Continue**</span></span>  
     [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="ace29-144">работа продолжается.</span><span class="sxs-lookup"><span data-stu-id="ace29-144">operations continue.</span></span> <span data-ttu-id="ace29-145">Записи аудита не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="ace29-145">Audit records are not retained.</span></span> <span data-ttu-id="ace29-146">Аудит продолжает попытки регистрации событий и будет возобновлен, если причина сбоя будет устранена.</span><span class="sxs-lookup"><span data-stu-id="ace29-146">The audit continues to attempt to log events and will resume if the failure condition is resolved.</span></span> <span data-ttu-id="ace29-147">Выбор варианта **Продолжить** разрешает непроверенные действия, которые могут нарушать политики безопасности.</span><span class="sxs-lookup"><span data-stu-id="ace29-147">Selecting the **Continue** option can allow unaudited activity which could violate your security policies.</span></span> <span data-ttu-id="ace29-148">Выберите этот параметр, если продолжение операции компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] является более важным, чем сохранение полного аудита.</span><span class="sxs-lookup"><span data-stu-id="ace29-148">Select this option when continuing operation of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] is more important than maintaining a complete audit.</span></span> <span data-ttu-id="ace29-149">Это параметр выбирается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ace29-149">This is the default selection.</span></span>  
  
     <span data-ttu-id="ace29-150">**Завершение работы сервера**</span><span class="sxs-lookup"><span data-stu-id="ace29-150">**Shut down server**</span></span>  
     <span data-ttu-id="ace29-151">Приводит к остановке сервера, когда экземпляр сервера, который выполняет запись по назначению, не может записать данные в цель аудита.</span><span class="sxs-lookup"><span data-stu-id="ace29-151">Forces a server shut down when the server instance writing to the target cannot write data to the audit target.</span></span> <span data-ttu-id="ace29-152">Имя входа, выполняющее эту команду, должно иметь разрешение `SHUTDOWN`.</span><span class="sxs-lookup"><span data-stu-id="ace29-152">The login issuing this must have the `SHUTDOWN` permission.</span></span> <span data-ttu-id="ace29-153">Если учетная запись не имеет этого разрешения, то функция завершится неуспешно и будет выдано сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ace29-153">If the logon does not have this permission, this function will fail and an error message will be raised.</span></span> <span data-ttu-id="ace29-154">Отсутствуют события аудита.</span><span class="sxs-lookup"><span data-stu-id="ace29-154">No audited events occur.</span></span> <span data-ttu-id="ace29-155">Выберите этот параметр, если сбой аудита может нанести ущерб безопасности или целостности системы.</span><span class="sxs-lookup"><span data-stu-id="ace29-155">Select this option when an audit failure could compromise the security or integrity of the system.</span></span>  
  
     <span data-ttu-id="ace29-156">**Ошибка операции**</span><span class="sxs-lookup"><span data-stu-id="ace29-156">**Fail operation**</span></span>  
     <span data-ttu-id="ace29-157">В случае если [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] не может выполнить запись в журнал аудита, этот параметр вызывает завершение действий с базами данных с ошибкой, если в противном случае они бы привели к возникновению событий аудита.</span><span class="sxs-lookup"><span data-stu-id="ace29-157">In cases where the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit cannot write to the audit log this option causes database actions to fail if they would otherwise cause audited events.</span></span> <span data-ttu-id="ace29-158">Отсутствуют события аудита.</span><span class="sxs-lookup"><span data-stu-id="ace29-158">No audited events occur.</span></span> <span data-ttu-id="ace29-159">Действия, которые не вызывают события аудита, можно продолжить.</span><span class="sxs-lookup"><span data-stu-id="ace29-159">Actions which do not cause audited events can continue.</span></span> <span data-ttu-id="ace29-160">Аудит продолжает попытки регистрации событий и будет возобновлен, если причина сбоя будет устранена.</span><span class="sxs-lookup"><span data-stu-id="ace29-160">The audit continues to attempt to log events and will resume if the failure condition is resolved.</span></span> <span data-ttu-id="ace29-161">Выберите этот параметр, если обеспечение полного аудита более важно, чем полный доступ к компоненту [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ace29-161">Select this option when maintaining a complete audit is more important than full access to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="ace29-162">Когда аудит находится в состоянии сбоя, выделенное административное соединение может продолжать выполнять подвергающиеся аудиту события.</span><span class="sxs-lookup"><span data-stu-id="ace29-162">When the audit is in a failed state, the Dedicated Administrator Connection can continue to perform audited events.</span></span>  
  
     <span data-ttu-id="ace29-163">Список**Назначение аудита**</span><span class="sxs-lookup"><span data-stu-id="ace29-163">**Audit destination** list</span></span>  
     <span data-ttu-id="ace29-164">Указывает цель для данных аудита.</span><span class="sxs-lookup"><span data-stu-id="ace29-164">Specifies the target for auditing data.</span></span> <span data-ttu-id="ace29-165">Возможные варианты — двоичный файл, журнал событий приложений Windows или журнал безопасности Windows.</span><span class="sxs-lookup"><span data-stu-id="ace29-165">The available options are a binary file, the Windows Application log, or the Windows Security log.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="ace29-166">не может выполнить запись в журнал безопасности Windows без настройки дополнительных параметров Windows.</span><span class="sxs-lookup"><span data-stu-id="ace29-166">cannot write to the Windows Security log without configuring additional settings in Windows.</span></span> <span data-ttu-id="ace29-167">Дополнительные сведения см. в статье [Запись событий подсистемы аудита SQL Server в журнал безопасности](write-sql-server-audit-events-to-the-security-log.md).</span><span class="sxs-lookup"><span data-stu-id="ace29-167">For more information, see [Write SQL Server Audit Events to the Security Log](write-sql-server-audit-events-to-the-security-log.md).</span></span>  
  
     <span data-ttu-id="ace29-168">**Путь к файлу**</span><span class="sxs-lookup"><span data-stu-id="ace29-168">**File path**</span></span>  
     <span data-ttu-id="ace29-169">Указывает местоположение папки, в которую записываются данные аудита, если **Тип назначения аудита** — файл.</span><span class="sxs-lookup"><span data-stu-id="ace29-169">Specifies the location of the folder where audit data is written when the **Audit destination** is a file.</span></span>  
  
     <span data-ttu-id="ace29-170">**Кнопка с многоточием (...)**</span><span class="sxs-lookup"><span data-stu-id="ace29-170">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="ace29-171">Открывает диалоговое окно " **расположение папки —**_server_name_ ", чтобы указать путь к файлу или создать папку, в которую записывается файл аудита.</span><span class="sxs-lookup"><span data-stu-id="ace29-171">Opens the **Locate Folder -**_server_name_ dialog box to specify a file path or create a folder where the audit file is written.</span></span>  
  
     <span data-ttu-id="ace29-172">**Максимальное количество файлов аудита:**</span><span class="sxs-lookup"><span data-stu-id="ace29-172">**Audit File Maximum Limit:**</span></span>  
     <span data-ttu-id="ace29-173">**Максимальное число файлов продолжения**</span><span class="sxs-lookup"><span data-stu-id="ace29-173">**Maximum rollover files**</span></span>  
     <span data-ttu-id="ace29-174">Указывает, что при достижении максимального числа файлов аудита самые старые файлы аудита перезаписываются новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="ace29-174">Specifies that, when the maximum number of audit files is reached, the oldest audit files are overwritten by new file content.</span></span>  
  
     <span data-ttu-id="ace29-175">**Максимальное число файлов**</span><span class="sxs-lookup"><span data-stu-id="ace29-175">**Maximum files**</span></span>  
     <span data-ttu-id="ace29-176">Указывает, что при достижении максимального числа файлов аудита любое действие, которое вызывает создание дополнительных событий аудита, завершится с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ace29-176">Specifies that, when the maximum number of audit files is reached, any action that causes additional audit events to be generated will fail with an error.</span></span>  
  
     <span data-ttu-id="ace29-177">Флажок**Неограниченное количество**</span><span class="sxs-lookup"><span data-stu-id="ace29-177">**Unlimited** check box</span></span>  
     <span data-ttu-id="ace29-178">При установке флажка **Неограниченное количество** для параметра **Максимальное число файлов продолжения** отсутствует ограничение на число создаваемых файлов аудита.</span><span class="sxs-lookup"><span data-stu-id="ace29-178">When the **Unlimited** check box under **Maximum rollover files** is selected, there is no limit imposed on the number of audit files that will be created.</span></span> <span data-ttu-id="ace29-179">Флажок **Неограниченное количество** установлен по умолчанию и используется для параметров **Максимальное число файлов продолжения** и **Максимальное число файлов** .</span><span class="sxs-lookup"><span data-stu-id="ace29-179">The **Unlimited** check box is selected by default and applies to both the **Maximum rollover files** and **Maximum files** selections.</span></span>  
  
     <span data-ttu-id="ace29-180">Поле**Количество файлов**</span><span class="sxs-lookup"><span data-stu-id="ace29-180">**Number of files** box</span></span>  
     <span data-ttu-id="ace29-181">Указывает количество создаваемых файлов аудита, до 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="ace29-181">Specifies the number of audit files to be created, up to 2,147,483,647.</span></span> <span data-ttu-id="ace29-182">Этот параметр доступен, только если флажок **Неограниченное количество** снят.</span><span class="sxs-lookup"><span data-stu-id="ace29-182">This option is only available if **Unlimited** is unchecked.</span></span>  
  
     <span data-ttu-id="ace29-183">**Максимальный размер файла**</span><span class="sxs-lookup"><span data-stu-id="ace29-183">**Maximum file size**</span></span>  
     <span data-ttu-id="ace29-184">Определяет максимальный размер для файла аудита, в мегабайтах (МБ), гигабайтах (ГБ) или терабайтах (ТБ).</span><span class="sxs-lookup"><span data-stu-id="ace29-184">Specifies the maximum size for an audit file in either megabytes (MB), gigabytes (GB), or terabytes (TB).</span></span> <span data-ttu-id="ace29-185">Вы можете задать значение от 1 024 МБ до 2 147 483 647 TB.</span><span class="sxs-lookup"><span data-stu-id="ace29-185">You can specify between 1024 MB and 2,147,483,647 TB.</span></span> <span data-ttu-id="ace29-186">Установка флажка в поле **Неограниченное количество** не налагает ограничения на размер файла.</span><span class="sxs-lookup"><span data-stu-id="ace29-186">Selecting the **Unlimited** check box does not place a limit on the size of the file.</span></span> <span data-ttu-id="ace29-187">При указании значения менее 1 024 МБ возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="ace29-187">Specifying a value lower than 1024 MB will fail, returning an error.</span></span> <span data-ttu-id="ace29-188">Флажок **Неограниченное количество** установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ace29-188">The **Unlimited** check box is selected by default.</span></span>  
  
     <span data-ttu-id="ace29-189">Флажок**Резервирование места на диске**</span><span class="sxs-lookup"><span data-stu-id="ace29-189">**Reserve disk space** check box</span></span>  
     <span data-ttu-id="ace29-190">Указывает, что пространство, заранее выделенное на диске, равно указанному максимальному размеру файла.</span><span class="sxs-lookup"><span data-stu-id="ace29-190">Specifies that space is pre-allocated on the disk equal to the specified maximum file size.</span></span> <span data-ttu-id="ace29-191">Этот параметр можно использовать, только если не установлен флажок **Неограниченное количество** для параметра **Максимальный размер файла** .</span><span class="sxs-lookup"><span data-stu-id="ace29-191">This setting can only be used if the **Unlimited** check box under **Maximum file size** is not selected.</span></span> <span data-ttu-id="ace29-192">Это флажок по умолчанию не установлен.</span><span class="sxs-lookup"><span data-stu-id="ace29-192">This check box is not selected by default.</span></span>  
  
3.  <span data-ttu-id="ace29-193">Кроме того, на странице **Фильтр** введите предикат или предложение `WHERE` относительно аудита сервера для указания дополнительных параметров, недоступных на странице **Общие** .</span><span class="sxs-lookup"><span data-stu-id="ace29-193">Optionally, on the **Filter** page, enter a predicate, or `WHERE` clause, to the server audit to specify additional options not available from the **General** page.</span></span> <span data-ttu-id="ace29-194">Заключите предикат в круглые скобки, например: `(object_name = 'EmployeesTable')`.</span><span class="sxs-lookup"><span data-stu-id="ace29-194">Enclose the predicate in parentheses; for example: `(object_name = 'EmployeesTable')`.</span></span>  
  
4.  <span data-ttu-id="ace29-195">После завершения выбора параметров нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ace29-195">When you are finished selecting options, click **OK**.</span></span>  
  
#### <a name="to-create-a-server-audit-specification"></a><span data-ttu-id="ace29-196">Создание спецификации аудита сервера</span><span class="sxs-lookup"><span data-stu-id="ace29-196">To create a server audit specification</span></span>  
  
1.  <span data-ttu-id="ace29-197">В обозревателе объектов щелкните знак «плюс», чтобы развернуть папку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="ace29-197">In Object Explorer, click the plus sign to expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="ace29-198">Щелкните правой кнопкой мыши папку **Спецификации аудита сервера** и выберите пункт **Создать спецификацию аудита сервера...** .</span><span class="sxs-lookup"><span data-stu-id="ace29-198">Right-click the **Server Audit Specifications** folder and select **New Server Audit Specification...**.</span></span>  
  
     <span data-ttu-id="ace29-199">В диалоговом окне **Создание спецификации аудита сервера** доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="ace29-199">The following options are available on the **Create Server Audit Specification** dialog box.</span></span>  
  
     <span data-ttu-id="ace29-200">**имя**;</span><span class="sxs-lookup"><span data-stu-id="ace29-200">**Name**</span></span>  
     <span data-ttu-id="ace29-201">Имя спецификации аудита сервера.</span><span class="sxs-lookup"><span data-stu-id="ace29-201">The name of the server audit specification.</span></span> <span data-ttu-id="ace29-202">Этот текст формируется автоматически во время создания новой спецификации аудита сервера, однако он доступен для изменения.</span><span class="sxs-lookup"><span data-stu-id="ace29-202">This is generated automatically when you create a new server audit specification but is editable.</span></span>  
  
     <span data-ttu-id="ace29-203">**Аудит**</span><span class="sxs-lookup"><span data-stu-id="ace29-203">**Audit**</span></span>  
     <span data-ttu-id="ace29-204">Имя существующего аудита сервера.</span><span class="sxs-lookup"><span data-stu-id="ace29-204">The name of an existing server audit.</span></span> <span data-ttu-id="ace29-205">Введите имя аудита или выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="ace29-205">Either type in the name of the audit or select it from the list.</span></span>  
  
     <span data-ttu-id="ace29-206">**Тип действия аудита**</span><span class="sxs-lookup"><span data-stu-id="ace29-206">**Audit Action Type**</span></span>  
     <span data-ttu-id="ace29-207">Указывает группы действий аудита на уровне сервера и действия аудита для захвата.</span><span class="sxs-lookup"><span data-stu-id="ace29-207">Specifies the server-level audit action groups and audit actions to capture.</span></span> <span data-ttu-id="ace29-208">Список групп действий аудита на уровне сервера и действий аудита, а также описание содержащихся в них событий см. в статье [Действия и группы действий подсистемы аудита SQL Server](sql-server-audit-action-groups-and-actions.md).</span><span class="sxs-lookup"><span data-stu-id="ace29-208">For the list of server-level audit action groups and audit actions and a description of the events they contain, see [SQL Server Audit Action Groups and Actions](sql-server-audit-action-groups-and-actions.md).</span></span>  
  
     <span data-ttu-id="ace29-209">**Схема объекта**</span><span class="sxs-lookup"><span data-stu-id="ace29-209">**Object Schema**</span></span>  
     <span data-ttu-id="ace29-210">Отображает схему для указанного **Имени объекта**.</span><span class="sxs-lookup"><span data-stu-id="ace29-210">Displays the schema for the specified **Object Name**.</span></span>  
  
     <span data-ttu-id="ace29-211">**Имени объекта**</span><span class="sxs-lookup"><span data-stu-id="ace29-211">**Object Name**</span></span>  
     <span data-ttu-id="ace29-212">Имя объекта для аудита.</span><span class="sxs-lookup"><span data-stu-id="ace29-212">The name of the object to audit.</span></span> <span data-ttu-id="ace29-213">Доступно только для действий аудита и неприменимо к группам аудита.</span><span class="sxs-lookup"><span data-stu-id="ace29-213">This is only available for audit actions; it does not apply to audit groups.</span></span>  
  
     <span data-ttu-id="ace29-214">**Кнопка с многоточием (...)**</span><span class="sxs-lookup"><span data-stu-id="ace29-214">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="ace29-215">Открывает диалоговое окно **Выбор объектов** для просмотра и выбора доступного объекта на основе указанного **Типа действия аудита**.</span><span class="sxs-lookup"><span data-stu-id="ace29-215">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Audit Action Type**.</span></span>  
  
     <span data-ttu-id="ace29-216">**Имя участника**</span><span class="sxs-lookup"><span data-stu-id="ace29-216">**Principal Name**</span></span>  
     <span data-ttu-id="ace29-217">Учетная запись для фильтрации аудита для объекта, подвергнутого аудиту.</span><span class="sxs-lookup"><span data-stu-id="ace29-217">The account to filter the audit by for the object being audited.</span></span>  
  
     <span data-ttu-id="ace29-218">**Кнопка с многоточием (...)**</span><span class="sxs-lookup"><span data-stu-id="ace29-218">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="ace29-219">Открывает диалоговое окно **Выбор объектов** для просмотра и выбора доступного объекта с учетом указанного параметра **Имя объекта**.</span><span class="sxs-lookup"><span data-stu-id="ace29-219">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Object Name**.</span></span>  
  
3.  <span data-ttu-id="ace29-220">По завершении нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ace29-220">When you are finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ace29-221">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ace29-221">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="ace29-222">Создание аудита сервера</span><span class="sxs-lookup"><span data-stu-id="ace29-222">To create a server audit</span></span>  
  
1.  <span data-ttu-id="ace29-223">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ace29-223">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ace29-224">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="ace29-224">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ace29-225">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ace29-225">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates a server audit called "HIPAA_Audit" with a binary file as the target and no options.  
    CREATE SERVER AUDIT HIPAA_Audit  
        TO FILE ( FILEPATH ='\\SQLPROD_1\Audit\' );  
    ```  
  
#### <a name="to-create-a-server-audit-specification"></a><span data-ttu-id="ace29-226">Создание спецификации аудита сервера</span><span class="sxs-lookup"><span data-stu-id="ace29-226">To create a server audit specification</span></span>  
  
1.  <span data-ttu-id="ace29-227">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ace29-227">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ace29-228">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="ace29-228">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ace29-229">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ace29-229">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    /*Creates a server audit specification called "HIPAA_Audit_Specification" that audits failed logins for the SQL Server audit "HIPAA_Audit" created above.  
    */  
  
    CREATE SERVER AUDIT SPECIFICATION HIPAA_Audit_Specification  
    FOR SERVER AUDIT HIPAA_Audit  
        ADD (FAILED_LOGIN_GROUP);  
    GO  
    -- Enables the audit.   
  
    ALTER SERVER AUDIT HIPAA_Audit  
    WITH (STATE = ON);  
    GO  
    ```  
  
 <span data-ttu-id="ace29-230">Дополнительные сведения см. в статьях [CREATE SERVER AUDIT (Transact-SQL)](/sql/t-sql/statements/create-server-audit-transact-sql) и [CREATE SERVER AUDIT SPECIFICATION (Transact-SQL)](/sql/t-sql/statements/create-server-audit-specification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ace29-230">For more information, see [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) and [CREATE SERVER AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-specification-transact-sql).</span></span>  
  
  
