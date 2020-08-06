---
title: Метод ListSSLCertificates (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListSSLCertificates method
ms.assetid: 88cd0936-b202-4ab8-90f2-d9c3f66d37f4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6a5ced8371817adc44bbbc89400dc83e0dfccef0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658612"
---
# <a name="listsslcertificates-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="fe500-102">Метод ListSSLCertificates (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="fe500-102">ListSSLCertificates Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="fe500-103">Возвращает список сертификатов на компьютере с сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="fe500-103">Returns a list of certificates on the report server computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe500-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe500-104">Syntax</span></span>  
  
```vb  
Public Sub CreateSSLCertificateBinding (ByRef CertificateHash() as String, _  
    ByRef CertName() as String, ByRef HostName() as String, ByRef Length as Int32, _   
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ListSSLCertificates(out string[] CertificateHash,   
    out string[] CertName, out string[] Hostname, out Int32 length,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe500-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fe500-105">Parameters</span></span>  
 <span data-ttu-id="fe500-106">*CertificateHash[]*</span><span class="sxs-lookup"><span data-stu-id="fe500-106">*CertificateHash[]*</span></span>  
 <span data-ttu-id="fe500-107">[out] Хэши сертификатов.</span><span class="sxs-lookup"><span data-stu-id="fe500-107">[out] The certificate hashes.</span></span>  
  
 <span data-ttu-id="fe500-108">*CertName[]*</span><span class="sxs-lookup"><span data-stu-id="fe500-108">*CertName[]*</span></span>  
 <span data-ttu-id="fe500-109">[out] Имена сертификата.</span><span class="sxs-lookup"><span data-stu-id="fe500-109">[out] Names of the certificate.</span></span>  
  
 <span data-ttu-id="fe500-110">*HostName[]*</span><span class="sxs-lookup"><span data-stu-id="fe500-110">*HostName[]*</span></span>  
 <span data-ttu-id="fe500-111">[out] Имена узлов для сертификатов.</span><span class="sxs-lookup"><span data-stu-id="fe500-111">[out] The host names for the certificates.</span></span>  
  
 <span data-ttu-id="fe500-112">*Длина*</span><span class="sxs-lookup"><span data-stu-id="fe500-112">*Length*</span></span>  
 <span data-ttu-id="fe500-113">[out] Представляет длину массивов *CertificateHash*, *CertName* и *HostName* .</span><span class="sxs-lookup"><span data-stu-id="fe500-113">[out] Represents the length of the *CertificateHash*, *CertName* and *HostName* arrays.</span></span>  
  
 <span data-ttu-id="fe500-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="fe500-114">*HRESULT*</span></span>  
 <span data-ttu-id="fe500-115">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="fe500-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe500-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fe500-116">Return Value</span></span>  
 <span data-ttu-id="fe500-117">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="fe500-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="fe500-118">Значение 0 означает, что вызов метода завершился успешно; код ошибки означает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="fe500-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe500-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="fe500-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe500-120">Требования</span><span class="sxs-lookup"><span data-stu-id="fe500-120">Requirements</span></span>  
 <span data-ttu-id="fe500-121">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe500-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe500-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="fe500-122">See Also</span></span>  
 [<span data-ttu-id="fe500-123">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="fe500-123">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
