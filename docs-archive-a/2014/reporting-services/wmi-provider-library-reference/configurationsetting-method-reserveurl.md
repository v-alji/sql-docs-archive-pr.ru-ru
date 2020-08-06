---
title: Метод ReserveURL (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ReservedURL method
ms.assetid: b9008a62-3edd-4f8a-99f2-7598c2133899
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 95a58938ada19b4e49f094e3d8d01b241f1a4286
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737748"
---
# <a name="reserveurl-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="f98cd-102">Метод ReserveURL (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="f98cd-102">ReserveURL Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="f98cd-103">Добавляет резервирование URL-адресов для заданного приложения.</span><span class="sxs-lookup"><span data-stu-id="f98cd-103">Adds a URL reservation for a given application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f98cd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f98cd-104">Syntax</span></span>  
  
```vb  
Public Sub ReserveURL(Application as String, _  
    UrlString as String, Lcid as Int32, _   
    ByRef [Error] as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ReserveURL(string Application, string UrlString, int Lcid,   
    out string error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f98cd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f98cd-105">Parameters</span></span>  
 <span data-ttu-id="f98cd-106">*Приложение*</span><span class="sxs-lookup"><span data-stu-id="f98cd-106">*Application*</span></span>  
 <span data-ttu-id="f98cd-107">Имя приложения, для которого резервируется URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="f98cd-107">The name of application to reserve the URL for.</span></span>  
  
 <span data-ttu-id="f98cd-108">*URLString*</span><span class="sxs-lookup"><span data-stu-id="f98cd-108">*URLString*</span></span>  
 <span data-ttu-id="f98cd-109">URL-адрес для резервирования.</span><span class="sxs-lookup"><span data-stu-id="f98cd-109">The URL for the reservation.</span></span>  
  
 <span data-ttu-id="f98cd-110">*lcid*</span><span class="sxs-lookup"><span data-stu-id="f98cd-110">*lcid*</span></span>  
 <span data-ttu-id="f98cd-111">Локаль, используемая для возвращаемых сообщений об ошибке.</span><span class="sxs-lookup"><span data-stu-id="f98cd-111">The locale to use for the error messages returned.</span></span>  
  
 <span data-ttu-id="f98cd-112">*Ошибка*</span><span class="sxs-lookup"><span data-stu-id="f98cd-112">*Error*</span></span>  
 <span data-ttu-id="f98cd-113">[out] Описания возникших ошибок.</span><span class="sxs-lookup"><span data-stu-id="f98cd-113">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="f98cd-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="f98cd-114">*HRESULT*</span></span>  
 <span data-ttu-id="f98cd-115">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="f98cd-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f98cd-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f98cd-116">Return Value</span></span>  
 <span data-ttu-id="f98cd-117">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="f98cd-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="f98cd-118">Значение 0 означает, что вызов метода завершился успешно; код ошибки означает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="f98cd-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f98cd-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="f98cd-119">Remarks</span></span>  
 <span data-ttu-id="f98cd-120">Строка*UrlString* не включает имя виртуального каталога.</span><span class="sxs-lookup"><span data-stu-id="f98cd-120">*UrlString* does not include the virtual directory name.</span></span> <span data-ttu-id="f98cd-121">Метод [SetVirtualDirectory](configurationsetting-method-setvirtualdirectory.md) служит специально для этой цели.</span><span class="sxs-lookup"><span data-stu-id="f98cd-121">The [SetVirtualDirectory](configurationsetting-method-setvirtualdirectory.md) method is provided for that purpose.</span></span>  
  
 <span data-ttu-id="f98cd-122">Для текущей учетной записи службы Windows создаются зарезервированные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="f98cd-122">URL reservations are created for the current windows service account.</span></span> <span data-ttu-id="f98cd-123">Изменение учетной записи Windows требует обновления всех зарезервированных URL-адресов вручную.</span><span class="sxs-lookup"><span data-stu-id="f98cd-123">Changing the windows service account requires updating all the URL reservations manually.</span></span>  
  
 <span data-ttu-id="f98cd-124">Этот метод вызывает жесткую очистку всех доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="f98cd-124">This method causes all application domains to hard recycle.</span></span> <span data-ttu-id="f98cd-125">После завершения этой операции выполняется перезапуск всех доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="f98cd-125">Application domains are restarted after this operation is complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f98cd-126">Требования</span><span class="sxs-lookup"><span data-stu-id="f98cd-126">Requirements</span></span>  
 <span data-ttu-id="f98cd-127">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f98cd-127">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f98cd-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="f98cd-128">See Also</span></span>  
 [<span data-ttu-id="f98cd-129">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="f98cd-129">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
