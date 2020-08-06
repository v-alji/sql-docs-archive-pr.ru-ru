---
title: Планирование обновления данных и источников данных, не поддерживающих проверку подлинности Windows (PowerPivot для SharePoint) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d8d875bc-7823-46b7-a939-867cefd4de12
author: minewiskan
ms.author: owend
ms.openlocfilehash: 63e37dec6f334395c0c1812c6f76d750c16c53ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664538"
---
# <a name="schedule-data-refresh-and-data-sources-that-do-not-support-windows-authentication-powerpivot-for-sharepoint"></a><span data-ttu-id="c2ad3-102">Планирование обновления данных и источники данных, которые не поддерживают проверку подлинности Windows (PowerPivot для SharePoint)</span><span class="sxs-lookup"><span data-stu-id="c2ad3-102">Schedule Data Refresh and Data Sources That Do Not Support Windows Authentication (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="c2ad3-103">В этом разделе рассматривается рабочий процесс планирования обновления данных PowerPivot для SharePoint, в котором могут использоваться источники данных, **НЕ** поддерживающие проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-103">This topic describes a workflow of PowerPivot for SharePoint schedule data fresh that can use data sources that do **NOT** support Windows Authentication.</span></span> <span data-ttu-id="c2ad3-104">В качестве примера можно назвать источники данных Oracle или IDM DB2.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-104">For example Oracle or IDM DB2 data sources.</span></span> <span data-ttu-id="c2ad3-105">На рисунках и в процедурах, которые приведены в этом разделе, речь идет об источниках данных Oracle, но тот же рабочий процесс применим к другим источникам данных.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-105">The illustrations and steps in this topic reference Oracle data sources but the same workflow applies to other data sources.</span></span>  
  
||  
|-|  
|<span data-ttu-id="c2ad3-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2010 &#124; SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2010 &#124; SharePoint 2013.</span></span>|  
  
 <span data-ttu-id="c2ad3-107">**Обзор** . Создание двух целевых приложений Secure Store.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-107">**Overview:** Create two Secure Store Target Applications.</span></span> <span data-ttu-id="c2ad3-108">Настройка использования учетных данных Windows в первом целевом приложении (PowerPivotDataRefresh).</span><span class="sxs-lookup"><span data-stu-id="c2ad3-108">Configure the first target application (PowerPivotDataRefresh) to use Windows credentials.</span></span> <span data-ttu-id="c2ad3-109">Настройка во втором целевом приложении учетных данных для источника данных, который не поддерживает проверку подлинности Windows, например для базы данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-109">Configure the second target application with the credentials for a data source that does not support windows authentication, for example, an Oracle database.</span></span> <span data-ttu-id="c2ad3-110">Кроме того, во втором целевом приложении используется первое целевое приложение в качестве учетной записи автоматического обновления данных.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-110">The second target application also uses the first target application for the unattended data refresh account.</span></span>  
  
 <span data-ttu-id="c2ad3-111">![as_powerpivot_refresh_no_windows_auth](../media/as-powerpivot-refresh-no-windows-auth.gif "as_powerpivot_refresh_no_windows_auth")</span><span class="sxs-lookup"><span data-stu-id="c2ad3-111">![as_powerpivot_refresh_no_windows_auth](../media/as-powerpivot-refresh-no-windows-auth.gif "as_powerpivot_refresh_no_windows_auth")</span></span>  
  
-   <span data-ttu-id="c2ad3-112">**(1) PowerPivotDatarefresh** : идентификатор целевого приложения Secure Store, в котором настроена аутентификация Windows.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-112">**(1) PowerPivotDatarefresh:** A Secure Store Target Application ID that is set with windows authentication.</span></span>  
  
-   <span data-ttu-id="c2ad3-113">**(2) OracleAuthentication** : идентификатор целевого приложения Secure Store, в котором заданы учетные данные Oracle.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-113">**(2) OracleAuthentication:** A Secure Store Target Application ID that is set with Oracle credentials.</span></span>  
  
-   <span data-ttu-id="c2ad3-114">**(3)** приложение службы PowerPivot настроено на использование целевого приложения "PowerPivotDataRefresh" для **учетной записи автоматического обновления данных**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-114">**(3)** The PowerPivot Service application is configure to use the target application "PowerPivotDataRefresh" for the **Unattended Data Refresh Account**.</span></span>  
  
-   <span data-ttu-id="c2ad3-115">**(4)** В книге PowerePivot используются данные Oracle.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-115">**(4)** PowerePivot Workbook uses Oracle data.</span></span> <span data-ttu-id="c2ad3-116">Настройки обновления книги указывают, что при соединении с источником данных следует использовать целевое приложение **(2)** в качестве учетных данных.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-116">The workbook refresh settings specify the data source connection to use the target application **(2)** for credentials.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c2ad3-117">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c2ad3-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="c2ad3-118">Имеется приложение службы PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-118">A PowerPivot Service Application exists.</span></span>  
  
-   <span data-ttu-id="c2ad3-119">Имеется приложение службы Secure Store.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-119">A Secure Store Service Application exists.</span></span>  
  
-   <span data-ttu-id="c2ad3-120">Имеется книга Excel с моделью данных PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-120">An Excel workbook with a PowerPivot data model exists.</span></span>  
  
## <a name="to-create-a-target-application-id-that-uses-windows-authentication"></a><span data-ttu-id="c2ad3-121">Создание идентификатора целевого приложения, в котором используется проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="c2ad3-121">To Create a Target Application ID that uses Windows Authentication</span></span>  
  
1.  <span data-ttu-id="c2ad3-122">В центре администрирования SharePoint щелкните **Управление приложениями служб**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-122">In SharePoint Central administration, click **Manage Service Applications**.</span></span>  
  
2.  <span data-ttu-id="c2ad3-123">Щелкните имя своего приложения службы Secure Store.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-123">Click the name of your secure store service application.</span></span>  
  
3.  <span data-ttu-id="c2ad3-124">На странице **Управление** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-124">On the **Manage** page, click **New**.</span></span> <span data-ttu-id="c2ad3-125">![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application")</span><span class="sxs-lookup"><span data-stu-id="c2ad3-125">![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application")</span></span>  
  
4.  <span data-ttu-id="c2ad3-126">На странице **Создание нового целевого приложения Secure Store** задайте следующие значения.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-126">On the **Create New Secure Store Target Application** page, configure the following values:</span></span>  
  
    -   <span data-ttu-id="c2ad3-127">**Идентификатор целевого приложения** : PowerPivotDataRefresh.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-127">**Target Application ID:** PowerPivotDataRefresh.</span></span>  
  
    -   <span data-ttu-id="c2ad3-128">**Отображаемое имя** : PowerPivotDataRefresh.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-128">**Display Name:** PowerPivotDataRefresh.</span></span>  
  
    -   <span data-ttu-id="c2ad3-129">**Адрес электронной почты для связи** : ?</span><span class="sxs-lookup"><span data-stu-id="c2ad3-129">**Contact E-mail:** ?</span></span>  
  
    -   <span data-ttu-id="c2ad3-130">**Тип целевого приложения** : группа.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-130">**Target Application Type:** Group.</span></span>  
  
    -   <span data-ttu-id="c2ad3-131">**URL-адрес страницы целевого приложения** : нет.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-131">**Target Application Page URL:** None.</span></span>  
  
5.  <span data-ttu-id="c2ad3-132">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-132">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="c2ad3-133">На странице «Учетные данные» оставьте неизменными два заданных по умолчанию имени поля и типа поля: **Имя пользователя Windows** и **Пароль Windows**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-133">On the Credentials page, leave the two default field names and field types for **Windows User Name** and **Windows Password**.</span></span>  
  
7.  <span data-ttu-id="c2ad3-134">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-134">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="c2ad3-135">На странице **Настройки членства** добавьте по крайней мере одного **администратора целевого приложения** , затем добавьте членов, которым требуется доступ к целевому приложению.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-135">On the **Membership Settings** page, add at least one **Target Application Administrator** and then add members that need access to the target application.</span></span>  
  
9. <span data-ttu-id="c2ad3-136">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-136">Click **OK**.</span></span>  
  
10. <span data-ttu-id="c2ad3-137">Новый идентификатор целевого приложения будет добавлен к списку.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-137">The new Target Application ID is added to the list.</span></span> <span data-ttu-id="c2ad3-138">Выберите идентификатор целевого приложения и щелкните **Set credential as_powerpivot_refresh_sss_set_key (задать учетные данные**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key")).</span><span class="sxs-lookup"><span data-stu-id="c2ad3-138">Select the Target application ID and click **Set Credentials**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span></span>  
  
11. <span data-ttu-id="c2ad3-139">Введите имя пользователя Windows и пароль Windows, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-139">Type the Windows User Name and Windows Password and then click **OK**.</span></span>  
  
## <a name="to-create-a-target-application-id-that-uses-oracle-credentials"></a><span data-ttu-id="c2ad3-140">Создание идентификатора целевого приложения, в котором используются учетные данные Oracle</span><span class="sxs-lookup"><span data-stu-id="c2ad3-140">To Create a Target Application ID that uses Oracle credentials</span></span>  
  
1.  <span data-ttu-id="c2ad3-141">В центре администрирования SharePoint щелкните **Управление приложениями служб**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-141">In SharePoint Central administration, click **Manage Service Applications**.</span></span>  
  
2.  <span data-ttu-id="c2ad3-142">Щелкните имя своего приложения службы Secure Store.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-142">Click the name of your Secure Store Service application.</span></span>  
  
3.  <span data-ttu-id="c2ad3-143">На странице **Управление** нажмите кнопку **создать**![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application").</span><span class="sxs-lookup"><span data-stu-id="c2ad3-143">On the **Manage** page, click **New**![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application").</span></span>  
  
4.  <span data-ttu-id="c2ad3-144">На странице **Создание нового целевого приложения Secure Store** задайте следующие значения.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-144">On the **Create New Secure Store Target Application** page, configure the following values:</span></span>  
  
    -   <span data-ttu-id="c2ad3-145">**Идентификатор целевого приложения** : OracleAuthentication.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-145">**Target Application ID:** OracleAuthentication.</span></span>  
  
    -   <span data-ttu-id="c2ad3-146">**Отображаемое имя** : OracleAuthentication.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-146">**Display Name:** OracleAuthentication.</span></span>  
  
    -   <span data-ttu-id="c2ad3-147">**Адрес электронной почты для связи** : ?</span><span class="sxs-lookup"><span data-stu-id="c2ad3-147">**Contact E-mail:** ?</span></span>  
  
    -   <span data-ttu-id="c2ad3-148">**Тип целевого приложения** : группа.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-148">**Target Application Type:** Group.</span></span>  
  
    -   <span data-ttu-id="c2ad3-149">**URL-адрес страницы целевого приложения** : нет.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-149">**Target Application Page URL:** None.</span></span>  
  
5.  <span data-ttu-id="c2ad3-150">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-150">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="c2ad3-151">На странице **учетные данные** измените имя первого поля на `Oracle User ID` и измените **тип поля** на `User Name` .</span><span class="sxs-lookup"><span data-stu-id="c2ad3-151">On the **Credentials** page, change the first field name to `Oracle User ID` and change the **Field Type** to `User Name`.</span></span>  
  
     <span data-ttu-id="c2ad3-152">Измените имя второго поля на `Oracle Password` , а **тип поля** — на `Password` .</span><span class="sxs-lookup"><span data-stu-id="c2ad3-152">Change the second field name to `Oracle Password` and the **Field Type** to `Password`.</span></span>  
  
7.  <span data-ttu-id="c2ad3-153">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-153">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="c2ad3-154">На странице **Настройки членства** добавьте по крайней мере одного **администратора целевого приложения** , затем добавьте членов, которым требуется доступ к целевому приложению.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-154">On the **Membership Settings** page, add at least one **Target Application Administrator** and then add members that need access to the target application.</span></span>  
  
9. <span data-ttu-id="c2ad3-155">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-155">Click **OK**.</span></span>  
  
10. <span data-ttu-id="c2ad3-156">Новый идентификатор целевого приложения будет добавлен к списку.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-156">The new Target Application ID is added to the list.</span></span> <span data-ttu-id="c2ad3-157">Выберите идентификатор целевого приложения и щелкните **Set credential as_powerpivot_refresh_sss_set_key (задать учетные данные**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key")).</span><span class="sxs-lookup"><span data-stu-id="c2ad3-157">Select the Target application ID and click **Set Credentials**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span></span>  
  
11. <span data-ttu-id="c2ad3-158">Введите идентификатор пользователя Oracle и пароль Oracle, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-158">Type the Oracle User ID and Oracle Password and then click **OK**.</span></span>  
  
 <span data-ttu-id="c2ad3-159">Дополнительные сведения см. в разделе "создание целевого приложения для проверки подлинности SQL Server" раздела [Использование безопасного хранилища с проверкой Подлинности SQL Server (SharePoint Server 2013)](https://technet.microsoft.com/library/gg298949.aspx) ( https://technet.microsoft.com/library/gg298949.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c2ad3-159">For more information, see section "To Create a target application for SQL Server Authentication" in [Use Secure Store with SQL Server Authentication (SharePoint Server 2013)](https://technet.microsoft.com/library/gg298949.aspx) (https://technet.microsoft.com/library/gg298949.aspx).</span></span>  
  
## <a name="to-configure-the-powerpivot-service-application"></a><span data-ttu-id="c2ad3-160">Настройка приложения службы PowerPivot</span><span class="sxs-lookup"><span data-stu-id="c2ad3-160">To Configure the PowerPivot Service Application</span></span>  
  
1.  <span data-ttu-id="c2ad3-161">В центре администрирования SharePoint нажмите кнопку «Управление приложениями служб».</span><span class="sxs-lookup"><span data-stu-id="c2ad3-161">In SharePoint central administration, click Manage Service Applications.</span></span>  
  
2.  <span data-ttu-id="c2ad3-162">Щелкните имя приложения службы PowerPivot, например "приложение службы PowerPivot по умолчанию".</span><span class="sxs-lookup"><span data-stu-id="c2ad3-162">Click the name of your PowerPivot Service Application, for example "Default PowerPivot Service Application".</span></span>  
  
3.  <span data-ttu-id="c2ad3-163">Нажмите кнопку **Настройка параметров приложения службы** в разделе «Действия».</span><span class="sxs-lookup"><span data-stu-id="c2ad3-163">Click **Configure service application settings** in the Actions section.</span></span>  
  
4.  <span data-ttu-id="c2ad3-164">В разделе **Обновление данных** задайте для **учетной записи автоматического обновления данных PowerPivot**значение `PowerPivotDataRefresh` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-164">In the **Data Refresh** section, set the **PowerPivot Unattended Data Refresh Account**to`PowerPivotDataRefresh` and then click **OK**.</span></span>  
  
     <span data-ttu-id="c2ad3-165">![as_powerpivot_refresh_new_refresh_acount](../media/as-powerpivot-refresh-new-refresh-acount.gif "as_powerpivot_refresh_new_refresh_acount")</span><span class="sxs-lookup"><span data-stu-id="c2ad3-165">![as_powerpivot_refresh_new_refresh_acount](../media/as-powerpivot-refresh-new-refresh-acount.gif "as_powerpivot_refresh_new_refresh_acount")</span></span>  
  
## <a name="to-configure-the-workbook"></a><span data-ttu-id="c2ad3-166">Настройка книги</span><span class="sxs-lookup"><span data-stu-id="c2ad3-166">To configure the workbook</span></span>  
  
1.  <span data-ttu-id="c2ad3-167">Перейдите к книге в галерее PowerPivot и щелкните **Управление обновлением данных**![as_powerpivot_refresh_manage_reresh](../media/as-powerpivot-refresh-manage-reresh.gif "as_powerpivot_refresh_manage_reresh").</span><span class="sxs-lookup"><span data-stu-id="c2ad3-167">Browse to your workbook in the PowerPivot Gallery and click **Manage Data Refresh**![as_powerpivot_refresh_manage_reresh](../media/as-powerpivot-refresh-manage-reresh.gif "as_powerpivot_refresh_manage_reresh").</span></span>  
  
2.  <span data-ttu-id="c2ad3-168">Если откроется страница **Журнал обновления данных** , нажмите кнопку **Настройка расписания**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-168">If you see the **Data Refresh History** page, click **Configure Schedule**.</span></span>  
  
3.  <span data-ttu-id="c2ad3-169">Выберите **Включить**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-169">Click **Enable**.</span></span>  
  
4.  <span data-ttu-id="c2ad3-170">Щелкните **Также обновлять как можно скорее**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-170">Click **Also Refresh as soon as possible**.</span></span>  
  
5.  <span data-ttu-id="c2ad3-171">В разделе **Учетные данные** щелкните **Использовать учетную запись обновления данных, настроенную администратором**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-171">In the **Credentials** section, click **Use the Data refresh account configured by the administrator**.</span></span>  
  
6.  <span data-ttu-id="c2ad3-172">Снимите флажок **Все источники данных**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-172">Clear **All data sources**.</span></span>  
  
7.  <span data-ttu-id="c2ad3-173">Выберите **Обновить** для источника данных, в котором используются данные Oracle.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-173">Select **Refresh** for the data source that uses the Oracle data.</span></span> <span data-ttu-id="c2ad3-174">В Microsoft Excel имя источника данных можно изменить в меню **Данные**, **Соединения**, **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="c2ad3-174">The name of the data source name can be changed in Microsoft Excel in the **Data**, **Connections**, **Properties** menu.</span></span>  
  
8.  <span data-ttu-id="c2ad3-175">В разделе источников данных выберите **Использовать расписание по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-175">Under your data source, Select **Use Default Schedule**.</span></span>  
  
9. <span data-ttu-id="c2ad3-176">Выберите **Подключиться с использованием учетных данных, сохраненных в службе Secure Store (SSS) для подключения к источнику данных. Введите идентификатор, используемый для поиска учетных данных, в поле "Идентификатор SSS"**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-176">Select **Connect using the credentials saved in Secure Store Service (SSS) to log on to the data source. Enter the ID used to look up the credentials in the SSS ID box**.</span></span>  
  
10. <span data-ttu-id="c2ad3-177">В поле **идентификатор:** введите `OracleAuthentication` .</span><span class="sxs-lookup"><span data-stu-id="c2ad3-177">In the **ID:** box, type `OracleAuthentication`.</span></span>  
  
11. <span data-ttu-id="c2ad3-178">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-178">Click **OK**.</span></span>  
  
     <span data-ttu-id="c2ad3-179">Если появляется следующее сообщение об ошибке: `The provided Secure Store target application is either incorrectly configured or does not exist`.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-179">If you see an error message similar to: `The provided Secure Store target application is either incorrectly configured or does not exist`.</span></span>  
  
     <span data-ttu-id="c2ad3-180">Обычно применяются следующие два решения.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-180">The two common solutions are:</span></span>  
  
    -   <span data-ttu-id="c2ad3-181">Проверка правильности идентификатора целевого приложения.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-181">Verify that the Target Application ID is correct.</span></span>  
  
    -   <span data-ttu-id="c2ad3-182">Проверка того, заданы ли учетные данные для целевого приложения.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-182">Verify that you set credentials for the Target Application.</span></span>  
  
## <a name="to-verify-data-refresh-with-the-new-authentication"></a><span data-ttu-id="c2ad3-183">Проверка обновления данных с новыми параметрами проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="c2ad3-183">To Verify Data Refresh with the new authentication</span></span>  
 <span data-ttu-id="c2ad3-184">После нажатия кнопки **ОК**открывается страница **Журнал обновления** .</span><span class="sxs-lookup"><span data-stu-id="c2ad3-184">When you click **ok**, you see the **Refresh History** page.</span></span> <span data-ttu-id="c2ad3-185">Через несколько минут в журнале обновления должен появиться новый элемент, поскольку в предыдущих шагах был выбран параметр **Также обновлять как можно скорее**.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-185">Within a few minutes, you should see a new item in the refresh history because in the previous steps you selected **Also Refresh as soon as possible**.</span></span> <span data-ttu-id="c2ad3-186">Значение по умолчанию для задания таймера **Задание таймера обновления данных PowerPivot** равно 1 минуте.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-186">The default value for the timer job **PowerPivot Data Refresh Timer Job** is 1 minute.</span></span> <span data-ttu-id="c2ad3-187">Если новый элемент в журнале обновления не появляется, подождите несколько минут, затем обновите страницу в браузере.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-187">If you do not see a new item in the refresh history, wait a few minutes and refresh your browser.</span></span> <span data-ttu-id="c2ad3-188">Если новый элемент так и не появился, проверьте текущее значение задания таймера.</span><span class="sxs-lookup"><span data-stu-id="c2ad3-188">If you still do not see the new item, verify the current value of the timer job.</span></span>  
  
## <a name="more-information"></a><span data-ttu-id="c2ad3-189">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c2ad3-189">More Information</span></span>  
  
-   <span data-ttu-id="c2ad3-190">[Настройка службы Secure Store в SharePoint 2013](https://technet.microsoft.com/library/ee806866.aspx).</span><span class="sxs-lookup"><span data-stu-id="c2ad3-190">[Configure the Secure Store Service in SharePoint 2013](https://technet.microsoft.com/library/ee806866.aspx).</span></span>  
  
-   <span data-ttu-id="c2ad3-191">См. раздел "обновление данных по расписанию" статьи [Обновление данных PowerPivot с SharePoint 2013 и SQL Server 2012 SP1 (Analysis Services)](https://msdn.microsoft.com/library/jj879294.aspx#bkmk_windows_auth_interactive_data_refresh).</span><span class="sxs-lookup"><span data-stu-id="c2ad3-191">See the "Scheduled Data Refresh" section of [PowerPivot Data Refresh with SharePoint 2013 and SQL Server 2012 SP1 (Analysis Services)](https://msdn.microsoft.com/library/jj879294.aspx#bkmk_windows_auth_interactive_data_refresh).</span></span>  
  
  
