---
title: Метод RemoveURL (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RemoveURL method
ms.assetid: 3d98bd97-e152-48ce-ab1c-bd2c4f8b7fe9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3a32989e8ce8986b785e829d8cc7fcf58fbbf240
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665228"
---
# <a name="removeurl-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="00a37-102">Метод RemoveURL (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="00a37-102">RemoveURL Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="00a37-103">Удаляет URL-адрес, зарезервированный для сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="00a37-103">Removes a URL reserved for the report server.</span></span> <span data-ttu-id="00a37-104">Если нужно удалить несколько URL-адресов, это должно быть сделано одним вызовом данного API.</span><span class="sxs-lookup"><span data-stu-id="00a37-104">If there are multiple URLs that need to be removed, this must be done one by one calling this API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00a37-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00a37-105">Syntax</span></span>  
  
```vb  
Public Sub RemoveURL(ByVal Application As String, _  
    ByVal UrlString As String, ByVal Lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void RemoveURL(string Application, string UrlString, int Lcid,   
    out string Error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00a37-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="00a37-106">Parameters</span></span>  
 <span data-ttu-id="00a37-107">*Приложение*</span><span class="sxs-lookup"><span data-stu-id="00a37-107">*Application*</span></span>  
 <span data-ttu-id="00a37-108">Имя приложения, для которого удаляется резервирование.</span><span class="sxs-lookup"><span data-stu-id="00a37-108">The name of application for which to remove the reservation.</span></span>  
  
 <span data-ttu-id="00a37-109">*URLString*</span><span class="sxs-lookup"><span data-stu-id="00a37-109">*URLString*</span></span>  
 <span data-ttu-id="00a37-110">URL-адрес для резервирования.</span><span class="sxs-lookup"><span data-stu-id="00a37-110">The URL for the reservation.</span></span>  
  
 <span data-ttu-id="00a37-111">*lcid*</span><span class="sxs-lookup"><span data-stu-id="00a37-111">*lcid*</span></span>  
 <span data-ttu-id="00a37-112">Локаль, используемая для возвращаемых сообщений об ошибке.</span><span class="sxs-lookup"><span data-stu-id="00a37-112">The locale to use for the error messages returned.</span></span>  
  
 <span data-ttu-id="00a37-113">*Error*</span><span class="sxs-lookup"><span data-stu-id="00a37-113">*Error*</span></span>  
 <span data-ttu-id="00a37-114">[out] Описания возникших ошибок.</span><span class="sxs-lookup"><span data-stu-id="00a37-114">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="00a37-115">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="00a37-115">*HRESULT*</span></span>  
 <span data-ttu-id="00a37-116">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="00a37-116">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00a37-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="00a37-117">Return Value</span></span>  
 <span data-ttu-id="00a37-118">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="00a37-118">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="00a37-119">Значение 0 означает, что вызов метода завершился успешно; код ошибки означает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="00a37-119">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00a37-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="00a37-120">Remarks</span></span>  
 <span data-ttu-id="00a37-121">*UrlString* не включает имя виртуального каталога — для этого есть [метод SetVirtualDirectory (WMI MSReportServer_ConfigurationSetting)](configurationsetting-method-setvirtualdirectory.md).</span><span class="sxs-lookup"><span data-stu-id="00a37-121">*UrlString* does not include the Virtual Directory name - the [SetVirtualDirectory Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setvirtualdirectory.md) method is provided for that purpose.</span></span>  
  
 <span data-ttu-id="00a37-122">Прежде чем вызывать метод [ReserveURL](configurationsetting-method-reserveurl.md) , необходимо задать значение свойства конфигурации VirtualDirectory для параметра *Application* .</span><span class="sxs-lookup"><span data-stu-id="00a37-122">Before calling the [ReserveURL](configurationsetting-method-reserveurl.md) method, you must supply a value for the VirtualDirectory configuration property for the *Application* parameter.</span></span> <span data-ttu-id="00a37-123">Используйте [метод SetVirtualDirectory (WMI MSReportServer_ConfigurationSetting)](configurationsetting-method-setvirtualdirectory.md) для задания свойства VirtualDirectory.</span><span class="sxs-lookup"><span data-stu-id="00a37-123">Use the [SetVirtualDirectory Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setvirtualdirectory.md) method to set the VirtualDirectory property.</span></span>  
  
 <span data-ttu-id="00a37-124">Если службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] предоставляют SSL-сертификат и он не нужен никаким другим URL-адресам, он удаляется.</span><span class="sxs-lookup"><span data-stu-id="00a37-124">If an SSL Certificate was provisioned by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and no other URLs need it, it is removed.</span></span>  
  
 <span data-ttu-id="00a37-125">Во время этой операции данный метод вызывает жесткую очистку и остановку всех доменов неконфигурационных приложений; после этой операции домены приложений перезапускаются.</span><span class="sxs-lookup"><span data-stu-id="00a37-125">This method causes all non-configuration app domains to hard recycle and stop during this operation; app domains are restarted after this operation complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00a37-126">Требования</span><span class="sxs-lookup"><span data-stu-id="00a37-126">Requirements</span></span>  
 <span data-ttu-id="00a37-127">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00a37-127">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00a37-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="00a37-128">See Also</span></span>  
 [<span data-ttu-id="00a37-129">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="00a37-129">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
