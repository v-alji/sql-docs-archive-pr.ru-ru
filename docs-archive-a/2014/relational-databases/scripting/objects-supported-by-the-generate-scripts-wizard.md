---
title: Объекты, поддерживаемые мастером создания скриптов
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 071eb2cb-f073-41ca-9f4d-11d3b8803495
author: rothja
ms.author: jroth
ms.openlocfilehash: 5ddc1da0d2f87fc12dfbe034a683802f54b7d34f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667680"
---
# <a name="objects-supported-by-the-generate-scripts-wizard"></a><span data-ttu-id="2b139-102">Объекты, поддерживаемые мастером создания скриптов</span><span class="sxs-lookup"><span data-stu-id="2b139-102">Objects Supported by the Generate Scripts Wizard</span></span>
  <span data-ttu-id="2b139-103">Мастер создания и публикации скриптов поддерживает подмножество объектов, поддерживаемое компонентом [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b139-103">The Generate and Publish Scripts wizard supports a subset of the objects supported by the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
## <a name="supported-objects"></a><span data-ttu-id="2b139-104">Поддерживаемые объекты</span><span class="sxs-lookup"><span data-stu-id="2b139-104">Supported Objects</span></span>  
 <span data-ttu-id="2b139-105">В следующей таблице перечислены объекты, которые можно публиковать при поддержке мастера формирования и публикации скриптов.</span><span class="sxs-lookup"><span data-stu-id="2b139-105">The following table lists the objects that can be published supported by the Generate and Publish Scripts Wizard.</span></span>  
  
||||||  
|-|-|-|-|-|  
|<span data-ttu-id="2b139-106">Роль приложения</span><span class="sxs-lookup"><span data-stu-id="2b139-106">Application role</span></span>|<span data-ttu-id="2b139-107">роль базы данных;</span><span class="sxs-lookup"><span data-stu-id="2b139-107">Database role</span></span>|<span data-ttu-id="2b139-108">схема</span><span class="sxs-lookup"><span data-stu-id="2b139-108">Schema</span></span>|<span data-ttu-id="2b139-109">Определяемое пользователем статистическое выражение</span><span class="sxs-lookup"><span data-stu-id="2b139-109">User-defined aggregate</span></span>|<span data-ttu-id="2b139-110">Представление<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2b139-110">View<sup>1</sup></span></span>|  
|<span data-ttu-id="2b139-111">Сборка</span><span class="sxs-lookup"><span data-stu-id="2b139-111">Assembly</span></span>|<span data-ttu-id="2b139-112">Ограничение DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2b139-112">DEFAULT constraint</span></span>|<span data-ttu-id="2b139-113">Хранимая процедура<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2b139-113">Stored procedure<sup>1</sup></span></span>|<span data-ttu-id="2b139-114">Определяемый пользователем тип данных</span><span class="sxs-lookup"><span data-stu-id="2b139-114">User-defined data type</span></span>|<span data-ttu-id="2b139-115">Коллекция схем XML</span><span class="sxs-lookup"><span data-stu-id="2b139-115">XML schema collection</span></span>|  
|<span data-ttu-id="2b139-116">Ограничение CHECK</span><span class="sxs-lookup"><span data-stu-id="2b139-116">CHECK constraint</span></span>|<span data-ttu-id="2b139-117">Полнотекстовый каталог</span><span class="sxs-lookup"><span data-stu-id="2b139-117">Full-text catalog</span></span>|<span data-ttu-id="2b139-118">Синоним</span><span class="sxs-lookup"><span data-stu-id="2b139-118">Synonym</span></span>|<span data-ttu-id="2b139-119">Определяемая пользователем функция</span><span class="sxs-lookup"><span data-stu-id="2b139-119">User-defined function</span></span>||  
|<span data-ttu-id="2b139-120">CLR (среда CLR), хранимая процедура<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2b139-120">CLR (common language runtime) stored procedure<sup>1</sup></span></span>|<span data-ttu-id="2b139-121">Индекс</span><span class="sxs-lookup"><span data-stu-id="2b139-121">Index</span></span>|<span data-ttu-id="2b139-122">Таблица</span><span class="sxs-lookup"><span data-stu-id="2b139-122">Table</span></span>|<span data-ttu-id="2b139-123">Определяемая пользователем таблица</span><span class="sxs-lookup"><span data-stu-id="2b139-123">User-defined table</span></span>||  
|<span data-ttu-id="2b139-124">Определяемая пользователем функция CLR</span><span class="sxs-lookup"><span data-stu-id="2b139-124">CLR user-defined function</span></span>|<span data-ttu-id="2b139-125">Правило</span><span class="sxs-lookup"><span data-stu-id="2b139-125">Rule</span></span>|<span data-ttu-id="2b139-126">Пользователь<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2b139-126">User<sup>2</sup></span></span>|<span data-ttu-id="2b139-127">Определяемый пользователем тип</span><span class="sxs-lookup"><span data-stu-id="2b139-127">User-defined type</span></span>||  
  
 <span data-ttu-id="2b139-128"><sup>1</sup> Опубликовано без шифрования.</span><span class="sxs-lookup"><span data-stu-id="2b139-128"><sup>1</sup> Published without encryption.</span></span>  
  
 <span data-ttu-id="2b139-129"><sup>2</sup> все несистемные пользователи, которые существуют в базе данных, публикуются как роли.</span><span class="sxs-lookup"><span data-stu-id="2b139-129"><sup>2</sup> Any non-system users that exist in the database are published as Roles.</span></span>  
  
  
