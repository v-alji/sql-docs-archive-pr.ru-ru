---
title: База данных сервера отчетов не настроена (советник по переходу) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: b964300c-b220-4244-9fa6-c0c6a57760f6
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 072e689da3f43222396f071e607214a2ec494749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654755"
---
# <a name="report-server-database-is-not-configured-upgrade-advisor"></a><span data-ttu-id="b376b-102">База данных сервера отчетов настроена (советник по переходу)</span><span class="sxs-lookup"><span data-stu-id="b376b-102">Report server database is not configured (Upgrade Advisor)</span></span>
  <span data-ttu-id="b376b-103">Обновление заблокировано в связи с тем, что настройка сервера отчетов не завершена.</span><span class="sxs-lookup"><span data-stu-id="b376b-103">Upgrade is blocked due to an incomplete report server configuration.</span></span> <span data-ttu-id="b376b-104">База данных сервера отчетов не настроена.</span><span class="sxs-lookup"><span data-stu-id="b376b-104">The report server database is not configured.</span></span>  
  
||  
|-|  
|<span data-ttu-id="b376b-105">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Собственный режим &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Режим интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b376b-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="b376b-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="b376b-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="b376b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b376b-107">Description</span></span>  
 <span data-ttu-id="b376b-108">Программа обновления может обновить только полностью настроенный экземпляр сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="b376b-108">Setup can only upgrade a fully configured report server instance.</span></span> <span data-ttu-id="b376b-109">Чтобы продолжить, необходимо либо настроить базу данных сервера отчетов, либо с помощью **панели управления** Microsoft Windows удалить компонент сервера отчетов из установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b376b-109">To continue, you must either configure the report server database, or use Microsoft Windows **Control Panel** to remove the report server feature from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="b376b-110">После удаления служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]можно произвести обновление других компонентов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b376b-110">After you remove [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can upgrade other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="b376b-111">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="b376b-111">Corrective Action</span></span>  
 <span data-ttu-id="b376b-112">Если база данных сервера отчетов не была настроена, сервер отчетов находится в нерабочем состоянии и должен быть удален до обновления.</span><span class="sxs-lookup"><span data-stu-id="b376b-112">If you did not configure the report server database, the report server is not operational and should be removed prior to upgrade.</span></span>  
  
 <span data-ttu-id="b376b-113">Дополнительные сведения об удалении служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] см. в разделе [Удаление служб Reporting Services 2012](https://technet.microsoft.com/library/hh479745.aspx\(v=sql.11\)).</span><span class="sxs-lookup"><span data-stu-id="b376b-113">For additional information on uninstalling [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , see [Uninstall Reporting Services 2012](https://technet.microsoft.com/library/hh479745.aspx\(v=sql.11\)).</span></span> <span data-ttu-id="b376b-114">в разделе описывается удаление конкретной версии. Эта процедура похожа на ту, которая была в предыдущих версиях.</span><span class="sxs-lookup"><span data-stu-id="b376b-114">the topic describes how to uninstall a specific version and the procedures are similar for previous versions as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b376b-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="b376b-115">See Also</span></span>  
 [<span data-ttu-id="b376b-116">Reporting Services проблем обновления &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="b376b-116">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
