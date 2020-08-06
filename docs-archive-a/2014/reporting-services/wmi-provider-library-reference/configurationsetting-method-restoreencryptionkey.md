---
title: Метод RestoreEncryptionKey (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- RestoreEncryptionKey (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- RestoreEncryptionKey method
ms.assetid: 37e949f5-15af-4858-848a-f482ee94fcd9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e67478541bab615a6d441ae273ed3385a8654203
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737745"
---
# <a name="restoreencryptionkey-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="34520-102">Метод RestoreEncryptionKey (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="34520-102">RestoreEncryptionKey Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="34520-103">Повторно применяет заданный ключ шифрования к базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="34520-103">Reapplies the specified encryption key to the report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34520-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34520-104">Syntax</span></span>  
  
```vb  
Public Sub RestoreEncryptionKey(ByRef KeyFile() As Integer, _  
    ByRef Length As Int32, ByVal Password As String, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void RestoreEncryptionKey(out Byte[] KeyFile, out Int32 Length,   
            string Password, out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34520-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="34520-105">Parameters</span></span>  
 <span data-ttu-id="34520-106">*KeyFile[]*</span><span class="sxs-lookup"><span data-stu-id="34520-106">*KeyFile[]*</span></span>  
 <span data-ttu-id="34520-107">[out] Массив, содержащий зашифрованный ключ шифрования.</span><span class="sxs-lookup"><span data-stu-id="34520-107">[out] An array containing the encrypted encryption key.</span></span>  
  
 <span data-ttu-id="34520-108">*Длина*</span><span class="sxs-lookup"><span data-stu-id="34520-108">*Length*</span></span>  
 <span data-ttu-id="34520-109">[out] Длина массива, возвращаемого методом.</span><span class="sxs-lookup"><span data-stu-id="34520-109">[out] The length of the array returned by the method.</span></span>  
  
 <span data-ttu-id="34520-110">*Пароль*</span><span class="sxs-lookup"><span data-stu-id="34520-110">*Password*</span></span>  
 <span data-ttu-id="34520-111">Строка, которая используется для шифрования ключа шифрования.</span><span class="sxs-lookup"><span data-stu-id="34520-111">A string used to encrypt the encryption key.</span></span>  
  
 <span data-ttu-id="34520-112">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="34520-112">*HRESULT*</span></span>  
 <span data-ttu-id="34520-113">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="34520-113">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="34520-114">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="34520-114">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="34520-115">[out] Массив строк, содержащий дополнительные ошибки, возвращенные в результате вызова.</span><span class="sxs-lookup"><span data-stu-id="34520-115">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34520-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="34520-116">Return Value</span></span>  
 <span data-ttu-id="34520-117">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="34520-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="34520-118">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="34520-118">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="34520-119">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="34520-119">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34520-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="34520-120">Remarks</span></span>  
 <span data-ttu-id="34520-121">Если в базе данных сервера отчетов уже есть запись для сервера отчетов, то она удаляется.</span><span class="sxs-lookup"><span data-stu-id="34520-121">If an entry already exists for the report server in the report server database, it is deleted.</span></span> <span data-ttu-id="34520-122">Затем создается новая запись с использованием ключа шифрования и открытого ключа сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="34520-122">The new entry is then created using the specified encryption key and the report server's public key.</span></span>  
  
 <span data-ttu-id="34520-123">Этот метод наиболее эффективен при вызове после метода [DeleteEncryptionKey](configurationsetting-method-deleteencryptionkey.md) , который очищает список ключей шифрования.</span><span class="sxs-lookup"><span data-stu-id="34520-123">The method is most effective when called after the [DeleteEncryptionKey](configurationsetting-method-deleteencryptionkey.md) method, which clears the list of encryption keys.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34520-124">Требования</span><span class="sxs-lookup"><span data-stu-id="34520-124">Requirements</span></span>  
 <span data-ttu-id="34520-125">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34520-125">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34520-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="34520-126">See Also</span></span>  
 [<span data-ttu-id="34520-127">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="34520-127">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
