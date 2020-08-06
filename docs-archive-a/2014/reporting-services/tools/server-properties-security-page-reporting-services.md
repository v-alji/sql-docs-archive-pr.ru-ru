---
title: Свойства сервера (страница "Безопасность") — службы Reporting Services | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.security.f1
ms.assetid: f49aedc6-f145-4df1-8f69-d5d910f492c6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f709d42bf593b4933d9fc1fdc423c195967df382
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665230"
---
# <a name="server-properties-security-page---reporting-services"></a><span data-ttu-id="7d637-102">Свойства сервера (страница «Безопасность») — службы Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7d637-102">Server Properties (Security Page) - Reporting Services</span></span>
  <span data-ttu-id="7d637-103">Эта страница используется для отключения функций, которые могут нарушить безопасность сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="7d637-103">Use this page to turn off features that can potentially compromise a report server.</span></span> <span data-ttu-id="7d637-104">Отключение этих функций ограничивает некоторые возможности, но повышает общую безопасность сервера отчетов, устраняя определенные угрозы.</span><span class="sxs-lookup"><span data-stu-id="7d637-104">Turning off these features will limit some functionality, but can improve the overall security of the report server by mitigating specific threats.</span></span>  
  
 <span data-ttu-id="7d637-105">Чтобы открыть эту страницу, в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]подключитесь к экземпляру сервера отчетов, щелкните его правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7d637-105">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="7d637-106">Нажмите кнопку **Безопасность** , чтобы открыть эту страницу.</span><span class="sxs-lookup"><span data-stu-id="7d637-106">Click **Security** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7d637-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="7d637-107">Options</span></span>  
 <span data-ttu-id="7d637-108">**Использовать встроенную безопасность Windows для источников данных для отчетов**</span><span class="sxs-lookup"><span data-stu-id="7d637-108">**Enable Windows integrated security for report data sources**</span></span>  
 <span data-ttu-id="7d637-109">Указывает, можно ли установить соединение с источником данных отчета с помощью токена безопасности Windows для пользователя, запрашивающего отчет.</span><span class="sxs-lookup"><span data-stu-id="7d637-109">Specify whether a connection to a report data source can be made using the Windows security token of the user who requested the report.</span></span>  
  
 <span data-ttu-id="7d637-110">Если отключить эту функцию, функция встроенной безопасности Windows на страницах свойств источника данных отчета станет недоступной.</span><span class="sxs-lookup"><span data-stu-id="7d637-110">If you turn off this feature, the Windows Integrated Security feature in the report data source property pages will be unavailable.</span></span> <span data-ttu-id="7d637-111">Если источники данных отчета настроены для применения встроенной безопасности Windows, и эта функция отключается, сервер отчетов немедленно обновит все свойства соединения с источниками данных, чтобы запрашивать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="7d637-111">If report data sources are configured for Windows integrated security and you subsequently turn off this feature, the report server will immediately update all data source connection properties to prompt for credentials.</span></span>  
  
 <span data-ttu-id="7d637-112">**Разрешить автоматизированные отчеты**</span><span class="sxs-lookup"><span data-stu-id="7d637-112">**Enable Ad Hoc Reporting**</span></span>  
 <span data-ttu-id="7d637-113">Указывает, могут ли пользователи выполнять нерегламентированные запросы из отчета построителя отчетов, в котором автоматически формируются новые отчеты, когда пользователь щелкает интересующие его данные.</span><span class="sxs-lookup"><span data-stu-id="7d637-113">Specify whether users can perform ad hoc queries from a Report Builder report, where new reports are automatically generated when a user clicks data of interest.</span></span>  
  
 <span data-ttu-id="7d637-114">Этот параметр определяет, какое значение присваивается свойству `EnableLoadReportDefinition` сервера отчетов — `True` или `False`.</span><span class="sxs-lookup"><span data-stu-id="7d637-114">Setting this option determines whether the `EnableLoadReportDefinition` property on the report server is set to `True` or `False`.</span></span> <span data-ttu-id="7d637-115">Если отключить этот параметр, свойству присваивается значение `False`, и сервер отчетов не будет формировать отчеты с дополнительной информацией, создаваемые во время просмотра данных.</span><span class="sxs-lookup"><span data-stu-id="7d637-115">If you clear this option, the property will be set to `False` and report server will not generate clickthrough reports that are created during data exploration.</span></span> <span data-ttu-id="7d637-116">Все вызовы метода `LoadReportDefinition` будут блокированы.</span><span class="sxs-lookup"><span data-stu-id="7d637-116">All calls to the `LoadReportDefinition` method will be blocked.</span></span>  
  
 <span data-ttu-id="7d637-117">Отключение этого параметра снижает угрозу, при которой пользователи-злоумышленники запускают атаку типа «отказ в обслуживании», перегружая сервер отчетов запросами `LoadReportDefinition`.</span><span class="sxs-lookup"><span data-stu-id="7d637-117">Turning off this option mitigates a threat whereby a malicious user launches a denial of service attack by overloading the report server with `LoadReportDefinition` requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d637-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="7d637-118">See Also</span></span>  
 <span data-ttu-id="7d637-119">[Установка свойств сервера отчетов &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="7d637-119">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="7d637-120">[Соединение с сервером отчетов в Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="7d637-120">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="7d637-121">[Указание учетных данных и сведений о соединении для источников данных отчета] (.. /репорт-Дата/спеЦифи-кредентиал-Анд-коннектион-Информатион-фор-репорт-Дата-саурцес.МД [Report Server в справке Management Studio F1](report-server-in-management-studio-f1-help.md)</span><span class="sxs-lookup"><span data-stu-id="7d637-121">[Specify Credential and Connection Information for Report Data Sources](../report-data/specify-credential-and-connection-information-for-report-data-sources.md [Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md)</span></span>  
  
  
