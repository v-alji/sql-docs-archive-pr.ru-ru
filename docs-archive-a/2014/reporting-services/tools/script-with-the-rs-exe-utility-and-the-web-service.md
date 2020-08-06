---
title: Создание скриптов с помощью программы rs.exe и веб-службы | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Web service [Reporting Services], scripts
- rs utility
- XML Web service [Reporting Services], scripts
- Report Server Web service, scripts
- scripts [Reporting Services], Web service
ms.assetid: 0ec5ac6e-b3cf-49cd-96f6-6b4b7dc29982
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9d84bb8722fd31a08ff7788ad31c601b377c23d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665236"
---
# <a name="script-with-the-rsexe-utility-and-the-web-service"></a><span data-ttu-id="924d9-102">Создание скриптов с помощью программы rs.exe и веб-службы</span><span class="sxs-lookup"><span data-stu-id="924d9-102">Script with the rs.exe Utility and the Web Service</span></span>
  <span data-ttu-id="924d9-103">Разработчики и администраторы сервера отчетов могут выполнять на сервере отчетов операции с помощью программы **rs** (RS.exe).</span><span class="sxs-lookup"><span data-stu-id="924d9-103">Developers and report server administrators can perform operations on a report server through the use of the **rs** utility (RS.exe).</span></span> <span data-ttu-id="924d9-104">Эта программа позволяет управлять сервером отчетов программными средствами с помощью скриптов на языке [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="924d9-104">Using this utility, you can programmatically administer a report server using scripts written with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="924d9-105">можно использовать для запуска любых операций веб-службы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="924d9-105">scripts can be used to run any of the Report Server Web service operations.</span></span> <span data-ttu-id="924d9-106">С помощью сценариев можно копировать параметры безопасности в несколько отчетов на сервере, создавать или удалять элементы, копировать элементы сервера отчетов с одного сервера на другой и т. д.</span><span class="sxs-lookup"><span data-stu-id="924d9-106">Scripting can be used to copy security to multiple reports on a server, to add and delete items, to copy report server items from one server to another and more.</span></span> <span data-ttu-id="924d9-107">Дополнительные сведения о среде скриптов см. в разделе [Запуск файла скрипта служб Reporting Services](run-a-reporting-services-script-file.md).</span><span class="sxs-lookup"><span data-stu-id="924d9-107">For more information about the scripting environment, see [Run a Reporting Services Script File](run-a-reporting-services-script-file.md).</span></span> <span data-ttu-id="924d9-108">Файлы скриптов имеют определенный формат и написаны на языке [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET.</span><span class="sxs-lookup"><span data-stu-id="924d9-108">Script files take a certain format and are written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET.</span></span> <span data-ttu-id="924d9-109">Дополнительные сведения см. в разделе [Форматирование файла скрипта служб Reporting Services](format-a-reporting-services-script-file.md).</span><span class="sxs-lookup"><span data-stu-id="924d9-109">For more information, see [Format a Reporting Services Script File](format-a-reporting-services-script-file.md).</span></span>  
  
 <span data-ttu-id="924d9-110">Примеры скриптов см. в:</span><span class="sxs-lookup"><span data-stu-id="924d9-110">For script samples, see the following:</span></span>  
  
 <span data-ttu-id="924d9-111">[Пример Reporting Services rs.exe сценария для переноса содержимого между серверами отчетов](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="924d9-111">[Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>  
  
 <span data-ttu-id="924d9-112">[Образцы продуктов служб SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889)</span><span class="sxs-lookup"><span data-stu-id="924d9-112">[SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="924d9-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="924d9-113">See Also</span></span>  
 <span data-ttu-id="924d9-114">[Написание скриптов для задач развертывания и администрирования](script-deployment-and-administrative-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="924d9-114">[Script Deployment and Administrative Tasks](script-deployment-and-administrative-tasks.md) </span></span>  
 <span data-ttu-id="924d9-115">[Веб-служба сервера отчетов](../report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="924d9-115">[Report Server Web Service](../report-server-web-service/report-server-web-service.md) </span></span>  
 <span data-ttu-id="924d9-116">[Технический справочник (службы SSRS)](../technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="924d9-116">[Technical Reference &#40;SSRS&#41;](../technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="924d9-117">Служебная программа RS.exe (SSRS)</span><span class="sxs-lookup"><span data-stu-id="924d9-117">RS.exe Utility &#40;SSRS&#41;</span></span>](rs-exe-utility-ssrs.md)  
  
  
