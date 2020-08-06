---
title: MSSQLSERVER_21862 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21862 (Database Engine error)
ms.assetid: a1d393dd-453b-4d45-9aa5-7d371213e32b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b945350d9c7a862d4274f464afbd7fc5472f732c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731654"
---
# <a name="mssqlserver_21862"></a><span data-ttu-id="27360-102">MSSQLSERVER_21862</span><span class="sxs-lookup"><span data-stu-id="27360-102">MSSQLSERVER_21862</span></span>
    
## <a name="details"></a><span data-ttu-id="27360-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="27360-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="27360-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="27360-104">Product Name</span></span>|<span data-ttu-id="27360-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="27360-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="27360-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="27360-106">Event ID</span></span>|<span data-ttu-id="27360-107">21862</span><span class="sxs-lookup"><span data-stu-id="27360-107">21862</span></span>|  
|<span data-ttu-id="27360-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="27360-108">Event Source</span></span>|<span data-ttu-id="27360-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="27360-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="27360-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="27360-110">Component</span></span>|<span data-ttu-id="27360-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="27360-111">SQLEngine</span></span>|  
|<span data-ttu-id="27360-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="27360-112">Symbolic Name</span></span>|<span data-ttu-id="27360-113">SQLErrorNum21862</span><span class="sxs-lookup"><span data-stu-id="27360-113">SQLErrorNum21862</span></span>|  
|<span data-ttu-id="27360-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="27360-114">Message Text</span></span>|<span data-ttu-id="27360-115">Столбцы FILESTREAM нельзя опубликовать в публикации с использованием метода синхронизации «database snapshot» или «database snapshot character».</span><span class="sxs-lookup"><span data-stu-id="27360-115">FILESTREAM columns cannot be published in a publication by using a synchronization method of either 'database snapshot' or 'database snapshot character'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="27360-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="27360-116">Explanation</span></span>  
 <span data-ttu-id="27360-117">Данные FILESTREAM недоступны через моментальный снимок базы данных, поэтому агент моментальных снимков не сможет прочитать данные FILESTREAM, если в качестве метода синхронизации публикации указан параметр *database snapshot* или *database_snapshot_character*.</span><span class="sxs-lookup"><span data-stu-id="27360-117">Because FILESTREAM data cannot be accessed through a database snapshot, the snapshot agent will be unable to read FILESTREAM data when either the *database snapshot* or *database_snapshot_character* parameter is specified for the synchronization method of the publication.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="27360-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="27360-118">User Action</span></span>  
 <span data-ttu-id="27360-119">Измените метод синхронизации публикации на любой другой, кроме *database snapshot* или *database_snapshot_character*, либо просто исключите столбец FILESTREAM из публикации.</span><span class="sxs-lookup"><span data-stu-id="27360-119">Change the publication synchronization method to something other than *database snapshot* or *database_snapshot_character*, or just exclude the FILESTREAM column from the publication.</span></span>  
  
  
