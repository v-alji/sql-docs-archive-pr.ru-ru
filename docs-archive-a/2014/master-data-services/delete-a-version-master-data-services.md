---
title: Удаление версии (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- versions [Master Data Services], deleting
- deleting versions [Master Data Services]
ms.assetid: 2a4eeffe-8379-4744-ad44-c27d8c8ac9a8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f83a3bc396b2a13ac7ac03ef653b16a0d556189a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668406"
---
# <a name="delete-a-version-master-data-services"></a><span data-ttu-id="0a96d-102">Удаление версии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0a96d-102">Delete a Version (Master Data Services)</span></span>
  <span data-ttu-id="0a96d-103">В службах [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]версия удаляется тогда, когда связанные с ней основные данные больше не нужны.</span><span class="sxs-lookup"><span data-stu-id="0a96d-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete a version when you are sure you no longer need the master data associated with the version.</span></span> <span data-ttu-id="0a96d-104">После удаления версии связанные с ней основные данные больше нельзя получить.</span><span class="sxs-lookup"><span data-stu-id="0a96d-104">After you delete a version, you cannot retrieve the associated master data.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="0a96d-105">После удаления единственной версии модели она станет непригодной к использованию.</span><span class="sxs-lookup"><span data-stu-id="0a96d-105">If a model has only one version and you delete it, the model becomes unusable.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0a96d-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="0a96d-106">Prerequisites</span></span>  
 <span data-ttu-id="0a96d-107">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="0a96d-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="0a96d-108">пользователь должен иметь разрешения на просмотр представления mdm.viw_SYSTEM_SCHEMA_VERSION и на выполнение хранимой процедуры mds.udpVersionDelete в базе данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a96d-108">You must have permission to view the mdm.viw_SYSTEM_SCHEMA_VERSION view and to execute the mds.udpVersionDelete stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="0a96d-109">Дополнительные сведения см. в разделе [Защита объектов базы данных (службы Master Data Services)](database-object-security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0a96d-109">For more information, see [Database Object Security &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span></span>  
  
### <a name="to-delete-a-version"></a><span data-ttu-id="0a96d-110">Удаление версии</span><span class="sxs-lookup"><span data-stu-id="0a96d-110">To delete a version</span></span>  
  
1.  <span data-ttu-id="0a96d-111">Откройте среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] и установите соединение с экземпляром компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] для базы данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a96d-111">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="0a96d-112">Откройте представление mdm.viw_SYSTEM_SCHEMA_VERSION.</span><span class="sxs-lookup"><span data-stu-id="0a96d-112">Open the mdm.viw_SYSTEM_SCHEMA_VERSION view.</span></span>  
  
3.  <span data-ttu-id="0a96d-113">Найдите удаляемую версию модели и скопируйте значение в поле **ID** .</span><span class="sxs-lookup"><span data-stu-id="0a96d-113">Find the version of the model you want to delete and copy the value in the **ID** field.</span></span>  
  
4.  <span data-ttu-id="0a96d-114">Создайте новый запрос.</span><span class="sxs-lookup"><span data-stu-id="0a96d-114">Create a new query.</span></span>  
  
5.  <span data-ttu-id="0a96d-115">Введите следующий текст, заменив *version_ID* значением, скопированным в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="0a96d-115">Type the following text, replacing *version_ID* with the value you copied in step 2.</span></span>  
  
    ```  
    EXEC [mdm].[udpVersionDelete] @Version_ID='version_ID'  
    ```  
  
6.  <span data-ttu-id="0a96d-116">Выполните запрос.</span><span class="sxs-lookup"><span data-stu-id="0a96d-116">Run the query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0a96d-117">Возможно, придется подождать несколько минут, чтобы изменение отобразилось в веб-приложении.</span><span class="sxs-lookup"><span data-stu-id="0a96d-117">You may have to wait a few minutes before the Web application reflects the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a96d-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="0a96d-118">See Also</span></span>  
 <span data-ttu-id="0a96d-119">[Версии &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0a96d-119">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 [<span data-ttu-id="0a96d-120">Копирование версии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0a96d-120">Copy a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/copy-a-version-master-data-services.md)  
  
  
