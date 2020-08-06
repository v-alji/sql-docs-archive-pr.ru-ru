---
title: Добавление отступов | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 9dce05c1-c52f-455d-8b8d-6f303e242760
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2d0b7ee8819f98df5e5658321a3d950ca31083b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665722"
---
# <a name="adding-indentation"></a><span data-ttu-id="28f46-102">Добавление отступов</span><span class="sxs-lookup"><span data-stu-id="28f46-102">Adding Indentation</span></span>
  <span data-ttu-id="28f46-103">Редактор запросов позволяет одновременно задать отступ для больших участков кода, а также изменить величину отступа.</span><span class="sxs-lookup"><span data-stu-id="28f46-103">Query Editor allows you to indent large sections of code with a single step, and you can change the amount of the indentation.</span></span>  
  
## <a name="indenting-code"></a><span data-ttu-id="28f46-104">Добавление отступов кода</span><span class="sxs-lookup"><span data-stu-id="28f46-104">Indenting Code</span></span>  
  
#### <a name="to-indent-multiple-lines-of-code"></a><span data-ttu-id="28f46-105">Добавление отступа для нескольких строк кода</span><span class="sxs-lookup"><span data-stu-id="28f46-105">To indent multiple lines of code</span></span>  
  
1.  <span data-ttu-id="28f46-106">На панели инструментов нажмите кнопку **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="28f46-106">On the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="28f46-107">Создайте второй запрос, который выбирает значения столбцов **BusinessEntityID**, FirstName, **MiddleName**и **LastName** из таблицы **Person** схемы **Person** .</span><span class="sxs-lookup"><span data-stu-id="28f46-107">Create a second query that selects the **BusinessEntityID**, FirstName, **MiddleName**, and **LastName** columns from the **Person** table of the **Person** schema.</span></span> <span data-ttu-id="28f46-108">Разместите каждый столбец на отдельной строке, чтобы код выглядел следующим образом:</span><span class="sxs-lookup"><span data-stu-id="28f46-108">Place each column on a separate line so the code looks like this:</span></span>  
  
    ```  
    -- Search for a contact  
    SELECT   
    BusinessEntityID,  
    FirstName,   
    MiddleName,   
    LastName  
    FROM Person.Person  
    WHERE LastName = 'Sanchez';  
    GO  
    ```  
  
3.  <span data-ttu-id="28f46-109">Выделите весь текст, содержащийся в столбцах с `BusinessEntityID` по `LastName`.</span><span class="sxs-lookup"><span data-stu-id="28f46-109">Select all text from `BusinessEntityID` to `LastName`.</span></span>  
  
4.  <span data-ttu-id="28f46-110">Чтобы добавить отступ для всех выбранных строк, на панели инструментов **Редактор SQL** нажмите кнопку **Увеличить отступ** .</span><span class="sxs-lookup"><span data-stu-id="28f46-110">On the **SQL Editor** toolbar, click **Increase Indent** to indent all the lines at once.</span></span>  
  
#### <a name="to-change-the-default-indentation"></a><span data-ttu-id="28f46-111">Изменение указанного по умолчанию отступа</span><span class="sxs-lookup"><span data-stu-id="28f46-111">To change the default indentation</span></span>  
  
1.  <span data-ttu-id="28f46-112">В меню **Сервис** выберите команду **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="28f46-112">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="28f46-113">Последовательно раскройте элементы **Текстовый редактор**и **Все языки**, а затем нажмите **Вкладки** и установите необходимые значения отступов.</span><span class="sxs-lookup"><span data-stu-id="28f46-113">Expand **Text Editor**, expand **All Languages**, and click **Tabs** , and set indentation values as appropriate.</span></span> <span data-ttu-id="28f46-114">Обратите внимание, что можно изменять как значения отступов, так и значение табуляции, а также указать, следует ли заменять знаки табуляции пробелами.</span><span class="sxs-lookup"><span data-stu-id="28f46-114">Note that you can change the size of the indent as well as the size of tabs, and whether tabs are converted to spaces.</span></span>  
  
     <span data-ttu-id="28f46-115">![Внешний вид диалогового окна «Вкладки»](media/tabsdialog.gif "Внешний вид диалогового окна «Вкладки»")</span><span class="sxs-lookup"><span data-stu-id="28f46-115">![Appearance of the Tabs dialog box](media/tabsdialog.gif "Appearance of the Tabs dialog box")</span></span>  
  
3.  <span data-ttu-id="28f46-116">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="28f46-116">Click **OK**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="28f46-117">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="28f46-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="28f46-118">Разворачивание окна редактора запросов</span><span class="sxs-lookup"><span data-stu-id="28f46-118">Maximizing Query Editor</span></span>](lesson-2-3-maximizing-query-editor.md)  
  
  
