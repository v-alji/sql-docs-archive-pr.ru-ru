---
title: Свойства SQL Server (вкладка "Дополнительно") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 2ffd10fd-bac1-478f-9cff-96ed6c8b787f
author: stevestein
ms.author: sstein
ms.openlocfilehash: a9a77fd0a43627b49bb8719f6fa943408f64fcca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654697"
---
# <a name="sql-server-properties-advanced-tab"></a><span data-ttu-id="9311f-102">Свойства SQL Server (вкладка «Дополнительно»)</span><span class="sxs-lookup"><span data-stu-id="9311f-102">SQL Server Properties (Advanced Tab)</span></span>
  <span data-ttu-id="9311f-103">По умолчанию на вкладке **Дополнительно** присутствуют следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="9311f-103">The following properties appear on the **Advanced** tab by default.</span></span> <span data-ttu-id="9311f-104">Если определены пользовательские свойства, они также отображаются на этой вкладке вместе со значениями.</span><span class="sxs-lookup"><span data-stu-id="9311f-104">If custom properties are defined, they also appear on this tab, with their values.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9311f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9311f-105">Options</span></span>  
 <span data-ttu-id="9311f-106">**Кластеризованный**</span><span class="sxs-lookup"><span data-stu-id="9311f-106">**Clustered**</span></span>  
 <span data-ttu-id="9311f-107">Указывает, установлена ли эта служба в качестве ресурса кластеризованного сервера.</span><span class="sxs-lookup"><span data-stu-id="9311f-107">Indicates if this service is installed as a resource of a clustered server.</span></span>  
  
 <span data-ttu-id="9311f-108">**Передача отзывов пользователей**</span><span class="sxs-lookup"><span data-stu-id="9311f-108">**Customer Feedback Reporting**</span></span>  
 <span data-ttu-id="9311f-109">Указывает, был ли запущен контроль качества обслуживания для этой службы.</span><span class="sxs-lookup"><span data-stu-id="9311f-109">Indicates whether Service Quality Monitoring has been enabled on this service.</span></span> <span data-ttu-id="9311f-110">Дополнительные сведения о передаче отзывов пользователей см. в разделе «Настройки параметров отчета об ошибках» электронной документации.</span><span class="sxs-lookup"><span data-stu-id="9311f-110">For more information on Customer Feedback Reporting, search Books Online for the topic, "Error and Usage Report Settings."</span></span>  
  
 <span data-ttu-id="9311f-111">**Путь к данным**</span><span class="sxs-lookup"><span data-stu-id="9311f-111">**Data Path**</span></span>  
 <span data-ttu-id="9311f-112">Отображает путь к двоичным файлам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для установленной копии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9311f-112">Displays the path to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] binaries for this installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9311f-113">**Каталог дампа**</span><span class="sxs-lookup"><span data-stu-id="9311f-113">**Dump Directory**</span></span>  
 <span data-ttu-id="9311f-114">Отображает расположение дампа памяти в случае возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="9311f-114">Displays the location where memory dumps are placed in case of an error.</span></span>  
  
 <span data-ttu-id="9311f-115">**Отчет об ошибках**</span><span class="sxs-lookup"><span data-stu-id="9311f-115">**Error Reporting**</span></span>  
 <span data-ttu-id="9311f-116">Если установлено значение **Да**, то в случае возникновения серьезного сбоя программа "Доктор Ватсон» направит сведения либо в [!INCLUDE[msCoName](../../includes/msconame-md.md)] , либо на сервер ошибок.</span><span class="sxs-lookup"><span data-stu-id="9311f-116">When set to **Yes**, the Dr. Watson program forwards information to either [!INCLUDE[msCoName](../../includes/msconame-md.md)] or your error server if a serious failure occurs.</span></span> <span data-ttu-id="9311f-117">Дополнительные сведения по отчетам об ошибках см. в разделе «Настройки параметров отчета об ошибках» электронной документации.</span><span class="sxs-lookup"><span data-stu-id="9311f-117">For more information on Error Reporting, search Books Online for the topic, "Error and Usage Report Settings."</span></span> <span data-ttu-id="9311f-118">Чтобы изменить это значение, в обозревателе объектов среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] щелкните сервер правой кнопкой мыши, выберите пункт **Свойства**и перейдите на страницу **Прочие параметры сервера** .</span><span class="sxs-lookup"><span data-stu-id="9311f-118">To change this value, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, right-click your server, click **Properties**, and then click the **Misc. Server Settings** page.</span></span> <span data-ttu-id="9311f-119">Параметры находятся в области **Информационный отчет** .</span><span class="sxs-lookup"><span data-stu-id="9311f-119">The options are presented in the **Information Reporting** area.</span></span>  
  
 <span data-ttu-id="9311f-120">**Версия файла**</span><span class="sxs-lookup"><span data-stu-id="9311f-120">**File Version**</span></span>  
 <span data-ttu-id="9311f-121">Отображает версию исполняемого объекта [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9311f-121">Displays the version of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executable.</span></span>  
  
 <span data-ttu-id="9311f-122">**Путь установки**</span><span class="sxs-lookup"><span data-stu-id="9311f-122">**Install Path**</span></span>  
 <span data-ttu-id="9311f-123">Отображает путь к двоичным файлам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для установленной копии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9311f-123">Displays the path to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] binaries for this installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9311f-124">**Идентификатор экземпляра**</span><span class="sxs-lookup"><span data-stu-id="9311f-124">**Instance ID**</span></span>  
 <span data-ttu-id="9311f-125">Указывает экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , использующий эту службу.</span><span class="sxs-lookup"><span data-stu-id="9311f-125">Indicates the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that used this service.</span></span>  
  
 <span data-ttu-id="9311f-126">**Язык**</span><span class="sxs-lookup"><span data-stu-id="9311f-126">**Language**</span></span>  
 <span data-ttu-id="9311f-127">Отображает установленный по умолчанию язык для сообщений сервера.</span><span class="sxs-lookup"><span data-stu-id="9311f-127">Displays the default language for server messages.</span></span>  
  
 <span data-ttu-id="9311f-128">**Корневая папка реестра**</span><span class="sxs-lookup"><span data-stu-id="9311f-128">**Registry Root**</span></span>  
 <span data-ttu-id="9311f-129">Отображает расположение разделов реестра, используемых этим приложением.</span><span class="sxs-lookup"><span data-stu-id="9311f-129">Displays the location of the registry keys used by this application.</span></span>  
  
 <span data-ttu-id="9311f-130">**Версия пакета обновления**</span><span class="sxs-lookup"><span data-stu-id="9311f-130">**Service Pack Level**</span></span>  
 <span data-ttu-id="9311f-131">Отображает версию пакета обновления для этого экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9311f-131">Displays the service pack level of this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9311f-132">**Номер SKU**</span><span class="sxs-lookup"><span data-stu-id="9311f-132">**SKU Name**</span></span>  
 <span data-ttu-id="9311f-133">Отображает номер SKU продукта, иногда называемый выпуском продукта.</span><span class="sxs-lookup"><span data-stu-id="9311f-133">Displays the product stock keeping unit (SKU), sometimes called the product edition.</span></span>  
  
 <span data-ttu-id="9311f-134">**Параметры запуска**</span><span class="sxs-lookup"><span data-stu-id="9311f-134">**Startup Parameters**</span></span>  
 <span data-ttu-id="9311f-135">Указывает все параметры запуска, используемые этим экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9311f-135">Lists any startup parameters that are used by this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9311f-136">Параметры разделяются точками с запятой.</span><span class="sxs-lookup"><span data-stu-id="9311f-136">Parameters are separated by semi-colons.</span></span> <span data-ttu-id="9311f-137">Параметры по умолчанию включают пути к файлу данных главной базы данных (`master.mdf`), файлу журнала главной базы данных (`mastlog.ldf`) и файлу журнала ошибок.</span><span class="sxs-lookup"><span data-stu-id="9311f-137">The default parameters include the paths to the data file for the master database (`master.mdf`), the log file for the master database (`mastlog.ldf`), and the error log file.</span></span> <span data-ttu-id="9311f-138">Дополнительные сведения о синтаксисе параметров запуска см. в разделе **Использование параметров запуска службы SQL Server**электронной документации.</span><span class="sxs-lookup"><span data-stu-id="9311f-138">For the syntax of startup parameters, search Books Online for the topic **Using the SQL Server Service Startup Options.**</span></span>  
  
 <span data-ttu-id="9311f-139">**Номер SKU**</span><span class="sxs-lookup"><span data-stu-id="9311f-139">**Stock Keeping Unit**</span></span>  
 <span data-ttu-id="9311f-140">Отображает номер SKU продукта.</span><span class="sxs-lookup"><span data-stu-id="9311f-140">Displays the product stock keeping unit (SKU) number.</span></span>  
  
 <span data-ttu-id="9311f-141">**Версия**</span><span class="sxs-lookup"><span data-stu-id="9311f-141">**Version**</span></span>  
 <span data-ttu-id="9311f-142">Отображает номер версии этого экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9311f-142">Displays the version number of this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9311f-143">**Имя виртуального сервера**</span><span class="sxs-lookup"><span data-stu-id="9311f-143">**Virtual Server Name**</span></span>  
 <span data-ttu-id="9311f-144">**Имя виртуального сервера** , когда [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] установлен на кластеризованный сервер.</span><span class="sxs-lookup"><span data-stu-id="9311f-144">**Virtual Server Name** when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on a clustered server.</span></span>  
  
  
