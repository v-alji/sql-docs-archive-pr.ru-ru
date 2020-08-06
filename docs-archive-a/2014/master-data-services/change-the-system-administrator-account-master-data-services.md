---
title: Изменение учетной записи системного администратора (Master Data Services) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- administrators [Master Data Services], changing
ms.assetid: cf30312e-4338-49a7-90f0-6e4f7b431ff8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1d13cdc19c70c9e16c92dfd290393739d7e4f5e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734222"
---
# <a name="change-the-system-administrator-account-master-data-services"></a><span data-ttu-id="e2948-102">Изменение учетной записи системного администратора (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e2948-102">Change the System Administrator Account (Master Data Services)</span></span>
  <span data-ttu-id="e2948-103">Можно изменить учетную запись пользователя, назначенную [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] системным администратором.</span><span class="sxs-lookup"><span data-stu-id="e2948-103">You can change the user account that is designated as the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system administrator.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="e2948-104">После завершения этой процедуры учетная запись прежнего системного администратора будет удалена.</span><span class="sxs-lookup"><span data-stu-id="e2948-104">When you complete this procedure, the former system administrator user account is deleted.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e2948-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="e2948-105">Prerequisites</span></span>  
 <span data-ttu-id="e2948-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="e2948-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="e2948-107">Необходимо добавить имя пользователя нового системного администратора к списку пользователей [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2948-107">You must add the new administrator's user name to the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Users list.</span></span> <span data-ttu-id="e2948-108">Дополнительные сведения см. [в разделе Добавление пользователя &#40;Master Data Services&#41;](add-a-user-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e2948-108">For more information, see [Add a User &#40;Master Data Services&#41;](add-a-user-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="e2948-109">У пользователя должны быть разрешения на просмотр mdm.tblUser и на выполнение хранимой процедуры mds.udpSecurityMemberProcessRebuildModel в базе данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2948-109">You must have permission to view mdm.tblUser and to execute the mdm.udpSecurityMemberProcessRebuildModel stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="e2948-110">Дополнительные сведения см. в разделе [Защита объектов базы данных (службы Master Data Services)](../../2014/master-data-services/database-object-security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e2948-110">For more information, see [Database Object Security &#40;Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md).</span></span>  
  
### <a name="to-change-the-administrator-account"></a><span data-ttu-id="e2948-111">Изменение учетной записи администратора</span><span class="sxs-lookup"><span data-stu-id="e2948-111">To change the administrator account</span></span>  
  
1.  <span data-ttu-id="e2948-112">Откройте среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] и установите соединение с экземпляром компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] для базы данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e2948-112">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="e2948-113">В MDM. tblUser найдите пользователя, который будет новым администратором, и скопируйте значение в `SID` столбец.</span><span class="sxs-lookup"><span data-stu-id="e2948-113">In mdm.tblUser, find the user that will be the new administrator and copy the value in the `SID` column.</span></span>  
  
3.  <span data-ttu-id="e2948-114">Создайте новый запрос.</span><span class="sxs-lookup"><span data-stu-id="e2948-114">Create a new query.</span></span>  
  
4.  <span data-ttu-id="e2948-115">Введите следующий текст, заменив *domain \ user_name* именем пользователя и *идентификатором безопасности* нового администратора на значение, скопированное на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="e2948-115">Type the following text, replacing *DOMAIN\user_name* with the new administrator's user name and *SID* with the value you copied in step 2.</span></span>  
  
    ```  
    EXEC [mdm].[udpSecuritySetAdministrator] @UserName='DOMAIN\user_name', @SID = 'SID', @PromoteNonAdmin = 1  
    ```  
  
5.  <span data-ttu-id="e2948-116">Выполните запрос.</span><span class="sxs-lookup"><span data-stu-id="e2948-116">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2948-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="e2948-117">See Also</span></span>  
 [<span data-ttu-id="e2948-118">Администраторы (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e2948-118">Administrators &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/administrators-master-data-services.md)  
  
  
