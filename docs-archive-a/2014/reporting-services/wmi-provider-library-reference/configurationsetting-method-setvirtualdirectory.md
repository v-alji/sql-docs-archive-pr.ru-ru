---
title: Метод SetVirtualDirectory (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- SetVirtualDirectory method
ms.assetid: 1a25cb1d-38d5-401a-970b-87b642a780e4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7f45181f3f6a791f5cb64a7519285b6d2a87dd36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737697"
---
# <a name="setvirtualdirectory-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="3661c-102">Метод SetVirtualDirectory (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="3661c-102">SetVirtualDirectory Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="3661c-103">Задает имя виртуального каталога для указанного приложения.</span><span class="sxs-lookup"><span data-stu-id="3661c-103">Sets the name of the virtual directory for a given application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3661c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3661c-104">Syntax</span></span>  
  
```vb  
Public Sub SetVirtualDirectory(ByVal Application As String, _  
    ByVal VirtualDirectory As String, ByVal lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetVirtualDirectory(string Application, string VirtualDirectory,   
       int Lcid,out string Error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3661c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3661c-105">Parameters</span></span>  
 <span data-ttu-id="3661c-106">*Приложение*</span><span class="sxs-lookup"><span data-stu-id="3661c-106">*Application*</span></span>  
 <span data-ttu-id="3661c-107">Имя приложения, для которого задается виртуальный каталог.</span><span class="sxs-lookup"><span data-stu-id="3661c-107">The name of application for which to set the virtual directory.</span></span>  
  
 <span data-ttu-id="3661c-108">*VirtualDirectory*</span><span class="sxs-lookup"><span data-stu-id="3661c-108">*VirtualDirectory*</span></span>  
 <span data-ttu-id="3661c-109">Имя виртуального каталога.</span><span class="sxs-lookup"><span data-stu-id="3661c-109">The name of the virtual directory.</span></span>  
  
 <span data-ttu-id="3661c-110">*lcid*</span><span class="sxs-lookup"><span data-stu-id="3661c-110">*lcid*</span></span>  
 <span data-ttu-id="3661c-111">Идентификатор локали для виртуального каталога.</span><span class="sxs-lookup"><span data-stu-id="3661c-111">The locale id for the virtual directory.</span></span>  
  
 <span data-ttu-id="3661c-112">*Ошибка*</span><span class="sxs-lookup"><span data-stu-id="3661c-112">*Error*</span></span>  
 <span data-ttu-id="3661c-113">[out] Описания возникших ошибок.</span><span class="sxs-lookup"><span data-stu-id="3661c-113">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="3661c-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="3661c-114">*HRESULT*</span></span>  
 <span data-ttu-id="3661c-115">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="3661c-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3661c-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3661c-116">Return Value</span></span>  
 <span data-ttu-id="3661c-117">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="3661c-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="3661c-118">Значение 0 означает, что вызов метода завершился успешно; код ошибки означает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="3661c-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3661c-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="3661c-119">Remarks</span></span>  
 <span data-ttu-id="3661c-120">Для приложения можно задать только одно имя виртуального каталога для всех зарезервированных URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="3661c-120">An application can have only one virtual directory name for all URL reservations.</span></span>  
  
 <span data-ttu-id="3661c-121">Параметр VirtualDirectory должен соответствовать контексту именования для виртуальных каталогов.</span><span class="sxs-lookup"><span data-stu-id="3661c-121">VirtualDirectory must conform to naming conventions for virtual directories.</span></span> <span data-ttu-id="3661c-122">Параметр VirtualDirectory не должен быть пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="3661c-122">VirtualDirectory must not be empty string or blank.</span></span>  
  
 <span data-ttu-id="3661c-123">Обновляет значение элемента \Configuration\URLReservations\Application\VirtualDirectory.</span><span class="sxs-lookup"><span data-stu-id="3661c-123">Updates the value of the \Configuration\URLReservations\Application\VirtualDirectory element.</span></span> <span data-ttu-id="3661c-124">Выполняется успешно, даже еще не созданы зарезервированные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="3661c-124">Succeeds even if no URL reservations have been created yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3661c-125">Требования</span><span class="sxs-lookup"><span data-stu-id="3661c-125">Requirements</span></span>  
 <span data-ttu-id="3661c-126">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3661c-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3661c-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="3661c-127">See Also</span></span>  
 [<span data-ttu-id="3661c-128">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="3661c-128">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
