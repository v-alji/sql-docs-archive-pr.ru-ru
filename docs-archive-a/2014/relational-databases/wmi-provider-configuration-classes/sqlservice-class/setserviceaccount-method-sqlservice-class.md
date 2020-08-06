---
title: Метод SetServiceAccount (класс SqlService) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetServiceAccount Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceAccount method
ms.assetid: d5782892-e9d8-4d48-92af-b3afe9610f84
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6087a531802a7752ea794a44147c79fb7c3fa3ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729193"
---
# <a name="setserviceaccount-method-sqlservice-class"></a><span data-ttu-id="1bd4f-102">Метод SetServiceAccount (класс SqlService)</span><span class="sxs-lookup"><span data-stu-id="1bd4f-102">SetServiceAccount Method (SqlService Class)</span></span>
  <span data-ttu-id="1bd4f-103">Пытается изменить имя пользователя и пароль, с которыми выполняется экземпляр службы.</span><span class="sxs-lookup"><span data-stu-id="1bd4f-103">Attempts to change the user name and password that the service instance runs under.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bd4f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1bd4f-104">Syntax</span></span>  
  
```  
  
object  
.SetServiceAccount(  
ServiceStartName , ServiceStartPassword  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="1bd4f-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="1bd4f-105">Parts</span></span>  
 <span data-ttu-id="1bd4f-106">*object*</span><span class="sxs-lookup"><span data-stu-id="1bd4f-106">*object*</span></span>  
 <span data-ttu-id="1bd4f-107">Объект [класса SqlService](sqlservice-class.md) , представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="1bd4f-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="1bd4f-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="1bd4f-108">Parameters</span></span>  
 <span data-ttu-id="1bd4f-109">*сервицестартнаме*</span><span class="sxs-lookup"><span data-stu-id="1bd4f-109">*ServiceStartName*</span></span>  
 <span data-ttu-id="1bd4f-110">Строковое значение, указывающее имя учетной записи, под которым выполняется служба.</span><span class="sxs-lookup"><span data-stu-id="1bd4f-110">A string value that specifies the account name that the service runs under.</span></span> <span data-ttu-id="1bd4f-111">В зависимости от типа службы имя учетной записи может иметь формат ИмяДомена\ИмяПользователя.</span><span class="sxs-lookup"><span data-stu-id="1bd4f-111">Depending on the service type, the account name might be in the form of DomainName\Username.</span></span> <span data-ttu-id="1bd4f-112">При запуске процесс службы входит в систему, используя один из следующих двух форматов:</span><span class="sxs-lookup"><span data-stu-id="1bd4f-112">When it runs, the service process will be logged using one of two forms:</span></span>  
  
-   <span data-ttu-id="1bd4f-113">если учетная запись принадлежит встроенному домену, можно указать \ИмяПользователя;</span><span class="sxs-lookup"><span data-stu-id="1bd4f-113">If the account belongs to the built-in domain, \Username can be specified.</span></span>  
  
-   <span data-ttu-id="1bd4f-114">Если указано значение NULL, служба будет входить в систему как учетная запись **LocalSystem** .</span><span class="sxs-lookup"><span data-stu-id="1bd4f-114">If NULL is specified, the service will be logged on as the **LocalSystem** account.</span></span>  
  
 <span data-ttu-id="1bd4f-115">Для драйверов ядра или системного уровня значение *StartName* содержит имя объекта Driver, \Филесистем\рдр или \дривер\кснс, которое используется системой ввода-вывода для загрузки драйвера устройства.</span><span class="sxs-lookup"><span data-stu-id="1bd4f-115">For kernel or system-level drivers, *StartName* contains the driver object name, either \FileSystem\Rdr or \Driver\Xns, which the I/O system uses to load the device driver.</span></span> <span data-ttu-id="1bd4f-116">Если задано значение NULL, драйвер выполняется с именем объекта «значение по умолчанию», созданным системой ввода-вывода на основе имени службы, например DWDOM\Admin.</span><span class="sxs-lookup"><span data-stu-id="1bd4f-116">If NULL is specified, the driver runs with a default object name created by the I/O system based on the service name, for example, DWDOM\Admin.</span></span>  
  
 <span data-ttu-id="1bd4f-117">*сервицестартпассворд*</span><span class="sxs-lookup"><span data-stu-id="1bd4f-117">*ServiceStartPassword*</span></span>  
 <span data-ttu-id="1bd4f-118">Строковое значение, указывающее пароль для имени учетной записи в параметре *StartName* .</span><span class="sxs-lookup"><span data-stu-id="1bd4f-118">A string value that specifies the password for the account name in the *StartName* parameter.</span></span> <span data-ttu-id="1bd4f-119">Если пароль не меняется, указывается значение NULL.</span><span class="sxs-lookup"><span data-stu-id="1bd4f-119">Specify NULL if you are not changing the password.</span></span> <span data-ttu-id="1bd4f-120">Если служба не имеет пароля, указывается пустая строка.</span><span class="sxs-lookup"><span data-stu-id="1bd4f-120">Specify an empty string if the service has no password.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="1bd4f-121">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1bd4f-121">Property Value/Return Value</span></span>  
 <span data-ttu-id="1bd4f-122">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1bd4f-122">A `uint32` value, which is 0 if the service was successfully modified or 1 if the request is not supported.</span></span> <span data-ttu-id="1bd4f-123">Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="1bd4f-123">Any other number indicates an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bd4f-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="1bd4f-124">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bd4f-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="1bd4f-125">See Also</span></span>  
 <span data-ttu-id="1bd4f-126">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="1bd4f-126">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
