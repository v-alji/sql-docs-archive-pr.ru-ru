---
title: Удаление модуля подготовки отчетов | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- deleting rendering extensions
- removing rendering extensions
- rendering extensions [Reporting Services], removing
ms.assetid: 2abfebfb-065f-45cc-a904-c914394cf900
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77a8a9ac44b35f338f978913985617e4f264ddb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664748"
---
# <a name="removing-a-rendering-extension"></a><span data-ttu-id="c36c2-102">Удаление модуля подготовки отчетов</span><span class="sxs-lookup"><span data-stu-id="c36c2-102">Removing a Rendering Extension</span></span>
  <span data-ttu-id="c36c2-103">Чтобы удалить [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] модуль подготовки отчетов, просто удалите `Extension` элемент для модуля подготовки отчетов из файла rsreportserver.config, расположенного в папке **%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<Instance Name> Папка \Reporting Services\ReportServer** .</span><span class="sxs-lookup"><span data-stu-id="c36c2-103">To remove a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] rendering extension, simply remove the `Extension` element for your rendering extension from the rsreportserver.config file, located in **%ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<Instance Name>\Reporting Services\ReportServer** folder.</span></span> <span data-ttu-id="c36c2-104">Если вы внесли записи для конструктор отчетов, а также для сервера отчетов, удалите `Extension` элемент из [файла конфигурации RSReportDesigner](../../report-server/rsreportdesigner-configuration-file.md) .</span><span class="sxs-lookup"><span data-stu-id="c36c2-104">If you made entries for a Report Designer as well as a report server, remove the `Extension` element from the [RSReportDesigner Configuration File](../../report-server/rsreportdesigner-configuration-file.md) as well.</span></span> <span data-ttu-id="c36c2-105">После удаления сведений о конфигурации модуль подготовки отчетов становится недоступным компоненту.</span><span class="sxs-lookup"><span data-stu-id="c36c2-105">After the configuration information is removed, the rendering extension is no longer available to the component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c36c2-106">См. также:</span><span class="sxs-lookup"><span data-stu-id="c36c2-106">See Also</span></span>  
 <span data-ttu-id="c36c2-107">[Файлы конфигурации служб Reporting Services](../../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="c36c2-107">[Reporting Services Configuration Files](../../report-server/reporting-services-configuration-files.md) </span></span>  
 <span data-ttu-id="c36c2-108">[Реализация модуля подготовки отчетов](implementing-a-rendering-extension.md) </span><span class="sxs-lookup"><span data-stu-id="c36c2-108">[Implementing a Rendering Extension](implementing-a-rendering-extension.md) </span></span>  
 <span data-ttu-id="c36c2-109">[Общие сведения о модулях подготовки отчетов](rendering-extensions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="c36c2-109">[Rendering Extensions Overview](rendering-extensions-overview.md) </span></span>  
 <span data-ttu-id="c36c2-110">[Реализация интерфейса IRenderingExtension](implementing-the-irenderingextension-interface.md) </span><span class="sxs-lookup"><span data-stu-id="c36c2-110">[Implementing the IRenderingExtension Interface](implementing-the-irenderingextension-interface.md) </span></span>  
 <span data-ttu-id="c36c2-111">[Рекомендации по обеспечению безопасности для модулей](../security-considerations-for-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="c36c2-111">[Security Considerations for Extensions](../security-considerations-for-extensions.md) </span></span>  
 [<span data-ttu-id="c36c2-112">Развертывание модуля подготовки отчетов</span><span class="sxs-lookup"><span data-stu-id="c36c2-112">Deploying a Rendering Extension</span></span>](deploying-a-rendering-extension.md)  
  
  
