---
title: Срочное применение разрешений для элемента (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- members [Master Data Services], applying permissions immediately
- permissions [Master Data Services], applying member permissions immediately
ms.assetid: 5b16de66-5c39-49f5-992f-402a9eb319aa
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e960ad06213b7c5057a6249b72ce225a6abe35e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665393"
---
# <a name="immediately-apply-member-permissions-master-data-services"></a><span data-ttu-id="8f6e5-102">Срочное применение разрешения для элемента (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="8f6e5-102">Immediately Apply Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="8f6e5-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]можно не ждать, пока безопасность элемента задействуется через обычные промежутки времени, а применить разрешения для элемента немедленно.</span><span class="sxs-lookup"><span data-stu-id="8f6e5-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], instead of waiting for member security to be applied at regular intervals, you can apply member permissions immediately.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8f6e5-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="8f6e5-104">Prerequisites</span></span>  
 <span data-ttu-id="8f6e5-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="8f6e5-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="8f6e5-106">пользователь должен иметь разрешения на выполнение хранимой процедуры mdm.udpSecurityMemberProcessRebuildModel в базе данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8f6e5-106">You must have permission to execute the mdm.udpSecurityMemberProcessRebuildModel stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="8f6e5-107">Дополнительные сведения см. в разделе [Защита объектов базы данных (службы Master Data Services)](database-object-security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8f6e5-107">For more information, see [Database Object Security &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span></span>  
  
### <a name="to-immediately-apply-hierarchy-member-permissions"></a><span data-ttu-id="8f6e5-108">Немедленное применение разрешений для элементов иерархии</span><span class="sxs-lookup"><span data-stu-id="8f6e5-108">To immediately apply hierarchy member permissions</span></span>  
  
1.  <span data-ttu-id="8f6e5-109">Откройте среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] и установите соединение с экземпляром компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] для базы данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8f6e5-109">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="8f6e5-110">Создайте новый запрос.</span><span class="sxs-lookup"><span data-stu-id="8f6e5-110">Create a new query.</span></span>  
  
3.  <span data-ttu-id="8f6e5-111">Введите следующий текст, заменив *database* именем своей базы данных, а *Model_Name* — именем модели.</span><span class="sxs-lookup"><span data-stu-id="8f6e5-111">Type the following text, replacing *database* with the name of your database and *Model_Name* with the name of the model.</span></span>  
  
    ```  
    USE [database];  
    GO  
  
    DECLARE @Model_ID INT;  
    SELECT @Model_ID = ID FROM mdm.tblModel WHERE [Name] = N'Model_Name';  
    EXEC [mdm].[udpSecurityMemberProcessRebuildModel] @Model_ID=@Model_ID, @ProcessNow=1;  
    GO  
    ```  
  
4.  <span data-ttu-id="8f6e5-112">Выполните запрос.</span><span class="sxs-lookup"><span data-stu-id="8f6e5-112">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f6e5-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="8f6e5-113">See Also</span></span>  
 <span data-ttu-id="8f6e5-114">[Назначение разрешений элемента иерархии &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="8f6e5-114">[Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="8f6e5-115">Разрешения на элементы иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="8f6e5-115">Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
