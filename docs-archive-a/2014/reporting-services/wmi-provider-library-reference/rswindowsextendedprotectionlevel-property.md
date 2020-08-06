---
title: Свойство RSWindowsExtendedProtectionLevel (WMI MSReportServer_ConfigurationSetting) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 162ffe86-69c3-49d2-b9ed-49d097c05551
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02ff3bad42ae25adf6cfa563944d89bac2c600e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658607"
---
# <a name="rswindowsextendedprotectionlevel-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="6058d-102">Свойство RSWindowsExtendedProtectionLevel (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="6058d-102">RSWindowsExtendedProtectionLevel Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="6058d-103">Возвращает строковое значение, указывающее уровень защиты, на поддержку которого настроен сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="6058d-103">Returns a string value that indicates the level of protection the report server is configured to support.</span></span> <span data-ttu-id="6058d-104">Это свойство доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="6058d-104">This property is read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6058d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6058d-105">Syntax</span></span>  
  
```vb  
Public Dim RSWindowsExtendedProtectionLevel As String  
```  
  
```csharp  
public string RSWindowsExtendedProtectionLevel;  
```  
  
## <a name="remarks"></a><span data-ttu-id="6058d-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="6058d-106">Remarks</span></span>  
 <span data-ttu-id="6058d-107">Возвращает строковое значение, указывающее уровень защиты, на поддержку которого настроен сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="6058d-107">Returns a string value that indicates the level of protection the report server is configured to support.</span></span> <span data-ttu-id="6058d-108">Если сервер отчетов, к которому подключен поставщик WMI, не поддерживает расширенную защиту, возвращается пустая строка ("").</span><span class="sxs-lookup"><span data-stu-id="6058d-108">If the report server that the WMI provider is connected to does not support extended protection, "" (empty string) is returned.</span></span> <span data-ttu-id="6058d-109">Допустимые значения приведены в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="6058d-109">The following list shows valid values:</span></span>  
  
 `"Off" | "Allow" | "Require"`  
  
## <a name="example-code"></a><span data-ttu-id="6058d-110">Пример кода</span><span class="sxs-lookup"><span data-stu-id="6058d-110">Example Code</span></span>  
 [<span data-ttu-id="6058d-111">Класс MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="6058d-111">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="see-also"></a><span data-ttu-id="6058d-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="6058d-112">See Also</span></span>  
 <span data-ttu-id="6058d-113">[Свойство RSWindowsExtendedProtectionScenario (WMI MSReportServer_ConfigurationSetting)](rswindowsextendedprotectionscenario-property.md) </span><span class="sxs-lookup"><span data-stu-id="6058d-113">[RSWindowsExtendedProtectionScenario Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionscenario-property.md) </span></span>  
 <span data-ttu-id="6058d-114">[Метод SetExtendedProtectionSettings (WMI MSReportServer_ConfigurationSetting)](configurationsetting-method-setextendedprotectionsettings.md) </span><span class="sxs-lookup"><span data-stu-id="6058d-114">[SetExtendedProtectionSettings Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span></span>  
 <span data-ttu-id="6058d-115">[Расширенная защита для проверки подлинности с использованием служб Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="6058d-115">[Extended Protection for Authentication with Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span></span>  
 [<span data-ttu-id="6058d-116">RSReportServer Configuration File</span><span class="sxs-lookup"><span data-stu-id="6058d-116">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
  
  
