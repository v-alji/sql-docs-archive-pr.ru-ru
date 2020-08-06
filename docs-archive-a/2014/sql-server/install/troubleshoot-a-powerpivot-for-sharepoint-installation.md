---
title: Устранение неполадок при установке PowerPivot для SharePoint | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 97bc2ce7-af04-4372-ad79-c96b8c3417ab
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3adc27132d976288c14ac702baae0b842e8aef0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659163"
---
# <a name="troubleshoot-a-powerpivot-for-sharepoint-installation"></a><span data-ttu-id="715a6-102">Устранение неполадок установки PowerPivot для SharePoint</span><span class="sxs-lookup"><span data-stu-id="715a6-102">Troubleshoot a PowerPivot for SharePoint Installation</span></span>
  <span data-ttu-id="715a6-103">Если вместо ожидаемых страниц и компонентов выдаются ошибки, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="715a6-103">If you get errors instead of the pages and features you expect, do the following.</span></span>  
  
-   <span data-ttu-id="715a6-104">Откройте заметки о выпуске SharePoint и [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , чтобы выяснить, какие существуют способы решения известных проблем установки.</span><span class="sxs-lookup"><span data-stu-id="715a6-104">Review release notes for both SharePoint and [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to get workarounds for known installation problems.</span></span> <span data-ttu-id="715a6-105">Заметки о выпуске доступны на установочном носителе или на сайте Майкрософт, с которого было загружено программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="715a6-105">Release notes are provided with the installation media or on the Microsoft site from which you downloaded the software.</span></span>  
  
    -   <span data-ttu-id="715a6-106">[Заметки о Выпуске SQL Server 2014](https://technet.microsoft.com/library/dn169381\(v=sql.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="715a6-106">[SQL Server 2014 Release Notes](https://technet.microsoft.com/library/dn169381\(v=sql.15\).aspx).</span></span>  
  
-   <span data-ttu-id="715a6-107">См. раздел [Устранение неполадок установки PowerPivot (и других надстроек)](https://social.technet.microsoft.com/wiki/contents/articles/13737.troubleshooting-installations-of-powerpivot-and-other-add-ins.aspx)портала TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="715a6-107">See the Technet wiki topic, [Troubleshooting Installations of PowerPivot (and other add-ins)](https://social.technet.microsoft.com/wiki/contents/articles/13737.troubleshooting-installations-of-powerpivot-and-other-add-ins.aspx).</span></span>  
  
## <a name="issues"></a><span data-ttu-id="715a6-108">Проблемы</span><span class="sxs-lookup"><span data-stu-id="715a6-108">Issues</span></span>  
  
### <a name="powerpivot-gallery-thumbnail-images-show-as-a-red-x"></a><span data-ttu-id="715a6-109">Миниатюрные изображения в галерее PowerPivot отображаются в виде красного x</span><span class="sxs-lookup"><span data-stu-id="715a6-109">PowerPivot Gallery Thumbnail images show as a red X</span></span>  
 <span data-ttu-id="715a6-110">Одной из возможных причин **Интеграция функций PowerPivot для семейства веб-сайтов** не активна.</span><span class="sxs-lookup"><span data-stu-id="715a6-110">One Possible cause is the **PowerPivot features Integration for Site Collections** is not active.</span></span> <span data-ttu-id="715a6-111">Выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="715a6-111">Complete the following:</span></span>  
  
1.  <span data-ttu-id="715a6-112">В библиотеке PowerPivot Gallery щелкните **Site Settings (параметры сайта** ) либо на значке шестеренки ![Параметры SharePoint](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "Параметры SharePoint") , либо в списке " **домашний** ".</span><span class="sxs-lookup"><span data-stu-id="715a6-112">In the PowerPivot Gallery library, click **Site Settings** from either the gear icon ![SharePoint Settings](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "SharePoint Settings") or the **Home** list.</span></span>  
  
2.  <span data-ttu-id="715a6-113">Щелкните **Компоненты семейства веб-сайтов** в разделе **Администрирование семейства веб-сайтов**.</span><span class="sxs-lookup"><span data-stu-id="715a6-113">In the **Site Collection Administration** section, click **Site Collection Features**.</span></span>  
  
3.  <span data-ttu-id="715a6-114">Щелкните **Компоненты коллекции сайтов**.</span><span class="sxs-lookup"><span data-stu-id="715a6-114">Click **Site Collection Features**.</span></span>  
  
4.  <span data-ttu-id="715a6-115">Убедитесь, что значение **Функции интеграции с PowerPivot для семейств веб-сайтов** равно **Активны**.</span><span class="sxs-lookup"><span data-stu-id="715a6-115">Verify **PowerPivot features Integration for Site Collections** is **Active**.</span></span>  
  
 <span data-ttu-id="715a6-116">Дополнительные причины этой проблемы см. в разделе [Галерея PowerPivot с красным крестиком для значков](https://support.microsoft.com/kb/2361559) ( https://support.microsoft.com/kb/2361559) .</span><span class="sxs-lookup"><span data-stu-id="715a6-116">For additional causes of this issue, see [PowerPivot Gallery shows Red X's for Icons](https://support.microsoft.com/kb/2361559) (https://support.microsoft.com/kb/2361559).</span></span>  
  
  
