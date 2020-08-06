---
title: Метод ReencryptSecureInformation (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- ReencryptSecureInformation (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- ReencryptSecureInformation method
ms.assetid: 8a487497-c207-45b2-8c92-87c58cc68716
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1a0c657b69d624df8895ae4d5a6d12277b011b24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666419"
---
# <a name="reencryptsecureinformation-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="3963d-102">Метод ReencryptSecureInformation (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="3963d-102">ReencryptSecureInformation Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="3963d-103">Создает новый ключ шифрования и повторно зашифровывает с его помощью всю защищенную информацию в каталоге.</span><span class="sxs-lookup"><span data-stu-id="3963d-103">Generates a new encryption key and re-encrypts all secure information in the catalog using this new key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3963d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3963d-104">Syntax</span></span>  
  
```vb  
Public Sub ReencryptSecureInformation(ByRef HRESULT as Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void ReencryptSecureInformation (out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3963d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3963d-105">Parameters</span></span>  
 <span data-ttu-id="3963d-106">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="3963d-106">*HRESULT*</span></span>  
 <span data-ttu-id="3963d-107">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="3963d-107">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="3963d-108">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="3963d-108">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="3963d-109">[out] Массив строк, содержащий дополнительные ошибки, возвращенные в результате вызова.</span><span class="sxs-lookup"><span data-stu-id="3963d-109">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3963d-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3963d-110">Return Value</span></span>  
 <span data-ttu-id="3963d-111">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="3963d-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="3963d-112">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="3963d-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="3963d-113">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="3963d-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3963d-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="3963d-114">Remarks</span></span>  
 <span data-ttu-id="3963d-115">Метод ReencryptSecureInformation позволяет администратору заменить существующий ключ шифрования новым ключом.</span><span class="sxs-lookup"><span data-stu-id="3963d-115">The ReencryptSecureInformation method allows the administrator to replace the existing encryption key with a new key.</span></span>  
  
 <span data-ttu-id="3963d-116">При вызове этого метода сервер отчетов создает новый ключ шифрования и проходит по всему зашифрованному содержимому для его повторного шифрования с использованием нового ключа.</span><span class="sxs-lookup"><span data-stu-id="3963d-116">When this method is invoked, the report server generates a new encryption key and iterates through all encrypted content to re-encrypt it with the new encryption key.</span></span>  
  
 <span data-ttu-id="3963d-117">В модулях доставки защищенные сведения могут храниться в структуре параметров доставки.</span><span class="sxs-lookup"><span data-stu-id="3963d-117">Delivery extensions can store secured information in their delivery settings structures.</span></span> <span data-ttu-id="3963d-118">При вызове метода ReencryptSecureInformation сервер отчетов загружает каждую подписку и соответствующий модуль доставки и повторно зашифровывает сведения, которые хранятся в связанных параметрах.</span><span class="sxs-lookup"><span data-stu-id="3963d-118">When ReencryptSecureInformation is called, the report server loads each subscription and the corresponding delivery extension to re-encrypt information stored in the associated settings.</span></span>  
  
 <span data-ttu-id="3963d-119">Если этот метод запускается на компьютерах масштабного развертывания, то каждый компьютер потребует повторной инициализации.</span><span class="sxs-lookup"><span data-stu-id="3963d-119">If this method is run on a computer in a scale-out deployment, each computer in the scale-out deployment will need to be initialized again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3963d-120">Требования</span><span class="sxs-lookup"><span data-stu-id="3963d-120">Requirements</span></span>  
 <span data-ttu-id="3963d-121">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3963d-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3963d-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="3963d-122">See Also</span></span>  
 [<span data-ttu-id="3963d-123">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="3963d-123">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
