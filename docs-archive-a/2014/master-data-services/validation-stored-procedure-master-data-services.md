---
title: Хранимая процедура проверки (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 332d3c86-4440-4f12-a6cb-ffbfbccde52c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8fa6b01d950c87768d10b0252c1ccbab2b932fe1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664284"
---
# <a name="validation-stored-procedure-master-data-services"></a><span data-ttu-id="252c0-102">Проверка хранимых процедур (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="252c0-102">Validation Stored Procedure (Master Data Services)</span></span>
  <span data-ttu-id="252c0-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]проверьте версию на применение бизнес-правил ко всем элементам версии модели.</span><span class="sxs-lookup"><span data-stu-id="252c0-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], validate a version to apply business rules to all members in the model version.</span></span>  
  
 <span data-ttu-id="252c0-104">В этом разделе объясняется, как использовать хранимую процедуру **mdm.udpValidateModel** для проверки данных.</span><span class="sxs-lookup"><span data-stu-id="252c0-104">This topic explains how to use the **mdm.udpValidateModel** stored procedure to validate data.</span></span> <span data-ttu-id="252c0-105">Администратор веб-приложения [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] может проводить проверку в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="252c0-105">If you are an administrator in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application, you can do validation in the UI instead.</span></span> <span data-ttu-id="252c0-106">Дополнительные сведения см. в разделе [Подтверждение исправления проблемы, обнаруженной при проверке на соответствие бизнес-правилам (службы Master Data Services)](validate-a-version-against-business-rules-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="252c0-106">For more information, see [Validate a Version against Business Rules &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="252c0-107">При запуске проверки до завершения промежуточного процесса элементы, для которых этот процесс не был завершен, не будут проверены.</span><span class="sxs-lookup"><span data-stu-id="252c0-107">If you invoke validation before the staging process is complete, members that have not finished staging will not be validated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="252c0-108">Пример</span><span class="sxs-lookup"><span data-stu-id="252c0-108">Example</span></span>  
  
```  
DECLARE @ModelName nVarchar(50) = 'Customer'   
DECLARE @Model_id int   
DECLARE @UserName nvarchar(50)= 'DOMAIN\user_name'   
DECLARE @User_ID int   
DECLARE @Version_ID int   
  
SET @User_ID = (SELECT ID    
                 FROM mdm.tblUser u   
                 WHERE u.UserName = @UserName)   
SET @Model_ID = (SELECT Top 1 Model_ID   
                 FROM mdm.viw_SYSTEM_SCHEMA_VERSION   
                 WHERE Model_Name = @ModelName)   
SET @Version_ID = (SELECT MAX(ID)   
                 FROM mdm.viw_SYSTEM_SCHEMA_VERSION   
                 WHERE Model_ID = @Model_ID)  
  
EXECUTE mdm.udpValidateModel @User_ID, @Model_ID, @Version_ID, 1  
  
```  
  
## <a name="parameters"></a><span data-ttu-id="252c0-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="252c0-109">Parameters</span></span>  
 <span data-ttu-id="252c0-110">Параметры данной процедуры имеют следующие значения:</span><span class="sxs-lookup"><span data-stu-id="252c0-110">The parameters of this procedure are as follows:</span></span>  
  
|<span data-ttu-id="252c0-111">Параметр</span><span class="sxs-lookup"><span data-stu-id="252c0-111">Parameter</span></span>|<span data-ttu-id="252c0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="252c0-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="252c0-113">UserID</span><span class="sxs-lookup"><span data-stu-id="252c0-113">UserID</span></span>|<span data-ttu-id="252c0-114">Идентификатор пользователя.</span><span class="sxs-lookup"><span data-stu-id="252c0-114">The user ID.</span></span>|  
|<span data-ttu-id="252c0-115">Model_ID</span><span class="sxs-lookup"><span data-stu-id="252c0-115">Model_ID</span></span>|<span data-ttu-id="252c0-116">Идентификатор модели.</span><span class="sxs-lookup"><span data-stu-id="252c0-116">The model ID.</span></span>|  
|<span data-ttu-id="252c0-117">Version_ID</span><span class="sxs-lookup"><span data-stu-id="252c0-117">Version_ID</span></span>|<span data-ttu-id="252c0-118">Идентификатор версии.</span><span class="sxs-lookup"><span data-stu-id="252c0-118">The version ID.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="252c0-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="252c0-119">See Also</span></span>  
 <span data-ttu-id="252c0-120">[Master Data Services &#40;импорта данных&#41;](overview-importing-data-from-tables-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="252c0-120">[Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span></span>  
 [<span data-ttu-id="252c0-121">Подтверждение исправления проблемы, обнаруженной при проверке на соответствие бизнес-правилам (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="252c0-121">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](validate-a-version-against-business-rules-master-data-services.md)  
  
  
