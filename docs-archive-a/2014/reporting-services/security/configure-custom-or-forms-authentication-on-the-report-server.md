---
title: Настройка нестандартной проверки подлинности или проверки подлинности с помощью форм на сервере отчетов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Forms authentication, configuring
- custom authentication [Reporting Services]
ms.assetid: e8601a8f-e66d-4649-8e4d-a46ca20ec7d0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1447e1e695f0e59dbc07b7e19f4df335a1220a97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656979"
---
# <a name="configure-custom-or-forms-authentication-on-the-report-server"></a><span data-ttu-id="2200b-102">Настройка нестандартной проверки подлинности или проверку подлинности с помощью форм на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="2200b-102">Configure Custom or Forms Authentication on the Report Server</span></span>
  <span data-ttu-id="2200b-103">Службы Reporting Services предоставляют открытую архитектуру, которая позволяет подключать нестандартные модули проверки подлинности и модули проверки подлинности с помощью форм.</span><span class="sxs-lookup"><span data-stu-id="2200b-103">Reporting Services provides an extensible architecture that allows you to plug in custom or forms-based authentication modules.</span></span> <span data-ttu-id="2200b-104">Можно рассмотреть возможность реализации нестандартного модуля проверки подлинности, если требования к развертыванию не включают встроенной безопасности Windows или обычную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="2200b-104">You might consider implementing a custom authentication extension if deployment requirements do not include Windows integrated security or Basic authentication.</span></span> <span data-ttu-id="2200b-105">Наиболее распространенный сценарий использования нестандартной проверки подлинности — доступ к веб-приложению через Интернет или экстрасеть.</span><span class="sxs-lookup"><span data-stu-id="2200b-105">The most common scenario for using custom authentication is to support Internet or extranet access to a Web application.</span></span> <span data-ttu-id="2200b-106">Замена модуля проверки подлинности Windows по умолчанию нестандартным модулем проверки подлинности обеспечивает более широкие возможности управления предоставлением доступа к серверу отчетов внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="2200b-106">Replacing the default Windows Authentication extension with a custom authentication extension gives you more control over how external users are granted access to the report server.</span></span>  
  
 <span data-ttu-id="2200b-107">На практике для развертывания нестандартного модуля проверки подлинности требуется выполнить несколько шагов, в том числе копировать сборки и файлы приложений, изменять файлы конфигурации и выполнять тестирование.</span><span class="sxs-lookup"><span data-stu-id="2200b-107">In practice, deploying a custom authentication extension requires multiple steps that include copying assemblies and application files, modifying configuration files, and testing.</span></span> <span data-ttu-id="2200b-108">В этом разделе рассматриваются только параметры проверки подлинности, указанные в файлах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2200b-108">This topic focuses on just the authentication settings that you specify in the configuration files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2200b-109">Чтобы создать нестандартный модуль проверки подлинности, необходимо написать определенный код и хорошо разбираться в системе безопасности [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2200b-109">Creating a custom authentication extension requires custom code and expertise in [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] security.</span></span> <span data-ttu-id="2200b-110">Если не нужно создавать нестандартный модуль проверки подлинности, можно использовать группы и учетные записи [!INCLUDE[msCoName](../../includes/msconame-md.md)] Active Directory, но это связано со значительным уменьшением области развертывания сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="2200b-110">If you do not want to create a custom authentication extension, you can use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Active Directory groups and accounts, but you should greatly reduce the scope of a report server deployment.</span></span> <span data-ttu-id="2200b-111">Дополнительные сведения о нестандартной проверке подлинности см. в разделе [Implementing a Security Extension](../extensions/security-extension/implementing-a-security-extension.md).</span><span class="sxs-lookup"><span data-stu-id="2200b-111">For more information about custom authentication, see [Implementing a Security Extension](../extensions/security-extension/implementing-a-security-extension.md).</span></span>  
  
 <span data-ttu-id="2200b-112">Кроме того, если нужно использовать проверку подлинности с помощью форм или нестандартный модуль проверки подлинности в среде служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , интегрированной с продуктом SharePoint, то необходимо настроить сайт SharePoint на использование выбранного метода проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2200b-112">Additionally, if you want to use Forms authentication or a custom authentication extension in a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] environment that is integrated with a SharePoint product, you must configure the SharePoint site to use the authentication method that you choose.</span></span> <span data-ttu-id="2200b-113">Дополнительные сведения о настройке проверки подлинности в SharePoint см. в разделе [Authentication Samples](https://go.microsoft.com/fwlink/?LinkId=115575) в библиотеке MSDN [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2200b-113">For more information about configuring authentication in SharePoint, see [Authentication Samples](https://go.microsoft.com/fwlink/?LinkId=115575) on [!INCLUDE[msCoName](../../includes/msconame-md.md)] Developer Network (MSDN).</span></span>  
  
### <a name="to-configure-a-report-server-to-use-custom-authentication"></a><span data-ttu-id="2200b-114">Настройка сервера отчетов для использования нестандартной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="2200b-114">To configure a report server to use Custom authentication</span></span>  
  
1.  <span data-ttu-id="2200b-115">Откройте файл конфигурации RSReportServer.config в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="2200b-115">Open RSReportServer.config in a text editor.</span></span>  
  
2.  <span data-ttu-id="2200b-116">Найдите `Authentication`> <.</span><span class="sxs-lookup"><span data-stu-id="2200b-116">Find <`Authentication`>.</span></span>  
  
3.  <span data-ttu-id="2200b-117">Скопируйте следующую структуру XML:</span><span class="sxs-lookup"><span data-stu-id="2200b-117">Copy the following XML structure:</span></span>  
  
    ```  
    <Authentication>  
          <AuthenticationTypes>  
                 <Custom />  
          </AuthenticationTypes>  
          <EnableAuthPersistence>true</EnableAuthPersistence>  
    </Authentication>  
    ```  
  
4.  <span data-ttu-id="2200b-118">Вставьте его поверх существующих записей для <`Authentication`>.</span><span class="sxs-lookup"><span data-stu-id="2200b-118">Paste it over the existing entries for <`Authentication`>.</span></span>  
  
     <span data-ttu-id="2200b-119">Следует заметить, что `Custom` нельзя использовать с другими типами проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2200b-119">Note that you cannot use `Custom` with other authentication types.</span></span>  
  
5.  <span data-ttu-id="2200b-120">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="2200b-120">Save the file.</span></span>  
  
6.  <span data-ttu-id="2200b-121">Откройте файл конфигурации Web.config для сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="2200b-121">Open the Web.config file for the report server.</span></span> <span data-ttu-id="2200b-122">По умолчанию он находится в \Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportServer.</span><span class="sxs-lookup"><span data-stu-id="2200b-122">By default, it is located at \Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportServer.</span></span>  
  
7.  <span data-ttu-id="2200b-123">Найдите параметр `authentication mode` и установите значение `Forms`.</span><span class="sxs-lookup"><span data-stu-id="2200b-123">Find `authentication mode` and set it `Forms`.</span></span>  
  
    ```  
    <authentication mode = "Forms" />  
    ```  
  
8.  <span data-ttu-id="2200b-124">Найдите параметр `identity impersonate` и установите значение `False`.</span><span class="sxs-lookup"><span data-stu-id="2200b-124">Find `identity impersonate` and set it to `False`.</span></span>  
  
    ```  
    <identity impersonate = "false" />  
    ```  
  
9. <span data-ttu-id="2200b-125">Откройте файл конфигурации Web.config для диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="2200b-125">Open the Web.config file for Report Manager.</span></span> <span data-ttu-id="2200b-126">По умолчанию она находится в каталоге «\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportManager».</span><span class="sxs-lookup"><span data-stu-id="2200b-126">By default, it is located at \Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportManager.</span></span>  
  
10. <span data-ttu-id="2200b-127">Найдите параметр `authentication mode` и установите значение `Forms`.</span><span class="sxs-lookup"><span data-stu-id="2200b-127">Find `authentication mode` and set it `Forms`.</span></span>  
  
    ```  
    <authentication mode = "Forms" />  
    ```  
  
11. <span data-ttu-id="2200b-128">Найдите параметр `identity impersonate` и установите значение `False`.</span><span class="sxs-lookup"><span data-stu-id="2200b-128">Find `identity impersonate` and set it to `False`.</span></span>  
  
    ```  
    <identity impersonate = "false" />  
    ```  
  
12. <span data-ttu-id="2200b-129">Добавьте элемент структуры `PassThroughCookies` к файлу конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2200b-129">Add the `PassThroughCookies` element structure to the configuration file.</span></span> <span data-ttu-id="2200b-130">Дополнительные сведения см. в разделе [Настройка передачи куки-файлов для нестандартной проверки подлинности пользователя в диспетчере отчетов](configure-the-web-portal-to-pass-custom-authentication-cookies.md).</span><span class="sxs-lookup"><span data-stu-id="2200b-130">For more information, see [Configure Report Manager to Pass Custom Authentication Cookies](configure-the-web-portal-to-pass-custom-authentication-cookies.md).</span></span>  
  
13. <span data-ttu-id="2200b-131">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="2200b-131">Save the file.</span></span>  
  
14. <span data-ttu-id="2200b-132">Если настроено масштабное развертывание, повторите все предыдущие шаги для других серверов отчетов в развертывании.</span><span class="sxs-lookup"><span data-stu-id="2200b-132">If you configured a scale-out deployment, repeat all of the previous steps for other report servers in the deployment.</span></span>  
  
15. <span data-ttu-id="2200b-133">Перезапустите сервер отчетов, чтобы очистить все открытые сеансы.</span><span class="sxs-lookup"><span data-stu-id="2200b-133">Restart the report server to clear any sessions that are currently open.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2200b-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="2200b-134">See Also</span></span>  
 <span data-ttu-id="2200b-135">[Реализация модуля безопасности](../extensions/security-extension/implementing-a-security-extension.md) </span><span class="sxs-lookup"><span data-stu-id="2200b-135">[Implementing a Security Extension](../extensions/security-extension/implementing-a-security-extension.md) </span></span>  
 <span data-ttu-id="2200b-136">[Проверка подлинности с использованием сервера отчетов](authentication-with-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="2200b-136">[Authentication with the Report Server](authentication-with-the-report-server.md) </span></span>  
 <span data-ttu-id="2200b-137">[Файл конфигурации RSReportServer](../report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="2200b-137">[RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="2200b-138">[Настройка обычной проверки подлинности на сервере отчетов](configure-basic-authentication-on-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="2200b-138">[Configure Basic Authentication on the Report Server](configure-basic-authentication-on-the-report-server.md) </span></span>  
 [<span data-ttu-id="2200b-139">Настройка аутентификации Windows на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="2200b-139">Configure Windows Authentication on the Report Server</span></span>](configure-windows-authentication-on-the-report-server.md)  
  
  
