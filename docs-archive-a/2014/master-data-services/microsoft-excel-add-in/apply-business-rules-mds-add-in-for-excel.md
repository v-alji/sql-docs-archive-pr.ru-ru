---
title: Применение бизнес-правил (надстройка MDS для Excel) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: cd106345-f561-4966-88d3-a69139b2bd78
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: aad5ce6bcebb635fa4659c32654d67406d4ba0dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730805"
---
# <a name="apply-business-rules-mds-add-in-for-excel"></a><span data-ttu-id="50673-102">Применение бизнес-правил (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="50673-102">Apply Business Rules (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="50673-103">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] можно применить бизнес-правила, когда необходимо проверить данные и подтвердить их правильность.</span><span class="sxs-lookup"><span data-stu-id="50673-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] apply business rules when you want to validate data and confirm that it is valid.</span></span> <span data-ttu-id="50673-104">Затем можно исправить выявленные проблемы и повторно опубликовать данные.</span><span class="sxs-lookup"><span data-stu-id="50673-104">You can correct validations and re-publish the data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50673-105">Проверка данных выполняется автоматически при их публикации.</span><span class="sxs-lookup"><span data-stu-id="50673-105">Data validation occurs automatically when you publish data.</span></span> <span data-ttu-id="50673-106">Дополнительные сведения см. в разделе [Проверка хранимых процедур (службы Master Data Services)](../validation-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="50673-106">For more information, see [Validation Stored Procedure &#40;Master Data Services&#41;](../validation-stored-procedure-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="50673-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="50673-107">Prerequisites</span></span>  
 <span data-ttu-id="50673-108">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="50673-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="50673-109">Необходимо иметь доступ к функциональной области **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="50673-109">You must have access to the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="50673-110">Необходимо иметь активный лист, содержащий данные, управляемые MDS.</span><span class="sxs-lookup"><span data-stu-id="50673-110">You must have an active worksheet that contains MDS-managed data.</span></span>  
  
### <a name="to-apply-business-rules"></a><span data-ttu-id="50673-111">Применение бизнес-правил</span><span class="sxs-lookup"><span data-stu-id="50673-111">To apply business rules</span></span>  
  
1.  <span data-ttu-id="50673-112">В группе **Публикация и проверка** нажмите **Применить правила**.</span><span class="sxs-lookup"><span data-stu-id="50673-112">In the **Publish and Validate** group, click **Apply Rules**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="50673-113">Число элементов (строк), проверяемых за один раз, зависит от значения параметра в [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50673-113">The number of members (rows) that are validated at one time depends on a setting in [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span> <span data-ttu-id="50673-114">Дополнительные сведения см. в статье [Business Rule Settings](../system-settings-master-data-services.md#BusinessRules).</span><span class="sxs-lookup"><span data-stu-id="50673-114">For more information, see [Business Rule Settings](../system-settings-master-data-services.md#BusinessRules).</span></span>  
  
2.  <span data-ttu-id="50673-115">Данные проверяются по бизнес-правилам, после чего отображаются два столбца состояния.</span><span class="sxs-lookup"><span data-stu-id="50673-115">The data is validated against business rules and two status columns are displayed.</span></span> <span data-ttu-id="50673-116">Если эти столбцы не отобразились автоматически, в группе **Публикация и проверка** нажмите кнопку **Показать состояние** , чтобы увидеть их.</span><span class="sxs-lookup"><span data-stu-id="50673-116">If these columns are not displayed automatically, in the **Publish and Validate** group, click **Show Status** to view them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50673-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="50673-117">See Also</span></span>  
 [<span data-ttu-id="50673-118">Публикация &#40;данных надстройка MDS для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="50673-118">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
