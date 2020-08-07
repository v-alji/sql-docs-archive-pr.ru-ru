---
title: Указание параметров сведений об устройстве в URL-адресе | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], URLs
- URL access [Reporting Services], device information settings
ms.assetid: cb7f7577-c6a8-4e6f-8e60-5ec0760f29c3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 00cd1fdc3b5fbe129ae4d51b220a11bc48b4744c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734938"
---
# <a name="specify-device-information-settings-in-a-url"></a><span data-ttu-id="753eb-102">Указание настройки сведений об устройстве в URL-адресе</span><span class="sxs-lookup"><span data-stu-id="753eb-102">Specify Device Information Settings in a URL</span></span>
  <span data-ttu-id="753eb-103">Настройки сведений об устройстве передаются в модуль подготовки отчетов.</span><span class="sxs-lookup"><span data-stu-id="753eb-103">Device information settings are parameters that are passed to a rendering extension.</span></span> <span data-ttu-id="753eb-104">Если для подготовки отчета к просмотру используются методы веб-службы сервера отчетов [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], то в качестве входного параметра передается XML-элемент `DeviceInfo`.</span><span class="sxs-lookup"><span data-stu-id="753eb-104">If you use the methods of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Report Server Web service to render a report, a `DeviceInfo` XML element is passed as an input parameter.</span></span> <span data-ttu-id="753eb-105">Дочерние элементы для элемента `DeviceInfo` зависят от настроек сведений об устройстве различных модулей подготовки отчетов.</span><span class="sxs-lookup"><span data-stu-id="753eb-105">Child elements of the `DeviceInfo` element are specific to the device information settings of different rendering extensions.</span></span> <span data-ttu-id="753eb-106">Настройки сведений об устройстве можно включить в URL-адрес с помощью строки параметров *rc:tag=value* , где параметр *tag* представляет имя элемента с настройками сведений об устройстве, к которому выполняется доступ.</span><span class="sxs-lookup"><span data-stu-id="753eb-106">You can include device information settings in a URL by using the *rc:tag=value* parameter string, where *tag* is the name of the device information settings element being accessed.</span></span> <span data-ttu-id="753eb-107">Дополнительную информацию о настройках сведений в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] см. в статье [Передача настроек сведений об устройстве модулям подготовки отчетов к просмотру](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="753eb-107">For more information about device information settings in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="753eb-108">Пример</span><span class="sxs-lookup"><span data-stu-id="753eb-108">Example</span></span>  
 <span data-ttu-id="753eb-109">В следующем примере с помощью параметра сведений об устройстве *OutputFormat* для модуля подготовки изображений для указанного отчета задается формат JPEG (для удобочитаемости добавлены разрывы строк).</span><span class="sxs-lookup"><span data-stu-id="753eb-109">The following example sets the format of the specified report to JPEG by using the *OutputFormat* device information setting of the image rendering extension (the line breaks have been added for legibility):</span></span>  
  
```  
http://servername/reportserver?/SampleReports  
/Employee Sales Summary&EmployeeID=38&rs:  
Command=Render&rs:Format=IMAGE&rc:OutputFormat=JPEG  
```  
  
## <a name="see-also"></a><span data-ttu-id="753eb-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="753eb-110">See Also</span></span>  
 <span data-ttu-id="753eb-111">[Доступ по URL-адресу (службы SSRS)](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="753eb-111">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="753eb-112">Ссылка на параметр доступа по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="753eb-112">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
