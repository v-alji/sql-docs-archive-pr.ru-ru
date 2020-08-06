---
title: Метод ListIPAddresses (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListIPAddresses method
ms.assetid: 7e7cf182-fba0-4604-a474-098461e23e9d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 845f7ba7db02a0b860f966184463580733af0faf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658624"
---
# <a name="listipaddresses-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="2d528-102">Метод ListIPAddresses (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="2d528-102">ListIPAddresses Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="2d528-103">Список IP-адресов для компьютера, на котором размещен сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="2d528-103">Lists the IP addresses for the report server computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d528-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d528-104">Syntax</span></span>  
  
```vb  
Public Sub ListIPAddresses (ByRef IPAddress() as String, _  
    ByRef IPVersion()as String, ByRef IsDhcpEnabled () as Boolean, _   
    ByRef Length as Int32, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ListIPAddresses (out string[] IPAddress,   
    out string[] IPVersion, out bool[] isDhcpEnabled, out int length,   
    out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d528-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2d528-105">Parameters</span></span>  
 <span data-ttu-id="2d528-106">*IPAddress[]*</span><span class="sxs-lookup"><span data-stu-id="2d528-106">*IPAddress[]*</span></span>  
 <span data-ttu-id="2d528-107">[out] Список IP-адресов для компьютера.</span><span class="sxs-lookup"><span data-stu-id="2d528-107">[out] The list of IP address for the computer.</span></span>  
  
 <span data-ttu-id="2d528-108">*IPVersion[]*</span><span class="sxs-lookup"><span data-stu-id="2d528-108">*IPVersion[]*</span></span>  
 <span data-ttu-id="2d528-109">[out] Версия IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="2d528-109">[out] The version for the IP addresses.</span></span>  
  
 <span data-ttu-id="2d528-110">*IsDhcpEnabled[]*</span><span class="sxs-lookup"><span data-stu-id="2d528-110">*IsDhcpEnabled[]*</span></span>  
 <span data-ttu-id="2d528-111">[out] Показывает, используется ли для получения IP-адресов DHCP.</span><span class="sxs-lookup"><span data-stu-id="2d528-111">[out] Indicates whether the IP addresses are DHCP enabled.</span></span>  
  
 <span data-ttu-id="2d528-112">*Длина*</span><span class="sxs-lookup"><span data-stu-id="2d528-112">*Length*</span></span>  
 <span data-ttu-id="2d528-113">[out] Длина массива, возвращаемого методом.</span><span class="sxs-lookup"><span data-stu-id="2d528-113">[out] The length of the array returned by the method.</span></span>  
  
 <span data-ttu-id="2d528-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="2d528-114">*HRESULT*</span></span>  
 <span data-ttu-id="2d528-115">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="2d528-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d528-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2d528-116">Return Value</span></span>  
 <span data-ttu-id="2d528-117">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="2d528-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="2d528-118">Значение 0 означает, что вызов метода завершился успешно; код ошибки означает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="2d528-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d528-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="2d528-119">Remarks</span></span>  
 <span data-ttu-id="2d528-120">Строки*IPVersion* имеют значения V4 и V6.</span><span class="sxs-lookup"><span data-stu-id="2d528-120">*IPVersion* strings are V4, V6.</span></span>  
  
 <span data-ttu-id="2d528-121">Если *исдхкпенаблед* имеет значение `True` , то *IPAddress* является динамическим.</span><span class="sxs-lookup"><span data-stu-id="2d528-121">If *IsDhcpEnabled* is `True`, the *IPAddress* is dynamic.</span></span> <span data-ttu-id="2d528-122">Его не следует использовать для привязок SSL.</span><span class="sxs-lookup"><span data-stu-id="2d528-122">It should not be used for SSL bindings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d528-123">Требования</span><span class="sxs-lookup"><span data-stu-id="2d528-123">Requirements</span></span>  
 <span data-ttu-id="2d528-124">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d528-124">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d528-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="2d528-125">See Also</span></span>  
 [<span data-ttu-id="2d528-126">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="2d528-126">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
