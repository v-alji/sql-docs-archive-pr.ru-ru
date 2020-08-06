---
title: MSSQLSERVER_17204 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17204 (Database Engine error)
ms.assetid: 40db66f9-dd5e-478c-891e-a06d363a2552
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c63f0b3d2aff8b909e3a7fc841c9038cf95a475e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658792"
---
# <a name="mssqlserver_17204"></a><span data-ttu-id="e0d9f-102">MSSQLSERVER_17204</span><span class="sxs-lookup"><span data-stu-id="e0d9f-102">MSSQLSERVER_17204</span></span>
    
## <a name="details"></a><span data-ttu-id="e0d9f-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="e0d9f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e0d9f-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="e0d9f-104">Product Name</span></span>|<span data-ttu-id="e0d9f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e0d9f-105">SQL Server</span></span>|  
|<span data-ttu-id="e0d9f-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="e0d9f-106">Event ID</span></span>|<span data-ttu-id="e0d9f-107">17204</span><span class="sxs-lookup"><span data-stu-id="e0d9f-107">17204</span></span>|  
|<span data-ttu-id="e0d9f-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="e0d9f-108">Event Source</span></span>|<span data-ttu-id="e0d9f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e0d9f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e0d9f-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="e0d9f-110">Component</span></span>|<span data-ttu-id="e0d9f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e0d9f-111">SQLEngine</span></span>|  
|<span data-ttu-id="e0d9f-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="e0d9f-112">Symbolic Name</span></span>|<span data-ttu-id="e0d9f-113">DBLKIO_DEVOPENFAILED</span><span class="sxs-lookup"><span data-stu-id="e0d9f-113">DBLKIO_DEVOPENFAILED</span></span>|  
|<span data-ttu-id="e0d9f-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="e0d9f-114">Message Text</span></span>|<span data-ttu-id="e0d9f-115">%ls: не удалось открыть файл %ls для номера файла %d.</span><span class="sxs-lookup"><span data-stu-id="e0d9f-115">%ls: Could not open file %ls for file number %d.</span></span>  <span data-ttu-id="e0d9f-116">Ошибка операционной системы: %ls.</span><span class="sxs-lookup"><span data-stu-id="e0d9f-116">OS error: %ls.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e0d9f-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="e0d9f-117">Explanation</span></span>  
 <span data-ttu-id="e0d9f-118">Программе SQL Server не удалось открыть указанный файл из-за указанной ошибки.</span><span class="sxs-lookup"><span data-stu-id="e0d9f-118">SQL Server was unable to open the specified file due to the specified error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e0d9f-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="e0d9f-119">User Action</span></span>  
 <span data-ttu-id="e0d9f-120">Определите причину, исправьте ошибку операционной системы, затем еще раз попытайтесь выполнить операцию.</span><span class="sxs-lookup"><span data-stu-id="e0d9f-120">Diagnose and correct the operating system, then retry the operation.</span></span>  
  
  
