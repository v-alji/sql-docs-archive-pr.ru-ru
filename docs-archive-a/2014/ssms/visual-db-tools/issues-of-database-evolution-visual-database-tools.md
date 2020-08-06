---
title: Проблемы развития базы данных (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- compatibility [SQL Server], multuser database changes
- database evolution [SQL Server]
ms.assetid: 1ed6ae10-d212-4ec2-8569-1b94ab1cba6d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 80daa694cd015a83657368902b07da254e6196ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749555"
---
# <a name="issues-of-database-evolution-visual-database-tools"></a><span data-ttu-id="34143-102">Проблемы развития базы данных (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="34143-102">Issues of Database Evolution (Visual Database Tools)</span></span>
  <span data-ttu-id="34143-103">При изменении структуры развернутой базы данных необходимо следить, чтобы изменения были совместимы с существующими данными и структурой базы данных.</span><span class="sxs-lookup"><span data-stu-id="34143-103">If you change the structure of a deployed database, you must take special care that your alteration is compatible with the existing data and database structure.</span></span> <span data-ttu-id="34143-104">Возможно, необходимо будет принять особые меры при выполнении следующих изменений:</span><span class="sxs-lookup"><span data-stu-id="34143-104">You might need to take special steps when you make the following modifications:</span></span>  
  
-   <span data-ttu-id="34143-105">**Добавление ограничения**. При добавлении ограничения может оказаться, что в базе данных уже содержатся данные, которые не удовлетворяют добавляемому ограничению.</span><span class="sxs-lookup"><span data-stu-id="34143-105">**Adding a Constraint** If you add a constraint, the database might already contain data that does not satisfy it.</span></span> <span data-ttu-id="34143-106">При попытке сохранить ограничение [диалоговое окно "Уведомления после сохранения" (визуальные инструменты для баз данных)](visual-database-tools.md) сообщает, что не удалось создать ограничение в базе данных.</span><span class="sxs-lookup"><span data-stu-id="34143-106">When you try to save the new constraint, the [Post-Save Notifications Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) informs you that the database server could not create the constraint.</span></span> <span data-ttu-id="34143-107">Чтобы принудительно принять новое ограничение в базе данных, можно снять флажок **Проверять существующие данные при создании**.</span><span class="sxs-lookup"><span data-stu-id="34143-107">To force the database to accept the new constraint, you can clear the **Check existing data on creation** check box.</span></span>  
  
-   <span data-ttu-id="34143-108">**Добавление связи** . При добавлении связи может оказаться, что в базе данных уже содержатся строки таблицы внешнего ключа, для которых отсутствуют соответствующие строки в таблице первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="34143-108">**Adding a Relationship** If you add a relationship, the database might already contain rows of the foreign-key table that do not have corresponding rows in the primary-key table.</span></span> <span data-ttu-id="34143-109">То есть существующие данные могут не удовлетворять условию ссылочной целостности.</span><span class="sxs-lookup"><span data-stu-id="34143-109">That is, the existing data might not satisfy referential integrity.</span></span> <span data-ttu-id="34143-110">При попытке сохранить новую связь [диалоговое окно "Уведомления после сохранения" (визуальные инструменты для баз данных)](visual-database-tools.md) сообщает, что серверу базы данных не удалось сохранить исправленную таблицу внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="34143-110">When you try to save the new relationship, the[Post-Save Notifications Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) informs you that the database server could not save the revised foreign-key table.</span></span> <span data-ttu-id="34143-111">Чтобы принудительно принять изменение, можно снять флажок **Проверять существующие данные при создании**.</span><span class="sxs-lookup"><span data-stu-id="34143-111">To force the database to accept the modification, you can clear the **Check existing data on creation** check box.</span></span>  
  
-   <span data-ttu-id="34143-112">**Изменение таблицы, входящей в индексированное представление** . При изменении таблицы, входящей в индексированное представление Microsoft SQL Server, индексы представления могут быть потеряны.</span><span class="sxs-lookup"><span data-stu-id="34143-112">**Modifying a Table Contributing to an Indexed View** If you modify a table that contributes to a Microsoft SQL Server indexed view, the indexes on the view will be lost.</span></span> <span data-ttu-id="34143-113">Дополнительные сведения о повторном создании индексов см. в электронной документации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="34143-113">See the SQL Server Books Online for information on recreating indexes.</span></span>  
  
-   <span data-ttu-id="34143-114">**Удаление объекта** . При удалении объекта, такого как столбец, таблица или представление, из базы данных сначала убедитесь в том, что на него не ссылается другой объект базы данных.</span><span class="sxs-lookup"><span data-stu-id="34143-114">**Deleting an Object** If you delete an object, such as a column, table, or view, check first to be sure that the object is not referenced by another object in the database.</span></span>  
  
 <span data-ttu-id="34143-115">При любых изменениях структуры базы данных необходимо сохранять журнал изменений.</span><span class="sxs-lookup"><span data-stu-id="34143-115">No matter how you alter the database design, you should retain a history of the alterations.</span></span> <span data-ttu-id="34143-116">Одним из подходов является сохранение скриптов всех изменений, когда-либо сделанных в производственной базе данных.</span><span class="sxs-lookup"><span data-stu-id="34143-116">One approach is to retain SQL scripts for all modifications that you ever make to your production database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34143-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="34143-117">See Also</span></span>  
 <span data-ttu-id="34143-118">[Ограничения UNIQUE и проверочные ограничения](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="34143-118">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="34143-119">Многопользовательские среды (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="34143-119">Multiuser Environments &#40;Visual Database Tools&#41;</span></span>](multiuser-environments-visual-database-tools.md)  
  
  
