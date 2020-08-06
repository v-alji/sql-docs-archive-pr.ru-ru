---
title: Включение и отключение печати на стороне клиента для служб Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0e709c96-7517-4547-8ef6-5632f8118524
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 031a7cd9b5da07b03b76b6bf49db63572a8fe546
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665797"
---
# <a name="enable-and-disable-client-side-printing-for-reporting-services"></a><span data-ttu-id="e3336-102">Включение и отключение печати на стороне клиента для служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e3336-102">Enable and Disable Client-Side Printing for Reporting Services</span></span>
  <span data-ttu-id="e3336-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)]Элемент управления ActiveX, **RSClientPrint**, обеспечивает печать на стороне клиента для отчетов, просматриваемых в браузере.</span><span class="sxs-lookup"><span data-stu-id="e3336-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX control, **RSClientPrint**, provides client-side printing for reports viewed in a browser.</span></span> <span data-ttu-id="e3336-104">Данный элемент управления отображает пользовательское диалоговое окно печати, которое поддерживает функции, общие с другими диалоговыми окнами печати.</span><span class="sxs-lookup"><span data-stu-id="e3336-104">The control displays a custom print dialog box that supports features common to other print dialog boxes.</span></span> <span data-ttu-id="e3336-105">Среди этих функций — предварительный просмотр, выбор страниц для указания отдельных страниц и диапазонов, поля и ориентация страниц.</span><span class="sxs-lookup"><span data-stu-id="e3336-105">The features include print preview, page selections for specifying specific pages and ranges, page margins, and orientation.</span></span> <span data-ttu-id="e3336-106">Хотя по умолчанию клиентская печать допускается, эту функцию можно отключить.</span><span class="sxs-lookup"><span data-stu-id="e3336-106">Although client-side printing is enabled by default, you can disable the feature to prevent it from being used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3336-107">Для загрузки элементов управления ActiveX требуется разрешение администратора.</span><span class="sxs-lookup"><span data-stu-id="e3336-107">Downloading ActiveX controls requires administrator permissions.</span></span>  
  
## <a name="downloading-the-activex-control"></a><span data-ttu-id="e3336-108">Загрузка элементов управления ActiveX</span><span class="sxs-lookup"><span data-stu-id="e3336-108">Downloading the ActiveX Control</span></span>  
 <span data-ttu-id="e3336-109">Каждый пользователь, который хочет использовать функцию печати, должен загрузить и установить элемент управления ActiveX, который обеспечивает функцию клиентской печати.</span><span class="sxs-lookup"><span data-stu-id="e3336-109">Each user who wants to use the print feature must download and install the ActiveX control that provides client print functionality.</span></span> <span data-ttu-id="e3336-110">Когда пользователь в первый раз нажимает значок **принтера** на панели инструментов отчета, элемент управления Microsoft ActiveX загружается на компьютер.</span><span class="sxs-lookup"><span data-stu-id="e3336-110">The first time a user clicks the **Printer** icon on the report toolbar, the Microsoft ActiveX control is downloaded to the computer.</span></span> <span data-ttu-id="e3336-111">После загрузки элемента управления диалоговое окно **Печать** отображается каждый раз, когда пользователь щелкает значок **принтера** .</span><span class="sxs-lookup"><span data-stu-id="e3336-111">After the control is downloaded, the **Print** dialog box displays whenever the user clicks the **Printer** icon.</span></span>  
  
 <span data-ttu-id="e3336-112">В зависимости от настройки браузера, пользователю может быть указана необходимость установки элемента управления, либо установка элемента управления может быть ему запрещена, либо элемент управления может быть установлен в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="e3336-112">Depending on browser settings, the user may be prompted to install the control, be prevented from installing the control, or have the control install transparently in the background.</span></span>  
  
 <span data-ttu-id="e3336-113">Для [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer параметры, влияющие на загрузку и установку элементов управления ActiveX, указываются через узел **элементы управления ActiveX и подключаемые модули** на странице **Параметры безопасности** для зоны веб-содержимого.</span><span class="sxs-lookup"><span data-stu-id="e3336-113">For [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer, settings that affect ActiveX control download and installation are specified through the **ActiveX controls and plug-ins** node in the **Security Settings** page for the Web content zone.</span></span> <span data-ttu-id="e3336-114">Следующие настройки определяют, может ли пользователь загружать и запускать элементы управления печатью, исходя из настроек безопасности зоны Интернета:</span><span class="sxs-lookup"><span data-stu-id="e3336-114">The following settings determine whether users can download and run the print control, based on Web zone security preferences:</span></span>  
  
-   <span data-ttu-id="e3336-115">Загрузка подписанных элементов управления ActiveX.</span><span class="sxs-lookup"><span data-stu-id="e3336-115">Download signed ActiveX controls.</span></span>  
  
-   <span data-ttu-id="e3336-116">Включение в скрипты элементов управления ActiveX, отмеченных как безопасные.</span><span class="sxs-lookup"><span data-stu-id="e3336-116">Script ActiveX controls marked safe for scripting.</span></span>  
  
-   <span data-ttu-id="e3336-117">Запуск элементов управления и дополнений ActiveX.</span><span class="sxs-lookup"><span data-stu-id="e3336-117">Run ActiveX controls and plug-ins.</span></span>  
  
 <span data-ttu-id="e3336-118">Пользователи, желающие использовать **RSClientPrint** для печати на стороне клиента, должны включить следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="e3336-118">Users who want to use **RSClientPrint** to perform client-side printing must enable the following:</span></span>  
  
-   <span data-ttu-id="e3336-119">**Скачивание подписанных элементов управления ActiveX** и **сценариев элемента управления ActiveX, помеченных как надежные для создания сценариев** в целях установки.</span><span class="sxs-lookup"><span data-stu-id="e3336-119">**Download signed ActiveX controls** and **Script ActiveX control marked safe for scripting** for installation purposes.</span></span>  
  
-   <span data-ttu-id="e3336-120">**Запускайте элементы управления ActiveX и подключаемые** модули для выполнения текущих операций печати.</span><span class="sxs-lookup"><span data-stu-id="e3336-120">**Run ActiveX controls and plug-ins** for ongoing print operations.</span></span>  
  
 <span data-ttu-id="e3336-121">Элемент управления ActiveX **RSClientPrint** подписан, то есть он содержит действительный цифровой сертификат из [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3336-121">The **RSClientPrint** ActiveX control is signed, meaning it contains a valid digital certificate from [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span></span>  
  
## <a name="enabling-and-disabling-client-side-printing"></a><span data-ttu-id="e3336-122">Разрешение и запрет печати на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="e3336-122">Enabling and Disabling Client-Side Printing</span></span>  
 <span data-ttu-id="e3336-123">Администраторы сервера отчетов могут отключить функцию печати, задав системному свойству сервера отчетов **EnableClientPrinting** значение `false` .</span><span class="sxs-lookup"><span data-stu-id="e3336-123">Report server administrators have the option of disabling the print feature by setting the report server system property **EnableClientPrinting** to `false`.</span></span> <span data-ttu-id="e3336-124">Это отключает клиентскую печать всех отчетов, управляемых этим сервером.</span><span class="sxs-lookup"><span data-stu-id="e3336-124">This will disable client-side printing for all reports managed by that server.</span></span> <span data-ttu-id="e3336-125">По умолчанию **EnableClientPrinting** имеет значение `true` .</span><span class="sxs-lookup"><span data-stu-id="e3336-125">By default, **EnableClientPrinting** is set to `true`.</span></span> <span data-ttu-id="e3336-126">Вы можете запретить печать на стороне клиента следующими способами.</span><span class="sxs-lookup"><span data-stu-id="e3336-126">You can disable client-side printing in the following ways:</span></span>  
  
-   <span data-ttu-id="e3336-127">Для **сервера отчетов в собственном режиме**</span><span class="sxs-lookup"><span data-stu-id="e3336-127">For a **Native mode report server**:</span></span>  
  
    1.  <span data-ttu-id="e3336-128">Запустите [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="e3336-128">Start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with administrative privileges.</span></span>  
  
    2.  <span data-ttu-id="e3336-129">Подключитесь к экземпляру сервера отчетов в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3336-129">Connect to a report server instance in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
    3.  <span data-ttu-id="e3336-130">Щелкните правой кнопкой мыши узел сервера отчетов и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e3336-130">Right-click the report server node, and then click **Properties**.</span></span> <span data-ttu-id="e3336-131">Если параметр **Свойства** недоступен, то убедитесь, что среда [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] запущена с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="e3336-131">If the **Properties** option is disabled, verify you started [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with administrative privileges.</span></span>  
  
    4.  <span data-ttu-id="e3336-132">Выберите **включить скачивание для элемента управления печатью клиента ActiveX**.</span><span class="sxs-lookup"><span data-stu-id="e3336-132">Select **Enable download for the ActiveX client print control**.</span></span>  
  
    5.  <span data-ttu-id="e3336-133">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3336-133">Click **OK**.</span></span>  
  
-   <span data-ttu-id="e3336-134">Для **сервера отчетов в режиме интеграции с SharePoint**:</span><span class="sxs-lookup"><span data-stu-id="e3336-134">For a **SharePoint mode report server**:</span></span>  
  
    1.  <span data-ttu-id="e3336-135">В центре администрирования SharePoint перейдите на страницу **Управление приложением**.</span><span class="sxs-lookup"><span data-stu-id="e3336-135">In SharePoint Central Administration, click **Application Management**.</span></span>  
  
    2.  <span data-ttu-id="e3336-136">Выберите **Управление приложениями службы**.</span><span class="sxs-lookup"><span data-stu-id="e3336-136">Click **Manage service applications**.</span></span>  
  
    3.  <span data-ttu-id="e3336-137">Щелкните рядом с именем приложения службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , затем нажмите кнопку **Управление** на ленте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e3336-137">Click the name of your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application, and then click **Manage** in the SharePoint ribbon.</span></span>  
  
    4.  <span data-ttu-id="e3336-138">Нажмите кнопку **Системные параметры**.</span><span class="sxs-lookup"><span data-stu-id="e3336-138">Click **System Settings**.</span></span>  
  
    5.  <span data-ttu-id="e3336-139">Выберите **Включение печати на стороне клиента**.</span><span class="sxs-lookup"><span data-stu-id="e3336-139">Select **Enable Client Printing**.</span></span> <span data-ttu-id="e3336-140">Параметр **Включение печати на стороне клиента** расположен в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="e3336-140">The **Enable Client Printing** option is near the bottom of the page.</span></span>  
  
    6.  <span data-ttu-id="e3336-141">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3336-141">Click **OK**.</span></span>  
  
-   <span data-ttu-id="e3336-142">Напишите скрипт или код, чтобы задать системному свойству сервера отчетов **EnableClientPrinting** значение`false.`</span><span class="sxs-lookup"><span data-stu-id="e3336-142">Write script or code to set the report server system property **EnableClientPrinting** to `false.`</span></span>  
  
 <span data-ttu-id="e3336-143">Следующий образец скрипта иллюстрирует один из способов отключения клиентской печати.</span><span class="sxs-lookup"><span data-stu-id="e3336-143">The following sample script illustrates one approach for disabling client-side printing.</span></span> <span data-ttu-id="e3336-144">Скомпилируйте и запустите следующий код [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], чтобы присвоить свойству **EnableClientPrinting** значение **False**.</span><span class="sxs-lookup"><span data-stu-id="e3336-144">Compile and then run the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] code to set the **EnableClientPrinting** property to **False**.</span></span> <span data-ttu-id="e3336-145">После выполнения кода перезапустите IIS.</span><span class="sxs-lookup"><span data-stu-id="e3336-145">After you run the code, restart IIS.</span></span>  
  
### <a name="sample-script"></a><span data-ttu-id="e3336-146">Образец скрипта</span><span class="sxs-lookup"><span data-stu-id="e3336-146">Sample Script</span></span>  
  
```  
Imports System  
Imports System.Web.Services.Protocols  
Class Sample  
   Public Shared Sub Main()  
Dim rs As New ReportingService()  
      rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
        Dim props(0) As [Property]  
        Dim setProp As New [Property]  
        setProp.Name = "EnableClientPrinting"  
        setProp.Value = "False"   
        props(0) = setProp  
        Try  
            rs.SetSystemProperties(props)  
        Catch ex As System.Web.Services.Protocols.SoapException  
            Console.Write(ex.Detail.InnerXml)  
        Catch e as Exception  
            Console.Write(e.Message)  
        End Try  
    End Sub 'Main  
End Class 'Sample  
```  
  
  
