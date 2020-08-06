---
title: MSSQLSERVER_611 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 611 (Database Engine error)
ms.assetid: ac6a213f-5c38-44ad-bc85-a62863786614
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f0caa1c218e8b80059c0c97aac652da7db870af3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668370"
---
# <a name="mssqlserver_611"></a><span data-ttu-id="d18b2-102">MSSQLSERVER_611</span><span class="sxs-lookup"><span data-stu-id="d18b2-102">MSSQLSERVER_611</span></span>
    
## <a name="details"></a><span data-ttu-id="d18b2-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="d18b2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d18b2-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="d18b2-104">Product Name</span></span>|<span data-ttu-id="d18b2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d18b2-105">SQL Server</span></span>|  
|<span data-ttu-id="d18b2-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="d18b2-106">Event ID</span></span>|<span data-ttu-id="d18b2-107">611</span><span class="sxs-lookup"><span data-stu-id="d18b2-107">611</span></span>|  
|<span data-ttu-id="d18b2-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="d18b2-108">Event Source</span></span>|<span data-ttu-id="d18b2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d18b2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d18b2-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="d18b2-110">Component</span></span>|<span data-ttu-id="d18b2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d18b2-111">SQLEngine</span></span>|  
|<span data-ttu-id="d18b2-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="d18b2-112">Symbolic Name</span></span>|<span data-ttu-id="d18b2-113">VAR_SIZE_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="d18b2-113">VAR_SIZE_TOO_BIG</span></span>|  
|<span data-ttu-id="d18b2-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="d18b2-114">Message Text</span></span>|<span data-ttu-id="d18b2-115">Не удается добавить или обновить строку, поскольку суммарный размер переменных столбцов с учетом дополнительной памяти превысил допустимый на %d байт.</span><span class="sxs-lookup"><span data-stu-id="d18b2-115">Cannot insert or update a row because total variable column size, including overhead, is %d bytes more than the limit.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d18b2-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="d18b2-116">Explanation</span></span>  
 <span data-ttu-id="d18b2-117">Максимальный размер переменного столбца превышает размер, определенный схемой.</span><span class="sxs-lookup"><span data-stu-id="d18b2-117">The maximum variable column size is more than that allowed by the schema.</span></span> <span data-ttu-id="d18b2-118">Ошибка 611 возвращается при превышении размера столбца переменной, когда разрешен формат хранения vardecimal, либо если его размер превышает максимально допустимый в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] для записи со сжатием данных.</span><span class="sxs-lookup"><span data-stu-id="d18b2-118">Error 611 is returned when the variable column is over the limit in the fixed case when vardecimal storage format is enabled, or when the variable column size is over the limit allowed in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] for a compressed data record.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d18b2-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="d18b2-119">User Action</span></span>  
 <span data-ttu-id="d18b2-120">Уменьшите размер записи.</span><span class="sxs-lookup"><span data-stu-id="d18b2-120">Reduce the size of the record.</span></span>  
  
  
