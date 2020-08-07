---
title: Подключение к зарегистрированным серверам и к обозревателю объектов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: d6b3911f-68b4-4483-831b-df89d6400add
author: stevestein
ms.author: sstein
ms.openlocfilehash: b4bc75ad7f3682765dc102064a5621cd541ccd12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727822"
---
# <a name="connect-with-registered-servers-and-object-explorer"></a><span data-ttu-id="35154-102">Подключение к зарегистрированным серверам и к обозревателю объектов</span><span class="sxs-lookup"><span data-stu-id="35154-102">Connect with Registered Servers and Object Explorer</span></span>
  <span data-ttu-id="35154-103">В этом учебнике показано, как использовать зарегистрированные серверы и обозреватель объектов.</span><span class="sxs-lookup"><span data-stu-id="35154-103">This tutorial demonstrates the use of Registered Servers and Object Explorer.</span></span>  
  
 <span data-ttu-id="35154-104">В этом учебнике используется образец базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="35154-104">This tutorial uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="35154-105">По соображениям безопасности образцы базы данных по умолчанию не устанавливаются.</span><span class="sxs-lookup"><span data-stu-id="35154-105">To help enhance security, by default, the sample databases are not installed.</span></span> <span data-ttu-id="35154-106">Дополнительные сведения см. в разделе [Установка образцов кода и образцов баз данных SQL Server](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="35154-106">For more information, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
## <a name="connecting-to-servers"></a><span data-ttu-id="35154-107">Подключение к серверам</span><span class="sxs-lookup"><span data-stu-id="35154-107">Connecting to Servers</span></span>  
 <span data-ttu-id="35154-108">Панель инструментов компонента «Зарегистрированные серверы» содержит кнопки для компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)], а также служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]и [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35154-108">The toolbar of the Registered Servers component has buttons for the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="35154-109">Можно зарегистрировать один или более из этих типов серверов, чтобы упростить управление ими.</span><span class="sxs-lookup"><span data-stu-id="35154-109">You can register one or more of these server types for convenient management.</span></span> <span data-ttu-id="35154-110">В этом упражнении предстоит зарегистрировать базу данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="35154-110">Try the following exercise to register the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
#### <a name="to-register-the-database"></a><span data-ttu-id="35154-111">Регистрация базы данных</span><span class="sxs-lookup"><span data-stu-id="35154-111">To register the database</span></span>  
  
1.  <span data-ttu-id="35154-112">Если потребуется, на панели инструментов "Зарегистрированные серверы" нажмите кнопку **Ядро СУБД** .</span><span class="sxs-lookup"><span data-stu-id="35154-112">On the Registered Servers toolbar, click **Database Engine** if you have to.</span></span> <span data-ttu-id="35154-113">(Этот режим может быть уже выбран).</span><span class="sxs-lookup"><span data-stu-id="35154-113">(It may already be selected.)</span></span>  
  
2.  <span data-ttu-id="35154-114">Разверните узел **Ядро СУБД**.</span><span class="sxs-lookup"><span data-stu-id="35154-114">Expand **Database Engine**.</span></span>  
  
3.  <span data-ttu-id="35154-115">Щелкните правой кнопкой мыши пункт **Группы локальных серверов**и выберите пункт **Регистрация нового сервера**.</span><span class="sxs-lookup"><span data-stu-id="35154-115">Right-click **Local Server Groups**, and then click **New Server Registration**.</span></span>  
  
4.  <span data-ttu-id="35154-116">В диалоговом окне **Регистрация нового сервера** в текстовом поле **Имя сервера** введите имя экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35154-116">In the **New Server Registration** dialog box, in the **Server name** text box, type the name of your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="35154-117">В поле **Имя зарегистрированного сервера** введите [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35154-117">In the **Registered server name** box, type [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
6.  <span data-ttu-id="35154-118">На вкладке **Свойства соединения** в списке **Подключение к базе данных** выберите **\<Browse server...>** .</span><span class="sxs-lookup"><span data-stu-id="35154-118">On the **Connection Properties** tab, in the **Connect to database** list, select **\<Browse server...>**.</span></span>  
  
7.  <span data-ttu-id="35154-119">В диалоговом окне **Просмотр баз данных** нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="35154-119">In the **Browse for Databases** dialog box, click **Yes**.</span></span>  
  
8.  <span data-ttu-id="35154-120">В диалоговом окне **Поиск базы данных на сервере** выберите [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="35154-120">In the **Browse Server for Database** dialog box, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **OK**.</span></span>  
  
9. <span data-ttu-id="35154-121">Чтобы убедиться в том, что сервер был зарегистрирован правильно, нажмите кнопку **Проверка**.</span><span class="sxs-lookup"><span data-stu-id="35154-121">To verify that the server has been registered correctly, click **Test**.</span></span>  
  
10. <span data-ttu-id="35154-122">В диалоговом окне **Регистрация нового сервера** нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="35154-122">In the **New Server Registration** dialog box, click **Save**.</span></span>  
  
## <a name="connecting-with-object-explorer"></a><span data-ttu-id="35154-123">Подключение с помощью обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="35154-123">Connecting with Object Explorer</span></span>  
 <span data-ttu-id="35154-124">Как и зарегистрированные серверы, обозреватель объектов может подключаться к компоненту [!INCLUDE[ssDE](../../includes/ssde-md.md)], а также к службам [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]и [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35154-124">Like Registered Servers, Object Explorer can connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
#### <a name="to-connect-with-object-explorer"></a><span data-ttu-id="35154-125">Подключение с помощью обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="35154-125">To connect with Object Explorer</span></span>  
  
1.  <span data-ttu-id="35154-126">На панели инструментов обозревателя объектов нажмите кнопку **Подключиться** , чтобы раскрыть список возможных типов соединений, а затем выберите параметр **Ядро СУБД**.</span><span class="sxs-lookup"><span data-stu-id="35154-126">On the toolbar of Object Explorer, click **Connect** for a list of possible connection types, and then select **Database Engine**.</span></span>  
  
2.  <span data-ttu-id="35154-127">В диалоговом окне **Соединение с сервером** в поле **Имя сервера** введите имя экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35154-127">In the **Connect to Server** dialog box, in the **Server name** text box, type the name of your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="35154-128">Нажмите кнопку **Параметры** и изучите доступные варианты.</span><span class="sxs-lookup"><span data-stu-id="35154-128">Click **Options** and explore the choices.</span></span>  
  
4.  <span data-ttu-id="35154-129">Для подключения к серверу нажмите **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="35154-129">To connect to the server, click **Connect**.</span></span> <span data-ttu-id="35154-130">Если соединение уже установлено, последует возврат в окно обозревателя объектов с фокусом, установленным на нужном сервере.</span><span class="sxs-lookup"><span data-stu-id="35154-130">If you are already connected, this action just returns you to Object Explorer and sets the focus on that server.</span></span>  
  
     <span data-ttu-id="35154-131">С помощью обозревателя объектов можно управлять системой безопасности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , репликацией и компонентом Database Mail.</span><span class="sxs-lookup"><span data-stu-id="35154-131">With Object Explorer you can administer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Security, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, Replication, and Database Mail.</span></span> <span data-ttu-id="35154-132">Обозреватель объектов позволяет управлять лишь некоторыми из возможностей служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]и [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35154-132">Object Explorer can only manage some of the features of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span></span> <span data-ttu-id="35154-133">Каждый из этих компонентов имеет дополнительные специальные инструменты работы.</span><span class="sxs-lookup"><span data-stu-id="35154-133">Each of those components has additional specialized tools.</span></span>  
  
5.  <span data-ttu-id="35154-134">В обозревателе объектов разверните папку **Базы данных** и выберите [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35154-134">In Object Explorer, expand the **Databases** folder and select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
     <span data-ttu-id="35154-135">Обратите внимание, что в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] системные базы данных находятся в отдельной папке.</span><span class="sxs-lookup"><span data-stu-id="35154-135">Notice that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] presents the system databases in a separate folder.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="35154-136">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="35154-136">Next Task in Lesson</span></span>  
 [<span data-ttu-id="35154-137">Изменение макета окружения</span><span class="sxs-lookup"><span data-stu-id="35154-137">Change the Environment Layout</span></span>](lesson-1-3-change-the-environment-layout.md)  
  
  
