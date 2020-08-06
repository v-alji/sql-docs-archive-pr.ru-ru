---
title: На сервере отчетов обнаружены пользовательские элементы отчета (советник по переходу) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- custom report items, upgrading
ms.assetid: aee32006-65b2-4dfe-9570-d85a249d17b2
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: feacf6aa6f233f85a67b43e7b72d3a50913991bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657483"
---
# <a name="custom-report-items-were-detected-on-the-report-server-upgrade-advisor"></a><span data-ttu-id="564cb-102">На сервере отчетов были обнаружены пользовательские элементы отчета (советник по переходу)</span><span class="sxs-lookup"><span data-stu-id="564cb-102">Custom report items were detected on the report server (Upgrade Advisor)</span></span>
  <span data-ttu-id="564cb-103">Пользовательские элементы отчета, созданные для предыдущих версий, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] несовместимы с [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="564cb-103">Custom report items that were created for previous releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] are not compatible with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="564cb-104">Обновление может быть продолжено, но отчеты, использующие пользовательские элементы отчета, будут работать неправильно.</span><span class="sxs-lookup"><span data-stu-id="564cb-104">Upgrade can continue, but reports that use the custom report item will not run as expected.</span></span> <span data-ttu-id="564cb-105">Помощник по обновлению обнаружил пользовательские элементы отчета.</span><span class="sxs-lookup"><span data-stu-id="564cb-105">Upgrade Advisor detected custom report items.</span></span> <span data-ttu-id="564cb-106">Обновление может быть продолжено, но после завершения обновления необходимо вручную переместить файлы пользовательского элемента отчета в новую папку установки.</span><span class="sxs-lookup"><span data-stu-id="564cb-106">Upgrade can continue, but you must manually move the custom report item files to the new installation folder after upgrade completes.</span></span>  
  
||  
|-|  
|<span data-ttu-id="564cb-107">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Собственный режим &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Режим интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="564cb-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="564cb-108">Компонент</span><span class="sxs-lookup"><span data-stu-id="564cb-108">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="564cb-109">Описание</span><span class="sxs-lookup"><span data-stu-id="564cb-109">Description</span></span>  
 <span data-ttu-id="564cb-110">Советник по переходу обнаружил пользовательские настройки расширения служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в файлах конфигурации. Это указывает на то, что установка включает одну или несколько пользовательских сборок для отчетов.</span><span class="sxs-lookup"><span data-stu-id="564cb-110">Upgrade Advisor detected custom [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] extension settings in the configuration files, indicating that your installation includes one or more custom assemblies for reports.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="564cb-111">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="564cb-111">Corrective Action</span></span>  
 <span data-ttu-id="564cb-112">После завершения обновления вручную поместите файлы пользовательского элемента отчета в новую папку установки.</span><span class="sxs-lookup"><span data-stu-id="564cb-112">After upgrade completes, manually move the custom report item files to the new installation folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="564cb-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="564cb-113">See Also</span></span>  
 [<span data-ttu-id="564cb-114">Reporting Services проблем обновления &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="564cb-114">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
