---
title: MSSQLSERVER_1807 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1807 (Database Engine error)
ms.assetid: 13c1b240-098b-4d9e-89aa-21599548e074
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 261d352084e490fb7f9216e1a7e352542e85a6f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658793"
---
# <a name="mssqlserver_1807"></a><span data-ttu-id="ced47-102">MSSQLSERVER_1807</span><span class="sxs-lookup"><span data-stu-id="ced47-102">MSSQLSERVER_1807</span></span>
    
## <a name="details"></a><span data-ttu-id="ced47-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="ced47-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ced47-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="ced47-104">Product Name</span></span>|<span data-ttu-id="ced47-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ced47-105">SQL Server</span></span>|  
|<span data-ttu-id="ced47-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ced47-106">Event ID</span></span>|<span data-ttu-id="ced47-107">1807</span><span class="sxs-lookup"><span data-stu-id="ced47-107">1807</span></span>|  
|<span data-ttu-id="ced47-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="ced47-108">Event Source</span></span>|<span data-ttu-id="ced47-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ced47-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ced47-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="ced47-110">Component</span></span>|<span data-ttu-id="ced47-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ced47-111">SQLEngine</span></span>|  
|<span data-ttu-id="ced47-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="ced47-112">Symbolic Name</span></span>|<span data-ttu-id="ced47-113">CANNOT_EX_LOCK</span><span class="sxs-lookup"><span data-stu-id="ced47-113">CANNOT_EX_LOCK</span></span>|  
|<span data-ttu-id="ced47-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="ced47-114">Message Text</span></span>|<span data-ttu-id="ced47-115">Не удалось получить монопольную блокировку для базы данных «%.\*ls».</span><span class="sxs-lookup"><span data-stu-id="ced47-115">Could not obtain exclusive lock on database '%.\*ls'.</span></span> <span data-ttu-id="ced47-116">Повторите операцию позже.</span><span class="sxs-lookup"><span data-stu-id="ced47-116">Retry the operation later.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ced47-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="ced47-117">Explanation</span></span>  
 <span data-ttu-id="ced47-118">Операция, которой необходима монопольная блокировка базы данных, не смогла получить ее.</span><span class="sxs-lookup"><span data-stu-id="ced47-118">An operation that required exclusive access to the database was unable to obtain it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ced47-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="ced47-119">User Action</span></span>  
 <span data-ttu-id="ced47-120">Отключите все соединения с базой данных и повторите запрос.</span><span class="sxs-lookup"><span data-stu-id="ced47-120">Disconnect all the connections to that database or try the query again later.</span></span>  
  
  
