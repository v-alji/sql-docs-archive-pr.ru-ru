---
title: Развертывание модуля обработки данных | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- Extension element
- deploying [Reporting Services], extensions
ms.assetid: e5c0b5a9-1386-47cb-aade-96653ecfaa54
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 84fc2d2853ce7a6aae77f313ef0f4026ad2f35cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750503"
---
# <a name="deploying-a-data-processing-extension"></a><span data-ttu-id="16190-102">Развертывание модуля обработки данных</span><span class="sxs-lookup"><span data-stu-id="16190-102">Deploying a Data Processing Extension</span></span>
  <span data-ttu-id="16190-103">После создания модуля обработки данных для служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] и компиляции его в библиотеку [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] необходимо сделать модуль доступным для обнаружения сервером отчетов и конструктором отчетов.</span><span class="sxs-lookup"><span data-stu-id="16190-103">Once you have written and compiled your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension into a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] library, you need to make it discoverable by the report server and by Report Designer.</span></span> <span data-ttu-id="16190-104">Для этого нужно просто скопировать модуль в соответствующие каталоги и добавить записи в соответствующие файлы конфигурации служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16190-104">This is as easy as copying the extension to the appropriate directories and adding entries to the appropriate [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration files.</span></span>  
  
## <a name="configuration-file-extension-element"></a><span data-ttu-id="16190-105">Элемент Extension в файле конфигурации</span><span class="sxs-lookup"><span data-stu-id="16190-105">Configuration-File Extension Element</span></span>  
 <span data-ttu-id="16190-106">Модули обработки данных, развертываемые на сервере отчетов или в конструкторе отчетов, необходимо вставить в файлы конфигурации в виде элементов **Extension**.</span><span class="sxs-lookup"><span data-stu-id="16190-106">Data processing extensions that you deploy to the report server or Report Designer need to be entered as **Extension** elements in the configuration files.</span></span> <span data-ttu-id="16190-107">Для сервера отчетов используется файл RSReportServer.config, а для конструктора отчетов — файл RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="16190-107">These files are RSReportServer.config for the report server and RSReportDesigner.config for Report Designer.</span></span>  
  
 <span data-ttu-id="16190-108">В следующей таблице описаны атрибуты элемента **Extension** для модулей обработки данных.</span><span class="sxs-lookup"><span data-stu-id="16190-108">The following table describes the attributes for the **Extension** element for data processing extensions.</span></span>  
  
|<span data-ttu-id="16190-109">attribute</span><span class="sxs-lookup"><span data-stu-id="16190-109">Attribute</span></span>|<span data-ttu-id="16190-110">Description</span><span class="sxs-lookup"><span data-stu-id="16190-110">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="16190-111">Уникальное имя модуля, например «SQL» для модуля обработки данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] или «OLEDB» для модуля обработки данных OLE DB.</span><span class="sxs-lookup"><span data-stu-id="16190-111">A unique name for the extension, for example, "SQL" for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data processing extension or "OLEDB" for the OLE DB data processing extension.</span></span> <span data-ttu-id="16190-112">Длина атрибута `Name` не должна превышать 255 символов.</span><span class="sxs-lookup"><span data-stu-id="16190-112">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="16190-113">Имя должно быть уникальным среди всех элементов, вложенных в элемент **Extension** файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="16190-113">The name must be unique among all entries within the **Extension** element of a configuration file.</span></span>|  
|`Type`|<span data-ttu-id="16190-114">Список с разделителями-запятыми, содержащий полное пространство имен и имя сборки.</span><span class="sxs-lookup"><span data-stu-id="16190-114">A comma-separated list that includes the fully qualified namespace along with the name of the assembly.</span></span>|  
|`Visible`|<span data-ttu-id="16190-115">Значение `false` показывает, что модуль обработки данных не должен отображаться в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="16190-115">A value of `false` indicates that the data processing extension should not be visible in user interfaces.</span></span> <span data-ttu-id="16190-116">Если атрибут не указан, по умолчанию используется значение `true`.</span><span class="sxs-lookup"><span data-stu-id="16190-116">If the attribute is not included, the default value is `true`.</span></span>|  
  
 <span data-ttu-id="16190-117">Дополнительные сведения о файлах RSReportServer.config и RSReportDesigner.config см. в разделе [Файлы конфигурации служб Reporting Services](../../report-server/reporting-services-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="16190-117">For more information about the RSReportServer.config or RSReportDesigner.config files, see [Reporting Services Configuration Files](../../report-server/reporting-services-configuration-files.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16190-118">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="16190-118">In This Section</span></span>  
  
|<span data-ttu-id="16190-119">Раздел</span><span class="sxs-lookup"><span data-stu-id="16190-119">Topic</span></span>|<span data-ttu-id="16190-120">Описание</span><span class="sxs-lookup"><span data-stu-id="16190-120">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="16190-121">Руководство. Развертывание модуля обработки данных на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="16190-121">How to: Deploy a Data Processing Extension to a Report Server</span></span>](deploying-a-data-processing-extension-to-a-report-server.md)|<span data-ttu-id="16190-122">Описывает развертывание модуля обработки данных на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="16190-122">Describes how to deploy your data processing extension to a report server.</span></span>|  
|[<span data-ttu-id="16190-123">Руководство. Развертывание модуля обработки данных в конструкторе отчетов</span><span class="sxs-lookup"><span data-stu-id="16190-123">How to: Deploy a Data Processing Extension to Report Designer</span></span>](deploying-a-data-processing-extension-to-report-designer.md)|<span data-ttu-id="16190-124">Описывает развертывание модуля обработки данных в конструкторе отчетов.</span><span class="sxs-lookup"><span data-stu-id="16190-124">Describes how to deploy your data processing extension to Report Designer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16190-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="16190-125">See Also</span></span>  
 <span data-ttu-id="16190-126">[Расширения Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="16190-126">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="16190-127">[Реализация модуля обработки данных](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="16190-127">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="16190-128">Библиотека модулей служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="16190-128">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
