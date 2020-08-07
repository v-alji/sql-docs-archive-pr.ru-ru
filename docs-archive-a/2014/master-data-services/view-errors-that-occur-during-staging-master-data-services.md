---
title: Просмотр ошибок, происходящих во время промежуточного процесса (Master Data Services) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- staging process [Master Data Services], viewing errors
ms.assetid: 6d2bff84-624b-47fc-a4a5-d9ea01d13412
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3b39d039b29090f3021c764126ebb782ce25cbfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731793"
---
# <a name="view-errors-that-occur-during-the-staging-process-master-data-services"></a><span data-ttu-id="53476-102">Возможность просмотра ошибки, которая возникает в ходе промежуточного процесса (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="53476-102">View Errors that Occur During the Staging Process (Master Data Services)</span></span>
  <span data-ttu-id="53476-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]можно просмотреть ошибки, которые возникают в ходе промежуточного процесса.</span><span class="sxs-lookup"><span data-stu-id="53476-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can view errors that occur during the staging process.</span></span> <span data-ttu-id="53476-104">В базе данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] существуют два представления, в которых показываются ошибки:</span><span class="sxs-lookup"><span data-stu-id="53476-104">In the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database, there are two views that show errors:</span></span>  
  
-   <span data-ttu-id="53476-105">Stg.viw_name_MemberErrorDetails для обновлений конечных или объединенных элементов.</span><span class="sxs-lookup"><span data-stu-id="53476-105">stg.viw_name_MemberErrorDetails for leaf or consolidated member updates.</span></span>  
  
-   <span data-ttu-id="53476-106">Stg.viw_name_RelationshipErrorDetails для обновления связей иерархии.</span><span class="sxs-lookup"><span data-stu-id="53476-106">stg.viw_name_RelationshipErrorDetails for hierarchy relationship updates.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="53476-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="53476-107">Prerequisites</span></span>  
 <span data-ttu-id="53476-108">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="53476-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="53476-109">В базе данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] необходимо иметь разрешения SELECT для представления stg.viw_name_MemberErrorDetails или stg.viw_name_RelationshipErrorDetails.</span><span class="sxs-lookup"><span data-stu-id="53476-109">In the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database, you must have SELECT permissions to either the stg.viw_name_MemberErrorDetails or stg.viw_name_RelationshipErrorDetails view.</span></span>  
  
-   <span data-ttu-id="53476-110">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="53476-110">You must be a model administrator.</span></span> <span data-ttu-id="53476-111">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="53476-111">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-view-staging-errors"></a><span data-ttu-id="53476-112">Для просмотра промежуточных ошибок</span><span class="sxs-lookup"><span data-stu-id="53476-112">To view staging errors</span></span>  
  
1.  <span data-ttu-id="53476-113">Откройте среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] и установите соединение с экземпляром компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] для базы данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="53476-113">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="53476-114">Откройте новый запрос.</span><span class="sxs-lookup"><span data-stu-id="53476-114">Open a new query.</span></span>  
  
3.  <span data-ttu-id="53476-115">Введите следующий текст, заменяя имя именем своей промежуточной таблицы, например viw_Product_MemberErrorDetails.</span><span class="sxs-lookup"><span data-stu-id="53476-115">Type the following text, replacing name with the name of your staging table, for example, viw_Product_MemberErrorDetails.</span></span>  
  
     `SELECT * FROM stg.viw_name_MemberErrorDetails`  
  
4.  <span data-ttu-id="53476-116">Выполните запрос.</span><span class="sxs-lookup"><span data-stu-id="53476-116">Excecute the query.</span></span> <span data-ttu-id="53476-117">Сведения об ошибках отображаются в поле **ErrorDescription** .</span><span class="sxs-lookup"><span data-stu-id="53476-117">Error details are displayed in the **ErrorDescription** field.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="53476-118">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="53476-118">Next Steps</span></span>  
 <span data-ttu-id="53476-119">Дополнительные сведения о сообщениях об ошибках см. в разделе [Ошибки промежуточного процесса (службы Master Data Services)](../../2014/master-data-services/staging-process-errors-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="53476-119">For more details on error messages, see [Staging Process Errors &#40;Master Data Services&#41;](../../2014/master-data-services/staging-process-errors-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53476-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="53476-120">See Also</span></span>  
 <span data-ttu-id="53476-121">[Master Data Services &#40;импорта данных&#41;](overview-importing-data-from-tables-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="53476-121">[Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span></span>  
 [<span data-ttu-id="53476-122">Устранение неполадок в промежуточном процессе (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="53476-122">Troubleshooting the Staging Process (Master Data Services)</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-the-staging-process-master-data-services.aspx)  
  
  
