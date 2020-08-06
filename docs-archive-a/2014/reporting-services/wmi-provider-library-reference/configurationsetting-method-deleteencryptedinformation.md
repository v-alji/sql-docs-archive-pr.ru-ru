---
title: Метод DeleteEncryptedInformation (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DeleteEncryptedInformation (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DeleteEncryptedInformation method
ms.assetid: c14ed187-bdd9-4304-88e3-72072f03c21b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d00dc3e90816cd04c84f124cdc3d25a9ac122bba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658641"
---
# <a name="deleteencryptedinformation-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="08b33-102">Метод DeleteEncryptedInformation (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="08b33-102">DeleteEncryptedInformation Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="08b33-103">Удаляет зашифрованные данные из базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="08b33-103">Deletes the encrypted information from the report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08b33-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08b33-104">Syntax</span></span>  
  
```vb  
Public Sub DeleteEncryptedInformation(ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void DeleteEncryptedInformation(out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08b33-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="08b33-105">Parameters</span></span>  
 <span data-ttu-id="08b33-106">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="08b33-106">*HRESULT*</span></span>  
 <span data-ttu-id="08b33-107">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="08b33-107">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="08b33-108">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="08b33-108">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="08b33-109">[out] Массив строк, содержащий дополнительные ошибки, возвращенные в результате вызова.</span><span class="sxs-lookup"><span data-stu-id="08b33-109">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08b33-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="08b33-110">Return Value</span></span>  
 <span data-ttu-id="08b33-111">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="08b33-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="08b33-112">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="08b33-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="08b33-113">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="08b33-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08b33-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="08b33-114">Remarks</span></span>  
 <span data-ttu-id="08b33-115">При вызове этого метода удаляются следующие данные.</span><span class="sxs-lookup"><span data-stu-id="08b33-115">When this method is invoked, the following data is deleted:</span></span>  
  
-   <span data-ttu-id="08b33-116">Зашифрованные сведения об источнике данных, в том числе имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="08b33-116">Data source information that is encrypted, including user name and password.</span></span>  
  
-   <span data-ttu-id="08b33-117">Данные о подписке, зашифрованные с помощью интерфейсов модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="08b33-117">Subscription data that is encrypted using the delivery extension interfaces.</span></span>  
  
-   <span data-ttu-id="08b33-118">Все сведения о таблице ключей в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="08b33-118">All the information from the keys table in the report server database.</span></span>  
  
 <span data-ttu-id="08b33-119">После вызова этого метода пользователь должен инициализировать каждый компьютер, использующий базу данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="08b33-119">After this method is invoked, the user must initialize each computer that uses the report server database.</span></span>  
  
 <span data-ttu-id="08b33-120">Вызов метода DeleteEncryptedInformation не затрагивает файл конфигурации сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="08b33-120">Calling the DeleteEncryptedInformation method does not affect the report server configuration file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08b33-121">Требования</span><span class="sxs-lookup"><span data-stu-id="08b33-121">Requirements</span></span>  
 <span data-ttu-id="08b33-122">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08b33-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08b33-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="08b33-123">See Also</span></span>  
 [<span data-ttu-id="08b33-124">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="08b33-124">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
