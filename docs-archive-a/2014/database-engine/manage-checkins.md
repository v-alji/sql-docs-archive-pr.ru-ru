---
title: Управление возвратами | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- checkins [SQL Server Management Studio]
- checking in files
- source controls [SQL Server Management Studio], checkins
ms.assetid: 293e60f3-15e3-4258-b73a-8baabe15c760
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a868aafff6d9bd389671544b5f1898e82707d933
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669041"
---
# <a name="manage-checkins"></a><span data-ttu-id="e1eb4-102">Управление возвратами</span><span class="sxs-lookup"><span data-stu-id="e1eb4-102">Manage Checkins</span></span>
  <span data-ttu-id="e1eb4-103">Чтобы сохранить изменения в файле, контролируемом системой управления версиями, необходимо вернуть файл.</span><span class="sxs-lookup"><span data-stu-id="e1eb4-103">To make changes to a source-controlled file available to other users, you must check in the file.</span></span> <span data-ttu-id="e1eb4-104">Когда файл возвращается, созданная версия файла копируется поставщику системы управления версиями и становится последней версией файла, как правило, доступной пользователям с соответствующими разрешениями.</span><span class="sxs-lookup"><span data-stu-id="e1eb4-104">When you check in a file, the version you have created is copied to the source control provider, becomes the latest version of the file, and is generally available to users who have the appropriate permissions.</span></span>  
  
 <span data-ttu-id="e1eb4-105">Используйте [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] для возврата файлов.</span><span class="sxs-lookup"><span data-stu-id="e1eb4-105">Use [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to check in files.</span></span> <span data-ttu-id="e1eb4-106">Если необходимо регулярно обновлять хранилище системы управления версиями, при этом сохраняя контроль над группой файлов, можно указать, что возвращаемые файлы остаются извлеченными.</span><span class="sxs-lookup"><span data-stu-id="e1eb4-106">When you need to update the source control store periodically, but also need to maintain control over a set of files, you can specify that files you check in remain checked out to you.</span></span>  
  
 <span data-ttu-id="e1eb4-107">В следующей таблице описаны подразделы, содержащиеся в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e1eb4-107">The following table describes the topics in this section.</span></span>  
  
|<span data-ttu-id="e1eb4-108">Раздел</span><span class="sxs-lookup"><span data-stu-id="e1eb4-108">Topic</span></span>|<span data-ttu-id="e1eb4-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e1eb4-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e1eb4-110">Возврат файлов</span><span class="sxs-lookup"><span data-stu-id="e1eb4-110">Check In Files</span></span>](../../2014/database-engine/check-in-files.md)|<span data-ttu-id="e1eb4-111">Инструкции по возврату измененного файла.</span><span class="sxs-lookup"><span data-stu-id="e1eb4-111">Provides instructions on how to check in a file you have modified.</span></span>|  
|[<span data-ttu-id="e1eb4-112">Просмотр списка измененных файлов</span><span class="sxs-lookup"><span data-stu-id="e1eb4-112">View a List of Modified Files</span></span>](../../2014/database-engine/view-a-list-of-modified-files.md)|<span data-ttu-id="e1eb4-113">Отображение списка измененных файлов, которые можно одновременно вернуть при завершении работы.</span><span class="sxs-lookup"><span data-stu-id="e1eb4-113">Explains how to display a list of modified files that you can check in together when you are finished working.</span></span>|  
|[<span data-ttu-id="e1eb4-114">Изменение возвращенных файлов</span><span class="sxs-lookup"><span data-stu-id="e1eb4-114">Edit Checked-In Files</span></span>](../../2014/database-engine/edit-checked-in-files.md)|<span data-ttu-id="e1eb4-115">Настройка среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] для возможности изменения неизвлеченных файлов.</span><span class="sxs-lookup"><span data-stu-id="e1eb4-115">Explains how to configure the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment so that you can modify files that are not checked out.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1eb4-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="e1eb4-116">See Also</span></span>  
 [<span data-ttu-id="e1eb4-117">Управление извлечениями</span><span class="sxs-lookup"><span data-stu-id="e1eb4-117">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
