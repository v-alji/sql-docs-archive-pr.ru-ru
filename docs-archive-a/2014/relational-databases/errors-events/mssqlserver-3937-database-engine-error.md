---
title: MSSQLSERVER_3937 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3937 (Database Engine error)
ms.assetid: 312d5bbe-c8de-42db-af4b-4ccb448ce6ef
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cac466e6eb50ad4b7a8848a1159963cb0fd35e22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731626"
---
# <a name="mssqlserver_3937"></a><span data-ttu-id="7088b-102">MSSQLSERVER_3937</span><span class="sxs-lookup"><span data-stu-id="7088b-102">MSSQLSERVER_3937</span></span>
    
## <a name="details"></a><span data-ttu-id="7088b-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="7088b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7088b-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="7088b-104">Product Name</span></span>|<span data-ttu-id="7088b-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7088b-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7088b-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="7088b-106">Event ID</span></span>|<span data-ttu-id="7088b-107">3937</span><span class="sxs-lookup"><span data-stu-id="7088b-107">3937</span></span>|  
|<span data-ttu-id="7088b-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="7088b-108">Event Source</span></span>|<span data-ttu-id="7088b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7088b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7088b-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="7088b-110">Component</span></span>|<span data-ttu-id="7088b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7088b-111">SQLEngine</span></span>|  
|<span data-ttu-id="7088b-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="7088b-112">Symbolic Name</span></span>|<span data-ttu-id="7088b-113">XACT_FILESTREAM_ROLLBACK_ERROR</span><span class="sxs-lookup"><span data-stu-id="7088b-113">XACT_FILESTREAM_ROLLBACK_ERROR</span></span>|  
|<span data-ttu-id="7088b-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="7088b-114">Message Text</span></span>|<span data-ttu-id="7088b-115">При уведомлении драйвера фильтра FILESTREAM об откате транзакции произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="7088b-115">An error occurred while trying to notify the FILESTREAM filter driver that a transaction was rolled back.</span></span> <span data-ttu-id="7088b-116">Код ошибки: 0x%0x.</span><span class="sxs-lookup"><span data-stu-id="7088b-116">Error code: 0x%0x.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7088b-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="7088b-117">Explanation</span></span>  
 <span data-ttu-id="7088b-118">Драйвер RsFx возвратил ошибку при выдаче уведомления об откате транзакции.</span><span class="sxs-lookup"><span data-stu-id="7088b-118">An error was returned by the RsFx driver when issuing a rollback notification for a transaction.</span></span> <span data-ttu-id="7088b-119">Возможно, это вызвано недостатком ресурсов.</span><span class="sxs-lookup"><span data-stu-id="7088b-119">This is probably caused by a resource shortage.</span></span> <span data-ttu-id="7088b-120">Это может привести к небольшой утечке памяти в драйвере фильтра RsFx, но память будет освобождена, когда завершится процесс sqlservr.exe, создавший транзакцию.</span><span class="sxs-lookup"><span data-stu-id="7088b-120">This can cause a small memory leak in the RsFx filter driver, but this will be freed when the sqlservr.exe process that created the transaction exits.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7088b-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="7088b-121">User Action</span></span>  
  
