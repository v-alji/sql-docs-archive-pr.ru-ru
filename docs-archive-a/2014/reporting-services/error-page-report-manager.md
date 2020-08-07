---
title: Страница "ошибка" (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8311ed32-00f3-451d-8279-946429f5fee1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fc50a5b0516bcbf8221ce3ee130090f66a929c3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735053"
---
# <a name="error-page-report-manager"></a><span data-ttu-id="becda-102">Страница «Ошибка» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="becda-102">Error Page (Report Manager)</span></span>
  <span data-ttu-id="becda-103">Страница «Ошибка» используется для просмотра подробностей состояния ошибки.</span><span class="sxs-lookup"><span data-stu-id="becda-103">Use the Error page to view details about an error condition.</span></span> <span data-ttu-id="becda-104">На этой странице отображаются ошибки на сервере или на основе сеанса.</span><span class="sxs-lookup"><span data-stu-id="becda-104">Server-based or session-based errors appear on this page.</span></span> <span data-ttu-id="becda-105">Ошибки проверки, связанные с конкретными элементами управления на страницах, отображаются в строке сразу после соответствующего элемента.</span><span class="sxs-lookup"><span data-stu-id="becda-105">Validation errors that relate to specific page controls display inline next to the control.</span></span>  
  
-   <span data-ttu-id="becda-106">Если при переходе на локальный сервер отчетов отображаются ошибки, аналогичные приведенным ниже, см. раздел [Настройка сервера отчетов в собственном режиме для локального администрирования &#40;SSRS&#41;](report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="becda-106">If you are browsing to a local report server and you see errors similar to the following, see: [Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;](report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md)</span></span>  
  
     <span data-ttu-id="becda-107">Пользователь "домен \\ [имя пользователя]" не имеет необходимых разрешений.</span><span class="sxs-lookup"><span data-stu-id="becda-107">User 'Domain\\[user name]' does not have required permissions.</span></span> <span data-ttu-id="becda-108">Убедитесь, что предоставлены достаточные разрешения и учтены ограничения контроля учетных записей Windows.</span><span class="sxs-lookup"><span data-stu-id="becda-108">Verify that sufficient permissions have been granted and Windows User Account Control (UAC) restrictions have been addressed.</span></span>  
  
-   <span data-ttu-id="becda-109">Если отображаются сообщения об ошибке, подобные приведенному далее, см. раздел [Configure a Report Server for Remote Administration](report-server/configure-a-report-server-for-remote-administration.md).</span><span class="sxs-lookup"><span data-stu-id="becda-109">If you see error messages similar to the following, see [Configure a Report Server for Remote Administration](report-server/configure-a-report-server-for-remote-administration.md).</span></span>  
  
     <span data-ttu-id="becda-110">Невозможно найти компьютер.</span><span class="sxs-lookup"><span data-stu-id="becda-110">The machine could not be found.</span></span> <span data-ttu-id="becda-111">"Сервер RPC недоступен.</span><span class="sxs-lookup"><span data-stu-id="becda-111">"The RPC server is unavailable.</span></span> <span data-ttu-id="becda-112">(Исключение HRESULT: 0x800706BA.)".</span><span class="sxs-lookup"><span data-stu-id="becda-112">(Exception from HRESULT: 0x800706BA)".</span></span>  
  
-   <span data-ttu-id="becda-113">Можно задать свойства сервера на сервере отчетов [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , чтобы возвращались дополнительные сведения об ошибках, возникающих на удаленных серверах.</span><span class="sxs-lookup"><span data-stu-id="becda-113">You can set server properties on a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server to return additional information about error conditions that occur on remote servers.</span></span> <span data-ttu-id="becda-114">Если сообщение об ошибке содержит текст "Дополнительные сведения об этой ошибке, перейдите на сервер отчетов на локальном компьютере сервера или включите" включить удаленные ошибки ", см. раздел [включение &#40;ошибок Reporting Services&#41;](report-server/enable-remote-errors-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="becda-114">If an error message contains the text "For more information about this error, navigate to the report server on the local server machine, or enable remote errors", see [Enable Remote Errors &#40;Reporting Services&#41;](report-server/enable-remote-errors-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="becda-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="becda-115">See Also</span></span>  
 <span data-ttu-id="becda-116">[Настройка диспетчер отчетов &#40;собственном режиме&#41;](report-server/configure-web-portal.md) </span><span class="sxs-lookup"><span data-stu-id="becda-116">[Configure Report Manager &#40;Native Mode&#41;](report-server/configure-web-portal.md) </span></span>  
 <span data-ttu-id="becda-117">[Ссылки на ошибки и события &#40;Reporting Services&#41;](troubleshooting/errors-and-events-reference-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="becda-117">[Errors and Events Reference &#40;Reporting Services&#41;](troubleshooting/errors-and-events-reference-reporting-services.md) </span></span>  
 [<span data-ttu-id="becda-118">Справка F1 диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="becda-118">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
