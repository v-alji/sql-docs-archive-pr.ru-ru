---
title: MSSQLSERVER_945 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 945 (Database Engine error)
ms.assetid: ee501d13-0bd9-4627-896c-ed5b1bdb88b3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 51284cdcf48f1bf713a853f9c87457cb5291cc4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658752"
---
# <a name="mssqlserver_945"></a><span data-ttu-id="9adbb-102">MSSQLSERVER_945</span><span class="sxs-lookup"><span data-stu-id="9adbb-102">MSSQLSERVER_945</span></span>
    
## <a name="details"></a><span data-ttu-id="9adbb-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="9adbb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9adbb-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="9adbb-104">Product Name</span></span>|<span data-ttu-id="9adbb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9adbb-105">SQL Server</span></span>|  
|<span data-ttu-id="9adbb-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="9adbb-106">Event ID</span></span>|<span data-ttu-id="9adbb-107">945</span><span class="sxs-lookup"><span data-stu-id="9adbb-107">945</span></span>|  
|<span data-ttu-id="9adbb-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="9adbb-108">Event Source</span></span>|<span data-ttu-id="9adbb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9adbb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9adbb-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="9adbb-110">Component</span></span>|<span data-ttu-id="9adbb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9adbb-111">SQLEngine</span></span>|  
|<span data-ttu-id="9adbb-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="9adbb-112">Symbolic Name</span></span>|<span data-ttu-id="9adbb-113">DB_IS_SHUTDOWN</span><span class="sxs-lookup"><span data-stu-id="9adbb-113">DB_IS_SHUTDOWN</span></span>|  
|<span data-ttu-id="9adbb-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="9adbb-114">Message Text</span></span>|<span data-ttu-id="9adbb-115">Не удалось открыть базу данных «%.\*ls» вследствие недоступности файлов, нехватки памяти или места на диске.</span><span class="sxs-lookup"><span data-stu-id="9adbb-115">Database '%.\*ls' cannot be opened due to inaccessible files or insufficient memory or disk space.</span></span>  <span data-ttu-id="9adbb-116">Подробности см. в журнале ошибок SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9adbb-116">See the SQL Server error log for details.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9adbb-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="9adbb-117">Explanation</span></span>  
 <span data-ttu-id="9adbb-118">Не удалось обратиться к базе данных из-за отсутствия файлов или других ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9adbb-118">The database could not be accessed because files or other resources are missing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9adbb-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="9adbb-119">User Action</span></span>  
 <span data-ttu-id="9adbb-120">Проверьте, нет ли в журнале ошибок дополнительных сведений об ошибках памяти, места на диске или разрешений.</span><span class="sxs-lookup"><span data-stu-id="9adbb-120">Check the error log for additional information about memory, disk space, or permission failure.</span></span> <span data-ttu-id="9adbb-121">Проверьте местоположение MDF- и NDF-файлов этой базы данных и удостоверьтесь, что у учетной записи, используемой компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)], есть разрешения на доступ к этим файлам.</span><span class="sxs-lookup"><span data-stu-id="9adbb-121">Confirm the location of the .mdf and .ndf files for the affected database and confirm that the account used by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] has permission to access those files.</span></span> <span data-ttu-id="9adbb-122">После устранения неполадки перезапустите базу данных, установив параметр ONLINE в инструкции ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="9adbb-122">After correcting the problem, restart the database by using ALTER DATABASE to set it ONLINE.</span></span>  
  
  
