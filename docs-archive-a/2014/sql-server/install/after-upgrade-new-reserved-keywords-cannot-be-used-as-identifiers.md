---
title: После обновления новые зарезервированные ключевые слова нельзя использовать в качестве идентификаторов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- keywords [SQL Server], after upgrade
- keywords [SQL Server], reserved
- keywords [SQL Server]
ms.assetid: cb242081-54f8-4273-a8ef-52f3751c25ef
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 36f7f8cadcba5e114feee4a3c42de6f40070ce72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659251"
---
# <a name="after-upgrade-new-reserved-keywords-cannot-be-used-as-identifiers"></a><span data-ttu-id="21d95-102">После обновления новые зарезервированные ключевые слова не могут быть использованы в качестве идентификаторов</span><span class="sxs-lookup"><span data-stu-id="21d95-102">After upgrade, new reserved keywords cannot be used as identifiers</span></span>
  <span data-ttu-id="21d95-103">Советник по переходу обнаружил использование слов, зарезервированных в качестве ключевых.</span><span class="sxs-lookup"><span data-stu-id="21d95-103">Upgrade Advisor detected the use of words that are reserved keywords.</span></span> <span data-ttu-id="21d95-104">Зарезервированное ключевое слово нельзя использовать в качестве идентификатора или имени объекта, если только имя не заключено в разделители.</span><span class="sxs-lookup"><span data-stu-id="21d95-104">A reserved keyword cannot be used as an identifier or object name unless the name is delimited.</span></span>  
  
## <a name="component"></a><span data-ttu-id="21d95-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="21d95-105">Component</span></span>  
 <span data-ttu-id="21d95-106">Компонент Database Engine</span><span class="sxs-lookup"><span data-stu-id="21d95-106">Database Engine</span></span>  
  
## <a name="description"></a><span data-ttu-id="21d95-107">Описание</span><span class="sxs-lookup"><span data-stu-id="21d95-107">Description</span></span>  
 <span data-ttu-id="21d95-108">Для уровня совместимости 90 и ниже следующие слова не являются зарезервированными и могут использоваться в качестве идентификаторов и имен объектов в скриптах [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21d95-108">At compatibility level 90 or lower, the following words are not reserved keywords and can be used as identifiers or object names in [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="21d95-109">Для уровня совместимости 100 эти слова являются зарезервированными ключевыми словами и не должны использоваться в качестве идентификаторов и имен объектов.</span><span class="sxs-lookup"><span data-stu-id="21d95-109">At compatibility level 100, these words are fully reserved keywords and should not be used as identifiers or object names.</span></span>  
  
-   <span data-ttu-id="21d95-110">EXTERNAL</span><span class="sxs-lookup"><span data-stu-id="21d95-110">EXTERNAL</span></span>  
  
-   <span data-ttu-id="21d95-111">MERGE</span><span class="sxs-lookup"><span data-stu-id="21d95-111">MERGE</span></span>  
  
-   <span data-ttu-id="21d95-112">PIVOT</span><span class="sxs-lookup"><span data-stu-id="21d95-112">PIVOT</span></span>  
  
-   <span data-ttu-id="21d95-113">REVERT</span><span class="sxs-lookup"><span data-stu-id="21d95-113">REVERT</span></span>  
  
-   <span data-ttu-id="21d95-114">STOPLIST</span><span class="sxs-lookup"><span data-stu-id="21d95-114">STOPLIST</span></span>  
  
-   <span data-ttu-id="21d95-115">TABLESAMPLE</span><span class="sxs-lookup"><span data-stu-id="21d95-115">TABLESAMPLE</span></span>  
  
-   <span data-ttu-id="21d95-116">UNPIVOT</span><span class="sxs-lookup"><span data-stu-id="21d95-116">UNPIVOT</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="21d95-117">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="21d95-117">Corrective Action</span></span>  
 <span data-ttu-id="21d95-118">Рекомендуется переименовать объект.</span><span class="sxs-lookup"><span data-stu-id="21d95-118">We recommend that you rename the object.</span></span> <span data-ttu-id="21d95-119">Если это не удается сделать до обновления, то попробуйте воспользоваться следующими методами для переименования объекта.</span><span class="sxs-lookup"><span data-stu-id="21d95-119">If that cannot be done before upgrading, use one of the following methods until the name can be changed:</span></span>  
  
-   <span data-ttu-id="21d95-120">Сохраните уровень совместимости 90 или ниже.</span><span class="sxs-lookup"><span data-stu-id="21d95-120">Retain the database compatibility level setting of 90 or lower.</span></span>  
  
-   <span data-ttu-id="21d95-121">Для ссылок на объект пользуйтесь идентификаторами с разделителями.</span><span class="sxs-lookup"><span data-stu-id="21d95-121">Refer to the object by using delimited identifiers.</span></span> <span data-ttu-id="21d95-122">Например, оператор `CREATE TABLE [MERGE] ([MERGE] int);` использует квадратные скобки для разделения имени объекта при слиянии.</span><span class="sxs-lookup"><span data-stu-id="21d95-122">For example, the statement `CREATE TABLE [MERGE] ([MERGE] int);` uses brackets to delimit the object name MERGE.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="21d95-123">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="21d95-123">External Resources</span></span>  
 [<span data-ttu-id="21d95-124">Зарезервированные ключевые слова (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="21d95-124">Reserved Keywords &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reserved-keywords-transact-sql)  
  
 [<span data-ttu-id="21d95-125">MERGE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="21d95-125">MERGE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/merge-transact-sql)  
  
 [<span data-ttu-id="21d95-126">Идентификаторы с разделителями (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="21d95-126">Delimited Identifiers (Database Engine)</span></span>](https://go.microsoft.com/fwlink/?LinkId=112509)  
  
 [<span data-ttu-id="21d95-127">Уровень совместимости инструкции ALTER DATABASE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="21d95-127">ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level)  
  
  
