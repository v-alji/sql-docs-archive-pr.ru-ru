---
title: Настройка электронной почты для приложения службы Reporting Services (SharePoint 2010 и SharePoint 2013) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 38fc34a6-aae7-4dde-9ad2-f1eee0c42a9f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 628122289f8a9d83a307d70a369ab51f8f571c04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665850"
---
# <a name="configure-e-mail-for-a-reporting-services-service-application-sharepoint-2010-and-sharepoint-2013"></a><span data-ttu-id="6058c-102">Настройка электронной почты для приложения служб Reporting Services (SharePoint 2010 и SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="6058c-102">Configure E-mail for a Reporting Services Service Application (SharePoint 2010 and SharePoint 2013)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="6058c-103">Функция предупреждения об изменении данных служб отправляет предупреждения в сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="6058c-103">data alerting sends alerts in e-mail messages.</span></span> <span data-ttu-id="6058c-104">Для отправки электронной почты могут потребоваться настройка приложения службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] и изменение модуля доставки электронной почты приложением службы.</span><span class="sxs-lookup"><span data-stu-id="6058c-104">To send e-mail you may need to configure your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application and you may need to modify the e-mail delivery extension for the service application.</span></span> <span data-ttu-id="6058c-105">Необходимо настроить параметры электронной почты и в том случае, если планируется использование модуля доставки электронной почты функцией подписки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6058c-105">The e-mail settings are also required if you plan to use the e-mail delivery extension for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] subscription feature.</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="6058c-106">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Режим интеграции с sharepoint &#124; sharepoint 2010 и sharepoint 2013.</span><span class="sxs-lookup"><span data-stu-id="6058c-106">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode &#124; SharePoint 2010 and SharePoint 2013.</span></span>|  
  
### <a name="to-configure-e-mail-for-the-shared-service"></a><span data-ttu-id="6058c-107">Настройка электронной почты для общей службы</span><span class="sxs-lookup"><span data-stu-id="6058c-107">To configure e-mail for the shared service</span></span>  
  
1.  <span data-ttu-id="6058c-108">В центре администрирования SharePoint перейдите на страницу **Управление приложением**.</span><span class="sxs-lookup"><span data-stu-id="6058c-108">In SharePoint Central Administration, click the **Application Management**.</span></span>  
  
2.  <span data-ttu-id="6058c-109">В группе **Приложения службы** выберите пункт **Управление приложениями службы**.</span><span class="sxs-lookup"><span data-stu-id="6058c-109">In the **Service Applications** group, click **Manage service applications**.</span></span>  
  
3.  <span data-ttu-id="6058c-110">В списке **Имя** выберите имя нужного приложения службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6058c-110">In the **Name** list, click the name of your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
4.  <span data-ttu-id="6058c-111">Нажмите кнопку **Параметры электронной почты** на странице **Управление приложением служб Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="6058c-111">Click **E-mail Settings** on the **Manage Reporting Services Application** page.</span></span>  
  
5.  <span data-ttu-id="6058c-112">Установите флажок **Использовать SMTP-сервер**.</span><span class="sxs-lookup"><span data-stu-id="6058c-112">Select **Use SMTP server**.</span></span>  
  
6.  <span data-ttu-id="6058c-113">В поле **Исходящий SMTP-сервер** введите имя SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="6058c-113">In the **Outbound SMTP server** box, type the name of an SMTP server.</span></span>  
  
7.  <span data-ttu-id="6058c-114">В поле **Адрес отправителя** введите адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="6058c-114">In the **From address** box, type an e-mail address.</span></span>  
  
     <span data-ttu-id="6058c-115">Этот адрес будет использоваться как адрес отправителя всех электронных сообщений с предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="6058c-115">This address is the sender of all alert e-mail messages.</span></span>  
  
     <span data-ttu-id="6058c-116">Учетная запись пользователя, указанная в поле **Адрес отправителя** , должна быть управляемой учетной записью, указанной при настройке пула приложений для приложения службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6058c-116">The account of the user specified in **From address** must be a managed account that you specified when you configured the application pool for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="6058c-117">Если имеются необходимые разрешения, можно просмотреть список существующих управляемых учетных записей на странице «Учетные записи службы» центра администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6058c-117">If you have permission, you can view a list of existing managed accounts on the Service Accounts page in SharePoint Central Administration.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="ntlm-authentication"></a><span data-ttu-id="6058c-118">Проверка подлинности NTLM</span><span class="sxs-lookup"><span data-stu-id="6058c-118">NTLM Authentication</span></span>  
  
1.  <span data-ttu-id="6058c-119">Если среда электронной почты требует проверки подлинности NTLM и не поддерживает анонимный доступ, необходимо изменить настройки модуля доставки электронной почты приложениям службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6058c-119">If your email environment requires NTLM authentication and does not allow anonymous access, you need to modify the e-mail delivery extension configuration for your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service applications.</span></span> <span data-ttu-id="6058c-120">Измените **значение SMTPAuthenticate равным** , чтобы использовать значение "2".</span><span class="sxs-lookup"><span data-stu-id="6058c-120">Change the **SMTPAuthenticate** to use a value of "2".</span></span> <span data-ttu-id="6058c-121">Это значение нельзя изменить через пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="6058c-121">This value cannot be changed from the user interface.</span></span> <span data-ttu-id="6058c-122">Следующий пример скрипта PowerShell обновляет полную конфигурацию расширения сервера отчетов для доставки электронной почты приложением службы с именем SSRS_TESTAPPLICATION.</span><span class="sxs-lookup"><span data-stu-id="6058c-122">The following PowerShell script example, updates the full configuration for the report server e-mail delivery extension for the service application named "SSRS_TESTAPPLICATION".</span></span> <span data-ttu-id="6058c-123">Обратите внимание, что некоторые перечисленные в скрипте узлы (например, адрес отправителя) можно также задать через пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="6058c-123">Note some of the nodes listed in the script can also be set from the user interface, for example the "From" address.</span></span>  
  
    ```powershell
    $app = Get-SPRSServiceApplication | Where {$_.name -like "SSRS_TESTAPPLICATION *"}  
    $emailCfg = Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml
    $emailXml = [xml]$emailCfg
    $emailXml.SelectSingleNode("//SMTPServer").InnerText = "your email server name"  
    $emailXml.SelectSingleNode("//SendUsing").InnerText = "2"  
    $emailXml.SelectSingleNode("//SMTPAuthenticate").InnerText = "2"  
    $emailXml.SelectSingleNode("//From").InnerText = "your FROM email address"  
    Set-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" -ExtensionConfiguration $emailXml.OuterXml  
    ```  
  
2.  <span data-ttu-id="6058c-124">Если необходимо проверить имя приложения службы, выполните командлет **Get-SPRSServiceApplication** .</span><span class="sxs-lookup"><span data-stu-id="6058c-124">If you need to verify the name of your service application, run the **Get-SPRSServiceApplication** cmdlet.</span></span>  
  
    ```powershell
    Get-SPRSServiceApplication  
    ```  
  
3.  <span data-ttu-id="6058c-125">Следующий пример возвращает текущие значения модуля доставки электронной почты для приложения службы с именем SSRS_TESTAPPLICATION.</span><span class="sxs-lookup"><span data-stu-id="6058c-125">The following example will return the current values of the e-mail extension for the service application named "SSRS_TESTAPPLICATION".</span></span>  
  
    ```powershell
    $app = get-sprsserviceapplication | Where {$_.name -like "SSRSTEST_APPLICATION*"}  
    Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml  
    ```  
  
4.  <span data-ttu-id="6058c-126">Следующий пример создает новый файл с именем emailconfig.txt, содержащий текущие значения модуля доставки электронной почты для приложения службы с именем SSRS_TESTAPPLICATION.</span><span class="sxs-lookup"><span data-stu-id="6058c-126">The following example will create a new file named "emailconfig.txt" with the current values of the e-mail extension for the service application named "SSRS_TESTAPPLICATION"</span></span>  
  
    ```powershell
    $app = Get-SPRSServiceApplication | Where {$_.name -like "SSRS_TESTAPPLICATION*"}  
    Get-SPRSExtension -identity $app -ExtensionType "Delivery" -name "Report Server Email" | Select -ExpandProperty ConfigurationXml | Out-File c:\emailconfig.txt  
    ```
