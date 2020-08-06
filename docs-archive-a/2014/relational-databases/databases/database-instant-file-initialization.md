---
title: Мгновенная инициализация файлов базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- initializing files [SQL Server]
- instant file initializations [SQL Server]
- fast file initialization (SQL Server)
- file initialization [SQL Server]
ms.assetid: 1ad468f5-4f75-480b-aac6-0b01b048bd67
author: stevestein
ms.author: sstein
ms.openlocfilehash: dedd2c5b8d075dee8aeeb438904137558c664d95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658818"
---
# <a name="database-instant-file-initialization"></a><span data-ttu-id="b37f5-102">Мгновенная инициализация файлов базы данных</span><span class="sxs-lookup"><span data-stu-id="b37f5-102">Database Instant File Initialization</span></span>
  <span data-ttu-id="b37f5-103">Файлы данных и журналов инициализируются, чтобы перезаписать все существующие данные на диске, оставшиеся после удаленных файлов.</span><span class="sxs-lookup"><span data-stu-id="b37f5-103">Data and log files are initialized to overwrite any existing data left on the disk from previously deleted files.</span></span> <span data-ttu-id="b37f5-104">Файлы данных и журналов сначала инициализируются с помощью заполнения нулями при выполнении одной из следующих операций.</span><span class="sxs-lookup"><span data-stu-id="b37f5-104">Data and log files are first initialized by filling the files with zeros when you perform one of the following operations:</span></span>  
  
-   <span data-ttu-id="b37f5-105">создавать базу данных;</span><span class="sxs-lookup"><span data-stu-id="b37f5-105">Create a database.</span></span>  
  
-   <span data-ttu-id="b37f5-106">Добавление файлов, журналов или данных в существующую базу данных.</span><span class="sxs-lookup"><span data-stu-id="b37f5-106">Add files, log or data, to an existing database.</span></span>  
  
-   <span data-ttu-id="b37f5-107">Увеличение размера существующего файла (включая операции автоувеличения).</span><span class="sxs-lookup"><span data-stu-id="b37f5-107">Increase the size of an existing file (including autogrow operations).</span></span>  
  
-   <span data-ttu-id="b37f5-108">Восстановление базы данных или файловой группы.</span><span class="sxs-lookup"><span data-stu-id="b37f5-108">Restore a database or filegroup.</span></span>  
  
 <span data-ttu-id="b37f5-109">Вследствие инициализации файлов эти операции занимают больше времени.</span><span class="sxs-lookup"><span data-stu-id="b37f5-109">File initialization causes these operations to take longer.</span></span> <span data-ttu-id="b37f5-110">Однако, если данные записываются в файлы первый раз, операционной системе не требуется заполнять файлы нулями.</span><span class="sxs-lookup"><span data-stu-id="b37f5-110">However, when data is written to the files for the first time, the operating system does not have to fill the files with zeros.</span></span>  
  
## <a name="instant-file-initialization"></a><span data-ttu-id="b37f5-111">Мгновенная инициализация файлов</span><span class="sxs-lookup"><span data-stu-id="b37f5-111">Instant File Initialization</span></span>  
 <span data-ttu-id="b37f5-112">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]файлы данных могут быть инициализированы мгновенно.</span><span class="sxs-lookup"><span data-stu-id="b37f5-112">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data files can be initialized instantaneously.</span></span> <span data-ttu-id="b37f5-113">Это разрешено для быстрого выполнения упомянутых ранее файловых операций.</span><span class="sxs-lookup"><span data-stu-id="b37f5-113">This allows for fast execution of the previously mentioned file operations.</span></span> <span data-ttu-id="b37f5-114">Мгновенная инициализация файлов освобождает место на диске, не заполняя пространство нулями.</span><span class="sxs-lookup"><span data-stu-id="b37f5-114">Instant file initialization reclaims used disk space without filling that space with zeros.</span></span> <span data-ttu-id="b37f5-115">Вместо этого содержимое диска перезаписывается, поскольку в файлы записываются новые данные.</span><span class="sxs-lookup"><span data-stu-id="b37f5-115">Instead, disk content is overwritten as new data is written to the files.</span></span> <span data-ttu-id="b37f5-116">Файлы журналов не могут быть инициализированы мгновенно.</span><span class="sxs-lookup"><span data-stu-id="b37f5-116">Log files cannot be initialized instantaneously.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b37f5-117">Мгновенная инициализация файлов доступна только в [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[winxppro](../../includes/winxppro-md.md)] , [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] или более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="b37f5-117">Instant file initialization is available only on [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[winxppro](../../includes/winxppro-md.md)] or [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] or later versions.</span></span>  
  
 <span data-ttu-id="b37f5-118">Мгновенная инициализация файлов доступна, только если учетной записи службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER) предоставлено разрешение SE_MANAGE_VOLUME_NAME.</span><span class="sxs-lookup"><span data-stu-id="b37f5-118">Instant file initialization is only available if the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER) service account has been granted SE_MANAGE_VOLUME_NAME.</span></span> <span data-ttu-id="b37f5-119">Участники группы администраторов Windows обладают этим правом и могут предоставить его другим пользователям, добавив их в политику безопасности **Выполнение задач обслуживания томов** .</span><span class="sxs-lookup"><span data-stu-id="b37f5-119">Members of the Windows Administrator group have this right and can grant it to other users by adding them to the **Perform Volume Maintenance Tasks** security policy.</span></span> <span data-ttu-id="b37f5-120">Дополнительные сведения о назначении прав пользователей см. в документации по Windows.</span><span class="sxs-lookup"><span data-stu-id="b37f5-120">For more information about assigning user rights, see the Windows documentation.</span></span>  
  
 <span data-ttu-id="b37f5-121">Мгновенная инициализация недоступна при включенном TDE.</span><span class="sxs-lookup"><span data-stu-id="b37f5-121">Instant file initialization is not available when TDE is enabled.</span></span>  
  
 <span data-ttu-id="b37f5-122">Предоставление учетной записи разрешения `Perform volume maintenance tasks` .</span><span class="sxs-lookup"><span data-stu-id="b37f5-122">To grant an account the `Perform volume maintenance tasks` permission:</span></span>  
  
1.  <span data-ttu-id="b37f5-123">На компьютере, где будет создан файл резервной копии, откройте приложение `Local Security Policy` (`secpol.msc`).</span><span class="sxs-lookup"><span data-stu-id="b37f5-123">On the computer where the backup file will be created, open the `Local Security Policy` application (`secpol.msc`).</span></span>  
  
2.  <span data-ttu-id="b37f5-124">Разверните на левой панели узел **Локальные политики**, а затем щелкните пункт **Назначение прав пользователей**.</span><span class="sxs-lookup"><span data-stu-id="b37f5-124">In the left pane, expand **Local Policies**, and then click **User Rights Assignment**.</span></span>  
  
3.  <span data-ttu-id="b37f5-125">На правой панели дважды щелкните **Выполнение задач по обслуживанию томов**.</span><span class="sxs-lookup"><span data-stu-id="b37f5-125">In the right pane, double-click **Perform volume maintenance tasks**.</span></span>  
  
4.  <span data-ttu-id="b37f5-126">Щелкните кнопку **Добавить пользователя или группу** и добавьте любые учетные записи пользователя, которые использовались для резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="b37f5-126">Click **Add User or Group** and add any user accounts that are used for backups.</span></span>  
  
5.  <span data-ttu-id="b37f5-127">Нажмите кнопку **Применить**, а затем закройте все `Local Security Policy` диалоговые окна.</span><span class="sxs-lookup"><span data-stu-id="b37f5-127">Click **Apply**, and then close all `Local Security Policy` dialog boxes.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="b37f5-128">Соображения безопасности</span><span class="sxs-lookup"><span data-stu-id="b37f5-128">Security Considerations</span></span>  
 <span data-ttu-id="b37f5-129">Поскольку удаленное содержимое диска перезаписывается только по мере записи новых данных в файлы, доступ к удаленному содержимому может получить неавторизованный участник.</span><span class="sxs-lookup"><span data-stu-id="b37f5-129">Because the deleted disk content is overwritten only as new data is written to the files, the deleted content might be accessed by an unauthorized principal.</span></span> <span data-ttu-id="b37f5-130">По мере подключения файла базы данных к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]угроза раскрытия сведений уменьшается благодаря списку управления доступом на уровне пользователей (DACL) в файле.</span><span class="sxs-lookup"><span data-stu-id="b37f5-130">While the database file is attached to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this information disclosure threat is reduced by the discretionary access control list (DACL) on the file.</span></span> <span data-ttu-id="b37f5-131">DACL разрешает доступ к файлу только учетной записи службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и локальному администратору.</span><span class="sxs-lookup"><span data-stu-id="b37f5-131">This DACL allows file access only to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and the local administrator.</span></span> <span data-ttu-id="b37f5-132">Однако при отсоединении файла доступ к нему может получить пользователь или служба, не обладающие правом SE_MANAGE_VOLUME_NAME.</span><span class="sxs-lookup"><span data-stu-id="b37f5-132">However, when the file is detached, it may be accessed by a user or service that does not have SE_MANAGE_VOLUME_NAME.</span></span> <span data-ttu-id="b37f5-133">Аналогичная угроза существует при резервном копировании базы данных.</span><span class="sxs-lookup"><span data-stu-id="b37f5-133">A similar threat exists when the database is backed up.</span></span> <span data-ttu-id="b37f5-134">Удаленное содержимое может стать доступным неавторизованному пользователю или службе, если файл резервного копирования не защищен соответствующим DACL.</span><span class="sxs-lookup"><span data-stu-id="b37f5-134">The deleted content can become available to an unauthorized user or service if the backup file is not protected with an appropriate DACL.</span></span>  
  
 <span data-ttu-id="b37f5-135">Если вероятность раскрытия удаленного содержимого является серьезной проблемой, необходимо выполнить одно из следующих действия (или оба).</span><span class="sxs-lookup"><span data-stu-id="b37f5-135">If the potential for disclosing deleted content is a concern, you should do one or both of the following:</span></span>  
  
-   <span data-ttu-id="b37f5-136">Всегда проверяйте, что все отсоединенные файлы данных и резервные копии имеют ограничивающие DACL.</span><span class="sxs-lookup"><span data-stu-id="b37f5-136">Always make sure that any detached data files and backup files have restrictive DACLs.</span></span>  
  
-   <span data-ttu-id="b37f5-137">Отключите мгновенную инициализацию файлов для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , отозвав право SE_MANAGE_VOLUME_NAME учетной записи службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b37f5-137">Disable instant file initialization for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by revoking SE_MANAGE_VOLUME_NAME from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b37f5-138">Отключение мгновенной инициализации файлов влияет только на создаваемые или увеличивающиеся в размере файлы после отзыва прав пользователя.</span><span class="sxs-lookup"><span data-stu-id="b37f5-138">Disabling instant file initialization only affects files that are created or increased in size after the user right is revoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b37f5-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="b37f5-139">See Also</span></span>  
 [<span data-ttu-id="b37f5-140">CREATE DATABASE (SQL Server Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b37f5-140">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  
