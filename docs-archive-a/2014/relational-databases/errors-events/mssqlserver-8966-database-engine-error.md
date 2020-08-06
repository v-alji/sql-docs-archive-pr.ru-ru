---
title: MSSQLSERVER_8966 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8966 (Database Engine error)
ms.assetid: 6b1150fd-9dfd-4df9-8f08-8eca237667db
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8d3a12d5d0732ba8694db3d4c7dcae1eac59d28b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669421"
---
# <a name="mssqlserver_8966"></a><span data-ttu-id="ef714-102">MSSQLSERVER_8966</span><span class="sxs-lookup"><span data-stu-id="ef714-102">MSSQLSERVER_8966</span></span>
    
## <a name="details"></a><span data-ttu-id="ef714-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="ef714-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ef714-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="ef714-104">Product Name</span></span>|<span data-ttu-id="ef714-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ef714-105">SQL Server</span></span>|  
|<span data-ttu-id="ef714-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ef714-106">Event ID</span></span>|<span data-ttu-id="ef714-107">8966</span><span class="sxs-lookup"><span data-stu-id="ef714-107">8966</span></span>|  
|<span data-ttu-id="ef714-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="ef714-108">Event Source</span></span>|<span data-ttu-id="ef714-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ef714-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ef714-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="ef714-110">Component</span></span>|<span data-ttu-id="ef714-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ef714-111">SQLEngine</span></span>|  
|<span data-ttu-id="ef714-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="ef714-112">Symbolic Name</span></span>|<span data-ttu-id="ef714-113">DBCC3_FAILED_TO_READ_AND_LATCH_PAGE</span><span class="sxs-lookup"><span data-stu-id="ef714-113">DBCC3_FAILED_TO_READ_AND_LATCH_PAGE</span></span>|  
|<span data-ttu-id="ef714-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="ef714-114">Message Text</span></span>|<span data-ttu-id="ef714-115">Невозможно прочитать страницу P_ID и заблокировать ее кратковременной блокировкой типа TYPE.</span><span class="sxs-lookup"><span data-stu-id="ef714-115">Unable to read and latch page P_ID with latch type TYPE.</span></span> <span data-ttu-id="ef714-116">Ошибка операции OPERATION.</span><span class="sxs-lookup"><span data-stu-id="ef714-116">OPERATION failed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ef714-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="ef714-117">Explanation</span></span>  
 <span data-ttu-id="ef714-118">Чтение страницы окончилось неудачей или нельзя было установить кратковременную блокировку на PFS- или GAM-странице.</span><span class="sxs-lookup"><span data-stu-id="ef714-118">The page read failed or a latch could not be taken on a PFS or GAM page.</span></span> <span data-ttu-id="ef714-119">В журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может быть добавлено сообщение об истечении времени ожидания кратковременной блокировки или другие сопутствующие сообщения.</span><span class="sxs-lookup"><span data-stu-id="ef714-119">There may be latch time-out or other accompanying messages in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ef714-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="ef714-120">User Action</span></span>  
 <span data-ttu-id="ef714-121">Ознакомьтесь с сопровождающими сообщениями в журнале регистрации ошибок SQL и устраните эти ошибки.</span><span class="sxs-lookup"><span data-stu-id="ef714-121">Review the SQL error log for accompanying messages and resolve these errors.</span></span>  
  
  
