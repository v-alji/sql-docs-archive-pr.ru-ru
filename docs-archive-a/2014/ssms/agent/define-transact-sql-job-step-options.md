---
title: Определение параметров для шагов заданий Transact-SQL | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL job step
- job steps [Transact-SQL]
- SQL Server Agent jobs, Transact-SQL step
ms.assetid: b2a47057-f6fb-432b-a7b6-5d61f33a5d9c
author: stevestein
ms.author: sstein
ms.openlocfilehash: cc1d6412e52e74ce0c6d987d6189c0c72ffd7df7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729010"
---
# <a name="define-transact-sql-job-step-options"></a><span data-ttu-id="26a83-102">Определение параметров для шагов заданий Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="26a83-102">Define Transact-SQL Job Step Options</span></span>
  <span data-ttu-id="26a83-103">В этом разделе описано, как определить параметры [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] шагов задания агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или управляющие объекты SQL Server.</span><span class="sxs-lookup"><span data-stu-id="26a83-103">This topic describes how to define options for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent [!INCLUDE[tsql](../../includes/tsql-md.md)] job steps in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="26a83-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="26a83-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="26a83-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="26a83-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="26a83-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="26a83-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="26a83-107">**Для определения параметров шага задания Transact-SQL с помощью:** ,</span><span class="sxs-lookup"><span data-stu-id="26a83-107">**To define Transact-SQL job step options, using:** ,</span></span>  
  
     [<span data-ttu-id="26a83-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="26a83-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="26a83-109">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="26a83-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="26a83-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="26a83-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="26a83-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="26a83-111">Security</span></span>  
 <span data-ttu-id="26a83-112">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="26a83-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="26a83-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="26a83-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-transact-sql-job-step-options"></a><span data-ttu-id="26a83-114">Определение параметров шага задания Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="26a83-114">To define Transact-SQL job step options</span></span>  
  
1.  <span data-ttu-id="26a83-115">В **обозревателе объектов**разверните пункт **Агент SQL Server**, затем **Задания**, щелкните правой кнопкой задание, которое необходимо изменить, и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="26a83-115">In **Object Explorer**, expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="26a83-116">Щелкните страницу **Шаги** , шаг задания, а затем — **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="26a83-116">Click the **Steps** page, click a job step, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="26a83-117">Проверьте, что в диалоговом окне **Свойства шага задания** задан тип задания **Скрипт Transact-SQL (TSQL)**, и выберите страницу **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="26a83-117">On the **Job Step Properties** dialog, confirm that the job type is **Transact-SQL script (TSQL)**, and then select the **Advanced** page.</span></span>  
  
4.  <span data-ttu-id="26a83-118">Выберите из списка **Действие при успехе** действие, которое будет инициироваться при успешном выполнении задания.</span><span class="sxs-lookup"><span data-stu-id="26a83-118">Specify an action to take if the job is successful by selecting from the **On success action** list.</span></span>  
  
5.  <span data-ttu-id="26a83-119">Укажите число повторных попыток, введя число в диапазоне от 0 до 9999 в поле **Повторные попытки** .</span><span class="sxs-lookup"><span data-stu-id="26a83-119">Specify a number of retry attempts by entering a number from 0 to 9999 into the **Retry attempts** box.</span></span>  
  
6.  <span data-ttu-id="26a83-120">Укажите интервал между повторными попытками, введя число минут в диапазоне от 0 до 9999 в поле **Интервал повтора** .</span><span class="sxs-lookup"><span data-stu-id="26a83-120">Specify a retry interval by entering a number of minutes from 0 to 9999 into the **Retry interval** box.</span></span>  
  
7.  <span data-ttu-id="26a83-121">Выберите из списка **Действие при ошибке** действие, которое будет инициироваться при неудачном выполнении задания.</span><span class="sxs-lookup"><span data-stu-id="26a83-121">Specify an action to take if the job fails by choosing from the **On failure action** list.</span></span>  
  
8.  <span data-ttu-id="26a83-122">Если задание является скриптом [!INCLUDE[tsql](../../includes/tsql-md.md)] , возможен выбор из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="26a83-122">If the job is a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, you can choose from the following options:</span></span>  
  
    -   <span data-ttu-id="26a83-123">Введите имя **файла вывода**.</span><span class="sxs-lookup"><span data-stu-id="26a83-123">Enter the name of an **Output file**.</span></span> <span data-ttu-id="26a83-124">По умолчанию файл перезаписывается при каждом выполнении шага задания.</span><span class="sxs-lookup"><span data-stu-id="26a83-124">By default the file is overwritten each time the job step executes.</span></span> <span data-ttu-id="26a83-125">Если не нужно перезаписывать файл вывода, поставьте флажок **Дописать выходные данные в существующий файл**.</span><span class="sxs-lookup"><span data-stu-id="26a83-125">If you do not want the output file overwritten, check **Append output to existing file**.</span></span> <span data-ttu-id="26a83-126">Этот параметр доступен только элементам предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="26a83-126">This option is only available to members of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="26a83-127">Имейте в виду, что среда [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] не позволяет пользователям просматривать произвольные файлы файловой системы, поэтому нельзя просмотреть в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] шаги заданий, записанные в файловую систему.</span><span class="sxs-lookup"><span data-stu-id="26a83-127">Note that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] does not allow users to view arbitrary files on the file system, so you cannot use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to view job step logs that are written to the file system.</span></span>  
  
    -   <span data-ttu-id="26a83-128">Установите флажок **Сохранять данные журнала в таблице** , если журнал шага задания необходимо вести в таблице базы данных.</span><span class="sxs-lookup"><span data-stu-id="26a83-128">Check **Log to table** if you want to log the job step to a database table.</span></span> <span data-ttu-id="26a83-129">По умолчанию содержимое таблицы перезаписывается при каждом выполнении шага задания.</span><span class="sxs-lookup"><span data-stu-id="26a83-129">By default the table contents are overwritten each time the job step executes.</span></span> <span data-ttu-id="26a83-130">Если не нужно, чтобы содержимое таблицы перезаписывалось, поставьте флажок **Дописать выходные данные в существующую запись в таблице**.</span><span class="sxs-lookup"><span data-stu-id="26a83-130">If you do not want the table contents overwritten, check **Append output to existing entry in table**.</span></span> <span data-ttu-id="26a83-131">После выполнения шага задания можно просмотреть содержимое этой таблицы, нажав **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="26a83-131">After the job step executes, you can view the contents of this table by clicking **View**.</span></span>  
  
    -   <span data-ttu-id="26a83-132">Установите флажок **Включить в журнал выходные данные шага** , если результаты шага должны быть включены в его журнал.</span><span class="sxs-lookup"><span data-stu-id="26a83-132">Check **Include step output in history** if you want the output included in the step's history.</span></span> <span data-ttu-id="26a83-133">Результат будет отображен только в случае отсутствия ошибок.</span><span class="sxs-lookup"><span data-stu-id="26a83-133">Output will only be shown if there were no errors.</span></span> <span data-ttu-id="26a83-134">Кроме того, отображаемый результат может быть усечен.</span><span class="sxs-lookup"><span data-stu-id="26a83-134">Also, output may be truncated.</span></span>  
  
9. <span data-ttu-id="26a83-135">Если члену предопределенной роли сервера **sysadmin** нужно выполнить шаг задания в контексте другого имени входа SQL, ему следует выбрать имя входа SQL из списка **Выполнять от имени** .</span><span class="sxs-lookup"><span data-stu-id="26a83-135">If you are a member of the **sysadmin** fixed server role and you want to run this job step as a different SQL login, select the SQL login from the **Run as user** list.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="26a83-136">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="26a83-136">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="26a83-137">**Определение параметров шага задания Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="26a83-137">**To define Transact-SQL job step options**</span></span>  
  
 <span data-ttu-id="26a83-138">Воспользуйтесь классом `JobStep` в любом языке программирования (Visual Basic, Visual C# или PowerShell).</span><span class="sxs-lookup"><span data-stu-id="26a83-138">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
  
  
