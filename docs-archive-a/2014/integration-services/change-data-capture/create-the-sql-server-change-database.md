---
title: Создание базы данных изменения SQL Server | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- oraIns
ms.assetid: 4f79c24a-e99a-4a06-8637-51eeec406259
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0eaeb26d5bea4c9e50db29aaa45297ba763dbbfa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740217"
---
# <a name="create-the-sql-server-change-database"></a><span data-ttu-id="e8833-102">Создание базы данных изменения SQL Server</span><span class="sxs-lookup"><span data-stu-id="e8833-102">Create the SQL Server Change Database</span></span>
  <span data-ttu-id="e8833-103">При запуске мастера создания экземпляра открывается страница «Создание базы данных CDC».</span><span class="sxs-lookup"><span data-stu-id="e8833-103">When you start the New Instance wizard, the Create CDC Database page opens.</span></span> <span data-ttu-id="e8833-104">На странице «Создание базы данных CDC» содержатся сведения о новом экземпляре CDC, а также создается новая база данных изменений.</span><span class="sxs-lookup"><span data-stu-id="e8833-104">Use the Create CDC Database page to provide information about the new CDC instance and create a new Change database.</span></span>  
  
 <span data-ttu-id="e8833-105">При создании новой базы данных CDC она должна быть подготовлена для работы CDC SQL Server, для чего потребуется имя входа, которое является членом предопределенной роли сервера `sysadmin` .</span><span class="sxs-lookup"><span data-stu-id="e8833-105">When you create a new CDC database it is enabled for SQL Server CDC and this enablement requires a login that is a member of the `sysadmin` fixed-server role.</span></span>  
  
 <span data-ttu-id="e8833-106">Если пользователь, запускающий мастер создания экземпляра CDC Oracle, не является членом предопределенной роли сервера `sysadmin` , то открывается диалоговое окно «Соединение с SQL Server», где необходимо ввести учетные данные члена роли sysadmin, чтобы обеспечить выполнение в базе данных задачи обеспечения работы CDC SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e8833-106">When a user that starts the Create an Oracle CDC Instance wizard is not a member of the `sysadmin` fixed-server role, the Connect to SQL Server dialog box opens and requests the credentials for a member of the sysadmin role to carry out the Enable the database for SQL Server CDC task.</span></span> <span data-ttu-id="e8833-107">При создании базы данных CDC имя входа `sysadmin` удаляется, а работа возобновляется с первоначальным именем входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которое использовалось для входа в консоль конструктора Oracle.</span><span class="sxs-lookup"><span data-stu-id="e8833-107">When the CDC database is created, the `sysadmin` login is discarded and work resumes with the original [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used when the Oracle Designer Console was entered.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e8833-108">Для выполнения остальных задач, кроме обеспечения работы CDC SQL Server в базе данных, имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , использовавшееся для запуска мастера создания экземпляра, должно принадлежать к предопределенной роли сервера `dbcreator` и обладать разрешениями UPDATE на базу данных MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="e8833-108">For tasks other than Enable the database for SQL Server CDC of, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used for running the New Instance Wizard must have the `dbcreator` fixed-server role and UPDATE permissions on the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="e8833-109">Сведения о вводе данных в диалоговое окно «Подключение к SQL Server» см. в разделе [SQL Server Connection for Instance Creation](sql-server-connection-for-instance-creation.md).</span><span class="sxs-lookup"><span data-stu-id="e8833-109">For information on entering the data in the Connect to SQL Server dialog box, see [SQL Server Connection for Instance Creation](sql-server-connection-for-instance-creation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e8833-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="e8833-110">Options</span></span>  
 <span data-ttu-id="e8833-111">**Экземпляр CDC Oracle**</span><span class="sxs-lookup"><span data-stu-id="e8833-111">**Oracle CDC Instance**</span></span>  
 <span data-ttu-id="e8833-112">Укажите следующие сведения для создаваемого экземпляра CDC.</span><span class="sxs-lookup"><span data-stu-id="e8833-112">Type the following information about the CDC instance you are creating.</span></span>  
  
-   <span data-ttu-id="e8833-113">**Имя**. Введите имя новой службы.</span><span class="sxs-lookup"><span data-stu-id="e8833-113">**Name**: Type a name for the new service.</span></span> <span data-ttu-id="e8833-114">Оно также будет использоваться в качестве имени новой базы данных изменений.</span><span class="sxs-lookup"><span data-stu-id="e8833-114">This will also be the name of the new Change database.</span></span>  
  
-   <span data-ttu-id="e8833-115">**Описание**. Введите описание нового экземпляра, чтобы проще идентифицировать его.</span><span class="sxs-lookup"><span data-stu-id="e8833-115">**Description**: Type a description for the new instance to help you identify it.</span></span> <span data-ttu-id="e8833-116">Водить описание не обязательно.</span><span class="sxs-lookup"><span data-stu-id="e8833-116">This is optional.</span></span>  
  
 <span data-ttu-id="e8833-117">**База данных изменений SQL Server**</span><span class="sxs-lookup"><span data-stu-id="e8833-117">**SQL Server Change Database**</span></span>  
 <span data-ttu-id="e8833-118">Этот раздел используется для создания базы данных.</span><span class="sxs-lookup"><span data-stu-id="e8833-118">This section is used to create the database.</span></span>  
  
1.  <span data-ttu-id="e8833-119">**Изменение базы данных**. Имя новой базы данных изменений.</span><span class="sxs-lookup"><span data-stu-id="e8833-119">**Change Database**: The name of the new Change database.</span></span> <span data-ttu-id="e8833-120">Этой базе данных назначается то же имя, которое было присвоено экземпляру.</span><span class="sxs-lookup"><span data-stu-id="e8833-120">The name of the database is the same as the name that you gave to the instance.</span></span> <span data-ttu-id="e8833-121">В этом поле, доступном только для чтения, отображается полный пусть к базе данных.</span><span class="sxs-lookup"><span data-stu-id="e8833-121">This read-only field displays the full path to the database.</span></span>  
  
2.  <span data-ttu-id="e8833-122">**Создание базы данных**. Щелкните **Создать базу данных** , чтобы создать ее.</span><span class="sxs-lookup"><span data-stu-id="e8833-122">**Create Database**: Click **Create Database** to create the database.</span></span>  
  
     <span data-ttu-id="e8833-123">Для создания базы данных имя входа должно быть членом роли сервера `sysasmin` .</span><span class="sxs-lookup"><span data-stu-id="e8833-123">To create the database, the login must have the `sysasmin` server role.</span></span> <span data-ttu-id="e8833-124">Дополнительные сведения см. в приведенном выше примечании о безопасности.</span><span class="sxs-lookup"><span data-stu-id="e8833-124">See the security note above for more information.</span></span>  
  
     <span data-ttu-id="e8833-125">После создания базы данных можно нажать кнопку **Далее** , чтобы перейди к диалоговому окну [Connect to an Oracle Source Database](connect-to-an-oracle-source-database.md).</span><span class="sxs-lookup"><span data-stu-id="e8833-125">After you create the database, you can click **Next** to [Connect to an Oracle Source Database](connect-to-an-oracle-source-database.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8833-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="e8833-126">See Also</span></span>  
 <span data-ttu-id="e8833-127">[Как создать экземпляр изменения базы данных SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="e8833-127">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="e8833-128">Служба CDC Oracle</span><span class="sxs-lookup"><span data-stu-id="e8833-128">The Oracle CDC Service</span></span>](the-oracle-cdc-service.md)  
  
  
