---
title: Метод SetUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetUnattendedExecutionAccount method
ms.assetid: 1ba6be6f-b05c-4ea0-af98-cd0780290b70
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 73cf4c633c51de1e3e6b878c66d73ee710e98df6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737709"
---
# <a name="setunattendedexecutionaccount-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="ca2a0-102">Метод SetUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="ca2a0-102">SetUnattendedExecutionAccount Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="ca2a0-103">Задает учетную запись для автоматического выполнения отчетов.</span><span class="sxs-lookup"><span data-stu-id="ca2a0-103">Specifies the account used to execute reports unattended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca2a0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca2a0-104">Syntax</span></span>  
  
```vb  
Public Sub SetUnattendedExecutionAccount(UserName as String, _  
    Password as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetUnattendedExecutionAccount (string UserName,   
    string Password, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca2a0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ca2a0-105">Parameters</span></span>  
 <span data-ttu-id="ca2a0-106">*UserName*</span><span class="sxs-lookup"><span data-stu-id="ca2a0-106">*UserName*</span></span>  
 <span data-ttu-id="ca2a0-107">Учетная запись Windows для автоматического выполнения.</span><span class="sxs-lookup"><span data-stu-id="ca2a0-107">A Windows account to be used for unattended executions.</span></span>  
  
 <span data-ttu-id="ca2a0-108">*Пароль*</span><span class="sxs-lookup"><span data-stu-id="ca2a0-108">*Password*</span></span>  
 <span data-ttu-id="ca2a0-109">Пароль для указанной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="ca2a0-109">The password for the specified account.</span></span>  
  
 <span data-ttu-id="ca2a0-110">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="ca2a0-110">*HRESULT*</span></span>  
 <span data-ttu-id="ca2a0-111">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="ca2a0-111">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca2a0-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ca2a0-112">Return Value</span></span>  
 <span data-ttu-id="ca2a0-113">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="ca2a0-113">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="ca2a0-114">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="ca2a0-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="ca2a0-115">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="ca2a0-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca2a0-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="ca2a0-116">Remarks</span></span>  
 <span data-ttu-id="ca2a0-117">Метод SetUnattendedExecutionAccount не проверяет, удается ли серверу отчетов войти под именем указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="ca2a0-117">The SetUnattendedExecutionAccount method does not verify whether the report server can log in as the specified user.</span></span>  
  
 <span data-ttu-id="ca2a0-118">Запускать автоматическое выполнение в контексте службы Windows сервера отчетов с помощью метода SetUnattendedExecutionAccount нельзя.</span><span class="sxs-lookup"><span data-stu-id="ca2a0-118">It is not possible to use the SetUnattendedExecutionAccount method to run unattended executions in the context of the report server Windows service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca2a0-119">Требования</span><span class="sxs-lookup"><span data-stu-id="ca2a0-119">Requirements</span></span>  
 <span data-ttu-id="ca2a0-120">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca2a0-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca2a0-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="ca2a0-121">See Also</span></span>  
 [<span data-ttu-id="ca2a0-122">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="ca2a0-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
