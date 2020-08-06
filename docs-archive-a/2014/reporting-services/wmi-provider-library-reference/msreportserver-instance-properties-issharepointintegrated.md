---
title: Свойство IsSharePointIntegrated (WMI MSReportServer_Instance) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- IsSharePointIntegrated property
ms.assetid: e21d00ad-5d9a-4290-8d74-7eeeda39e1ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0c92ebe586d37053b47f90ca98c31b3068a7b91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658608"
---
# <a name="issharepointintegrated-property-wmi-msreportserver_instance"></a><span data-ttu-id="ba31d-102">Свойство IsSharePointIntegrated (WMI MSReportServer_Instance)</span><span class="sxs-lookup"><span data-stu-id="ba31d-102">IsSharePointIntegrated Property (WMI MSReportServer_Instance)</span></span>
  <span data-ttu-id="ba31d-103">Указывает, находится ли сервер отчетов в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ba31d-103">Specifies whether the report server is in SharePoint integrated mode.</span></span> <span data-ttu-id="ba31d-104">Начиная с [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] это свойство всегда возвращает значение `False`, поскольку в режиме интеграции с SharePoint экземпляры служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] являются совместно используемыми службами SharePoint, которые не управляются поставщиками WMI.</span><span class="sxs-lookup"><span data-stu-id="ba31d-104">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], this property always returns `False` because in SharePoint mode, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instances are SharePoint shared services and are not controlled by WMI providers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba31d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba31d-105">Syntax</span></span>  
  
```vb  
Public Dim IsSharePointIntegrated As Boolean  
```  
  
```csharp  
public Boolean IsSharePointIntegrated;  
```  
  
## <a name="property-values"></a><span data-ttu-id="ba31d-106">Значения свойств</span><span class="sxs-lookup"><span data-stu-id="ba31d-106">Property Values</span></span>  
 <span data-ttu-id="ba31d-107">Значение `Boolean` показывает, работает ли сервер отчетов в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ba31d-107">A `Boolean` value that indicates whether the report server is in SharePoint integrated mode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba31d-108">Требования</span><span class="sxs-lookup"><span data-stu-id="ba31d-108">Requirements</span></span>  
 <span data-ttu-id="ba31d-109">**Пространство имен:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba31d-109">**Namespace:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba31d-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="ba31d-110">See Also</span></span>  
 <span data-ttu-id="ba31d-111">[Элементы MSReportServer_Instance](msreportserver-instance-members.md) </span><span class="sxs-lookup"><span data-stu-id="ba31d-111">[MSReportServer_Instance Members](msreportserver-instance-members.md) </span></span>  
 [<span data-ttu-id="ba31d-112">Класс MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="ba31d-112">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
  
