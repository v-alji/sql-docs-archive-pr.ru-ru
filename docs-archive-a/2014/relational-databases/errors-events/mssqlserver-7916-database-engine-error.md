---
title: MSSQLSERVER_7916 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7916 (Database Engine error)
ms.assetid: 9bac3536-de14-4e98-84c2-bde9a59ba0d1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 21b31eedf61369d9c4d1cfdfd5f53eebd3f5341c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664931"
---
# <a name="mssqlserver_7916"></a><span data-ttu-id="bca38-102">MSSQLSERVER_7916</span><span class="sxs-lookup"><span data-stu-id="bca38-102">MSSQLSERVER_7916</span></span>
    
## <a name="details"></a><span data-ttu-id="bca38-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="bca38-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bca38-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="bca38-104">Product Name</span></span>|<span data-ttu-id="bca38-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bca38-105">SQL Server</span></span>|  
|<span data-ttu-id="bca38-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="bca38-106">Event ID</span></span>|<span data-ttu-id="bca38-107">7916</span><span class="sxs-lookup"><span data-stu-id="bca38-107">7916</span></span>|  
|<span data-ttu-id="bca38-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="bca38-108">Event Source</span></span>|<span data-ttu-id="bca38-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bca38-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bca38-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="bca38-110">Component</span></span>|<span data-ttu-id="bca38-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bca38-111">SQLEngine</span></span>|  
|<span data-ttu-id="bca38-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="bca38-112">Symbolic Name</span></span>|<span data-ttu-id="bca38-113">DBCC2_REPAIR_RECORD_DELETED</span><span class="sxs-lookup"><span data-stu-id="bca38-113">DBCC2_REPAIR_RECORD_DELETED</span></span>|  
|<span data-ttu-id="bca38-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="bca38-114">Message Text</span></span>|<span data-ttu-id="bca38-115">Исправление: удалена запись для объекта с идентификатором O_ID, идентификатором индекса I_ID, идентификатором секции PN_ID, идентификатором единицы распределения A_ID (тип TYPE) на странице P_ID, в области памяти S_ID.</span><span class="sxs-lookup"><span data-stu-id="bca38-115">Repair: Deleted record for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), on page P_ID, slot S_ID.</span></span> <span data-ttu-id="bca38-116">Индексы будут перестроены.</span><span class="sxs-lookup"><span data-stu-id="bca38-116">Indexes will be rebuilt.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bca38-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="bca38-117">Explanation</span></span>  
 <span data-ttu-id="bca38-118">Данное информационное сообщение отправлено функцией REPAIR и означает, что указанная запись была удалена со страницы.</span><span class="sxs-lookup"><span data-stu-id="bca38-118">This is an information messages from REPAIR that indicates the specified record was deleted from the page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bca38-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="bca38-119">User Action</span></span>  
 <span data-ttu-id="bca38-120">None</span><span class="sxs-lookup"><span data-stu-id="bca38-120">None</span></span>  
  
  
