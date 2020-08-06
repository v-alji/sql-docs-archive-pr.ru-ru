---
title: Метод GetReportServerUrls (WMI MSReportServer_Instance) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- GetReportServerUrls method
ms.assetid: 4865e32c-0114-465a-be8c-be223a7bc09e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f36a5ba10c05276cffabc155e5289d675db8dae7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733522"
---
# <a name="getreportserverurls-method-wmi-msreportserver_instance"></a><span data-ttu-id="dfc5a-102">Метод GetReportServerUrls (WMI MSReportServer_Instance)</span><span class="sxs-lookup"><span data-stu-id="dfc5a-102">GetReportServerUrls Method (WMI MSReportServer_Instance)</span></span>
  <span data-ttu-id="dfc5a-103">Возвращает список URL-адресов, которые пользователи могут использовать для доступа к серверу отчетов и диспетчеру отчетов.</span><span class="sxs-lookup"><span data-stu-id="dfc5a-103">Returns a list of URLs users can use to access the report server and report manager.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfc5a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dfc5a-104">Syntax</span></span>  
  
```vb  
Public Sub GetReportServerUrls (ByRef ApplicationName() As String, ByRef URLs()_  
    As String, ByRef Length As Int32, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GetReportServerUrls(out string[] applicationName,   
    out string[] URLs, out int length, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfc5a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dfc5a-105">Parameters</span></span>  
 <span data-ttu-id="dfc5a-106">*ApplicationName[]*</span><span class="sxs-lookup"><span data-stu-id="dfc5a-106">*ApplicationName[]*</span></span>  
 <span data-ttu-id="dfc5a-107">Массив, который содержит установленные приложения.</span><span class="sxs-lookup"><span data-stu-id="dfc5a-107">An array that contains the applications that are installed.</span></span> <span data-ttu-id="dfc5a-108">Значения: либо `ReportServerWebService`, либо `ReportManager`.</span><span class="sxs-lookup"><span data-stu-id="dfc5a-108">Values are either `ReportServerWebService` or `ReportManager`.</span></span>  
  
 <span data-ttu-id="dfc5a-109">*URLs[]*</span><span class="sxs-lookup"><span data-stu-id="dfc5a-109">*URLs[]*</span></span>  
 <span data-ttu-id="dfc5a-110">Массив, который содержит успешно зарегистрированные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="dfc5a-110">An array that contains the successfully registered Urls.</span></span>  
  
 <span data-ttu-id="dfc5a-111">*Длина*</span><span class="sxs-lookup"><span data-stu-id="dfc5a-111">*Length*</span></span>  
 <span data-ttu-id="dfc5a-112">Целое значение, представляющее длину возвращенных массивов.</span><span class="sxs-lookup"><span data-stu-id="dfc5a-112">An integer value that contains the length of the arrays returned.</span></span>  
  
 <span data-ttu-id="dfc5a-113">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="dfc5a-113">*HRESULT*</span></span>  
 <span data-ttu-id="dfc5a-114">Значение, показывающее успешное завершение или код ошибки.</span><span class="sxs-lookup"><span data-stu-id="dfc5a-114">A value that indicates success or an error code.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="dfc5a-115">Возвращаемые значения</span><span class="sxs-lookup"><span data-stu-id="dfc5a-115">Return Values</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfc5a-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="dfc5a-116">Remarks</span></span>  
 <span data-ttu-id="dfc5a-117">Методы, доступные в управляющих объектах WMI, вызываются с помощью функции InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="dfc5a-117">Methods exposed by WMI management objects are called through the InvokeMethod function.</span></span> <span data-ttu-id="dfc5a-118">Дополнительные сведения см. в разделе «Выполнение методов в управляющих объектах» документации по инструментарию WMI платформы [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dfc5a-118">For more information, please see "Executing Methods on Management Objects" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework WMI documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfc5a-119">Требования</span><span class="sxs-lookup"><span data-stu-id="dfc5a-119">Requirements</span></span>  
 <span data-ttu-id="dfc5a-120">**Пространство имен:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfc5a-120">**Namespace:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc5a-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="dfc5a-121">See Also</span></span>  
 [<span data-ttu-id="dfc5a-122">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="dfc5a-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
