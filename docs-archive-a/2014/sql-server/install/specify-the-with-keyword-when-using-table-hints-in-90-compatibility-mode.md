---
title: Укажите ключевое слово WITH при использовании табличных подсказок в режиме совместимости 90 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- WITH keyword
- table hints [SQL Server]
ms.assetid: 7636cc85-5155-44db-baf6-df807761adb8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0ecd13475395cef4257d97eb7480f32420932e22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659161"
---
# <a name="specify-the-with-keyword-when-using-table-hints-in-90-compatibility-mode"></a><span data-ttu-id="c4c50-102">Указание ключевого слова WITH при использовании табличных подсказок в режиме совместимости 90</span><span class="sxs-lookup"><span data-stu-id="c4c50-102">Specify the WITH keyword when using table hints in 90 compatibility mode</span></span>
  <span data-ttu-id="c4c50-103">С некоторыми исключениями в предложении FROM запроса поддерживаются табличные указания только с ключевым словом WITH.</span><span class="sxs-lookup"><span data-stu-id="c4c50-103">With some exceptions, table hints are supported in the FROM clause of a query only when the hints are specified by using the WITH keyword.</span></span> <span data-ttu-id="c4c50-104">Дополнительные сведения см. в разделах «FROM ([!INCLUDE[tsql](../../includes/tsql-md.md)])» и «Табличные указания [!INCLUDE[tsql](../../includes/tsql-md.md)]» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4c50-104">For more information, see the topics "FROM ([!INCLUDE[tsql](../../includes/tsql-md.md)])" and "Table Hint ([!INCLUDE[tsql](../../includes/tsql-md.md)])" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="c4c50-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="c4c50-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="c4c50-106">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="c4c50-106">Corrective Action</span></span>  
 <span data-ttu-id="c4c50-107">Запросы, содержащие табличные указания в предложении FROM, необходимо изменить, включив перед табличными указаниями ключевое слово WITH.</span><span class="sxs-lookup"><span data-stu-id="c4c50-107">Modify queries that include table hints in the FROM clause by including the WITH keyword before the table hints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4c50-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="c4c50-108">See Also</span></span>  
 <span data-ttu-id="c4c50-109">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="c4c50-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="c4c50-110">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="c4c50-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
