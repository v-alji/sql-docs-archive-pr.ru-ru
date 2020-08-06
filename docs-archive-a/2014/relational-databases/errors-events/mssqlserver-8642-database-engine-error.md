---
title: MSSQLSERVER_8642 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8642 (Database Engine error)
ms.assetid: fc498059-202f-4d0b-8599-4e784b47c186
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e30296fa569599b91ca74edc7535d330119e1680
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666075"
---
# <a name="mssqlserver_8642"></a><span data-ttu-id="1aed3-102">MSSQLSERVER_8642</span><span class="sxs-lookup"><span data-stu-id="1aed3-102">MSSQLSERVER_8642</span></span>
    
## <a name="details"></a><span data-ttu-id="1aed3-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="1aed3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1aed3-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="1aed3-104">Product Name</span></span>|<span data-ttu-id="1aed3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1aed3-105">SQL Server</span></span>|  
|<span data-ttu-id="1aed3-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="1aed3-106">Event ID</span></span>|<span data-ttu-id="1aed3-107">8642</span><span class="sxs-lookup"><span data-stu-id="1aed3-107">8642</span></span>|  
|<span data-ttu-id="1aed3-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="1aed3-108">Event Source</span></span>|<span data-ttu-id="1aed3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1aed3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1aed3-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="1aed3-110">Component</span></span>|<span data-ttu-id="1aed3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1aed3-111">SQLEngine</span></span>|  
|<span data-ttu-id="1aed3-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="1aed3-112">Symbolic Name</span></span>|<span data-ttu-id="1aed3-113">EXCHNGSTART_ERR</span><span class="sxs-lookup"><span data-stu-id="1aed3-113">EXCHNGSTART_ERR</span></span>|  
|<span data-ttu-id="1aed3-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="1aed3-114">Message Text</span></span>|<span data-ttu-id="1aed3-115">Обработчику запросов не удалось запустить ресурсы потоков для параллельного исполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="1aed3-115">The query processor could not start the necessary thread resources for parallel query execution.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1aed3-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="1aed3-116">Explanation</span></span>  
 <span data-ttu-id="1aed3-117">Не хватает ресурсов потоков на сервере.</span><span class="sxs-lookup"><span data-stu-id="1aed3-117">Thread resources are low in the server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1aed3-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="1aed3-118">User Action</span></span>  
 <span data-ttu-id="1aed3-119">Снизьте загрузку на сервер и повторите запрос.</span><span class="sxs-lookup"><span data-stu-id="1aed3-119">Reduce load on the server, and run the query again.</span></span>  
  
  
