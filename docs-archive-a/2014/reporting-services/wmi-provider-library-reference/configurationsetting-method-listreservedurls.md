---
title: Метод ListReservedURLs (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListReservedURLs method
ms.assetid: 32335af1-5eae-4420-a0ef-b1e8a3267166
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7639741adb0c756961c4c6b63a3bffb627c4a89c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658621"
---
# <a name="listreservedurls-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="11736-102">Метод ListReservedURLs (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="11736-102">ListReservedURLs Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="11736-103">Выводит список URL-адресов, зарезервированных для всех приложений на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="11736-103">Lists URLs reserved for all applications on the report server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11736-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11736-104">Syntax</span></span>  
  
```vb  
Public Sub ListReservedUrls(ByRef Application() as String, ByRef UrlString() as String, _  
    ByRef Account() as String, ByRef AccountSID() as String, _  
    ByRef length() as Int32, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ListReservedUrls(out string[] Application, out string[] UrlString,  
        out string[] Account, out string[] AccountSID,  
        out int[] Length, out int[] HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11736-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="11736-105">Parameters</span></span>  
 <span data-ttu-id="11736-106">*Application[]*</span><span class="sxs-lookup"><span data-stu-id="11736-106">*Application[]*</span></span>  
 <span data-ttu-id="11736-107">[out] Приложения, которые имеют резервирование URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="11736-107">[out] The applications that have URL reservations.</span></span>  
  
 <span data-ttu-id="11736-108">*UrlString[]*</span><span class="sxs-lookup"><span data-stu-id="11736-108">*UrlString[]*</span></span>  
 <span data-ttu-id="11736-109">[out] Зарезервированные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="11736-109">[out] The URLs that are reserved.</span></span>  
  
 <span data-ttu-id="11736-110">*Account[]*</span><span class="sxs-lookup"><span data-stu-id="11736-110">*Account[]*</span></span>  
 <span data-ttu-id="11736-111">[out] Имена учетной записи, связанные с учетной записью для резервирования URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="11736-111">[out] The account names associated with the account for the URL reservations.</span></span>  
  
 <span data-ttu-id="11736-112">*AccountSID[]*</span><span class="sxs-lookup"><span data-stu-id="11736-112">*AccountSID[]*</span></span>  
 <span data-ttu-id="11736-113">[out] Идентификаторы безопасности, связанные с учетной записью для резервирования URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="11736-113">[out] The account SIDs associated with the account for the URL reservations.</span></span>  
  
 <span data-ttu-id="11736-114">*Длина*</span><span class="sxs-lookup"><span data-stu-id="11736-114">*Length*</span></span>  
 <span data-ttu-id="11736-115">[out] Длина массивов, возвращаемых методом.</span><span class="sxs-lookup"><span data-stu-id="11736-115">[out] The length of the arrays returned by the method.</span></span>  
  
 <span data-ttu-id="11736-116">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="11736-116">*HRESULT*</span></span>  
 <span data-ttu-id="11736-117">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="11736-117">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11736-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="11736-118">Return Value</span></span>  
 <span data-ttu-id="11736-119">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="11736-119">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="11736-120">Значение 0 означает, что вызов метода завершился успешно; код ошибки означает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="11736-120">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11736-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="11736-121">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11736-122">Требования</span><span class="sxs-lookup"><span data-stu-id="11736-122">Requirements</span></span>  
 <span data-ttu-id="11736-123">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11736-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11736-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="11736-124">See Also</span></span>  
 [<span data-ttu-id="11736-125">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="11736-125">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
