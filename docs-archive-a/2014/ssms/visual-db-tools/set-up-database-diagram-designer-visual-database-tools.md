---
title: Настройка конструктора диаграмм баз данных (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.diagnostic.InstallSqlDiagramSupport
helpviewer_keywords:
- Database Diagram Designer
- database diagrams [SQL Server], Database Diagram Designer
- diagrams [SQL Server], Database Diagram Designer
ms.assetid: 927321ee-b459-4f5b-9719-4a7a95639143
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6d59fa2ed197a410de6b68e388e76d2bf21c334d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734846"
---
# <a name="set-up-database-diagram-designer-visual-database-tools"></a><span data-ttu-id="1415b-102">Настройка конструктора диаграмм баз данных (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="1415b-102">Set Up Database Diagram Designer (Visual Database Tools)</span></span>
  <span data-ttu-id="1415b-103">Чтобы можно было использовать конструктор диаграмм баз данных, его вначале должен установить член роли **db_owner** для контроля доступа к диаграммам.</span><span class="sxs-lookup"><span data-stu-id="1415b-103">To use Database Diagram Designer, it must first be set up by a member of the **db_owner** role to control access to diagrams.</span></span>  
  
### <a name="to-set-up-database-diagramming"></a><span data-ttu-id="1415b-104">Настройка создания схем баз данных</span><span class="sxs-lookup"><span data-stu-id="1415b-104">To set up database diagramming</span></span>  
  
1.  <span data-ttu-id="1415b-105">Разверните узел базы данных в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="1415b-105">From Object Explorer, expand a database node.</span></span>  
  
2.  <span data-ttu-id="1415b-106">В окне подключения к базе данных разверните узел «Диаграммы баз данных».</span><span class="sxs-lookup"><span data-stu-id="1415b-106">Expand the Database Diagrams node under the database connection.</span></span>  
  
3.  <span data-ttu-id="1415b-107">Нажмите кнопку **Да** , когда получите подсказку о необходимости настроить создание диаграмм баз данных.</span><span class="sxs-lookup"><span data-stu-id="1415b-107">Select **Yes** when prompted if you want to set up database diagramming.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1415b-108">В базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] создаются таблица диаграмм базы данных, системные хранимые процедуры и системная функция.</span><span class="sxs-lookup"><span data-stu-id="1415b-108">This will create the database diagram table, system stored procedures, and a system function on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
4.  <span data-ttu-id="1415b-109">Visual Studio создает следующие объекты в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1415b-109">Visual Studio will create the following objects on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
    1.  <span data-ttu-id="1415b-110">таблица sysdiagrams;</span><span class="sxs-lookup"><span data-stu-id="1415b-110">sysdiagrams table</span></span>  
  
    2.  <span data-ttu-id="1415b-111">хранимая процедура sp_alterdiagram;</span><span class="sxs-lookup"><span data-stu-id="1415b-111">sp_alterdiagram stored procedure</span></span>  
  
    3.  <span data-ttu-id="1415b-112">хранимая процедура sp_creatediagram;</span><span class="sxs-lookup"><span data-stu-id="1415b-112">sp_creatediagram stored procedure</span></span>  
  
    4.  <span data-ttu-id="1415b-113">хранимая процедура sp_dropdiagram;</span><span class="sxs-lookup"><span data-stu-id="1415b-113">sp_dropdiagram stored procedure</span></span>  
  
    5.  <span data-ttu-id="1415b-114">хранимая процедура sp_renamediagram;</span><span class="sxs-lookup"><span data-stu-id="1415b-114">sp_renamediagram stored procedure</span></span>  
  
    6.  <span data-ttu-id="1415b-115">функция fn_diagramobjects;</span><span class="sxs-lookup"><span data-stu-id="1415b-115">fn_diagramobjects function</span></span>  
  
    7.  <span data-ttu-id="1415b-116">хранимая процедура sp_helpdiagrams;</span><span class="sxs-lookup"><span data-stu-id="1415b-116">sp_helpdiagrams stored procedure</span></span>  
  
    8.  <span data-ttu-id="1415b-117">хранимая процедура sp_helpdiagramsdefinition;</span><span class="sxs-lookup"><span data-stu-id="1415b-117">sp_helpdiagramsdefinition stored procedure</span></span>  
  
    9. <span data-ttu-id="1415b-118">хранимая процедура sp_upgraddiagrams.</span><span class="sxs-lookup"><span data-stu-id="1415b-118">sp_upgraddiagrams stored procedure</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1415b-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="1415b-119">See Also</span></span>  
 <span data-ttu-id="1415b-120">[Общие сведения о владении диаграммами базы данных &#40;визуальные инструменты для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="1415b-120">[Understand Database Diagram Ownership &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="1415b-121">[Обновление диаграмм баз данных из предыдущих выпусков &#40;визуальные инструменты для баз данных&#41;](upgrade-database-diagrams-from-previous-editions-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="1415b-121">[Upgrade Database Diagrams from Previous Editions &#40;Visual Database Tools&#41;](upgrade-database-diagrams-from-previous-editions-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="1415b-122">ALTER AUTHORIZATION (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1415b-122">ALTER AUTHORIZATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-authorization-transact-sql)  
  
  
