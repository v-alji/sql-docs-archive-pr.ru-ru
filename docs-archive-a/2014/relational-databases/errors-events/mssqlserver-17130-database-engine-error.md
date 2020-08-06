---
title: MSSQLSERVER_17130 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17130 (Database Engine error)
ms.assetid: 7ce6afca-221d-402f-89df-da7e74a339a8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b63be325273e4df33d837ec1548ed46701323977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731677"
---
# <a name="mssqlserver_17130"></a><span data-ttu-id="6908b-102">MSSQLSERVER_17130</span><span class="sxs-lookup"><span data-stu-id="6908b-102">MSSQLSERVER_17130</span></span>
    
## <a name="details"></a><span data-ttu-id="6908b-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="6908b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6908b-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="6908b-104">Product Name</span></span>|<span data-ttu-id="6908b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6908b-105">SQL Server</span></span>|  
|<span data-ttu-id="6908b-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6908b-106">Event ID</span></span>|<span data-ttu-id="6908b-107">17130</span><span class="sxs-lookup"><span data-stu-id="6908b-107">17130</span></span>|  
|<span data-ttu-id="6908b-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="6908b-108">Event Source</span></span>|<span data-ttu-id="6908b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6908b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6908b-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="6908b-110">Component</span></span>|<span data-ttu-id="6908b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6908b-111">SQLEngine</span></span>|  
|<span data-ttu-id="6908b-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="6908b-112">Symbolic Name</span></span>|<span data-ttu-id="6908b-113">INIT_NOLOCKSPACE</span><span class="sxs-lookup"><span data-stu-id="6908b-113">INIT_NOLOCKSPACE</span></span>|  
|<span data-ttu-id="6908b-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="6908b-114">Message Text</span></span>|<span data-ttu-id="6908b-115">Недостаточно памяти для заданного количества блокировок.</span><span class="sxs-lookup"><span data-stu-id="6908b-115">Not enough memory for the configured number of locks.</span></span> <span data-ttu-id="6908b-116">Выполняется попытка запуска с хэш-таблицей блокировок меньшего размера, что может негативно отразиться на производительности.</span><span class="sxs-lookup"><span data-stu-id="6908b-116">Attempting to start with a smaller lock hash table, which may impact performance.</span></span> <span data-ttu-id="6908b-117">Обратитесь к администратору базы данных с просьбой о выделении большего объема памяти для данного экземпляра компонента Database Engine.</span><span class="sxs-lookup"><span data-stu-id="6908b-117">Contact the database administrator to configure more memory for this instance of the Database Engine.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6908b-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="6908b-118">Explanation</span></span>  
 <span data-ttu-id="6908b-119">Недостаточно памяти для хэш-таблицы диспетчера блокировок нужного размера.</span><span class="sxs-lookup"><span data-stu-id="6908b-119">Not enough memory for the desired lock manager hash table size.</span></span>  <span data-ttu-id="6908b-120">Будет произведена попытка запуска с уменьшенным размером хэш-таблицы блокировок.</span><span class="sxs-lookup"><span data-stu-id="6908b-120">An attempt will be made to allocate a smaller hash table.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6908b-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="6908b-121">User Action</span></span>  
 <span data-ttu-id="6908b-122">Проверьте параметры конфигурации памяти сервера (min/max server memory) и нагрузку на память.</span><span class="sxs-lookup"><span data-stu-id="6908b-122">Check server memory configuration parameters (min/max server memory), check for memory pressures.</span></span> <span data-ttu-id="6908b-123">Предоставьте больше памяти для работы SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6908b-123">Provide SQL Server more memory.</span></span>  
  
  
