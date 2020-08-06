---
title: Метод InitializeReportServer (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- InitializeReportServer (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- InitializeReportServer method
ms.assetid: 0304acc2-1fd7-437b-94d9-1c1073dd3ca4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c6a8e44a98320ca2c9add6a1b6eef9362eef7731
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658630"
---
# <a name="initializereportserver-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="605a6-102">Метод InitializeReportServer (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="605a6-102">InitializeReportServer Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="605a6-103">Инициализирует указанный экземпляр службы отчетов.</span><span class="sxs-lookup"><span data-stu-id="605a6-103">Initializes the specified report service instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="605a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="605a6-104">Syntax</span></span>  
  
```vb  
Public Sub InitializeReportServer(ByVal InstallationID As String, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void InitializeReportServer(string InstallationID,   
    out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="605a6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="605a6-105">Parameters</span></span>  
 <span data-ttu-id="605a6-106">*InstallationID*</span><span class="sxs-lookup"><span data-stu-id="605a6-106">*InstallationID*</span></span>  
 <span data-ttu-id="605a6-107">Строка, используемая для шифрования ключа шифрования перед его возвращением.</span><span class="sxs-lookup"><span data-stu-id="605a6-107">A string used to encrypt the encryption key before it is returned.</span></span>  
  
 <span data-ttu-id="605a6-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="605a6-108">*HRESULT*</span></span>  
 <span data-ttu-id="605a6-109">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="605a6-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="605a6-110">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="605a6-110">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="605a6-111">[out] Массив строк, содержащий дополнительные ошибки, возвращенные в результате вызова.</span><span class="sxs-lookup"><span data-stu-id="605a6-111">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="605a6-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="605a6-112">Return Value</span></span>  
 <span data-ttu-id="605a6-113">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="605a6-113">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="605a6-114">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="605a6-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="605a6-115">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="605a6-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="605a6-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="605a6-116">Remarks</span></span>  
 <span data-ttu-id="605a6-117">При вызове этого метода ключ шифрования, который обращается к защищенным сведениям в базе данных сервера отчетов, зашифровывается с помощью открытого ключа сервера отчетов, определенного параметром *InstallationID*.</span><span class="sxs-lookup"><span data-stu-id="605a6-117">When this method is called, the encryption key that accesses the report server database secure information is encrypted using the public key of the report server identified by *InstallationID*.</span></span>  
  
 <span data-ttu-id="605a6-118">Указанный открытый ключ сервера отчетов должен быть предварительно записан в базу данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="605a6-118">The specified report server's public key must have previously been written into the report server database.</span></span>  
  
 <span data-ttu-id="605a6-119">Метод *InitializeReportServer* должен вызываться для сервера отчетов, который уже имеет доступ к защищенным сведениям, и поэтому может расшифровать ключ шифрования.</span><span class="sxs-lookup"><span data-stu-id="605a6-119">The *InitializeReportServer* method must be called against a report server that already has access to the secure information so that it can decrypt the encryption key.</span></span> <span data-ttu-id="605a6-120">Полученный зашифрованный ключ шифрования сохраняется в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="605a6-120">The resulting encrypted encryption key is then stored in the report server database.</span></span>  
  
 <span data-ttu-id="605a6-121">Если [для свойства "](configurationsetting-property-isinitialized.md) InitializeReportServer" сервера отчетов задано значение `true` при вызове метода, метод возвращает результат, не пытаясь зашифровать ключ шифрования.</span><span class="sxs-lookup"><span data-stu-id="605a6-121">If the report server's [IsInitialized](configurationsetting-property-isinitialized.md) property is set to `true` when the InitializeReportServer method is called, the method returns success without trying to encrypt the encryption key.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="605a6-122">Требования</span><span class="sxs-lookup"><span data-stu-id="605a6-122">Requirements</span></span>  
 <span data-ttu-id="605a6-123">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="605a6-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="605a6-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="605a6-124">See Also</span></span>  
 [<span data-ttu-id="605a6-125">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="605a6-125">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
