---
title: LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: fa082dca-bf88-46e7-b61e-7ac8835a3493
author: stevestein
ms.author: sstein
ms.openlocfilehash: e71f7b443a1999a5edbb17dc11ee4d578834faf4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665345"
---
# <a name="localdb_error_unknown_language_id"></a><span data-ttu-id="0a44b-102">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span><span class="sxs-lookup"><span data-stu-id="0a44b-102">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span></span>
    
## <a name="details"></a><span data-ttu-id="0a44b-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="0a44b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a44b-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="0a44b-104">Product Name</span></span>|<span data-ttu-id="0a44b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0a44b-105">SQL Server</span></span>|  
|<span data-ttu-id="0a44b-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="0a44b-106">Event ID</span></span>|<span data-ttu-id="0a44b-107">270</span><span class="sxs-lookup"><span data-stu-id="0a44b-107">270</span></span>|  
|<span data-ttu-id="0a44b-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="0a44b-108">Event Source</span></span>|<span data-ttu-id="0a44b-109">Среда выполнения локальной базы данных SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="0a44b-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="0a44b-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="0a44b-110">Component</span></span>|<span data-ttu-id="0a44b-111">API среды выполнения локальной базы данных</span><span class="sxs-lookup"><span data-stu-id="0a44b-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="0a44b-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="0a44b-112">Message Text</span></span>|<span data-ttu-id="0a44b-113">Ошибка при получении локализованного сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="0a44b-113">Error getting the localized error message.</span></span> <span data-ttu-id="0a44b-114">Язык, указанный параметром «Идентификатор языка», неизвестен.</span><span class="sxs-lookup"><span data-stu-id="0a44b-114">The language specified by 'Language ID' parameter is unknown.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0a44b-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="0a44b-115">Explanation</span></span>  
 <span data-ttu-id="0a44b-116">Запрошенный язык для сообщения об ошибке среды выполнения локальной базы данных неизвестен или не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0a44b-116">The requested language for the Local Database Runtime error message is unknown or not supported.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0a44b-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="0a44b-117">User Action</span></span>  
 <span data-ttu-id="0a44b-118">Попробуйте запросить один из поддерживаемых языков для сообщений об ошибках среды выполнения локальной базы данных или же язык по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0a44b-118">Try requesting one of the supported languages for Local Database Runtime error messages, or a default language.</span></span>  
  
  
