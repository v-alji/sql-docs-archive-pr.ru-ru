---
title: Предоставление разрешений для пользователей и оповещение администраторов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 166808e1-ada7-48d2-bda8-8f7c017fb3aa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5bf7f030871287379ce9fb32a1789b95cff0fc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668100"
---
# <a name="grant-permissions-to-users-and-alerting-administrators"></a><span data-ttu-id="5ebf4-102">Предоставление разрешений для пользователей и оповещение администраторов</span><span class="sxs-lookup"><span data-stu-id="5ebf4-102">Grant Permissions to Users and Alerting Administrators</span></span>
  <span data-ttu-id="5ebf4-103">Чтобы создавать, изменять, удалять и просматривать предупреждения данных, пользователи и администраторы предупреждений должны иметь разрешения SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5ebf4-103">Before users and alerting administrators can create, edit, delete, and view data alerts they must be granted SharePoint permissions.</span></span> <span data-ttu-id="5ebf4-104">Специальных разрешений для функции предупреждений об изменении данных в службах [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] нет, для этого используются встроенные разрешения SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5ebf4-104">There are no special permissions to use with the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] data alerting feature, you use the built-in SharePoint permissions.</span></span>  
  
 <span data-ttu-id="5ebf4-105">**Информационные работники**. Разрешения должны включать разрешения SharePoint на создание предупреждений и просмотр элементов.</span><span class="sxs-lookup"><span data-stu-id="5ebf4-105">**Information workers**-Permissions must include the Create Alert and View Items SharePoint permissions.</span></span> <span data-ttu-id="5ebf4-106">Встроенные уровне разрешений SharePoint — «Создание», «Участие», «Чтение» и «Только просмотр» — включают разрешения SharePoint на создание предупреждений и просмотр элементов.</span><span class="sxs-lookup"><span data-stu-id="5ebf4-106">The built-in SharePoint permission levels named Design, Contribute, Read, and View Only include the Create Alert and View Items SharePoint permissions.</span></span> <span data-ttu-id="5ebf4-107">Также можно создать собственный уровень разрешений, включающий разрешения, необходимые для поддержки пользователей, создающих, изменяющих, запускающих и просматривающих предупреждения данных.</span><span class="sxs-lookup"><span data-stu-id="5ebf4-107">You can also create a custom permission level with the permissions required to support users that create, edit, run, and view data alerts.</span></span>  
  
 <span data-ttu-id="5ebf4-108">**Администраторы предупреждений**. разрешения должны включать разрешение Управление предупреждением SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5ebf4-108">**Alerting administrators**-Permissions must include the Manage Alert SharePoint permission.</span></span> <span data-ttu-id="5ebf4-109">По умолчанию только уровень разрешения «Полный доступ» включает такое разрешение для сайтов, созданных с использованием шаблона веб-сайта группы.</span><span class="sxs-lookup"><span data-stu-id="5ebf4-109">By default only the Full Control permission level includes this permission for sites created with the Team Site site template.</span></span> <span data-ttu-id="5ebf4-110">Если используются другие шаблоны сайтов, появляются разные списки групп SharePoint по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ebf4-110">If you use other site templates, you will see different lists of default SharePoint groups.</span></span> <span data-ttu-id="5ebf4-111">Можно добавить разрешение на управление предупреждениями к одному из встроенных уровней разрешений или создать собственный уровень разрешений, включающий разрешения, позволяющие администраторам предупреждений просматривать и удалять предупреждения данных.</span><span class="sxs-lookup"><span data-stu-id="5ebf4-111">You can add the Manage Alert permission to one of the built-in permission levels or create a custom permission level with the permission required to support alerting administrators that view and delete data alerts.</span></span>  
  
 <span data-ttu-id="5ebf4-112">Дополнительные сведения о разрешениях SharePoint см. в разделе [Пользовательские разрешения и уровни разрешений (SharePoint Server 2010)](https://technet.microsoft.com/library/cc721640.aspx).</span><span class="sxs-lookup"><span data-stu-id="5ebf4-112">To learn more about SharePoint permissions, see [User permissions and permission levels (SharePoint Server 2010)](https://technet.microsoft.com/library/cc721640.aspx).</span></span>  
  
### <a name="to-grant-permissions"></a><span data-ttu-id="5ebf4-113">Предоставление разрешений</span><span class="sxs-lookup"><span data-stu-id="5ebf4-113">To grant permissions</span></span>  
  
1.  <span data-ttu-id="5ebf4-114">Перейдите на сайт SharePoint, для которого необходимо предоставить разрешения.</span><span class="sxs-lookup"><span data-stu-id="5ebf4-114">Go to the SharePoint site to which you want to grant permissions.</span></span>  
  
2.  <span data-ttu-id="5ebf4-115">На панели инструментов нажмите кнопку **Действия сайта** , а затем **Разрешения сайта**.</span><span class="sxs-lookup"><span data-stu-id="5ebf4-115">On the toolbar, click **Site Actions** and then click **Site Permissions**.</span></span>  
  
     <span data-ttu-id="5ebf4-116">Если этой возможности нет на экране, значит, отсутствует разрешение на предоставление разрешений другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="5ebf4-116">If you do not see this option, you do not sufficient permission to grant permissions to others.</span></span>  
  
3.  <span data-ttu-id="5ebf4-117">Нажмите кнопку **Предоставить разрешения**.</span><span class="sxs-lookup"><span data-stu-id="5ebf4-117">Click **Grant Permissions**.</span></span>  
  
4.  <span data-ttu-id="5ebf4-118">В поле **Пользователи и группы**введите имена пользователей, имена групп или адреса электронной почты, которым нужно предоставить разрешения.</span><span class="sxs-lookup"><span data-stu-id="5ebf4-118">In **Users/Groups**, type the user names, group names, or e-mail addresses you want grant permission to.</span></span>  
  
5.  <span data-ttu-id="5ebf4-119">Выберите действие **Добавить пользователей в группу SharePoint** или **Предоставить разрешение пользователям сразу** .</span><span class="sxs-lookup"><span data-stu-id="5ebf4-119">Select the **Add users to a SharePoint group** or **Grant users permission directly** option.</span></span> <span data-ttu-id="5ebf4-120">В зависимости от того, было ли выбрано действие **Добавить пользователей в группу SharePoint** или **Предоставить разрешение пользователям немедленно** , выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="5ebf4-120">Depending on whether you selected **Add users to a SharePoint group** or **Grant users permissions directly** do one of the following:</span></span>  
  
    -   <span data-ttu-id="5ebf4-121">Если выбрано действие **Добавить пользователей в группу SharePoint**, выберите в раскрывающемся списке уровень разрешений.</span><span class="sxs-lookup"><span data-stu-id="5ebf4-121">If you selected **Add users to a SharePoint group**, select a permission level in the drop-down list.</span></span>  
  
    -   <span data-ttu-id="5ebf4-122">Если выбрано действие **Предоставить разрешение пользователям сразу**, выберите уровень разрешений.</span><span class="sxs-lookup"><span data-stu-id="5ebf4-122">If you selected **Grant users permissions directly**, select a permission level.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5ebf4-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="5ebf4-123">See Also</span></span>  
 <span data-ttu-id="5ebf4-124">[Установка разрешений для элементов сервера отчетов на сайте SharePoint &#40;Reporting Services в режиме интеграции с SharePoint&#41;](security/set-permissions-for-report-server-items-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="5ebf4-124">[Set Permissions for Report Server Items on a SharePoint Site &#40;Reporting Services in SharePoint Integrated Mode&#41;](security/set-permissions-for-report-server-items-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="5ebf4-125">Предупреждения об изменении данных в службах Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5ebf4-125">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)  
  
  
