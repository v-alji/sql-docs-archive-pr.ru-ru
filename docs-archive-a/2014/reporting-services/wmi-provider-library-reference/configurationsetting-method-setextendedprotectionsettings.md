---
title: Метод SetExtendedProtectionSettings (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2d8e7232-42f4-41b6-98eb-c856f6c85d8c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ee937747b74bcf8d53012721b4be5bfca04185df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737727"
---
# <a name="setextendedprotectionsettings-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="da136-102">Метод SetExtendedProtectionSettings (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="da136-102">SetExtendedProtectionSettings Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="da136-103">Метод SetExtendedProtectionSettings устанавливает значения для свойств RSWindowsExtendedProtectionLevel и RSWindowsExtendedProtectionScenario в RSReportServer.config в файле конфигурации служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="da136-103">The SetExtendedProtectionSettings method is used to set the RSWindowsExtendedProtectionLevel and the RSWindowsExtendedProtectionScenario properties in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] configuration file RSReportServer.config.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da136-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da136-104">Syntax</span></span>  
  
```vb  
Public Sub SetExtendedProtectionSettings( _  
        ByVal ExtendedProtectionLevel As String, _  
        ByVal ExtendedProtectionScenario As String, _  
        ByRef Warnings() As String, _  
        ByRef Length As Int32, _  
        ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetExtendedProtectionSettings(  
            string ExtendedProtectionLevel,  
            string ExtendedProtectionScenario,  
            out string[] Warnings,  
            out Int32 Length,  
            out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da136-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="da136-105">Parameters</span></span>  
 <span data-ttu-id="da136-106">*ExtendedProtectionLevel*</span><span class="sxs-lookup"><span data-stu-id="da136-106">*ExtendedProtectionLevel*</span></span>  
 <span data-ttu-id="da136-107">Устанавливает свойство RSWindowsExtendedProtectionLevel в файле RSRreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="da136-107">Sets the RSWindowsExtendedProtectionLevel in the RSRreportserver.config file.</span></span> <span data-ttu-id="da136-108">Значение является обязательным и не зависит от регистра.</span><span class="sxs-lookup"><span data-stu-id="da136-108">The required value is not case sensitive.</span></span>  
  
 <span data-ttu-id="da136-109">Допустимые значения приведены в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="da136-109">The following list shows valid values:</span></span>  
  
 `"Off | Allow | Require"`  
  
 <span data-ttu-id="da136-110">*ExtendedProtectionScenario*</span><span class="sxs-lookup"><span data-stu-id="da136-110">*ExtendedProtectionScenario*</span></span>  
 <span data-ttu-id="da136-111">Устанавливает свойство RSWindowsExtendedProtectionScenario в файле RSReportserver.config.</span><span class="sxs-lookup"><span data-stu-id="da136-111">Sets the RSWindowsExtendedProtectionScenario in the RSReportserver.config file.</span></span> <span data-ttu-id="da136-112">Значение является обязательным и не зависит от регистра.</span><span class="sxs-lookup"><span data-stu-id="da136-112">The required value is not case sensitive.</span></span>  
  
 <span data-ttu-id="da136-113">Допустимые значения приведены в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="da136-113">The following list shows valid values:</span></span>  
  
 `"Any" | "Proxy" | "Direct"`  
  
## <a name="remarks"></a><span data-ttu-id="da136-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="da136-114">Remarks</span></span>  
 <span data-ttu-id="da136-115">Свойства RSWindowsExtendedProtectionLevel и RSWindowsExtendedProtectionScenario используются в том случае, если параметр AuthenticationTypes в файле RSReportServer.config имеет значение RSWindowNTLM, RSWindowsNegotiate или RSWindowsKerberos.</span><span class="sxs-lookup"><span data-stu-id="da136-115">The RSWindowsExtendedProtectionLevel and the RSWindowsExtendedProtectionScenario properties apply when the AuthenticationTypes in the RSReportServer.config file include RSWindowNTLM, RSWindowsNegotiate, or RSWindowsKerberos.</span></span> <span data-ttu-id="da136-116">Настройка этих свойств влияет на проверку подлинности пользователей и клиентского программного обеспечения на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="da136-116">Setting these properties affects how users and client software authenticate with a report server.</span></span> <span data-ttu-id="da136-117">Рекомендуется ознакомиться с документацией по расширенной защите, прежде чем устанавливать ExtendedProtectionLevel в значение `Allow` или `Require`.</span><span class="sxs-lookup"><span data-stu-id="da136-117">It is recommended that you read the documentation for extended protection before setting ExtendedProtectionLevel to either `Allow` or `Require`.</span></span>  
  
 <span data-ttu-id="da136-118">Для установки параметра ExtendedProtectionLevel пользователь должен быть членом группы BUILTIN\Administrators на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="da136-118">To set the ExtendedProtectionLevel, the user must be a member of the BUILTIN\Administrators group on the report server.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da136-119">Требования</span><span class="sxs-lookup"><span data-stu-id="da136-119">Requirements</span></span>  
 <span data-ttu-id="da136-120">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da136-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da136-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="da136-121">See Also</span></span>  
 <span data-ttu-id="da136-122">[Свойство RSWindowsExtendedProtectionScenario (WMI MSReportServer_ConfigurationSetting)](rswindowsextendedprotectionscenario-property.md) </span><span class="sxs-lookup"><span data-stu-id="da136-122">[RSWindowsExtendedProtectionScenario Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionscenario-property.md) </span></span>  
 <span data-ttu-id="da136-123">[Свойство RSWindowsExtendedProtectionLevel (WMI MSReportServer_ConfigurationSetting)](rswindowsextendedprotectionlevel-property.md) </span><span class="sxs-lookup"><span data-stu-id="da136-123">[RSWindowsExtendedProtectionLevel Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span></span>  
 <span data-ttu-id="da136-124">[Расширенная защита для проверки подлинности с использованием служб Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="da136-124">[Extended Protection for Authentication with Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span></span>  
 [<span data-ttu-id="da136-125">RSReportServer Configuration File</span><span class="sxs-lookup"><span data-stu-id="da136-125">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
  
  
