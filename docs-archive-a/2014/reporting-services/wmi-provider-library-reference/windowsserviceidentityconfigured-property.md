---
title: Свойство WindowsServiceIdentityConfigured (WMI MSReportServer_ConfigurationSetting) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- WindowsServiceIdentityConfigured
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- WindowsServiceIdentityConfigured property
ms.assetid: ebf8e559-7fe4-4a01-9810-85f18fc04596
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cb9b782aece15cf9aaf49b2bc427d34fa3d86525
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733490"
---
# <a name="windowsserviceidentityconfigured-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="9e5e6-102">Свойство WindowsServiceIdentityConfigured (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="9e5e6-102">WindowsServiceIdentityConfigured Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="9e5e6-103">Возвращает удостоверение, для выполнения с которым была в последний раз настроена служба Windows сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9e5e6-103">Returns the identity that the Report Server Windows service was last configured to run under.</span></span> <span data-ttu-id="9e5e6-104">Только для чтения.</span><span class="sxs-lookup"><span data-stu-id="9e5e6-104">Read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e5e6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e5e6-105">Syntax</span></span>  
  
```vb  
Public Dim WindowsServiceIdentityConfigured As String  
```  
  
```csharp  
public string WindowsServiceIdentityConfigured;  
```  
  
## <a name="property-values"></a><span data-ttu-id="9e5e6-106">Значения свойств</span><span class="sxs-lookup"><span data-stu-id="9e5e6-106">Property Values</span></span>  
 <span data-ttu-id="9e5e6-107">Значение `String`, содержащее удостоверение, которое в прошлый раз использовалось для выполнения службы Windows сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9e5e6-107">A `String` value containing the identity that the Report Server Windows service was last configured to run under.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="9e5e6-108">Пример кода</span><span class="sxs-lookup"><span data-stu-id="9e5e6-108">Example Code</span></span>  
 [<span data-ttu-id="9e5e6-109">Класс MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="9e5e6-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="9e5e6-110">Требования</span><span class="sxs-lookup"><span data-stu-id="9e5e6-110">Requirements</span></span>  
 <span data-ttu-id="9e5e6-111">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e5e6-111">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e5e6-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="9e5e6-112">See Also</span></span>  
 [<span data-ttu-id="9e5e6-113">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="9e5e6-113">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
