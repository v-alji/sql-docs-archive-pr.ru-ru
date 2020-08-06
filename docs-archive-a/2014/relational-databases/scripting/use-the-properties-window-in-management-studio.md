---
title: Использование окна «Свойства» в среде Management Studio
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- viewing properties
- Properties window [SQL Server Management Studio]
- complex properties [SQL Server Management Studio]
ms.assetid: 903d4aca-f57c-43d9-a893-702eceaa7004
author: rothja
ms.author: jroth
ms.openlocfilehash: 5030bf85fc87482b11e91967ff8fb1baf77a213e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668217"
---
# <a name="use-the-properties-window-in-management-studio"></a><span data-ttu-id="bb2ba-102">Использование окна «Свойства» в среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="bb2ba-102">Use the Properties Window in Management Studio</span></span>
  <span data-ttu-id="bb2ba-103">Окно свойств описывает состояние элемента в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], например соединение или оператор Showplan, и сведения об объектах базы данных, таких как таблицы, представления и конструкторы.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-103">The Properties window describes the state of an item in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], such as a connection or a Showplan operator, and information about database objects such as tables, views, and designers.</span></span>  
  
 <span data-ttu-id="bb2ba-104">Окно свойств можно использовать для просмотра свойств текущего соединения.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-104">You can use the Properties window to view the properties of the current connection.</span></span> <span data-ttu-id="bb2ba-105">Многие свойства в окне свойств доступны только для чтения, однако могут быть изменены другими средствами среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb2ba-105">Many properties are read-only in the Properties window but can be changed elsewhere in the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="bb2ba-106">Например, свойство «База данных» запроса в окне свойств доступно только для чтения, но может изменяться на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-106">For example, the Database property of a query is read-only in the Properties window, but can be changed on the tool bar.</span></span>  
  
### <a name="to-view-properties-using-the-properties-window"></a><span data-ttu-id="bb2ba-107">Просмотр свойств с помощью окна свойств</span><span class="sxs-lookup"><span data-stu-id="bb2ba-107">To view properties using the Properties window</span></span>  
  
1.  <span data-ttu-id="bb2ba-108">Если окна свойств нет на экране, выберите **Окно "Свойства"** в меню **Вид** или нажмите клавишу F4.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-108">If the Properties window is not visible, click **Properties Window** on the **View** menu, or press F4.</span></span>  
  
2.  <span data-ttu-id="bb2ba-109">Выберите объект, который необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-109">Set the focus on the object that you want to view.</span></span>  
  
3.  <span data-ttu-id="bb2ba-110">Найдите в окне свойств соответствующее свойство.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-110">Look for a specific property in the Properties window.</span></span>  
  
### <a name="to-view-connection-properties-of-a-query-window"></a><span data-ttu-id="bb2ba-111">Просмотр свойств соединения окна запроса</span><span class="sxs-lookup"><span data-stu-id="bb2ba-111">To view connection properties of a query window</span></span>  
  
1.  <span data-ttu-id="bb2ba-112">Если окна свойств нет на экране, выберите **Окно "Свойства"** в меню **Вид** или нажмите клавишу F4.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-112">If the Properties window is not visible, click **Properties Window** on the **View** menu, or press F4.</span></span>  
  
2.  <span data-ttu-id="bb2ba-113">В окне свойств можно увидеть все свойства соединения.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-113">In the Properties window, you can see all the connection properties.</span></span>  
  
### <a name="to-view-the-properties-of-a-showplan-operator"></a><span data-ttu-id="bb2ba-114">Просмотр свойств инструкции оператора Showplan</span><span class="sxs-lookup"><span data-stu-id="bb2ba-114">To view the properties of a Showplan operator</span></span>  
  
1.  <span data-ttu-id="bb2ba-115">В меню **Запрос** выберите пункт **Включить действительный план выполнения**.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-115">On the **Query** menu, click **Include Actual Execution Plan**.</span></span>  
  
2.  <span data-ttu-id="bb2ba-116">В редакторе SQL-запросов введите текст запроса и выполните его.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-116">In the SQL Query Editor, type and execute a query.</span></span>  
  
3.  <span data-ttu-id="bb2ba-117">Если окна свойств нет на экране, выберите **Окно "Свойства"** в меню **Вид** или нажмите клавишу F4.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-117">If the Properties window is not visible, click **Properties Window** on the **View** menu, or press F4.</span></span>  
  
4.  <span data-ttu-id="bb2ba-118">На вкладке **План выполнения** редактора SQL-запросов нажмите значки инструкций для просмотра сведений об инструкциях в окне свойств.</span><span class="sxs-lookup"><span data-stu-id="bb2ba-118">On the **Execution plan** tab of the SQL Query Editor click the icons of the operators to view information about the operators in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb2ba-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb2ba-119">See Also</span></span>  
 [<span data-ttu-id="bb2ba-120">Окно "Свойства" (среда Management Studio)</span><span class="sxs-lookup"><span data-stu-id="bb2ba-120">Properties Window &#40;Management Studio&#41;</span></span>](../../ssms/properties-window-management-studio.md)  
  
  
