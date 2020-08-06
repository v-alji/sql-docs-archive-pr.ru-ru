---
title: Метод SetServiceState (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetServiceState (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceState method
ms.assetid: 9e1ee42d-b388-4929-89c7-8741b956c3be
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 70b4a29b3379fc1d312af42a1f5b1296ee35dcf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737703"
---
# <a name="setservicestate-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="be459-102">Метод SetServiceState (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="be459-102">SetServiceState Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="be459-103">Включает и выключает службу Windows и веб-службу сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="be459-103">Turns the Report Server Windows and Web services on and off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be459-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be459-104">Syntax</span></span>  
  
```vb  
Public Sub SetServiceState(ByVal EnableWindowsService As Boolean, _  
    ByVal EnableWebService As Boolean, ByVal EnableReportManager As Boolean, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetSecureConnectionLevel(Boolean EnableWindowsService,  
    Boolean EnableWebService, Boolean EnableReportManager, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be459-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="be459-105">Parameters</span></span>  
 <span data-ttu-id="be459-106">*EnableWindowsService*</span><span class="sxs-lookup"><span data-stu-id="be459-106">*EnableWindowsService*</span></span>  
 <span data-ttu-id="be459-107">Значение `Boolean`, которое показывает состояние службы Windows.</span><span class="sxs-lookup"><span data-stu-id="be459-107">A `Boolean` value indicating the state of the Windows service.</span></span> <span data-ttu-id="be459-108">Значение `true` запускает службу Windows сервера отчетов; значение `false` останавливает службу Windows.</span><span class="sxs-lookup"><span data-stu-id="be459-108">A value of `true` starts the Report Server Windows service; a value of `false` stops the Windows service.</span></span>  
  
 <span data-ttu-id="be459-109">*EnableWebService*</span><span class="sxs-lookup"><span data-stu-id="be459-109">*EnableWebService*</span></span>  
 <span data-ttu-id="be459-110">`Boolean`Значение, указывающее состояние [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] веб-службы.</span><span class="sxs-lookup"><span data-stu-id="be459-110">A `Boolean` value indicating the state of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Web service.</span></span> <span data-ttu-id="be459-111">Значение `true` запускает веб-службу сервера отчетов; значение `false` останавливает веб-службу.</span><span class="sxs-lookup"><span data-stu-id="be459-111">A value of `true` starts the Report Server Web service; a value of `false` stops the Web service</span></span>  
  
 <span data-ttu-id="be459-112">*EnableReportManager*</span><span class="sxs-lookup"><span data-stu-id="be459-112">*EnableReportManager*</span></span>  
 <span data-ttu-id="be459-113">Значение `Boolean`, которое показывает требуемое состояние диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="be459-113">A `Boolean` value indicating the desired state of the Report manager.</span></span>  
  
 <span data-ttu-id="be459-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="be459-114">*HRESULT*</span></span>  
 <span data-ttu-id="be459-115">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="be459-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be459-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="be459-116">Return Value</span></span>  
 <span data-ttu-id="be459-117">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="be459-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="be459-118">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="be459-118">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="be459-119">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="be459-119">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be459-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="be459-120">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be459-121">Требования</span><span class="sxs-lookup"><span data-stu-id="be459-121">Requirements</span></span>  
 <span data-ttu-id="be459-122">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be459-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be459-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="be459-123">See Also</span></span>  
 [<span data-ttu-id="be459-124">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="be459-124">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
