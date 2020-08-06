---
title: MSSQLSERVER_4064 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4064 (Database Engine error)
ms.assetid: 32112b90-0a2f-4834-a027-756811732be7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 201098aadeb6bd091f0312532138f692ae8079b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667731"
---
# <a name="mssqlserver_4064"></a><span data-ttu-id="2650c-102">MSSQLSERVER_4064</span><span class="sxs-lookup"><span data-stu-id="2650c-102">MSSQLSERVER_4064</span></span>
    
## <a name="details"></a><span data-ttu-id="2650c-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="2650c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2650c-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="2650c-104">Product Name</span></span>|<span data-ttu-id="2650c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2650c-105">SQL Server</span></span>|  
|<span data-ttu-id="2650c-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="2650c-106">Event ID</span></span>|<span data-ttu-id="2650c-107">4064</span><span class="sxs-lookup"><span data-stu-id="2650c-107">4064</span></span>|  
|<span data-ttu-id="2650c-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="2650c-108">Event Source</span></span>|<span data-ttu-id="2650c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2650c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2650c-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="2650c-110">Component</span></span>|<span data-ttu-id="2650c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2650c-111">SQLEngine</span></span>|  
|<span data-ttu-id="2650c-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="2650c-112">Symbolic Name</span></span>|<span data-ttu-id="2650c-113">DB_UFAIL_FATAL</span><span class="sxs-lookup"><span data-stu-id="2650c-113">DB_UFAIL_FATAL</span></span>|  
|<span data-ttu-id="2650c-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="2650c-114">Message Text</span></span>|<span data-ttu-id="2650c-115">Невозможно открыть пользовательскую базу данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2650c-115">Cannot open user default database.</span></span> <span data-ttu-id="2650c-116">Ошибка входа.</span><span class="sxs-lookup"><span data-stu-id="2650c-116">Login failed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2650c-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="2650c-117">Explanation</span></span>  
 <span data-ttu-id="2650c-118">Имени входа SQL Server не удалось выполнить соединение из-за проблемы с базой данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2650c-118">The SQL Server login was unable to connect because of a problem with its default database.</span></span> <span data-ttu-id="2650c-119">Либо указана недопустимая база данных, либо у имени входа нет разрешения CONNECT для этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="2650c-119">Either the database itself is invalid or the login lacks CONNECT permission on the database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2650c-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="2650c-120">User Action</span></span>  
 <span data-ttu-id="2650c-121">При помощи инструкции ALTER LOGIN измените базу данных по умолчанию для этого имени входа.</span><span class="sxs-lookup"><span data-stu-id="2650c-121">Use ALTER LOGIN to change the login's default database.</span></span> <span data-ttu-id="2650c-122">Предоставьте имени входа разрешение CONNECT.</span><span class="sxs-lookup"><span data-stu-id="2650c-122">Grant CONNECT permission to the login.</span></span>  
  
  
