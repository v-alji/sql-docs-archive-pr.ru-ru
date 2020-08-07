---
title: Свойство RSWindowsExtendedProtectionScenario (WMI MSReportServer_ConfigurationSetting) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ac7ab80-9adf-4f65-abfa-fedf53b082b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 84e14d056cc0352b0d1d85bc12c9c873a1b89ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734914"
---
# <a name="rswindowsextendedprotectionscenario-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="89e90-102">Свойство RSWindowsExtendedProtectionScenario (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="89e90-102">RSWindowsExtendedProtectionScenario Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="89e90-103">Возвращает строковое значение, определяющее сценарий расширенной защиты, поддержка которого настроена на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="89e90-103">Returns a string value that indicates the extended protection scenario the report server is configured to allow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89e90-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89e90-104">Syntax</span></span>  
  
```vb  
Public Dim RSWindowsExtendedProtectionScenario As String  
```  
  
```csharp  
public string RSWindowsExtendedProtectionScenario;  
```  
  
## <a name="remarks"></a><span data-ttu-id="89e90-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="89e90-105">Remarks</span></span>  
 <span data-ttu-id="89e90-106">Возвращает строковое значение, определяющее сценарий расширенной защиты, поддержка которого настроена на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="89e90-106">Returns a string value that indicates the extended protection scenario the report server is configured to allow.</span></span> <span data-ttu-id="89e90-107">Если сервер отчетов, к которому подключен поставщик WMI, не поддерживает расширенную защиту, возвращается пустая строка ("").</span><span class="sxs-lookup"><span data-stu-id="89e90-107">If the report server that the WMI provider is connected to does not support extended protection, "" (empty string) is returned.</span></span>  
  
 <span data-ttu-id="89e90-108">Допустимые значения приведены в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="89e90-108">The following list shows valid values:</span></span>  
  
 `"Any | Proxy | Direct"`  
  
## <a name="example-code"></a><span data-ttu-id="89e90-109">Пример кода</span><span class="sxs-lookup"><span data-stu-id="89e90-109">Example Code</span></span>  
 [<span data-ttu-id="89e90-110">Класс MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="89e90-110">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="see-also"></a><span data-ttu-id="89e90-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="89e90-111">See Also</span></span>  
 <span data-ttu-id="89e90-112">[Свойство RSWindowsExtendedProtectionLevel (WMI MSReportServer_ConfigurationSetting)](rswindowsextendedprotectionlevel-property.md) </span><span class="sxs-lookup"><span data-stu-id="89e90-112">[RSWindowsExtendedProtectionLevel Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span></span>  
 <span data-ttu-id="89e90-113">[Метод SetExtendedProtectionSettings (WMI MSReportServer_ConfigurationSetting)](configurationsetting-method-setextendedprotectionsettings.md) </span><span class="sxs-lookup"><span data-stu-id="89e90-113">[SetExtendedProtectionSettings Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span></span>  
 <span data-ttu-id="89e90-114">[Расширенная защита для проверки подлинности с использованием служб Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="89e90-114">[Extended Protection for Authentication with Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span></span>  
 [<span data-ttu-id="89e90-115">RSReportServer Configuration File</span><span class="sxs-lookup"><span data-stu-id="89e90-115">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
  
  
