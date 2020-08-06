---
title: MSSQLSERVER_5237 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5237 (Database Engine error)
ms.assetid: 9ff28935-d1eb-47ee-99b3-1a65cb948ce7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 224317e290ce15aaed979129733b6273b3b663df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667105"
---
# <a name="mssqlserver_5237"></a><span data-ttu-id="75b03-102">MSSQLSERVER_5237</span><span class="sxs-lookup"><span data-stu-id="75b03-102">MSSQLSERVER_5237</span></span>
    
## <a name="details"></a><span data-ttu-id="75b03-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="75b03-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="75b03-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="75b03-104">Product Name</span></span>|<span data-ttu-id="75b03-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="75b03-105">SQL Server</span></span>|  
|<span data-ttu-id="75b03-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="75b03-106">Event ID</span></span>|<span data-ttu-id="75b03-107">5237</span><span class="sxs-lookup"><span data-stu-id="75b03-107">5237</span></span>|  
|<span data-ttu-id="75b03-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="75b03-108">Event Source</span></span>|<span data-ttu-id="75b03-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="75b03-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="75b03-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="75b03-110">Component</span></span>|<span data-ttu-id="75b03-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="75b03-111">SQLEngine</span></span>|  
|<span data-ttu-id="75b03-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="75b03-112">Symbolic Name</span></span>|<span data-ttu-id="75b03-113">DBCC4_INDEXED_VIEW_CHECK_QUERY_FAILED_NO_ERRORCODE</span><span class="sxs-lookup"><span data-stu-id="75b03-113">DBCC4_INDEXED_VIEW_CHECK_QUERY_FAILED_NO_ERRORCODE</span></span>|  
|<span data-ttu-id="75b03-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="75b03-114">Message Text</span></span>|<span data-ttu-id="75b03-115">Перекрестная проверка наборов строк с помощью команды DBCC для объекта NAME (идентификатор объекта O_ID) окончилась неудачей, так как произошла внутренняя ошибка запроса.</span><span class="sxs-lookup"><span data-stu-id="75b03-115">DBCC cross-rowset check failed for object 'NAME' (object ID O_ID) due to an internal query error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="75b03-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="75b03-116">Explanation</span></span>  
 <span data-ttu-id="75b03-117">Внутренняя ошибка привела к тому, что в команде DBCC не удалось выполнить запрос для проверки индексированных представлений.</span><span class="sxs-lookup"><span data-stu-id="75b03-117">An internal error resulted in DBCC not being able to execute the query to check indexed views.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="75b03-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="75b03-118">User Action</span></span>  
 <span data-ttu-id="75b03-119">Повторно выполните команду DBCC.</span><span class="sxs-lookup"><span data-stu-id="75b03-119">Rerun the DBCC command.</span></span>  
  
  
