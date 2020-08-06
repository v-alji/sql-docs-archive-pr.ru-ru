---
title: Свойство IsSharePointIntegrated (WMI) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- IsSharePointIntegrated property
ms.assetid: c548fed8-5e04-4faf-8b10-b37c86178056
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a1f3f38c23546ddf4dfb52c2a3af7c122af10cbd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666418"
---
# <a name="issharepointintegrated-property-wmi"></a><span data-ttu-id="21c14-102">Свойство IsSharePointIntegrated (WMI)</span><span class="sxs-lookup"><span data-stu-id="21c14-102">IsSharePointIntegrated Property (WMI)</span></span>
  <span data-ttu-id="21c14-103">Указывает, находится ли сервер отчетов в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="21c14-103">Specifies whether the report server is in SharePoint integrated mode.</span></span> <span data-ttu-id="21c14-104">Начиная с [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] это свойство всегда возвращает значение `False`, поскольку в режиме интеграции с SharePoint экземпляры служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] являются совместно используемыми службами SharePoint, которые не управляются поставщиками WMI.</span><span class="sxs-lookup"><span data-stu-id="21c14-104">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], this property always returns `False` because in SharePoint mode, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instances are SharePoint shared services and are not controlled by WMI providers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21c14-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21c14-105">Syntax</span></span>  
  
```vb  
Public Dim IsSharePointIntegrated As Boolean  
```  
  
```csharp  
public Boolean IsSharePointIntegrated;  
```  
  
## <a name="property-values"></a><span data-ttu-id="21c14-106">Значения свойств</span><span class="sxs-lookup"><span data-stu-id="21c14-106">Property Values</span></span>  
 <span data-ttu-id="21c14-107">Объект `Boolean`, который показывает, работает ли сервер отчетов в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="21c14-107">A `Boolean` object that indicates whether the report server is in SharePoint integrated mode.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="21c14-108">Пример кода</span><span class="sxs-lookup"><span data-stu-id="21c14-108">Example Code</span></span>  
 [<span data-ttu-id="21c14-109">Класс MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="21c14-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="21c14-110">Требования</span><span class="sxs-lookup"><span data-stu-id="21c14-110">Requirements</span></span>  
 <span data-ttu-id="21c14-111">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21c14-111">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21c14-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="21c14-112">See Also</span></span>  
 [<span data-ttu-id="21c14-113">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="21c14-113">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
