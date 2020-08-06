---
title: Метод SetServiceAccountPassword (класс SqlService) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetServiceAccountPassword Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceAccountPassword method
ms.assetid: e577a1ac-985c-4799-bb38-9393efc3def2
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: e7a83a6d3686b2ec2df98ae79b4c9d3347f621ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729194"
---
# <a name="setserviceaccountpassword-method-sqlservice-class"></a><span data-ttu-id="97f04-102">Метод SetServiceAccountPassword (класс SqlService)</span><span class="sxs-lookup"><span data-stu-id="97f04-102">SetServiceAccountPassword Method (SqlService Class)</span></span>
  <span data-ttu-id="97f04-103">Изменяет пароль учетной записи, под именем которой выполняется указанная служба.</span><span class="sxs-lookup"><span data-stu-id="97f04-103">Modifies the password for the account that the referenced service runs under.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97f04-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97f04-104">Syntax</span></span>  
  
```  
  
object  
.SetServiceAccountPassword(  
AccountOldPassword , ServiceStartPassword  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="97f04-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="97f04-105">Parts</span></span>  
 <span data-ttu-id="97f04-106">*object*</span><span class="sxs-lookup"><span data-stu-id="97f04-106">*object*</span></span>  
 <span data-ttu-id="97f04-107">Объект [класса SqlService](sqlservice-class.md) , представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="97f04-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="97f04-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="97f04-108">Parameters</span></span>  
 <span data-ttu-id="97f04-109">*аккаунтолдпассворд*</span><span class="sxs-lookup"><span data-stu-id="97f04-109">*AccountOldPassword*</span></span>  
 <span data-ttu-id="97f04-110">Строковое значение, указывающее существующий пароль для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="97f04-110">A string value that specifies the existing password for the account.</span></span>  
  
 <span data-ttu-id="97f04-111">*сервицестартпассворд*</span><span class="sxs-lookup"><span data-stu-id="97f04-111">*ServiceStartPassword*</span></span>  
 <span data-ttu-id="97f04-112">Строковое значение, указывающее новый пароль для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="97f04-112">A string value that specifies the new password for the account.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="97f04-113">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="97f04-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="97f04-114">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="97f04-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97f04-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="97f04-115">Remarks</span></span>  
  
