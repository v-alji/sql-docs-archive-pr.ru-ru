---
title: Просмотр сведений о шаге задания | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- displaying job step information
- jobs [SQL Server Agent], viewing
- SQL Server Agent jobs, viewing
- viewing job step information
ms.assetid: e3f06492-dc86-4e06-b186-ea58aff6d591
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5d9fc6a006884bc564b5db2bfa8b168c8ae59149
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654047"
---
# <a name="view-job-step-information"></a><span data-ttu-id="94763-102">View Job Step Information</span><span class="sxs-lookup"><span data-stu-id="94763-102">View Job Step Information</span></span>
  <span data-ttu-id="94763-103">В данном разделе описано, как просмотреть сведения о шаге задания в окне «Свойства шага задания».</span><span class="sxs-lookup"><span data-stu-id="94763-103">This topic describes how to view job step details in the Job Step Properties dialog.</span></span> <span data-ttu-id="94763-104">Также предоставляются сведения о просмотре выходных данных шага задания.</span><span class="sxs-lookup"><span data-stu-id="94763-104">It also includes information about viewing job step output.</span></span>  
  
-   <span data-ttu-id="94763-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="94763-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="94763-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="94763-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="94763-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="94763-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="94763-108">**Для просмотра сведений о шаге задания используется:**</span><span class="sxs-lookup"><span data-stu-id="94763-108">**To view job step information, using:**</span></span>  
  
     [<span data-ttu-id="94763-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="94763-109">SQL Server Management Studio</span></span>](#SSMS)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="94763-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="94763-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="94763-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="94763-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="94763-112">Если шаг задания был настроен так, чтобы вывод производился в таблицу или файл, и задание было запущено хотя бы однажды, можно видеть его вывод на странице **Дополнительно** окна **Свойства шага задания** .</span><span class="sxs-lookup"><span data-stu-id="94763-112">If the job step has been configured to write its output to a table or file and the job has run at least once, you can view its output on the **Advanced** page of the **Job Step Properties** dialog.</span></span> <span data-ttu-id="94763-113">При удалении задания или его шага журнал вывода удаляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="94763-113">When a job or job step is deleted, the output log is automatically deleted.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="94763-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="94763-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="94763-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="94763-115">Permissions</span></span>  
 <span data-ttu-id="94763-116">Если пользователь не принадлежит к предопределенной роли сервера **sysadmin** , он может просматривать лишь те задания, которыми владеет.</span><span class="sxs-lookup"><span data-stu-id="94763-116">You can view only those jobs that you own, unless you are a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="94763-117">А члены указанной роли могут просматривать все задания и все сведения об их шагах.</span><span class="sxs-lookup"><span data-stu-id="94763-117">Members of this role can view all jobs and job step details.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="94763-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="94763-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-job-step-information"></a><span data-ttu-id="94763-119">Просмотр сведений о шаге задания</span><span class="sxs-lookup"><span data-stu-id="94763-119">To view job step information</span></span>  
  
1.  <span data-ttu-id="94763-120">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="94763-120">In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="94763-121">Разверните узел **Агент SQL Server**, затем пункт **Задания**, щелкните правой кнопкой мыши задание, содержащее шаг, который следует просмотреть, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="94763-121">Expand **SQL Server Agent**, expand **Jobs**, right-click the job that contains the job step to be viewed, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="94763-122">В окне **Свойства задания** перейдите на страницу **Шаги** .</span><span class="sxs-lookup"><span data-stu-id="94763-122">In the **Job Properties** dialog, click the **Steps** page.</span></span>  
  
4.  <span data-ttu-id="94763-123">Щелкните шаг задания, который нужно просмотреть, и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="94763-123">Click the job step to be viewed, and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="94763-124">На странице **Общие** окна **Свойства шага задания** можно видеть тип шага задания и его действие.</span><span class="sxs-lookup"><span data-stu-id="94763-124">On the **General** page of the **Job Step Properties** dialog, you can view the type of job step and what it does.</span></span>  
  
6.  <span data-ttu-id="94763-125">Щелкните страницу **Дополнительно** , чтобы просмотреть действия, которые должен предпринимать агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в случае успешного или неуспешного выполнения этого шага задания, а также количество попыток выполнения этого этапа, куда должны выводиться результаты шага задания и под учетной записью какого пользователя он должен выполняться.</span><span class="sxs-lookup"><span data-stu-id="94763-125">Click the **Advanced** page to view the actions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent takes if the job step succeeds or fails, how many times the job step should be attempted, where the job step output is written, and the user the job step runs as.</span></span>  
  
#### <a name="to-view-job-step-output"></a><span data-ttu-id="94763-126">Просмотр выходных данных шага задания</span><span class="sxs-lookup"><span data-stu-id="94763-126">To view job step output</span></span>  
  
1.  <span data-ttu-id="94763-127">В окне **Свойства шага задания** перейдите на страницу **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="94763-127">In the **Job Step Properties** dialog, click the **Advanced** page.</span></span>  
  
2.  <span data-ttu-id="94763-128">В зависимости от версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , с которой имеется соединение, просмотреть таблицу или файл вывода шага задания можно различными способами.</span><span class="sxs-lookup"><span data-stu-id="94763-128">Depending on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connected to, you can view either the job step output file or table as follows:</span></span>  
  
    -   <span data-ttu-id="94763-129">Если установлено соединение с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или более поздними версиями, кнопку **Просмотр** можно нажать только при установленном флажке **Сохранять данные журнала в таблице** .</span><span class="sxs-lookup"><span data-stu-id="94763-129">When you are connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or later, you can click **View** only when **Log to table** is checked.</span></span> <span data-ttu-id="94763-130">В этом случае вывод шага задания производится в таблицу **sysjobstepslogs** в базе данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="94763-130">In this case, the job step output is written to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
    -   <span data-ttu-id="94763-131">Кнопка **Просмотр** недоступна, если выходные данные шагов задания записываются в файл.</span><span class="sxs-lookup"><span data-stu-id="94763-131">The **View** button is disabled when job step output is written to a file.</span></span> <span data-ttu-id="94763-132">Чтобы просмотреть файл вывода шага задания, используйте блокнот.</span><span class="sxs-lookup"><span data-stu-id="94763-132">To view a job step output file, use Notepad.</span></span>  
  
  
