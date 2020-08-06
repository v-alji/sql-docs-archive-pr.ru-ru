---
title: Просмотр аспектов управления на основе политик в объекте SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view facets
ms.assetid: 5f423b9f-a6c4-41a7-9d8d-8f4926ce1fb4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9137971a79e9e5a18e0ef5d901184133a4c3eff3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657692"
---
# <a name="view-the-policy-based-management-facets-on-a-sql-server-object"></a><span data-ttu-id="56145-102">Просмотр аспектов управления на основе политик в объекте SQL Server</span><span class="sxs-lookup"><span data-stu-id="56145-102">View the Policy-Based Management Facets on a SQL Server Object</span></span>
  <span data-ttu-id="56145-103">В этом разделе описано, как просмотреть все аспекты управления на основе политик, примененные к объекту SQL Server, в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56145-103">This topic describes how to view all of the Policy-Based Management facets applied to a specific SQL Server object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="56145-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="56145-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="56145-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="56145-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="56145-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="56145-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="56145-107">**Для просмотра всех аспектов в объекте используется:**</span><span class="sxs-lookup"><span data-stu-id="56145-107">**To view all of the facets in an object, using:**</span></span>  
  
     [<span data-ttu-id="56145-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="56145-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="56145-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="56145-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="56145-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="56145-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="56145-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="56145-111">Permissions</span></span>  
 <span data-ttu-id="56145-112">Требуется членство в роли PolicyAdministratorRole базы данных msdb.</span><span class="sxs-lookup"><span data-stu-id="56145-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="56145-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="56145-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-all-of-the-facets-in-an-object"></a><span data-ttu-id="56145-114">Просмотр всех аспектов в объекте</span><span class="sxs-lookup"><span data-stu-id="56145-114">To view all of the facets in an object</span></span>  
  
1.  <span data-ttu-id="56145-115">В обозревателе объектов щелкните правой кнопкой мыши экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], объект экземпляра, базу данных или объект базы данных и выберите команду **Аспекты**.</span><span class="sxs-lookup"><span data-stu-id="56145-115">In Object Explorer, right-click an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], instance object, database, or database object, and then click **Facets**.</span></span>  
  
2.  <span data-ttu-id="56145-116">В диалоговом окне **Просмотр аспектов —**_имя_объекта_ в списке **Аспект** выберите аспект, чтобы просмотреть его свойства.</span><span class="sxs-lookup"><span data-stu-id="56145-116">In the **View Facets -**_object_name_ dialog box, in the **Facet** list, select a facet to view its properties.</span></span> <span data-ttu-id="56145-117">Дополнительные сведения о доступных параметрах данного диалогового окна см. в разделе [View Facets Dialog Box](view-facets-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="56145-117">For more information on the available options in this dialog box, see [View Facets Dialog Box](view-facets-dialog-box.md).</span></span>  
  
3.  <span data-ttu-id="56145-118">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="56145-118">When finished, click **OK**.</span></span>  
  
  
