---
title: Многопользовательские среды (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- users [SQL Server], multiuser environments
- conflict resolution [Visual Database Tools]
- multiple users making database changes
- multiuser environments [Visual Database Tools]
- database modifications [SQL Server]
- version control [Visual Database Tools]
- Visual Database Tools [SQL Server], multiuser environments
ms.assetid: 330bd48c-9427-4967-b58e-b7c492d5ee36
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2e219ecda25f477aa459de674a43d9c2360376ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657457"
---
# <a name="multiuser-environments-visual-database-tools"></a><span data-ttu-id="e6d67-102">Многопользовательские среды (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="e6d67-102">Multiuser Environments (Visual Database Tools)</span></span>
  <span data-ttu-id="e6d67-103">Многопользовательской называется такая среда, в которой к базе данных, с которой работает пользователь, могут подключаться и другие пользователи, которые, кроме того, могут вносить в нее изменения.</span><span class="sxs-lookup"><span data-stu-id="e6d67-103">A multiuser environment is one in which other users can connect and make changes to the same database that you are working with.</span></span> <span data-ttu-id="e6d67-104">В результате с некоторыми объектами базы данных могут работать одновременно несколько пользователей.</span><span class="sxs-lookup"><span data-stu-id="e6d67-104">As a result, several users might be working with the same database objects at the same time.</span></span> <span data-ttu-id="e6d67-105">Таким образом, в многопользовательской среде при внесении изменений в базу данных могут отражаться и изменения, сделанные другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="e6d67-105">Thus, a multiuser environment introduces the possibility of the database being affected by changes made by other users while you are making changes, and vice versa.</span></span>  
  
 <span data-ttu-id="e6d67-106">При работе с базами данных в многопользовательской среде основной является проблема прав доступа.</span><span class="sxs-lookup"><span data-stu-id="e6d67-106">A key issue when working with databases in a multiuser environment is access permissions.</span></span> <span data-ttu-id="e6d67-107">Разрешения, которыми обладает пользователь, определяют масштаб действий, который он может выполнять в базе данных.</span><span class="sxs-lookup"><span data-stu-id="e6d67-107">The permissions you have for the database determine the extent of the work you can do with the database.</span></span> <span data-ttu-id="e6d67-108">Например, для изменения объектов базы данных нужно иметь соответствующие разрешения на запись.</span><span class="sxs-lookup"><span data-stu-id="e6d67-108">For example, to make changes to objects in a database, you must have the appropriate write permissions for the database.</span></span> <span data-ttu-id="e6d67-109">Дополнительные сведения о разрешениях в базе данных см. в документации по базе данных.</span><span class="sxs-lookup"><span data-stu-id="e6d67-109">For more information about permissions in your database, see your database documentation.</span></span> <span data-ttu-id="e6d67-110">Дополнительные сведения см. в разделе [Разрешения и визуальные инструменты для баз данных (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e6d67-110">For more information see [Permissions and Visual Database Tools &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="e6d67-111">При сохранении изменений, внесенных в таблицы, конструктор таблиц проверяет наличие изменений в базе данных с момента последнего сохранения пользователем.</span><span class="sxs-lookup"><span data-stu-id="e6d67-111">When you save changes made to tables, Table Designer verifies that the database has not been modified since you last saved changes.</span></span> <span data-ttu-id="e6d67-112">Если другой пользователь внес изменения, то первый пользователь будет уведомлен об изменениях в базе данных.</span><span class="sxs-lookup"><span data-stu-id="e6d67-112">If another user has made changes, you will be notified that the database has been modified.</span></span> <span data-ttu-id="e6d67-113">Возможно, эти изменения потребуется согласовывать.</span><span class="sxs-lookup"><span data-stu-id="e6d67-113">You may need to reconcile these changes.</span></span> <span data-ttu-id="e6d67-114">Дополнительные сведения см. в разделе [Согласование изменений, внесенных несколькими пользователями (визуальные инструменты для баз данных)](reconcile-changes-made-by-multiple-users-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e6d67-114">For more information, see [Reconcile Changes Made by Multiple Users &#40;Visual Database Tools&#41;](reconcile-changes-made-by-multiple-users-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="e6d67-115">Существуют принципы работы в многопользовательской среде, которых следует придерживаться во избежание конфликтов, связанных с изменениями.</span><span class="sxs-lookup"><span data-stu-id="e6d67-115">In a multiuser environment there are special considerations to keep in mind to avoid conflicting changes.</span></span> <span data-ttu-id="e6d67-116">Дополнительные сведения см. в разделе [Проблемы развития базы данных (визуальные инструменты для баз данных)](issues-of-database-evolution-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e6d67-116">For more information, see [Issues of Database Evolution &#40;Visual Database Tools&#41;](issues-of-database-evolution-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="e6d67-117">Один из способов предотвращения ошибок состоит в том, что изменения вносятся в копию базы данных, например в тестовую базу данных. Затем создается скрипт изменений, который применяет эти изменения к оригиналу после разрешения конфликтов в режиме «вне сети».</span><span class="sxs-lookup"><span data-stu-id="e6d67-117">One way to avoid problems is to work in a copy of the database, such as a test database, when you make changes, then you can create a change script that you can run to make those changes on the original database after resolving conflicts offline.</span></span> <span data-ttu-id="e6d67-118">Дополнительные сведения см. в разделе [Разработка, тестирование и создание баз данных (визуальные инструменты для баз данных)](development-test-and-production-databases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e6d67-118">For more information see [Development, Test, and Production Databases &#40;Visual Database Tools&#41;](development-test-and-production-databases-visual-database-tools.md).</span></span>  
  
  
