---
title: Reporting Services службы SharePoint и приложений служб | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 501aa9ee-8c13-458c-bf6f-24e00c82681b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5654764f7913002cdae58d3264848250a292c585
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669278"
---
# <a name="reporting-services-sharepoint-service-and-service-applications"></a><span data-ttu-id="71c4e-102">Служба SharePoint и Служебные приложения службы Reporting Services</span><span class="sxs-lookup"><span data-stu-id="71c4e-102">Reporting Services SharePoint Service and Service Applications</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="71c4e-103">спроектирован на основе архитектуры службы SharePoint и использует службу SharePoint, а также одно или несколько приложений службы.</span><span class="sxs-lookup"><span data-stu-id="71c4e-103">SharePoint mode is architected on the SharePoint service architecture and utilizes a SharePoint service and one to many service applications.</span></span> <span data-ttu-id="71c4e-104">Создание приложения службы открывает доступ к службе и формирует базу данных приложения службы.</span><span class="sxs-lookup"><span data-stu-id="71c4e-104">Creating a service application makes the service available and generates the service application database.</span></span> <span data-ttu-id="71c4e-105">Можно создать несколько приложений службы Reporting Services, однако для большинства сценариев развертывания достаточно одного приложения службы.</span><span class="sxs-lookup"><span data-stu-id="71c4e-105">You can create multiple Reporting Services service applications but one service application is sufficient for most deployment scenarios.</span></span>  
  
 <span data-ttu-id="71c4e-106">В этом разделе рассматриваются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="71c4e-106">This topic covers the following information:</span></span>  
  
-   [<span data-ttu-id="71c4e-107">Создание приложения службы Reporting Services</span><span class="sxs-lookup"><span data-stu-id="71c4e-107">Creating a Reporting Services Service Application</span></span>](#bkmk_createapp)  
  
-   [<span data-ttu-id="71c4e-108">Изменение взаимосвязей приложения службы с использованием группы прокси-серверов</span><span class="sxs-lookup"><span data-stu-id="71c4e-108">Modify the Associations of the Service Application with a proxy group</span></span>](#bkmk_associations)  
  
-   [<span data-ttu-id="71c4e-109">Изменение свойств приложения службы</span><span class="sxs-lookup"><span data-stu-id="71c4e-109">Edit Service Application Properties</span></span>](#bkmk_editserviceapplication)  
  
-   [<span data-ttu-id="71c4e-110">Создание приложения службы Reporting Services с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="71c4e-110">To create a Reporting Services Service Application using PowerShell</span></span>](#bkmk_powershell_create_ssrs_serviceapp)  
  
-   [<span data-ttu-id="71c4e-111">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="71c4e-111">Related Tasks</span></span>](#bkmk_related)  
  
##  <a name="creating-a-reporting-services-service-application"></a><a name="bkmk_createapp"></a><span data-ttu-id="71c4e-112">Создание приложения службы Reporting Services</span><span class="sxs-lookup"><span data-stu-id="71c4e-112">Creating a Reporting Services Service Application</span></span>  
 <span data-ttu-id="71c4e-113">Центр администрирования SharePoint или скрипты PowerShell можно использовать для создания приложений служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71c4e-113">You can use SharePoint Central Administration or PowerShell scripts to create the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] services applications.</span></span> <span data-ttu-id="71c4e-114">Дополнительные сведения об использовании центра администрирования SharePoint см. в разделе "Создание приложения службы Reporting Services" статьи [Установка служб Reporting Services в режиме интеграции с SharePoint для SharePoint 2010](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="71c4e-114">For more information on using SharePoint Central Administration, see the "Create a Reporting Services Service Application" section in [Install Reporting Services SharePoint Mode for SharePoint 2010](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md).</span></span> <span data-ttu-id="71c4e-115">В подразделе PowerShell этого раздела приведен пример скрипта PowerShell для создания приложений службы.</span><span class="sxs-lookup"><span data-stu-id="71c4e-115">See the PowerShell section later in this topic for a sample PowerShell script for creating service applications.</span></span>  
  
##  <a name="modify-the-associations-of-the-service-application-with-a-proxy-group"></a><a name="bkmk_associations"></a><span data-ttu-id="71c4e-116">Изменение сопоставлений приложения службы с помощью группы прокси-серверов</span><span class="sxs-lookup"><span data-stu-id="71c4e-116">Modify the Associations of the Service Application with a proxy group</span></span>  
 <span data-ttu-id="71c4e-117">Новая страница для создания приложения служб содержит раздел **Связь с веб-приложением**.</span><span class="sxs-lookup"><span data-stu-id="71c4e-117">The New page for creating a services application contains the section **Web Application Association**.</span></span> <span data-ttu-id="71c4e-118">Данный раздел позволяет связать приложение службы во время его создания.</span><span class="sxs-lookup"><span data-stu-id="71c4e-118">The section allows you to associate your service application as you create it.</span></span> <span data-ttu-id="71c4e-119">Для изменения взаимосвязи и установки пользовательской конфигурации в приложении службы выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="71c4e-119">Use the following steps to change the association and assign a customer configuration to the service application.</span></span> <span data-ttu-id="71c4e-120">Можно использовать тот же общий процесс, но вместо изменения взаимосвязи приложения службы с пользовательской группой добавить учетную запись-посредник в группу по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71c4e-120">The same general process can also be used to add the proxy to the default group rather than changing the association of the service application to a custom group.</span></span>  
  
1.  <span data-ttu-id="71c4e-121">В центре администрирования SharePoint в разделе «Управление приложениями» выберите пункт **Настройка связей приложения службы**.</span><span class="sxs-lookup"><span data-stu-id="71c4e-121">In SharePoint Central Administration, in the Application Management, click **Configure Service Application Associations**.</span></span>  
  
2.  <span data-ttu-id="71c4e-122">На странице «Связи между приложениями служб» измените представление для **Приложения служб**.</span><span class="sxs-lookup"><span data-stu-id="71c4e-122">On the Service application Associations page, change the view to **Service Applications**.</span></span>  
  
3.  <span data-ttu-id="71c4e-123">Найдите и щелкните название нового приложения службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71c4e-123">Find and click the name of your new [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Service application.</span></span> <span data-ttu-id="71c4e-124">Можно щелкнуть группу прокси-серверов приложения **по умолчанию** для добавления прокси-сервера в группу по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71c4e-124">You could also click the application proxy group name **default** to add the proxy to default group rather than completing the following steps.</span></span>  
  
4.  <span data-ttu-id="71c4e-125">В списке **Изменить следующую группу соединений** выберите **Пользовательская**.</span><span class="sxs-lookup"><span data-stu-id="71c4e-125">Select **Custom** in the selection box **Edit the following group of connections**.</span></span>  
  
5.  <span data-ttu-id="71c4e-126">Установите флажок для учетной записи-посредника и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="71c4e-126">Check the box for your proxy and click **Ok**.</span></span>  
  
##  <a name="edit-service-application-properties"></a><a name="bkmk_editserviceapplication"></a> <span data-ttu-id="71c4e-127">Изменение свойств приложения службы</span><span class="sxs-lookup"><span data-stu-id="71c4e-127">Edit Service Application Properties</span></span>  
 <span data-ttu-id="71c4e-128">Для изменения свойств можно повторно открыть страницу свойств приложения службы.</span><span class="sxs-lookup"><span data-stu-id="71c4e-128">You can reopen the property page of the service application to modify the properties.</span></span>  
  
1.  <span data-ttu-id="71c4e-129">В центре администрирования SharePoint, в разделе «Управление приложениями», выберите **Управление приложениями служб**.</span><span class="sxs-lookup"><span data-stu-id="71c4e-129">In SharePoint Central Administration, in the Application Management group, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="71c4e-130">Выберите приложение службы, щелкнув столбец типа, чтобы выделить всю строку.</span><span class="sxs-lookup"><span data-stu-id="71c4e-130">Select the service application by clicking the type column to select the entire row.</span></span> <span data-ttu-id="71c4e-131">Если щелкнуть имя приложения, откроется страница «Параметры управления» для службы, а не свойства приложения службы.</span><span class="sxs-lookup"><span data-stu-id="71c4e-131">If you click the name of the application it, the Management options page for the service opens instead of opening the properties of the service application.</span></span>  
  
3.  <span data-ttu-id="71c4e-132">На ленте «Приложения службы» нажмите кнопку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="71c4e-132">In the Service Applications ribbon, click **Properties**.</span></span>  
  
##  <a name="to-create-a-reporting-services-service-application-using-powershell"></a><a name="bkmk_powershell_create_ssrs_serviceapp"></a><span data-ttu-id="71c4e-133">Создание приложения службы Reporting Services с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="71c4e-133">To create a Reporting Services Service Application using PowerShell</span></span>  
 <span data-ttu-id="71c4e-134">Создать приложение службы и прокси-сервер можно с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71c4e-134">You can use PowerShell to create the Service application and proxy.</span></span> <span data-ttu-id="71c4e-135">В следующем примере предполагается, что пул приложения, который необходимо настроить для использования приложения службы, известен вам.</span><span class="sxs-lookup"><span data-stu-id="71c4e-135">The sample below assumes that you know what application pool you want to configure the service application to use.</span></span>  
  
1.  <span data-ttu-id="71c4e-136">Добавьте объект пула приложений, соответствующий имени пула приложений, в переменную, передаваемую в новое действие.</span><span class="sxs-lookup"><span data-stu-id="71c4e-136">Add the application pool object of your application pool name to a variable that is passed into the New action.</span></span>  
  
    ```powershell
    $appPoolName = Get-SPServiceApplicationPool "<application pool name>"  
    ```  
  
2.  <span data-ttu-id="71c4e-137">Создайте приложение службы с указанным именем и именем пула приложений.</span><span class="sxs-lookup"><span data-stu-id="71c4e-137">Create the service application with a name and application pool name you provide.</span></span>  
  
    ```powershell
    New-SPRSServiceApplication -Name 'MyServiceApplication' -ApplicationPool $appPoolName -DatabaseName 'MyServiceApplicationDatabase' -DatabaseServer '<Server Name>'  
    ```  
  
3.  <span data-ttu-id="71c4e-138">Получите новый объект приложения службы и передайте объект в канал командлета создания новой учетной записи-посредника.</span><span class="sxs-lookup"><span data-stu-id="71c4e-138">Get the new service application object, and pipe the object into the Pipe the new proxy cmdlet.</span></span>  
  
    ```powershell
    Get-SPRSServiceApplication -name MyServiceApplication | New-SPRSServiceApplicationProxy "MyServiceApplicationProxy"  
    ```  
  
##  <a name="related-tasks"></a><a name="bkmk_related"></a> <span data-ttu-id="71c4e-139">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="71c4e-139">Related Tasks</span></span>  
  
|<span data-ttu-id="71c4e-140">Задача</span><span class="sxs-lookup"><span data-stu-id="71c4e-140">Task</span></span>|<span data-ttu-id="71c4e-141">Ссылка</span><span class="sxs-lookup"><span data-stu-id="71c4e-141">Link</span></span>|  
|----------|----------|  
|<span data-ttu-id="71c4e-142">Управление параметрами приложения службы.</span><span class="sxs-lookup"><span data-stu-id="71c4e-142">Manage the settings of your Service Application.</span></span>|[<span data-ttu-id="71c4e-143">Управление Служебным приложением SharePoint службы Reporting Services</span><span class="sxs-lookup"><span data-stu-id="71c4e-143">Manage a Reporting Services SharePoint Service Application</span></span>](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md)|  
|<span data-ttu-id="71c4e-144">Резервное копирование и восстановление приложения службы и связанных компонентов, таких как ключи шифрования и прокси-серверы.</span><span class="sxs-lookup"><span data-stu-id="71c4e-144">Backup and restore the service application and related components such as encryption keys and proxy.</span></span>|[<span data-ttu-id="71c4e-145">Резервное копирование и восстановление приложения службы SharePoint — Reporting Services</span><span class="sxs-lookup"><span data-stu-id="71c4e-145">Backup and Restore Reporting Services SharePoint Service Applications</span></span>](../../2014/reporting-services/backup-and-restore-reporting-services-sharepoint-service-applications.md)|  
