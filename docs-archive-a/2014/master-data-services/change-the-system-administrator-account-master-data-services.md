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
# <a name="change-the-system-administrator-account-master-data-services"></a>Изменение учетной записи системного администратора (службы Master Data Services)
  Можно изменить учетную запись пользователя, назначенную [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] системным администратором.  
  
> [!WARNING]  
>  После завершения этой процедуры учетная запись прежнего системного администратора будет удалена.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения этой процедуры:  
  
-   Необходимо добавить имя пользователя нового системного администратора к списку пользователей [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]. Дополнительные сведения см. [в разделе Добавление пользователя &#40;Master Data Services&#41;](add-a-user-master-data-services.md).  
  
-   У пользователя должны быть разрешения на просмотр mdm.tblUser и на выполнение хранимой процедуры mds.udpSecurityMemberProcessRebuildModel в базе данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]. Дополнительные сведения см. в разделе [Защита объектов базы данных (службы Master Data Services)](../../2014/master-data-services/database-object-security-master-data-services.md).  
  
### <a name="to-change-the-administrator-account"></a>Изменение учетной записи администратора  
  
1.  Откройте среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] и установите соединение с экземпляром компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] для базы данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .  
  
2.  В MDM. tblUser найдите пользователя, который будет новым администратором, и скопируйте значение в `SID` столбец.  
  
3.  Создайте новый запрос.  
  
4.  Введите следующий текст, заменив *domain \ user_name* именем пользователя и *идентификатором безопасности* нового администратора на значение, скопированное на шаге 2.  
  
    ```  
    EXEC [mdm].[udpSecuritySetAdministrator] @UserName='DOMAIN\user_name', @SID = 'SID', @PromoteNonAdmin = 1  
    ```  
  
5.  Выполните запрос.  
  
## <a name="see-also"></a>См. также:  
 [Администраторы (службы Master Data Services)](../../2014/master-data-services/administrators-master-data-services.md)  
  
  
