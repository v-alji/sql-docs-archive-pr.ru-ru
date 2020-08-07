---
title: MSSQLSERVER_2508 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2508 (Database Engine error)
ms.assetid: c37d40e5-c665-4d66-a727-5cb845634fcc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 11dd1c72c8cae868b7ebcb02e72ef0db81aeafe2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731634"
---
# <a name="mssqlserver_2508"></a><span data-ttu-id="5cfbd-102">MSSQLSERVER_2508</span><span class="sxs-lookup"><span data-stu-id="5cfbd-102">MSSQLSERVER_2508</span></span>
    
## <a name="details"></a><span data-ttu-id="5cfbd-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="5cfbd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5cfbd-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="5cfbd-104">Product Name</span></span>|<span data-ttu-id="5cfbd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5cfbd-105">SQL Server</span></span>|  
|<span data-ttu-id="5cfbd-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="5cfbd-106">Event ID</span></span>|<span data-ttu-id="5cfbd-107">2508</span><span class="sxs-lookup"><span data-stu-id="5cfbd-107">2508</span></span>|  
|<span data-ttu-id="5cfbd-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="5cfbd-108">Event Source</span></span>|<span data-ttu-id="5cfbd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5cfbd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5cfbd-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="5cfbd-110">Component</span></span>|<span data-ttu-id="5cfbd-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5cfbd-111">SQLEngine</span></span>|  
|<span data-ttu-id="5cfbd-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="5cfbd-112">Symbolic Name</span></span>|<span data-ttu-id="5cfbd-113">DBCC_OUT_OF_DATE_PAGE_OR_ROW_COUNT</span><span class="sxs-lookup"><span data-stu-id="5cfbd-113">DBCC_OUT_OF_DATE_PAGE_OR_ROW_COUNT</span></span>|  
|<span data-ttu-id="5cfbd-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="5cfbd-114">Message Text</span></span>|<span data-ttu-id="5cfbd-115">Подсчет %.\*ls для объекта "%.\*ls", идентификатора индекса %d, идентификатора секции %I64d, идентификатора единицы размещения %I64d (тип %.\*ls) неверен.</span><span class="sxs-lookup"><span data-stu-id="5cfbd-115">The %.\*ls count for object "%.\*ls", index ID %d, partition ID %I64d, alloc unit ID %I64d (type %.\*ls) is incorrect.</span></span> <span data-ttu-id="5cfbd-116">Запустите команду DBCC UPDATEUSAGE.</span><span class="sxs-lookup"><span data-stu-id="5cfbd-116">Run DBCC UPDATEUSAGE.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5cfbd-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="5cfbd-117">Explanation</span></span>  
 <span data-ttu-id="5cfbd-118">В версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], предшествующих версии [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], значения количества строк таблиц и индексов, а также количества страниц могут стать неверными.</span><span class="sxs-lookup"><span data-stu-id="5cfbd-118">In versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], the values for the table and index row counts and page counts can become incorrect.</span></span> <span data-ttu-id="5cfbd-119">Базы данных, которые были созданы с помощью версий, предшествующих [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], могут содержать неверные подсчеты.</span><span class="sxs-lookup"><span data-stu-id="5cfbd-119">Databases that were created on versions prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] may contain incorrect counts.</span></span> <span data-ttu-id="5cfbd-120">Команда DBCC CHECKDB была улучшена, чтобы обнаруживать эти ошибки и возвращать предупреждающие сообщения.</span><span class="sxs-lookup"><span data-stu-id="5cfbd-120">DBCC CHECKDB has been enhanced to detect these errors and returns this warning message when the error encountered.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5cfbd-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="5cfbd-121">User Action</span></span>  
 <span data-ttu-id="5cfbd-122">Запустите команду DBCC UPDATEUSAGE для указанного объекта или индекса, или для базы данных, в которой содержится объект, чтобы исправить недопустимые подсчеты.</span><span class="sxs-lookup"><span data-stu-id="5cfbd-122">Run DBCC UPDATEUSAGE against the specified object or index, or against the database in which the object is contained to correct the invalid counts.</span></span>  
  
  
