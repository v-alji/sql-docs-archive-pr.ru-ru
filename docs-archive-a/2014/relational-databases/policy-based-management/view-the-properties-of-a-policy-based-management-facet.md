---
title: Просмотр свойств аспекта управления на основе политик | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view facet properties
ms.assetid: 022a244c-c2e7-4467-b9a2-c7a27859be22
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea24ff2768ecaeec426a8689455912d848b54813
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657691"
---
# <a name="view-the-properties-of-a-policy-based-management-facet"></a><span data-ttu-id="8edda-102">Просмотр свойств аспекта управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="8edda-102">View the Properties of a Policy-Based Management Facet</span></span>
  <span data-ttu-id="8edda-103">В этом разделе описывается просмотр свойств аспекта управления на основе политик в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8edda-103">This topic describes how to view the properties of a Policy-Based Management facet in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="8edda-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="8edda-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8edda-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="8edda-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8edda-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="8edda-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8edda-107">**Просмотр свойств аспекта с помощью:**</span><span class="sxs-lookup"><span data-stu-id="8edda-107">**To view the properties of a facet, using:**</span></span>  
  
     [<span data-ttu-id="8edda-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8edda-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8edda-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="8edda-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8edda-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="8edda-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8edda-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="8edda-111">Permissions</span></span>  
 <span data-ttu-id="8edda-112">Требуется членство в роли PolicyAdministratorRole базы данных msdb.</span><span class="sxs-lookup"><span data-stu-id="8edda-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8edda-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8edda-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-of-a-facet"></a><span data-ttu-id="8edda-114">Просмотр свойств аспекта</span><span class="sxs-lookup"><span data-stu-id="8edda-114">To view the properties of a facet</span></span>  
  
1.  <span data-ttu-id="8edda-115">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть сервер, содержащий аспект, который нужно просмотреть.</span><span class="sxs-lookup"><span data-stu-id="8edda-115">In **Object Explorer**, click the plus sign to expand the server that contains the facet whose properties you want to view.</span></span>  
  
2.  <span data-ttu-id="8edda-116">Щелкните знак «плюс», чтобы развернуть папку **Управление** .</span><span class="sxs-lookup"><span data-stu-id="8edda-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="8edda-117">Щелкните знак «плюс», чтобы развернуть папку **Управление политиками**.</span><span class="sxs-lookup"><span data-stu-id="8edda-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="8edda-118">Чтобы развернуть папку **Аспекты** , щелкните знак «плюс».</span><span class="sxs-lookup"><span data-stu-id="8edda-118">Click the plus sign to expand the **Facets** folder.</span></span>  
  
5.  <span data-ttu-id="8edda-119">Щелкните правой кнопкой мыши аспект, свойства которого необходимо просмотреть, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8edda-119">Right-click the facet whose properties you want to view and select **Properties**.</span></span> <span data-ttu-id="8edda-120">Дополнительные сведения о параметрах, доступных в диалоговом окне **Свойства аспекта —**_имя_аспекта_, см. в статьях [Диалоговое окно "Свойства аспекта", вкладка "Общие"](../../integration-services/general-page-of-integration-services-designers-options.md), [Диалоговое окно "Свойства аспекта", вкладка "Зависимые политики"](facet-properties-dialog-box-dependent-policies-page.md) и [Диалоговое окно "Свойства аспекта", вкладка "Зависимые условия"](facet-properties-dialog-box-dependent-conditions-page.md).</span><span class="sxs-lookup"><span data-stu-id="8edda-120">For more information on the available options in the **Facet Properties -**_facet_name_ dialog box, see [Facet Properties Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md), [Facet Properties Dialog Box, Dependent Policies Page](facet-properties-dialog-box-dependent-policies-page.md), and [Facet Properties Dialog Box, Dependent Conditions Page](facet-properties-dialog-box-dependent-conditions-page.md).</span></span>  
  
6.  <span data-ttu-id="8edda-121">После завершения нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="8edda-121">When finished, click **Close**.</span></span>  
  
  
