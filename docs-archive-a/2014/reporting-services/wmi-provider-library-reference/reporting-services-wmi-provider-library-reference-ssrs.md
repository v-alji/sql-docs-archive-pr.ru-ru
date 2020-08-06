---
title: Справочник по библиотеке поставщика WMI служб Reporting Services (SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- Reporting Services WMI Provider Library
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- WMI provider [Reporting Services], library
ms.assetid: 17ba711d-7eff-4423-9168-63dc425a3428
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2a98ca22f9d34627e484a698dcf540b31808d07e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658604"
---
# <a name="reporting-services-wmi-provider-library-reference-ssrs"></a><span data-ttu-id="80d68-102">Справочник по библиотеке поставщика WMI служб Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="80d68-102">Reporting Services WMI Provider Library Reference (SSRS)</span></span>
  <span data-ttu-id="80d68-103">Поставщик WMI служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] поддерживает операции WMI, позволяющие создавать скрипты и код для изменения параметров сервера и диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="80d68-103">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Windows Management Instrumentation (WMI) provider supports WMI operations that enable you to write scripts and code to modify settings of the report server and Report Manager.</span></span>  
  
 <span data-ttu-id="80d68-104">Например, чтобы изменить режим использования встроенной безопасности при соединении сервера отчетов с его базой данных, создайте экземпляр класса MSReportServer_ConfigurationSetting и воспользуйтесь свойством DatabaseIntegratedSecurity экземпляра сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="80d68-104">For example, if you want to change whether integrated security is used when the report server connects to the report server database, create an instance of the MSReportServer_ConfigurationSetting class and use the DatabaseIntegratedSecurity property of the of the report server instance.</span></span> <span data-ttu-id="80d68-105">Классы, показанные в следующей таблице, представляют компоненты служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="80d68-105">The classes shown in the following table represent [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] components.</span></span> <span data-ttu-id="80d68-106">Классы определены в пространстве имен [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)] или [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="80d68-106">The classes are defined in either the [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)] or the [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)] namespaces.</span></span> <span data-ttu-id="80d68-107">Все они поддерживают операции считывания и записи.</span><span class="sxs-lookup"><span data-stu-id="80d68-107">Each of the classes support read and write operations.</span></span> <span data-ttu-id="80d68-108">Операции создания не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="80d68-108">Create operations are not supported.</span></span>  
  
## <a name="classes"></a><span data-ttu-id="80d68-109">Классы</span><span class="sxs-lookup"><span data-stu-id="80d68-109">Classes</span></span>  
 [<span data-ttu-id="80d68-110">MSReportServer_Instance, класс</span><span class="sxs-lookup"><span data-stu-id="80d68-110">MSReportServer_Instance Class</span></span>](msreportserver-instance-class.md)  
 <span data-ttu-id="80d68-111">Основные сведения, необходимые клиенту для подключения к установленному серверу отчетов.</span><span class="sxs-lookup"><span data-stu-id="80d68-111">Provides basic information required for a client to connect to an installed report server.</span></span>  
  
 [<span data-ttu-id="80d68-112">Класс MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="80d68-112">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
 <span data-ttu-id="80d68-113">Представляет установочные параметры и параметры времени выполнения для экземпляра сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="80d68-113">Represents the installation and run-time parameters of a report server instance.</span></span> <span data-ttu-id="80d68-114">Эти параметры хранятся в файле конфигурации для сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="80d68-114">These parameters are stored in the configuration file for the report server.</span></span>  
  
 <span data-ttu-id="80d68-115">Дополнительные сведения об операциях WMI см. в документации по пакету SDK для инструментария WMI, поставляемому с [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] пакетом SDK.</span><span class="sxs-lookup"><span data-stu-id="80d68-115">For more information about WMI operations, see the WMI SDK documentation included with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80d68-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="80d68-116">See Also</span></span>  
 <span data-ttu-id="80d68-117">[Доступ к поставщику WMI Reporting Services](../tools/access-the-reporting-services-wmi-provider.md) </span><span class="sxs-lookup"><span data-stu-id="80d68-117">[Access the Reporting Services WMI Provider](../tools/access-the-reporting-services-wmi-provider.md) </span></span>  
 [<span data-ttu-id="80d68-118">Технический справочник (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="80d68-118">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
