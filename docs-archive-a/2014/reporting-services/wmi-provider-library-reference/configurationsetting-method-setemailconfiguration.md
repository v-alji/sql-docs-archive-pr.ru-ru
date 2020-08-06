---
title: Метод SetEmailConfiguration (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetEmailConfiguration (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEmailConfiguration method
ms.assetid: b40a2224-2c90-4d32-892f-1fe73a0591ca
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 19068d7d7fff8c31c455ef76e8d2c2caa26b743f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737730"
---
# <a name="setemailconfiguration-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="e2141-102">Метод SetEmailConfiguration (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="e2141-102">SetEmailConfiguration Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="e2141-103">Настраивает модуль доставки электронной почты, используемый сервером отчетов для отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e2141-103">Configures the e-mail delivery extension used by the report server to send e-mail.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2141-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2141-104">Syntax</span></span>  
  
```vb  
Public Sub SetEmailConfiguration(ByVal SendUsingSMTPServer As Boolean, _  
    ByVal SMTPServer As String, ByVal SenderEmailAddress As String, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetEmailConfiguration (Boolean SendUsingSMTPServer,   
   string SMTPServer, string SenderEmailAddress,   
   out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2141-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2141-105">Parameters</span></span>  
 <span data-ttu-id="e2141-106">*SendUsingSMTPServer*</span><span class="sxs-lookup"><span data-stu-id="e2141-106">*SendUsingSMTPServer*</span></span>  
 <span data-ttu-id="e2141-107">Логическое значение. Показывает, должен ли сервер отправлять почту с помощью SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="e2141-107">A Boolean value indicating whether the server is to use the SMTP server to send email.</span></span> <span data-ttu-id="e2141-108">Этот может принимать только значение true.</span><span class="sxs-lookup"><span data-stu-id="e2141-108">This value can only be set to true.</span></span> <span data-ttu-id="e2141-109">Значение по умолчанию — false.</span><span class="sxs-lookup"><span data-stu-id="e2141-109">Default value is false.</span></span>  
  
 <span data-ttu-id="e2141-110">*SMTPServer*</span><span class="sxs-lookup"><span data-stu-id="e2141-110">*SMTPServer*</span></span>  
 <span data-ttu-id="e2141-111">Строка, которая содержит имя или IP-адрес SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="e2141-111">A string containing the name or IP address of an SMTP server.</span></span>  
  
 <span data-ttu-id="e2141-112">*SenderEmailAddress*</span><span class="sxs-lookup"><span data-stu-id="e2141-112">*SenderEmailAddress*</span></span>  
 <span data-ttu-id="e2141-113">Адрес электронной почты, используемый в поле «От:» в сообщениях, отправленных с сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="e2141-113">The e-mail address used in the 'From:' field for e-mails sent from the report server.</span></span>  
  
 <span data-ttu-id="e2141-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="e2141-114">*HRESULT*</span></span>  
 <span data-ttu-id="e2141-115">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="e2141-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2141-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e2141-116">Return Value</span></span>  
 <span data-ttu-id="e2141-117">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="e2141-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="e2141-118">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="e2141-118">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="e2141-119">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="e2141-119">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2141-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="e2141-120">Remarks</span></span>  
 <span data-ttu-id="e2141-121">Если параметр *SendUsingSMTPServer* имеет значение `true` , запись **SendUsing** в файле конфигурации сервера отчетов устанавливается в значение 1.</span><span class="sxs-lookup"><span data-stu-id="e2141-121">When the *SendUsingSMTPServer* parameter is set to `true`, the **SendUsing** entry in the report server configuration file is set to 1.</span></span> <span data-ttu-id="e2141-122">Если *SendUsingSMTPServer* имеет значение `false` , запись **SendUsing** не настраивается.</span><span class="sxs-lookup"><span data-stu-id="e2141-122">When *SendUsingSMTPServer* is set to `false`, the **SendUsing** entry is not configured.</span></span>  
  
 <span data-ttu-id="e2141-123">Этот метод не позволяет пользователям задать для записи **SendUsing** в файле конфигурации сервера отчетов какое-либо значение, кроме 1.</span><span class="sxs-lookup"><span data-stu-id="e2141-123">This method does not provide a way for users to set the **SendUsing** entry in the report server configuration file to a value other than 1.</span></span> <span data-ttu-id="e2141-124">Чтобы настроить на сервере отчетов почтовый протокол, отличный от SMTP, необходимо изменить файл конфигурации вручную.</span><span class="sxs-lookup"><span data-stu-id="e2141-124">To configure the report server for anything other than SMTP mail, you must edit the configuration file manually.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2141-125">Требования</span><span class="sxs-lookup"><span data-stu-id="e2141-125">Requirements</span></span>  
 <span data-ttu-id="e2141-126">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2141-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2141-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="e2141-127">See Also</span></span>  
 [<span data-ttu-id="e2141-128">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="e2141-128">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
