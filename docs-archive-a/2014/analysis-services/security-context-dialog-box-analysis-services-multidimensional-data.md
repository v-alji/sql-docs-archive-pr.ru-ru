---
title: Диалоговое окно «контекст безопасности» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.browsecube.securitycontext.f1
ms.assetid: 238a4a4b-84bd-4b3d-9f02-f3adf57fa3af
author: minewiskan
ms.author: owend
ms.openlocfilehash: 58d5f71172ac16087ecc342342e70ade234226a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656619"
---
# <a name="security-context-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="67fa8-102">Диалоговое окно «Контекст безопасности» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="67fa8-102">Security Context Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="67fa8-103">Диалоговое окно **Контекст безопасности** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] позволяет изменить пользователя и роль, которые используются для исследования данных и метаданных объекта служб [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67fa8-103">Use the **Security Context** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to change the user and role used to examine data or metadata for a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="67fa8-104">Чтобы открыть диалоговое окно **Контекст безопасности** , нажмите кнопку **Контекст безопасности** на **панели инструментов** на вкладке **Вычисления** или **Браузер** конструктора кубов.</span><span class="sxs-lookup"><span data-stu-id="67fa8-104">You can display the **Security Context** dialog box by clicking **Security Context** in the **Toolbar** pane on either the **Calculations** tab or the **Browser** tab in Cube Designer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="67fa8-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="67fa8-105">Options</span></span>  
 <span data-ttu-id="67fa8-106">**Текущий пользователь**</span><span class="sxs-lookup"><span data-stu-id="67fa8-106">**Current user**</span></span>  
 <span data-ttu-id="67fa8-107">Выберите, если хотите использовать домен и имя текущего пользователя во время просмотра данных и метаданных объекта служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67fa8-107">Select to use the domain and user name of the current user while viewing the data and metadata of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="67fa8-108">**Другой пользователь**</span><span class="sxs-lookup"><span data-stu-id="67fa8-108">**Other user**</span></span>  
 <span data-ttu-id="67fa8-109">Введите домен и имя другого пользователя или группы, которые хотите использовать во время просмотра данных и метаданных объекта служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67fa8-109">Type the domain and user name of another user or group to use while viewing the data and metadata of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="67fa8-110">Чтобы указать домен и имя пользователя или группы, используйте следующий формат:</span><span class="sxs-lookup"><span data-stu-id="67fa8-110">The domain and name of the user or group uses the following format:</span></span>  
  
 <span data-ttu-id="67fa8-111">*\<Domain name>* **\\** *\<User account name>*</span><span class="sxs-lookup"><span data-stu-id="67fa8-111">*\<Domain name>* **\\** *\<User account name>*</span></span>  
  
 <span data-ttu-id="67fa8-112">**Роли**</span><span class="sxs-lookup"><span data-stu-id="67fa8-112">**Roles**</span></span>  
 <span data-ttu-id="67fa8-113">Выберите, если хотите использовать одну или несколько указанных ролей во время просмотра данных и метаданных объекта служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67fa8-113">Select to use one or more specified roles when viewing the data and metadata of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="67fa8-114">Несколько ролей можно выбрать, если они определены в базе данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67fa8-114">You can select the roles to use if multiple roles are defined in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67fa8-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="67fa8-115">See Also</span></span>  
 <span data-ttu-id="67fa8-116">[Ключевые показатели эффективности &#40;конструктора кубов&#41; &#40;Analysis Services многомерных данных&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="67fa8-116">[KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="67fa8-117">[Обозреватель &#40;конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="67fa8-117">[Browser &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="67fa8-118">Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="67fa8-118">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
