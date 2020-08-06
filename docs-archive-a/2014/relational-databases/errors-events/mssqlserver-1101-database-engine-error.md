---
title: MSSQLSERVER_1101 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1101 (Database Engine error)
ms.assetid: d63b67d5-59f5-4f77-904e-5ba67f2dd850
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 631b0ab1466815cbacfd71b4f9fd714fabd0f7b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667186"
---
# <a name="mssqlserver_1101"></a><span data-ttu-id="d6eca-102">MSSQLSERVER_1101</span><span class="sxs-lookup"><span data-stu-id="d6eca-102">MSSQLSERVER_1101</span></span>
    
## <a name="details"></a><span data-ttu-id="d6eca-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="d6eca-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6eca-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="d6eca-104">Product Name</span></span>|<span data-ttu-id="d6eca-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d6eca-105">SQL Server</span></span>|  
|<span data-ttu-id="d6eca-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="d6eca-106">Event ID</span></span>|<span data-ttu-id="d6eca-107">1101</span><span class="sxs-lookup"><span data-stu-id="d6eca-107">1101</span></span>|  
|<span data-ttu-id="d6eca-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="d6eca-108">Event Source</span></span>|<span data-ttu-id="d6eca-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d6eca-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d6eca-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="d6eca-110">Component</span></span>|<span data-ttu-id="d6eca-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d6eca-111">SQLEngine</span></span>|  
|<span data-ttu-id="d6eca-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="d6eca-112">Symbolic Name</span></span>|<span data-ttu-id="d6eca-113">NOALLOCPG</span><span class="sxs-lookup"><span data-stu-id="d6eca-113">NOALLOCPG</span></span>|  
|<span data-ttu-id="d6eca-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="d6eca-114">Message Text</span></span>|<span data-ttu-id="d6eca-115">Не удалось выделить новую страницу для базы данных "%.\*ls" вследствие нехватки места на диске в файловой группе "%.\*ls".</span><span class="sxs-lookup"><span data-stu-id="d6eca-115">Could not allocate a new page for database '%.\*ls' because of insufficient disk space in filegroup '%.\*ls'.</span></span> <span data-ttu-id="d6eca-116">Предоставьте необходимое место на диске, удалив объекты в файловой группе, добавив дополнительные файлы в файловую группу или указав параметр автоматического увеличения размера для существующих файлов в файловой группе.</span><span class="sxs-lookup"><span data-stu-id="d6eca-116">Create the necessary space by dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d6eca-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="d6eca-117">Explanation</span></span>  
 <span data-ttu-id="d6eca-118">Нет свободного места на диске в файловой группе.</span><span class="sxs-lookup"><span data-stu-id="d6eca-118">No disk space available in a filegroup.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d6eca-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="d6eca-119">User Action</span></span>  
 <span data-ttu-id="d6eca-120">Место в файловой группе можно освободить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d6eca-120">The following actions may make space available in the filegroup.</span></span>  
  
-   <span data-ttu-id="d6eca-121">Включить автоматическое расширение.</span><span class="sxs-lookup"><span data-stu-id="d6eca-121">Turn on AUTOGROW.</span></span>  
  
-   <span data-ttu-id="d6eca-122">Добавить файлы в файловую группу.</span><span class="sxs-lookup"><span data-stu-id="d6eca-122">Add more files to the file group.</span></span>  
  
-   <span data-ttu-id="d6eca-123">Освободить место на диске, удалив ненужные индексы или таблицы из файловой группы.</span><span class="sxs-lookup"><span data-stu-id="d6eca-123">Free up disk space by dropping unnecessary indexes or tables in the filegroup.</span></span>  
  
  
