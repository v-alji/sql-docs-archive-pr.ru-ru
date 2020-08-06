---
title: Завершение фрагментов кода Transact-SQL
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [SQL Server], completing snippets
- snippets [Transact-SQL], completing
- Transact-SQL snippets, completing
ms.assetid: a8316a58-bb57-485e-845f-84c23360314c
author: rothja
ms.author: jroth
ms.openlocfilehash: d90c77f72ba8ce80d26503645d9b04d795f5e503
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658160"
---
# <a name="complete-transact-sql-snippets"></a><span data-ttu-id="7c565-102">Завершение фрагментов кода Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7c565-102">Complete Transact-SQL Snippets</span></span>
  <span data-ttu-id="7c565-103">После вставки фрагмента кода [!INCLUDE[tsql](../../includes/tsql-md.md)] в скрипт нужно изменить содержимое этого фрагмента, чтобы получить завершенную инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7c565-103">Once a [!INCLUDE[tsql](../../includes/tsql-md.md)] code snippet has been inserted into a script, you edit the contents of the snippet to build a complete [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
## <a name="completing-snippets"></a><span data-ttu-id="7c565-104">Завершение фрагментов</span><span class="sxs-lookup"><span data-stu-id="7c565-104">Completing Snippets</span></span>  
 <span data-ttu-id="7c565-105">При добавлении фрагмента кода [!INCLUDE[tsql](../../includes/tsql-md.md)] в скрипт во вставленном фрагменте имеется одна или несколько подсвеченных точек замены.</span><span class="sxs-lookup"><span data-stu-id="7c565-105">When you add a [!INCLUDE[tsql](../../includes/tsql-md.md)] snippet to your script, the inserted snippet statement has one or more replacement points, which are highlighted.</span></span> <span data-ttu-id="7c565-106">При наведении указателя мыши на точку замены появляется подсказка с описанием синтаксического элемента, который можно указать.</span><span class="sxs-lookup"><span data-stu-id="7c565-106">If you rest your mouse pointer on a replacement point, a tooltip appears with a description of the syntax element you can specify.</span></span> <span data-ttu-id="7c565-107">Редактор запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] распознает фрагмент кода как отдельный блок в скрипте до закрытия исходного файла.</span><span class="sxs-lookup"><span data-stu-id="7c565-107">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor recognizes the snippet as separate from the surrounding script until you close the source file.</span></span> <span data-ttu-id="7c565-108">Точки замены остаются активными до закрытия исходного файла.</span><span class="sxs-lookup"><span data-stu-id="7c565-108">The replacement points remain active until you close the source file.</span></span>  
  
 <span data-ttu-id="7c565-109">Также в код шаблона, вставленный во фрагменте, можно добавить дополнительные синтаксические элементы.</span><span class="sxs-lookup"><span data-stu-id="7c565-109">You can also add additional syntax elements to the template code inserted by a snippet.</span></span> <span data-ttu-id="7c565-110">Например, если шаблон создания таблицы создает два определения столбца, для создания таблицы с числом столбцов больше двух необходимо добавить дополнительные определения столбцов.</span><span class="sxs-lookup"><span data-stu-id="7c565-110">For example, the Create Table snippet template generates two column definitions; you must add additional column definitions to create a table with more than two columns.</span></span>  
  
#### <a name="completing-the-snippet-statement"></a><span data-ttu-id="7c565-111">Завершение инструкций фрагмента кода</span><span class="sxs-lookup"><span data-stu-id="7c565-111">Completing the Snippet Statement</span></span>  
  
1.  <span data-ttu-id="7c565-112">С помощью клавиши табуляции можно перейти к следующей точке замены.</span><span class="sxs-lookup"><span data-stu-id="7c565-112">Use the TAB key to move from one replacement point to the next.</span></span> <span data-ttu-id="7c565-113">С помощью сочетания клавиш SHIFT и табуляции можно перейти к предыдущей точке замены.</span><span class="sxs-lookup"><span data-stu-id="7c565-113">Use SHIFT+TAB to move to the previous replacement point.</span></span>  
  
2.  <span data-ttu-id="7c565-114">Нажмите сочетание клавиш Click+ПРОБЕЛ для вызова IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="7c565-114">Click CTRL+SPACE to invoke IntelliSense.</span></span>  
  
3.  <span data-ttu-id="7c565-115">Выберите элемент из списка или введите собственный вариант.</span><span class="sxs-lookup"><span data-stu-id="7c565-115">Select an item from the list, or type a replacement of your choice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c565-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="7c565-116">See Also</span></span>  
 <span data-ttu-id="7c565-117">[вставлять фрагменты кода Transact-SQL](insert-transact-sql-snippets.md) </span><span class="sxs-lookup"><span data-stu-id="7c565-117">[Insert Transact-SQL Snippets](insert-transact-sql-snippets.md) </span></span>  
 [<span data-ttu-id="7c565-118">Вставка фрагментов кода окружения Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7c565-118">Insert Surround-with Transact-SQL snippets</span></span>](insert-surround-with-transact-sql-snippets.md)  
  
  
