---
title: Базы данных для разработки, тестирования и рабочей среды (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- production databases [SQL Server]
- testing databases
- database testing [SQL Server]
ms.assetid: cb403330-8cbe-41c6-bd23-bc432d50f173
author: stevestein
ms.author: sstein
ms.openlocfilehash: 98ac88aec42b53012e0f57233a089bddbd3c8cae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730006"
---
# <a name="development-test-and-production-databases-visual-database-tools"></a><span data-ttu-id="e041d-102">Базы данных для разработки, тестирования и производства (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="e041d-102">Development, Test, and Production Databases (Visual Database Tools)</span></span>
  <span data-ttu-id="e041d-103">В случае, когда две базы данных обладают одинаковыми структурами, изменения в одной базе данных можно распространить на вторую.</span><span class="sxs-lookup"><span data-stu-id="e041d-103">If you have two databases with identical structure, you can make changes in one database and propagate those changes to the other.</span></span> <span data-ttu-id="e041d-104">Например, если имеется личная база данных для разработки и база данных для совместного тестирования, можно изменить первую базу данных и распространить эти изменения в тестовую базу данных.</span><span class="sxs-lookup"><span data-stu-id="e041d-104">For example, if you have a personal development database and a group-wide test database, you can modify the development database, then propagate those changes to the test database.</span></span>  
  
 <span data-ttu-id="e041d-105">Для этого в базе данных, предназначенной для разработки, выполните все модификации за один сеанс, создайте скрипт изменения этого сеанса и выполните данный скрипт в базе данных, предназначенной для тестирования.</span><span class="sxs-lookup"><span data-stu-id="e041d-105">To accomplish this, perform all the modifications in a single session with the development database, create a Change Script of your session and later run the script on the test database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e041d-106">См. также:</span><span class="sxs-lookup"><span data-stu-id="e041d-106">See Also</span></span>  
 [<span data-ttu-id="e041d-107">Многопользовательские среды (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="e041d-107">Multiuser Environments &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
