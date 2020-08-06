---
title: Метод CreateSSLCertificateBinding (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- CreateSSLCertificateBinding
ms.assetid: 407d50e4-0a55-43cb-8ddf-2d82714071b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8b9a5f9394d655f7b0592ea688a46f3ac2b9c153
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658643"
---
# <a name="createsslcertificatebinding-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="ff38c-102">Метод CreateSSLCertificateBinding (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="ff38c-102">CreateSSLCertificateBinding Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="ff38c-103">Создает привязку SSL-сертификата.</span><span class="sxs-lookup"><span data-stu-id="ff38c-103">Creates an SSL Certificate binding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff38c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff38c-104">Syntax</span></span>  
  
```vb  
Public Sub CreateSSLCertificateBinding(ByVal Application As String, _  
    ByVal CertificateHash As String, ByVal IPAddress As String, _  
    ByVal Port As Int32, ByVal lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void CreateSSLCertificateBinding(string application,   
    string certificateHash, string IPAddress, int Port,   
    int lcid, out string error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff38c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ff38c-105">Parameters</span></span>  
 <span data-ttu-id="ff38c-106">*Приложение*</span><span class="sxs-lookup"><span data-stu-id="ff38c-106">*Application*</span></span>  
 <span data-ttu-id="ff38c-107">Имя приложения, для которого следует создать привязку к сертификату.</span><span class="sxs-lookup"><span data-stu-id="ff38c-107">The name of application that the certificate binding should be created for.</span></span>  
  
 <span data-ttu-id="ff38c-108">*CertificateHash*</span><span class="sxs-lookup"><span data-stu-id="ff38c-108">*CertificateHash*</span></span>  
 <span data-ttu-id="ff38c-109">Хэш для сертификата.</span><span class="sxs-lookup"><span data-stu-id="ff38c-109">The hash for the certificate.</span></span>  
  
 <span data-ttu-id="ff38c-110">*IPAddress*</span><span class="sxs-lookup"><span data-stu-id="ff38c-110">*IPAddress*</span></span>  
 <span data-ttu-id="ff38c-111">IP-адрес для приложения.</span><span class="sxs-lookup"><span data-stu-id="ff38c-111">The IP address for the application.</span></span>  
  
 <span data-ttu-id="ff38c-112">*порт*.</span><span class="sxs-lookup"><span data-stu-id="ff38c-112">*Port*</span></span>  
 <span data-ttu-id="ff38c-113">Порт SSL, связанный с привязкой.</span><span class="sxs-lookup"><span data-stu-id="ff38c-113">The SSL port associated with the binding.</span></span>  
  
 <span data-ttu-id="ff38c-114">*Код языка*</span><span class="sxs-lookup"><span data-stu-id="ff38c-114">*Lcid*</span></span>  
 <span data-ttu-id="ff38c-115">Локаль, используемая для возвращаемых сообщений об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ff38c-115">The locale to use for the error messages returned.</span></span>  
  
 <span data-ttu-id="ff38c-116">*Error*</span><span class="sxs-lookup"><span data-stu-id="ff38c-116">*Error*</span></span>  
 <span data-ttu-id="ff38c-117">[out] Описание случившихся ошибок.</span><span class="sxs-lookup"><span data-stu-id="ff38c-117">[out] The description of the errors that occurred.</span></span>  
  
 <span data-ttu-id="ff38c-118">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="ff38c-118">*HRESULT*</span></span>  
 <span data-ttu-id="ff38c-119">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="ff38c-119">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff38c-120">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ff38c-120">Return Value</span></span>  
 <span data-ttu-id="ff38c-121">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="ff38c-121">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="ff38c-122">Значение 0 означает, что вызов метода завершился успешно; код ошибки означает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="ff38c-122">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff38c-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="ff38c-123">Remarks</span></span>  
 <span data-ttu-id="ff38c-124">Этот метод позволяет добавить привязку приложения в файл rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="ff38c-124">This method adds a binding to rsreportserver.config for the application.</span></span> <span data-ttu-id="ff38c-125">Если привязка еще не существует в файле HTTP.SYS, то она в нем создается.</span><span class="sxs-lookup"><span data-stu-id="ff38c-125">If a binding does not already exist in HTTP.SYS, it is created there.</span></span>  
  
 <span data-ttu-id="ff38c-126">Перед созданием привязки при вызове метода происходит проверка зарезервированных URL-адресов для того, чтобы указанное приложение могло определить допустимость привязки сертификата SSL.</span><span class="sxs-lookup"><span data-stu-id="ff38c-126">Before creating the binding, the method call examines the Url Reservations for the specified application to determine if the SSL Certificate Binding is valid.</span></span>  
  
 <span data-ttu-id="ff38c-127">Выполняется проверка следующих условий, результатом которой могут стать ошибки.</span><span class="sxs-lookup"><span data-stu-id="ff38c-127">The following conditions are validated and can result in errors:</span></span>  
  
1.  <span data-ttu-id="ff38c-128">Сертификат не существует.</span><span class="sxs-lookup"><span data-stu-id="ff38c-128">Certificate does not exist.</span></span>  
  
2.  <span data-ttu-id="ff38c-129">Указанный сертификат не соответствует значению, указанному для параметра IPAddress для этого компьютера.</span><span class="sxs-lookup"><span data-stu-id="ff38c-129">The IPAddress specified does not correspond to an IPAddress of this computer.</span></span>  
  
3.  <span data-ttu-id="ff38c-130">Указанное значение параметра IPAddress является адресом категории DHCP IPAddress (изменение которого происходит периодически). Рекомендуется вместо указанного адреса использовать IP-адрес с подстановочными символами (0.0.0.0).</span><span class="sxs-lookup"><span data-stu-id="ff38c-130">The IPAddress specified is a DHCP IPAddress (changes periodically) - use the Wildcard IP address instead (0.0.0.0).</span></span>  
  
4.  <span data-ttu-id="ff38c-131">Указанное значение параметра IPAddress не соответствует IP-адресу, указанному в списке зарезервированных URL-адресов и не является подстановочным символом или именем хоста для существующего зарезервированного URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="ff38c-131">IPAddress specified does not match the IP address of a URL reservations AND neither a wildcard or host name URL reservation exist.</span></span>  
  
5.  <span data-ttu-id="ff38c-132">Наличие зарезервированного URL-адреса, определяющего, что имя хоста не совпадает с именем, указанным в сертификате имени хоста.</span><span class="sxs-lookup"><span data-stu-id="ff38c-132">A URL reservation that specifies a host name exists, but the host name does not match the certificate host name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff38c-133">Требования</span><span class="sxs-lookup"><span data-stu-id="ff38c-133">Requirements</span></span>  
 <span data-ttu-id="ff38c-134">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff38c-134">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff38c-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="ff38c-135">See Also</span></span>  
 [<span data-ttu-id="ff38c-136">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="ff38c-136">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
