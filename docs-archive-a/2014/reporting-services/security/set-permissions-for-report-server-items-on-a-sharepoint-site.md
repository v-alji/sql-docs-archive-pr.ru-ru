---
title: Задание разрешений для элементов сервера отчетов на сайте SharePoint (Reporting Services в режиме интеграции с SharePoint) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- permissions [Reporting Services], SharePoint integrated mode
- SharePoint integration [Reporting Services], permissions
ms.assetid: 2467c657-a3bf-4ec3-a88c-8877df19823d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f38497843ca99342f13952153d7fed957564e006
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730078"
---
# <a name="set-permissions-for-report-server-items-on-a-sharepoint-site-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="1a4b3-102">устанавливать разрешения на элементы сервера отчетов с помощью сайта SharePoint (службы Reporting Services в режиме интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="1a4b3-102">Set Permissions for Report Server Items on a SharePoint Site (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="1a4b3-103">Если параметры безопасности по умолчанию не обеспечивают нужного уровня доступа, можно создать разрешения, чтобы предоставить доступ к определенным элементам или операциям сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-103">If default security settings do not provide the level of access that you require, you can create new permission levels to provide access to specific report server items or operations.</span></span> <span data-ttu-id="1a4b3-104">Пользовательские параметры безопасности могут оказаться полезными, если требуется ограничить доступ к конкретному отчету.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-104">Custom security settings can be useful if you want to restrict access to a particular report.</span></span>  
  
 <span data-ttu-id="1a4b3-105">Для создания уровней и групп разрешений необходимо быть владельцем сайта.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-105">You must be a site owner to create permission levels and groups.</span></span> <span data-ttu-id="1a4b3-106">Уровни разрешений используются глобально на всем сайте.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-106">Permission levels are used globally throughout a site.</span></span> <span data-ttu-id="1a4b3-107">При создании нового уровня разрешений он становится доступным для других владельцев сайта.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-107">If you create a new permission level, it will be available to other site owners.</span></span>  
  
 <span data-ttu-id="1a4b3-108">Большая часть разрешений наследуется от родительского сайта.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-108">Most permissions are inherited from a parent site.</span></span> <span data-ttu-id="1a4b3-109">Если назначить разрешения на определенную библиотеку или элемент, наследование разрешений нарушается, и управление разрешениями на эту ветвь иерархии сайта требует дополнительных затрат.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-109">If you assign permissions on a specific library or item, you break permission inheritance and incur additional overhead in how manage permissions for that branch of your site hierarchy.</span></span>  
  
 <span data-ttu-id="1a4b3-110">Можно назначать разрешения на файлы определения отчета (RDL), модели (SMDL) и общего источника данных (RSDS).</span><span class="sxs-lookup"><span data-stu-id="1a4b3-110">You can set permissions on report definition (.rdl), model (.smdl), and shared data source (.rsds) files.</span></span> <span data-ttu-id="1a4b3-111">Нельзя объединять наследуемые и управляемые разрешения на одном элементе.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-111">You cannot combine inherited and managed permissions on the same item.</span></span> <span data-ttu-id="1a4b3-112">При прямом управлении разрешениями наследуемые разрешения не влияют на текущий элемент.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-112">If you choose to manage permissions directly, inherited permissions will have no effect on the current item.</span></span> <span data-ttu-id="1a4b3-113">При необходимости впоследствии восстановить наследование разрешений можно выбрать пункт **Наследовать разрешения** в меню **Действия** .</span><span class="sxs-lookup"><span data-stu-id="1a4b3-113">If you want to resume permission inheritance later, you can select **Inherit Permissions** on the **Actions** menu.</span></span>  
  
 <span data-ttu-id="1a4b3-114">Для задания разрешений на сущности и перспективы модели необходимо иметь уровень разрешений «Полный доступ» на эту модель.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-114">To set permissions on entities and perspectives in a model, you must have Full Control level of permission for the model.</span></span> <span data-ttu-id="1a4b3-115">Уровень «Полный доступ» включает разрешение «Управление разрешениями» — разрешение на уровне сайта, которое предоставляется владельцам сайта и другим группам SharePoint с уровнем разрешений «Полный доступ».</span><span class="sxs-lookup"><span data-stu-id="1a4b3-115">Full Control includes "Manage Permissions", which is a site level permission that is granted to site owners and other SharePoint groups who have Full Control level of permission.</span></span> <span data-ttu-id="1a4b3-116">Если необходимо предоставить определенным пользователям возможность устанавливать параметры безопасности для элементов модели, необходимо нарушить наследование разрешений и предоставить этим пользователям расширенные разрешения (например, «Полный доступ») на файл модели.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-116">If you want to offer specific users the ability to set model item security, you must break permission inheritance and grant elevated permissions (such as Full Control) to the user or group on the model file.</span></span> <span data-ttu-id="1a4b3-117">При предоставлении разрешений «Полный доступ» на элемент, такой как файл библиотеки, область действия этих разрешений ограничивается только этим элементом и не распространяется на родителя или другие элементы этой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-117">When you grant Full Control on an item such as a file in the library, the permissions are scoped to that item and do not extend to the parent or to other items within the same library.</span></span> <span data-ttu-id="1a4b3-118">После того как пользователь получит разрешение «Управление разрешениями» на данную модель, он сможет задавать параметры безопасности для элементов модели с помощью сайта SharePoint или конструктора моделей.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-118">After the user has Manage Permissions permission on the model, he or she can use set model item security via the SharePoint site or Model Designer.</span></span>  
  
### <a name="to-set-permissions-on-an-individual-report-model-or-data-source"></a><span data-ttu-id="1a4b3-119">Установка разрешений на отдельный отчет, модель или источник данных</span><span class="sxs-lookup"><span data-stu-id="1a4b3-119">To set permissions on an individual report, model, or data source</span></span>  
  
1.  <span data-ttu-id="1a4b3-120">Если библиотека еще не открыта, щелкните ее имя на панели «Быстрый запуск».</span><span class="sxs-lookup"><span data-stu-id="1a4b3-120">If the library is not already open, click its name on the Quick Launch.</span></span> <span data-ttu-id="1a4b3-121">Если имя библиотеки не отображается, щелкните **Просмотреть содержимое всего сайта**и выберите имя библиотеки.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-121">If the name of your library does not appear, click **View All Site Content**, and then click the name of your library.</span></span>  
  
2.  <span data-ttu-id="1a4b3-122">Укажите файл отчета, модели отчета и общего источника данных.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-122">Point to the report, report model, or shared data source file.</span></span>  
  
3.  <span data-ttu-id="1a4b3-123">Нажмите кнопку со стрелкой вниз и в меню выберите пункт **Управлять разрешениями**.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-123">Click the down arrow, and on the menu, click **Manage Permissions**.</span></span>  
  
4.  <span data-ttu-id="1a4b3-124">В меню **Действия** выберите пункт **Изменить разрешения**и нажмите кнопку **ОК** , чтобы подтвердить действие.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-124">On the **Actions** menu, click **Edit Permissions**, and then click **OK** to confirm the action.</span></span>  
  
5.  <span data-ttu-id="1a4b3-125">Чтобы назначить разрешения пользователю или группе, которые еще не имеют разрешения на использование файла, выберите **Создать**, а затем нажмите кнопку **Добавить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-125">To give permissions to a user or group that does not yet have permissions to use the file, click **New**, and then click **Add Users**.</span></span>  
  
6.  <span data-ttu-id="1a4b3-126">Для удаления или изменения разрешений для существующего пользователя или группы установите флажок рядом с именем пользователя или группы, щелкните **Действия**, а затем выберите пункт **Удаление разрешений пользователя** или **Изменение разрешений пользователя**.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-126">To remove or modify permissions for an existing user or group, click the check box next to the user or group, click **Actions**, and then click **Remove User Permissions** or **Edit User Permissions**.</span></span>  
  
### <a name="to-set-permissions-that-enable-model-item-security"></a><span data-ttu-id="1a4b3-127">Установка разрешений, позволяющих управлять безопасностью элементов модели</span><span class="sxs-lookup"><span data-stu-id="1a4b3-127">To set permissions that enable model item security</span></span>  
  
1.  <span data-ttu-id="1a4b3-128">Войдите на сайт SharePoint с учетной записью, обладающей разрешением «Управление разрешениями» на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-128">Log in to the SharePoint site using an account that has Manage Permissions permission on the site.</span></span>  
  
2.  <span data-ttu-id="1a4b3-129">Откройте библиотеку, которая содержит модель.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-129">Open the library that contains the model.</span></span>  
  
3.  <span data-ttu-id="1a4b3-130">Укажите модель.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-130">Point to the model.</span></span>  
  
4.  <span data-ttu-id="1a4b3-131">Щелкните стрелку вниз рядом с моделью и выберите пункт **Управление разрешениями**.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-131">Click the down arrow next to the model, and click **Manage Permissions**.</span></span>  
  
5.  <span data-ttu-id="1a4b3-132">Нажмите кнопку **Действия**.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-132">Click **Actions**.</span></span>  
  
6.  <span data-ttu-id="1a4b3-133">Нажмите кнопку **Изменить разрешения**.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-133">Click **Edit Permissions**.</span></span> <span data-ttu-id="1a4b3-134">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-134">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="1a4b3-135">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-135">Click **New**.</span></span>  
  
8.  <span data-ttu-id="1a4b3-136">Щелкните **Добавить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-136">Click **Add Users**.</span></span>  
  
9. <span data-ttu-id="1a4b3-137">В поле «Пользователи и группы» введите имя учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-137">In Users/Groups, enter the user account.</span></span>  
  
10. <span data-ttu-id="1a4b3-138">Выберите **Предоставить следующие разрешения**.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-138">Select **Give users permission directly**.</span></span>  
  
11. <span data-ttu-id="1a4b3-139">Выберите разрешение **Полный доступ**.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-139">Click **Full Control**.</span></span>  
  
12. <span data-ttu-id="1a4b3-140">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-140">Click **OK**.</span></span> <span data-ttu-id="1a4b3-141">После того как пользователь получил возможность изменять разрешения на конкретную модель, он может открыть модель для изменения ее внутренних разрешений.</span><span class="sxs-lookup"><span data-stu-id="1a4b3-141">Once a user has the ability to manage permissions for a specific model, he or she can open the model to edit permissions within the model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a4b3-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="1a4b3-142">See Also</span></span>  
 <span data-ttu-id="1a4b3-143">[Использование встроенных средств безопасности служб Windows SharePoint Services при работе с элементами сервера отчетов](use-built-in-security-in-windows-sharepoint-services-for-report-server-items.md) </span><span class="sxs-lookup"><span data-stu-id="1a4b3-143">[Use Built-in Security in Windows SharePoint Services for Report Server Items](use-built-in-security-in-windows-sharepoint-services-for-report-server-items.md) </span></span>  
 <span data-ttu-id="1a4b3-144">[Задание разрешений для работы сервера отчетов в веб-приложении SharePoint](set-permissions-for-report-server-operations-in-a-sharepoint-web-application.md) </span><span class="sxs-lookup"><span data-stu-id="1a4b3-144">[Set Permissions for Report Server Operations in a SharePoint Web Application](set-permissions-for-report-server-operations-in-a-sharepoint-web-application.md) </span></span>  
 <span data-ttu-id="1a4b3-145">[Сравнение ролей и задач служб Reporting Services с группами и разрешениями SharePoint](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="1a4b3-145">[Compare Roles and Tasks in Reporting Services to SharePoint Groups and Permissions](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md) </span></span>  
 <span data-ttu-id="1a4b3-146">[Справочная таблица по разрешениям на сайты SharePoint и списки для элементов сервера отчетов](sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span><span class="sxs-lookup"><span data-stu-id="1a4b3-146">[SharePoint Site and List Permission Reference for Report Server Items](sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span></span>  
 [<span data-ttu-id="1a4b3-147">Предоставление разрешений для элементов сервера отчетов на сайте SharePoint</span><span class="sxs-lookup"><span data-stu-id="1a4b3-147">Granting Permissions on Report Server Items on a SharePoint Site</span></span>](granting-permissions-on-report-server-items-on-a-sharepoint-site.md)  
  
  
