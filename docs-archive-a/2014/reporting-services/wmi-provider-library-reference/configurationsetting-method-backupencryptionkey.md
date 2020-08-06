---
title: Метод BackupEncryptionKey (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- BackupEncryptionKey Method (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- BackupEncryptionKey method
ms.assetid: da1d5dae-2517-448e-96fb-5379c93222ea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d625401324e2117ee1e9677d840854fa7b63c6e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737769"
---
# <a name="backupencryptionkey-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="9455d-102">Метод BackupEncryptionKey (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="9455d-102">BackupEncryptionKey Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="9455d-103">Создает резервную копию ключа шифрования для указанного экземпляра сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9455d-103">Backs up the encryption key for the specified report server instance.</span></span> <span data-ttu-id="9455d-104">Ключ шифрования хранится в зашифрованном виде под защитой пароля.</span><span class="sxs-lookup"><span data-stu-id="9455d-104">The encryption key is stored encrypted with a password.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9455d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9455d-105">Syntax</span></span>  
  
```vb  
Public Sub BackupEncryptionKey(Password as String, _  
    ByRef KeyFile() as Integer, ByRef Length as Int32, _  
    ByRef HRESULT as Int32, ByRef ExtendedErrors() as String)  
  
```  
  
```csharp  
public void BackupEncryptionKey(string Password, out Byte[] KeyFile,   
    out Int32 Length, out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9455d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9455d-106">Parameters</span></span>  
 <span data-ttu-id="9455d-107">*Пароль*</span><span class="sxs-lookup"><span data-stu-id="9455d-107">*Password*</span></span>  
 <span data-ttu-id="9455d-108">Строка, используемая для шифрования ключа шифрования перед его возвращением.</span><span class="sxs-lookup"><span data-stu-id="9455d-108">A string used to encrypt the encryption key before it is returned.</span></span>  
  
 <span data-ttu-id="9455d-109">*KeyFile[]*</span><span class="sxs-lookup"><span data-stu-id="9455d-109">*KeyFile[]*</span></span>  
 <span data-ttu-id="9455d-110">[out] Массив, содержащий зашифрованный ключ шифрования.</span><span class="sxs-lookup"><span data-stu-id="9455d-110">[out] An array containing the encrypted encryption key.</span></span>  
  
 <span data-ttu-id="9455d-111">*Длина*</span><span class="sxs-lookup"><span data-stu-id="9455d-111">*Length*</span></span>  
 <span data-ttu-id="9455d-112">[out] Длина массива, возвращаемого методом.</span><span class="sxs-lookup"><span data-stu-id="9455d-112">[out] The length of the array returned by the method.</span></span>  
  
 <span data-ttu-id="9455d-113">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="9455d-113">*HRESULT*</span></span>  
 <span data-ttu-id="9455d-114">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="9455d-114">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="9455d-115">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="9455d-115">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="9455d-116">[out] Массив строк, содержащий дополнительные ошибки, возвращенные в результате вызова.</span><span class="sxs-lookup"><span data-stu-id="9455d-116">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9455d-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9455d-117">Return Value</span></span>  
 <span data-ttu-id="9455d-118">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="9455d-118">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="9455d-119">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="9455d-119">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="9455d-120">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="9455d-120">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9455d-121">Требования</span><span class="sxs-lookup"><span data-stu-id="9455d-121">Requirements</span></span>  
 <span data-ttu-id="9455d-122">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9455d-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9455d-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="9455d-123">See Also</span></span>  
 [<span data-ttu-id="9455d-124">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="9455d-124">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
