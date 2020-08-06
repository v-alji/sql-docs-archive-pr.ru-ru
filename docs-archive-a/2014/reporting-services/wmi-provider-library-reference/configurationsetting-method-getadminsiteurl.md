---
title: Метод GetAdminSiteUrl (WMI) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- GetAdminSiteUrl method
ms.assetid: fbc5bf3c-120c-4aec-a4f2-f5391bd415f6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cae1a6f7e363ddce8c47c00eb5ef25fc832e59c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658628"
---
# <a name="getadminsiteurl-method-wmi"></a><span data-ttu-id="6e838-102">Метод GetAdminSiteUrl (WMI)</span><span class="sxs-lookup"><span data-stu-id="6e838-102">GetAdminSiteUrl Method (WMI)</span></span>
  <span data-ttu-id="6e838-103">Возвращает абсолютный URL-адрес веб-сайта центра администрирования фермы Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]или [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] , с которой интегрирован сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="6e838-103">Gets the absolute URL for the Central Administration Web site for the Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] farm that the report server is integrated with.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e838-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e838-104">Syntax</span></span>  
  
```vb  
Public Sub GetAdminSiteUrl(ByRef AdminSiteUrl as String, _  
ByRef HRESULT as Int32)  
```  
  
```csharp  
public void GetAdminSiteUrl(out string AdminSiteUrl, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e838-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6e838-105">Parameters</span></span>  
 <span data-ttu-id="6e838-106">*AdminSiteUrl*</span><span class="sxs-lookup"><span data-stu-id="6e838-106">*AdminSiteUrl*</span></span>  
 <span data-ttu-id="6e838-107">[out] Строка, содержащая абсолютный URL-адрес веб-сайта центра администрирования фермы SharePoint, с которой интегрирован сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="6e838-107">[out] A string that contains the absolute URL for the Central Administration Web site for the SharePoint farm that the report server is integrated with.</span></span>  
  
 <span data-ttu-id="6e838-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="6e838-108">*HRESULT*</span></span>  
 <span data-ttu-id="6e838-109">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="6e838-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e838-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6e838-110">Return Value</span></span>  
 <span data-ttu-id="6e838-111">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="6e838-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="6e838-112">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="6e838-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="6e838-113">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="6e838-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e838-114">Требования</span><span class="sxs-lookup"><span data-stu-id="6e838-114">Requirements</span></span>  
 <span data-ttu-id="6e838-115">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e838-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e838-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="6e838-116">See Also</span></span>  
 [<span data-ttu-id="6e838-117">Методы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="6e838-117">MSReportServer_ConfigurationSetting Methods</span></span>](msreportserver-configurationsetting-methods.md)  
  
  
