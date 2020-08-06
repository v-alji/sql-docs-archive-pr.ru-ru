---
title: Метод RemoveSSLCertificateBindings (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RemoveSSLCertificateBindings method
ms.assetid: b8b484c9-04c4-4ae9-980e-67bbe5aa8481
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d42d17d9c92f2e100a7800e607536ff6c7eab891
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735934"
---
# <a name="removesslcertificatebindings-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="bb959-102">Метод RemoveSSLCertificateBindings (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="bb959-102">RemoveSSLCertificateBindings Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="bb959-103">Удаляет привязку к SSL-сертификату.</span><span class="sxs-lookup"><span data-stu-id="bb959-103">Removes an SSL Certificate binding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb959-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb959-104">Syntax</span></span>  
  
```vb  
Public Sub RemoveSSLCertificateBinding(ByVal Application As String, _  
    ByVal CertificateHash As String, ByVal IPAddress As String, _  
    ByVal Port As Int32, ByVal Lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void RemoveSSLCertificateBindings(string Application,  
    string CertificateHash, string IPAddress, Int32 Port, Int32 Lcid,  
    out string Error, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb959-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb959-105">Parameters</span></span>  
 <span data-ttu-id="bb959-106">*Приложение*</span><span class="sxs-lookup"><span data-stu-id="bb959-106">*Application*</span></span>  
 <span data-ttu-id="bb959-107">Имя приложения, для которого следует удалить привязку к сертификату.</span><span class="sxs-lookup"><span data-stu-id="bb959-107">The name of application for which the certificate binding should be removed.</span></span>  
  
 <span data-ttu-id="bb959-108">*CertificateHash*</span><span class="sxs-lookup"><span data-stu-id="bb959-108">*CertificateHash*</span></span>  
 <span data-ttu-id="bb959-109">Хэш для сертификата.</span><span class="sxs-lookup"><span data-stu-id="bb959-109">The hash for the certificate.</span></span>  
  
 <span data-ttu-id="bb959-110">*IPAddress*</span><span class="sxs-lookup"><span data-stu-id="bb959-110">*IPAddress*</span></span>  
 <span data-ttu-id="bb959-111">IP-адрес для приложения.</span><span class="sxs-lookup"><span data-stu-id="bb959-111">The IP address for the application.</span></span>  
  
 <span data-ttu-id="bb959-112">*порт*.</span><span class="sxs-lookup"><span data-stu-id="bb959-112">*Port*</span></span>  
 <span data-ttu-id="bb959-113">Порт SSL, связанный с привязкой.</span><span class="sxs-lookup"><span data-stu-id="bb959-113">The SSL port associated with the binding.</span></span>  
  
 <span data-ttu-id="bb959-114">*lcid*</span><span class="sxs-lookup"><span data-stu-id="bb959-114">*lcid*</span></span>  
 <span data-ttu-id="bb959-115">Локаль, используемая для возвращаемых сообщений об ошибке.</span><span class="sxs-lookup"><span data-stu-id="bb959-115">The locale to use for the error messages that are returned.</span></span>  
  
 <span data-ttu-id="bb959-116">*Error*</span><span class="sxs-lookup"><span data-stu-id="bb959-116">*Error*</span></span>  
 <span data-ttu-id="bb959-117">[out] Описания возникших ошибок.</span><span class="sxs-lookup"><span data-stu-id="bb959-117">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="bb959-118">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="bb959-118">*HRESULT*</span></span>  
 <span data-ttu-id="bb959-119">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="bb959-119">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb959-120">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bb959-120">Return Value</span></span>  
 <span data-ttu-id="bb959-121">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="bb959-121">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="bb959-122">Значение 0 означает, что вызов метода завершился успешно; код ошибки означает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="bb959-122">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb959-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="bb959-123">Remarks</span></span>  
 <span data-ttu-id="bb959-124">При помощи этого метода выполняется удаление конкретной привязки, заданной в файле rsreportserver.config и, при указании дополнительных параметров, в файле HTTP.SYS.</span><span class="sxs-lookup"><span data-stu-id="bb959-124">This method removes the specific binding from the rsreportserver.config file and optionally HTTP.SYS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb959-125">Требования</span><span class="sxs-lookup"><span data-stu-id="bb959-125">Requirements</span></span>  
 <span data-ttu-id="bb959-126">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb959-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb959-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb959-127">See Also</span></span>  
 [<span data-ttu-id="bb959-128">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="bb959-128">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
