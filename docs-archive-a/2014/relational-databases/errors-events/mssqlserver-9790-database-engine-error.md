---
title: MSSQLSERVER_9790 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9790 (Database Engine error)
ms.assetid: 83fd379f-5deb-4f97-8cb4-282e3d3fed94
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6d6d065d4a0e841da3b5ecb84f902df17dcfd60c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658747"
---
# <a name="mssqlserver_9790"></a><span data-ttu-id="e6154-102">MSSQLSERVER_9790</span><span class="sxs-lookup"><span data-stu-id="e6154-102">MSSQLSERVER_9790</span></span>
    
## <a name="details"></a><span data-ttu-id="e6154-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="e6154-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e6154-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="e6154-104">Product Name</span></span>|<span data-ttu-id="e6154-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e6154-105">SQL Server</span></span>|  
|<span data-ttu-id="e6154-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e6154-106">Event ID</span></span>|<span data-ttu-id="e6154-107">9790</span><span class="sxs-lookup"><span data-stu-id="e6154-107">9790</span></span>|  
|<span data-ttu-id="e6154-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="e6154-108">Event Source</span></span>|<span data-ttu-id="e6154-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e6154-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e6154-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="e6154-110">Component</span></span>|<span data-ttu-id="e6154-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e6154-111">SQLEngine</span></span>|  
|<span data-ttu-id="e6154-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="e6154-112">Symbolic Name</span></span>|<span data-ttu-id="e6154-113">SB3_XMIT_ERROR_ENTRANCE_BROKER_SINGLE_USER</span><span class="sxs-lookup"><span data-stu-id="e6154-113">SB3_XMIT_ERROR_ENTRANCE_BROKER_SINGLE_USER</span></span>|  
|<span data-ttu-id="e6154-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="e6154-114">Message Text</span></span>|<span data-ttu-id="e6154-115">Не удалось найти маршрут для входящего сообщения.</span><span class="sxs-lookup"><span data-stu-id="e6154-115">Unable to route the incoming message.</span></span> <span data-ttu-id="e6154-116">Системная база данных MSDB, содержащая сведения о маршрутах, находится в режиме SINGLE USER.</span><span class="sxs-lookup"><span data-stu-id="e6154-116">The system database MSDB containing routing information is in SINGLE USER mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e6154-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="e6154-117">Explanation</span></span>  
 <span data-ttu-id="e6154-118">Произошла ошибка при попытке определения категории сообщения, полученного в автономном режиме, поскольку база данных MSDB находилась в однопользовательском режиме.</span><span class="sxs-lookup"><span data-stu-id="e6154-118">An error occurred while trying to classify a message received off the wire because the MSDB database was in Single User mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e6154-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="e6154-119">User Action</span></span>  
 <span data-ttu-id="e6154-120">С помощью команды ALTER DATABASE измените режим MSDB на MULTI USER.</span><span class="sxs-lookup"><span data-stu-id="e6154-120">Change MSDB to be in MULTI USER mode with the ALTER DATABASE command.</span></span>  
  
  
