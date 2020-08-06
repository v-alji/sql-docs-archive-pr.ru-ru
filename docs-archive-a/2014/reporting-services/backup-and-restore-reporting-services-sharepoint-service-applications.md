---
title: Резервное копирование и восстановление Reporting Services приложений служб SharePoint | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: dfb4ed77-90e5-4273-b690-89a945508ed2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 488659d269542381be9bcf1b1b6115acf89f8a98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664033"
---
# <a name="backup-and-restore-reporting-services-sharepoint-service-applications"></a><span data-ttu-id="fc6de-102">Резервное копирование и восстановление Служебного приложения SharePoint службы Reporting Services</span><span class="sxs-lookup"><span data-stu-id="fc6de-102">Backup and Restore Reporting Services SharePoint Service Applications</span></span>
  <span data-ttu-id="fc6de-103">В этом разделе описывается резервное копирование и восстановление приложения служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] с использованием центра администрирования SharePoint или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc6de-103">This topic describes how to backup and restore a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] services application using SharePoint Central Administration or PowerShell.</span></span> <span data-ttu-id="fc6de-104">В этом разделе содержится следующее.</span><span class="sxs-lookup"><span data-stu-id="fc6de-104">The topic contains:</span></span>  
  
-   [<span data-ttu-id="fc6de-105">Ограничения</span><span class="sxs-lookup"><span data-stu-id="fc6de-105">Limitations and Restrictions</span></span>](#bkmk_Restrictions)  
  
-   [<span data-ttu-id="fc6de-106">Создание резервной копии приложения службы</span><span class="sxs-lookup"><span data-stu-id="fc6de-106">Backup The Service application</span></span>](#bkmk_backup)  
  
-   [<span data-ttu-id="fc6de-107">Восстановление приложения службы</span><span class="sxs-lookup"><span data-stu-id="fc6de-107">Restore the Service Application</span></span>](#bkmk_restore)  
  
##  <a name="before-you-begin"></a><a name="bkmk_BeforeYouBegin"></a> <span data-ttu-id="fc6de-108">Перед началом</span><span class="sxs-lookup"><span data-stu-id="fc6de-108">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="bkmk_Restrictions"></a> <span data-ttu-id="fc6de-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="fc6de-109">Limitations and Restrictions</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc6de-110">Для приложений служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] можно выполнять частичное резервное копирование и восстановление с использованием функциональных возможностей резервного копирования и восстановления SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fc6de-110">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications can partially be backed up and restored using the SharePoint backup and restore functionality.</span></span> <span data-ttu-id="fc6de-111">**Требуются дополнительные шаги** и шаги описаны в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="fc6de-111">**Additional steps are required** and the steps are documented in this topic.</span></span> <span data-ttu-id="fc6de-112">В данный момент процесс резервного копирования **не создает** резервные копии ключей шифрования и учетных данных для учетных записей автоматического выполнения или проверки подлинности Windows в базе данных служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fc6de-112">Currently the backup process **does not** backup encryption keys and credentials for unattended execution accounts (UEA) or windows authentication to the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] database.</span></span>  
  
###  <a name="recommendations"></a><a name="bkmk_recommendations"></a> <span data-ttu-id="fc6de-113">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="fc6de-113">Recommendations</span></span>  
  
-   <span data-ttu-id="fc6de-114">Создайте резервную копию ключей шифрования перед началом резервного копирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fc6de-114">Backup the encryption keys before starting the SharePoint backup.</span></span> <span data-ttu-id="fc6de-115">Если резервная копия ключей шифрования не была создана, то после восстановления приложения службы будет невозможно осуществлять доступ к зашифрованным данным.</span><span class="sxs-lookup"><span data-stu-id="fc6de-115">If you do not backup the encryption keys, then you will not be able to access your encrypted data, following the restore of the service application.</span></span> <span data-ttu-id="fc6de-116">Зашифрованные данные будет необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="fc6de-116">You will need to delete your encrypted data.</span></span>  
  
-   <span data-ttu-id="fc6de-117">Убедитесь, что в приложении службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] используются учетные записи автоматического выполнения или проверка подлинности Windows для доступа к базе данных.</span><span class="sxs-lookup"><span data-stu-id="fc6de-117">Verify if your [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application is using UEA or Windows authentication for database access.</span></span> <span data-ttu-id="fc6de-118">Если используется одна из вышеупомянутых возможностей, следует узнать, какие учетные данные являются допустимыми, чтобы в последствии, после завершения процесса восстановления, было возможно правильно настроить приложение службы.</span><span class="sxs-lookup"><span data-stu-id="fc6de-118">If it is using either, verify what the proper credentials are so you can correctly configure the service application after the restore process.</span></span>  
  
-   <span data-ttu-id="fc6de-119">Проверьте журнал резервного копирования SharePoint созданный в той же папке, что и файл резервной копии.</span><span class="sxs-lookup"><span data-stu-id="fc6de-119">Review the SharePoint backup log is created in the same folder as the backup file.</span></span> <span data-ttu-id="fc6de-120">Этот файл обычно имеет имя **spbackup.log**</span><span class="sxs-lookup"><span data-stu-id="fc6de-120">The file is typically named **spbackup.log**</span></span>  
  
##  <a name="backup-the-service-application"></a><a name="bkmk_backup"></a><span data-ttu-id="fc6de-121">Создание резервной копии приложения службы</span><span class="sxs-lookup"><span data-stu-id="fc6de-121">Backup The Service application</span></span>  
 <span data-ttu-id="fc6de-122">Последовательно выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="fc6de-122">Complete the following steps in order:</span></span>  
  
1.  <span data-ttu-id="fc6de-123">Выполните резервное копирование ключей шифрования</span><span class="sxs-lookup"><span data-stu-id="fc6de-123">Backup the encryption keys</span></span>  
  
2.  <span data-ttu-id="fc6de-124">Резервное копирование приложения службы</span><span class="sxs-lookup"><span data-stu-id="fc6de-124">Backup the Service application</span></span>  
  
3.  <span data-ttu-id="fc6de-125">Убедитесь, что в приложении службы используются учетные данные автоматического выполнения или проверка подлинности Windows для доступа к базе данных.</span><span class="sxs-lookup"><span data-stu-id="fc6de-125">Verify if you service application uses an UEA or Windows authentication for database access.</span></span> <span data-ttu-id="fc6de-126">Если они используются, запишите эти учетные данные, чтобы их можно было использовать при настройке восстановленного приложения службы.</span><span class="sxs-lookup"><span data-stu-id="fc6de-126">If it does, make a note of the credentials so you can use them to configure the service application after it is restored.</span></span>  
  
### <a name="backup-the-encryption-keys-using-central-administration"></a><span data-ttu-id="fc6de-127">Выполните резервное копирование ключей шифрования, с помощью центра администрирования</span><span class="sxs-lookup"><span data-stu-id="fc6de-127">Backup the Encryption Keys using Central Administration</span></span>  
 <span data-ttu-id="fc6de-128">Сведения о резервном копировании [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] ключей шифрования см. в разделе "ключи шифрования" раздела [Управление приложением службы Reporting Services SharePoint](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="fc6de-128">For information on backing up the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] encryption keys, see the "Encryption Keys" section of [Manage a Reporting Services SharePoint Service Application](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span></span>  
  
###  <a name="backup-the-service-application-using-sharepoint-central-administration"></a><a name="bkmk_centraladmin"></a><span data-ttu-id="fc6de-129">Резервное копирование приложения службы с помощью центра администрирования SharePoint</span><span class="sxs-lookup"><span data-stu-id="fc6de-129">Backup the Service application Using SharePoint Central Administration</span></span>  
 <span data-ttu-id="fc6de-130">Для резервного копирования приложения службы, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fc6de-130">To back up the Service Application, complete the following steps:</span></span>  
  
1.  <span data-ttu-id="fc6de-131">В центре администрирования SharePoint нажмите кнопку **Создать резервную копию** в группе **Резервное копирование и восстановление** .</span><span class="sxs-lookup"><span data-stu-id="fc6de-131">In SharePoint Central Administration Click **Perform a backup** in the **Backup and Restore** group.</span></span>  
  
2.  <span data-ttu-id="fc6de-132">В узле **Общие службы** разверните (узел?) **Общие приложения служб** и выберите приложение службы.</span><span class="sxs-lookup"><span data-stu-id="fc6de-132">Under the **Shared Services** node, expand **Shared Service Applications** and select your service application.</span></span> <span data-ttu-id="fc6de-133">Оно будет иметь тип **Приложение службы SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="fc6de-133">It will have a type of **SQL Server Reporting Services Service Application**.</span></span>  
  
3.  <span data-ttu-id="fc6de-134">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fc6de-134">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="fc6de-135">Введите путь для **Расположения резервной копии:** и нажмите кнопку **Запустить резервное копирование**</span><span class="sxs-lookup"><span data-stu-id="fc6de-135">Type the path for the **Backup location:** and click **Start Backup**</span></span>  
  
5.  <span data-ttu-id="fc6de-136">Повторите описанный выше процесс, но вместо выбора приложения службы, разверните узел **Прокси серверы общих служб** и выберите прокси-сервер приложения службы.</span><span class="sxs-lookup"><span data-stu-id="fc6de-136">Repeat the process above but instead of selecting the service application, expand the **Shared Services Proxies** node, and select service application proxy.</span></span> <span data-ttu-id="fc6de-137">Оно будет иметь тип **Прокси-сервер приложения службы SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="fc6de-137">It will have a type of **SQL Server Reporting Services Service Application Proxy**.</span></span>  
  
 <span data-ttu-id="fc6de-138">Дополнительные сведения см. в следующих разделах документации по SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fc6de-138">For more information, see the following topics in the SharePoint documentation:</span></span>  
  
 <span data-ttu-id="fc6de-139">[Резервное копирование приложения службы (SharePoint Foundation 2010) в документации SharePoint](https://msdn.microsoft.com/library/ee748601.aspx).</span><span class="sxs-lookup"><span data-stu-id="fc6de-139">[Back up a service application (SharePoint Foundation 2010) in the SharePoint documenttation](https://msdn.microsoft.com/library/ee748601.aspx).</span></span>  
  
 [<span data-ttu-id="fc6de-140">Создайте резервную копию приложения службы (SharePoint Server 2010)</span><span class="sxs-lookup"><span data-stu-id="fc6de-140">Back up a service application (SharePoint Server 2010)</span></span>](https://technet.microsoft.com/library/ee428318.aspx)  
  
### <a name="verify-execution-account-and-database-authentication"></a><span data-ttu-id="fc6de-141">Проверьте учетную запись выполнения и проверку подлинности базы данных</span><span class="sxs-lookup"><span data-stu-id="fc6de-141">Verify Execution Account and Database Authentication</span></span>  
 <span data-ttu-id="fc6de-142">**Учетная запись выполнения.** Чтобы проверить используется ли в приложении службы учетная запись выполнения, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="fc6de-142">**Execution Account:** To verify if your service application is using an execution account:</span></span>  
  
1.  <span data-ttu-id="fc6de-143">В центре администрирования SharePoint щелкните **Управление приложениями службы** в группе **Управление приложениями** .</span><span class="sxs-lookup"><span data-stu-id="fc6de-143">In SharePoint Central Administration, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="fc6de-144">Щелкните имя приложения службы и нажмите кнопку **Управление** на ленте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fc6de-144">Click the name of your service application and then click **Manage** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="fc6de-145">Щелкните **Учетная запись выполнения**.</span><span class="sxs-lookup"><span data-stu-id="fc6de-145">Click **Execution Account**.</span></span>  
  
4.  <span data-ttu-id="fc6de-146">Если была настроена учетная запись выполнения, то при восстановлении резервной копии приложения службы будет необходимо иметь в наличии учетные данные.</span><span class="sxs-lookup"><span data-stu-id="fc6de-146">If an execution account is configured, you need to know the credentials when it is time to restore the service application backup.</span></span> <span data-ttu-id="fc6de-147">Не приступайте к процедуре резервного копирования и восстановления до тех пор, пока не будут известны правильные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="fc6de-147">Do not proceed with the backup and restore procedure until you know the correct credentials.</span></span>  
  
 <span data-ttu-id="fc6de-148">**Проверка подлинности базы данных.** Чтобы убедиться, что приложение службы использует проверку подлинности Windows для проверки подлинности базы данных, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fc6de-148">**Database Authentication:** To verify if your service application is using Windows Authentication for the database authentication:</span></span>  
  
1.  <span data-ttu-id="fc6de-149">В центре администрирования SharePoint щелкните **Управление приложениями службы** в группе **Управление приложениями** .</span><span class="sxs-lookup"><span data-stu-id="fc6de-149">In SharePoint Central Administration, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="fc6de-150">Щелкните рядом с именем приложения службы, затем нажмите кнопку **Свойства** на ленте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fc6de-150">Click the name of your service application and then click **Properties** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="fc6de-151">Проверьте раздел **База данных службы Reporting Services (SSRS)** .</span><span class="sxs-lookup"><span data-stu-id="fc6de-151">Review the **Reporting Services (SSRS) Service Database** section.</span></span>  
  
4.  <span data-ttu-id="fc6de-152">Если была настроена проверка подлинности Windows, то для настройки приложения службы после его восстановления будет необходимо знать верные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="fc6de-152">If Windows Authentication is configured, you need to know the credentials so you can configure the service application after you restore it.</span></span> <span data-ttu-id="fc6de-153">Не приступайте к процедуре резервного копирования и восстановления до тех пор, пока не будут известны правильные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="fc6de-153">Do not proceed with the backup and restore procedure until you know the correct credentials.</span></span>  
  
##  <a name="restore-the-service-application"></a><a name="bkmk_restore"></a><span data-ttu-id="fc6de-154">Восстановление приложения службы</span><span class="sxs-lookup"><span data-stu-id="fc6de-154">Restore the Service Application</span></span>  
 <span data-ttu-id="fc6de-155">Последовательно выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="fc6de-155">Complete the following steps in order:</span></span>  
  
1.  <span data-ttu-id="fc6de-156">Восстановление приложение службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fc6de-156">Restore the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
2.  <span data-ttu-id="fc6de-157">Восстановите ключи шифрования</span><span class="sxs-lookup"><span data-stu-id="fc6de-157">Restore the encryption keys</span></span>  
  
3.  <span data-ttu-id="fc6de-158">Если в приложении службы для доступа к базе данных использовалась учетная запись выполнения или проверка подлинности Windows, следует настроить учетные данные.</span><span class="sxs-lookup"><span data-stu-id="fc6de-158">If your service application was using an execution account or Windows authentication for database access, configure the credentials.</span></span>  
  
### <a name="restore-the-service-application-using-sharepoint-central-administration"></a><span data-ttu-id="fc6de-159">Восстановите резервную копию приложения службы в центре администрирования SharePoint</span><span class="sxs-lookup"><span data-stu-id="fc6de-159">Restore the Service application Using SharePoint Central Administration</span></span>  
  
1.  <span data-ttu-id="fc6de-160">В центре администрирования SharePoint нажмите кнопку **Восстановление из резервной копии** в группе **Резервное копирование и восстановление** .</span><span class="sxs-lookup"><span data-stu-id="fc6de-160">In SharePoint Central Administration Click **Restore from a backup** in the **Backup and Restore** group.</span></span>  
  
2.  <span data-ttu-id="fc6de-161">Введите путь к файлу резервной копии в поле **Расположение каталога резервного копирования** и нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="fc6de-161">Type the path to your backup file in **Backup Directory Location** box and click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="fc6de-162">Выберите резервную копию приложения службы в списке **Верхний компонент** затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fc6de-162">Select your service application backup from the **Top Component** list and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="fc6de-163">Выберите приложение служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fc6de-163">Select your [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] application and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="fc6de-164">В разделе **Имена входа и пароли** введите пароль для имени входа.</span><span class="sxs-lookup"><span data-stu-id="fc6de-164">In the **Login Names and Passwords** section type the password for the login name.</span></span> <span data-ttu-id="fc6de-165">В поле «Имя входа» следует ввести имя входа, использовавшееся приложением службы до создания резервной копии.</span><span class="sxs-lookup"><span data-stu-id="fc6de-165">The login name box should be populated with the login the service application was using prior to the backup.</span></span>  
  
6.  <span data-ttu-id="fc6de-166">Нажмите кнопку **Начать восстановление**.</span><span class="sxs-lookup"><span data-stu-id="fc6de-166">Click **Start Restore**.</span></span>  
  
7.  <span data-ttu-id="fc6de-167">Повторите описанный выше процесс, но вместо восстановления приложения службы, разверните узел **Общие службы** и узел **Приложения общей службы** .</span><span class="sxs-lookup"><span data-stu-id="fc6de-167">Repeat the process above but instead of restoring the service application, expand the **Shared Services** node and then expand the **Shared Service Applications** node.</span></span>  
  
 <span data-ttu-id="fc6de-168">Дополнительные сведения см. в следующих разделах документации по SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fc6de-168">For more information, see the following topics in the SharePoint documentation:</span></span>  
  
 <span data-ttu-id="fc6de-169">[Восстановление приложения службы (SharePoint Foundation 2010)](https://msdn.microsoft.com/library/ee748615.aspx).</span><span class="sxs-lookup"><span data-stu-id="fc6de-169">[Restore a service application (SharePoint Foundation 2010)](https://msdn.microsoft.com/library/ee748615.aspx).</span></span>  
  
 <span data-ttu-id="fc6de-170">[Восстановление приложения службы (SharePoint Server 2010)](https://technet.microsoft.com/library/ee428305.aspx).</span><span class="sxs-lookup"><span data-stu-id="fc6de-170">[Restore a service application (SharePoint Server 2010)](https://technet.microsoft.com/library/ee428305.aspx).</span></span>  
  
### <a name="restore-the-encryption-keys-using-central-administration"></a><span data-ttu-id="fc6de-171">Восстановление ключей шифрования с помощью центра администрирования</span><span class="sxs-lookup"><span data-stu-id="fc6de-171">Restore the Encryption Keys using Central Administration</span></span>  
 <span data-ttu-id="fc6de-172">Сведения о восстановлении [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] ключей шифрования см. в разделе "ключи шифрования" раздела [Управление приложением службы Reporting Services SharePoint](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="fc6de-172">For information on restoring the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] encryption keys, see the "Encryption Keys" section of [Manage a Reporting Services SharePoint Service Application](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span></span>  
  
### <a name="configure-the-execution-account-and-database-authentication"></a><span data-ttu-id="fc6de-173">Настройка учетной записи выполнения и проверки подлинности базы данных</span><span class="sxs-lookup"><span data-stu-id="fc6de-173">Configure the Execution Account and Database Authentication</span></span>  
 <span data-ttu-id="fc6de-174">**Учетная запись выполнения.** Если в приложении службы использовалась учетная запись выполнения, выполните следующие шаги для ее настройки.</span><span class="sxs-lookup"><span data-stu-id="fc6de-174">**Execution Account:** If your service application was using an execution account complete the following steps to configure it:</span></span>  
  
1.  <span data-ttu-id="fc6de-175">В центре администрирования SharePoint щелкните **Управление приложениями службы** в группе **Управление приложениями** .</span><span class="sxs-lookup"><span data-stu-id="fc6de-175">In SharePoint Central Administration, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="fc6de-176">Щелкните имя приложения службы и нажмите кнопку **Управление** на ленте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fc6de-176">Click the name of your service application and then click **Manage** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="fc6de-177">Щелкните **Учетная запись выполнения**.</span><span class="sxs-lookup"><span data-stu-id="fc6de-177">Click **Execution Account**.</span></span>  
  
4.  <span data-ttu-id="fc6de-178">Введите учетную запись, пароль и выберите поле **Указать учетную запись выполнения** .</span><span class="sxs-lookup"><span data-stu-id="fc6de-178">Type the account, password, and select the **Specify and Execution Account** box.</span></span>  
  
5.  <span data-ttu-id="fc6de-179">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fc6de-179">Click **OK**.</span></span>  
  
 <span data-ttu-id="fc6de-180">**Проверка подлинности базы данных.** Если в приложении службы для проверки подлинности базы данных используется проверка подлинности Windows, выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="fc6de-180">**Database Authentication:** If your service application was using Windows Authentication for the database authentication complete the following steps:</span></span>  
  
1.  <span data-ttu-id="fc6de-181">В центре администрирования SharePoint щелкните **Управление приложениями службы** в группе **Управление приложениями** .</span><span class="sxs-lookup"><span data-stu-id="fc6de-181">In SharePoint Central Administration click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="fc6de-182">Щелкните рядом с именем приложения службы, затем нажмите кнопку **Свойства** на ленте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fc6de-182">Click the name of your service application and then click **Properties** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="fc6de-183">Проверьте раздел **База данных службы Reporting Services (SSRS)** .</span><span class="sxs-lookup"><span data-stu-id="fc6de-183">Review the **Reporting Services (SSRS) Service Database** section.</span></span>  
  
4.  <span data-ttu-id="fc6de-184">Выберите параметр **Проверка подлинности Windows**.</span><span class="sxs-lookup"><span data-stu-id="fc6de-184">Select **Windows Authentication**.</span></span>  
  
5.  <span data-ttu-id="fc6de-185">Введите учетную запись и пароль.</span><span class="sxs-lookup"><span data-stu-id="fc6de-185">Type the account and password.</span></span> <span data-ttu-id="fc6de-186">Выберите **Использовать учетные данные Windows** если это уместно.</span><span class="sxs-lookup"><span data-stu-id="fc6de-186">Select **Use as Windows Credentials** if appropriate.</span></span>  
  
6.  <span data-ttu-id="fc6de-187">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fc6de-187">Click **Ok**</span></span>  
  
  
