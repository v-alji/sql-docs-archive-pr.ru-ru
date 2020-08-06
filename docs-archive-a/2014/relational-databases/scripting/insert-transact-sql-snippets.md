---
title: вставлять фрагменты кода Transact-SQL
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [SQL Server], snippets
- Transact-SQL snippets, code
- snippets [Transact-SQL], how to insert
ms.assetid: d66c96f4-2e84-4d79-9bfd-3635fdd98425
author: rothja
ms.author: jroth
ms.openlocfilehash: 26a7a224e700c726ee3d4437321843d45ddb6e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668235"
---
# <a name="insert-transact-sql-snippets"></a><span data-ttu-id="e3e58-102">вставлять фрагменты кода Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3e58-102">Insert Transact-SQL Snippets</span></span>
  <span data-ttu-id="e3e58-103">Фрагмент кода [!INCLUDE[tsql](../../includes/tsql-md.md)] можно использовать в качестве шаблона при написании новых инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] в редакторе запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3e58-103">A [!INCLUDE[tsql](../../includes/tsql-md.md)] code snippet is a template you can use as a starting point when writing new [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
## <a name="inserting-snippets"></a><span data-ttu-id="e3e58-104">Вставка фрагментов</span><span class="sxs-lookup"><span data-stu-id="e3e58-104">Inserting Snippets</span></span>  
 <span data-ttu-id="e3e58-105">Открыть упорядоченный по категориям перечень доступных для выбора фрагментов можно из меню **Вставить фрагмент** .</span><span class="sxs-lookup"><span data-stu-id="e3e58-105">You can use the **Insert Snippet** menu to open a categorized list of snippets to choose from.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="e3e58-106">содержат точки замены: текст с рекомендациями по синтаксису, относящемуся к данной точке.</span><span class="sxs-lookup"><span data-stu-id="e3e58-106">snippets contain replacement points: text that suggests the syntax relevant to that point.</span></span> <span data-ttu-id="e3e58-107">Например, во фрагменте CREATE TABLE находятся точки замены для таких элементов, как имя таблицы, имена столбцов, типы данных в столбцах.</span><span class="sxs-lookup"><span data-stu-id="e3e58-107">For example, the CREATE TABLE snippet has replacement points for elements such as the table name, column names, and column data types.</span></span> <span data-ttu-id="e3e58-108">После вставки фрагмента кода необходимо заменить текст замены, образовав правильную инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3e58-108">After inserting the snippet, you must change the replacement text to form a valid [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="e3e58-109">Дополнительные сведения см. в разделе [Завершение фрагментов кода Transact-SQL](complete-transact-sql-snippets.md).</span><span class="sxs-lookup"><span data-stu-id="e3e58-109">For more information, see [Complete Transact-SQL Snippets](complete-transact-sql-snippets.md).</span></span>  
  
#### <a name="inserting-a-snippet-by-using-the-insert-snippet-menu"></a><span data-ttu-id="e3e58-110">Вставка фрагмента с помощью меню «Вставить фрагмент»</span><span class="sxs-lookup"><span data-stu-id="e3e58-110">Inserting a Snippet by Using the Insert Snippet Menu</span></span>  
  
1.  <span data-ttu-id="e3e58-111">Откройте окно «Редактор запроса компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] » и переместите курсор в место будущей вставки фрагмента [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3e58-111">In the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window, put the cursor where you want to insert the [!INCLUDE[tsql](../../includes/tsql-md.md)] snippet.</span></span>  
  
2.  <span data-ttu-id="e3e58-112">Вызовите подсказку одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="e3e58-112">Launch the snippet picker tooltip in one of three ways:</span></span>  
  
    -   <span data-ttu-id="e3e58-113">Нажмите комбинацию клавиш CTRL+K или CTRL+X.</span><span class="sxs-lookup"><span data-stu-id="e3e58-113">Press CTRL+K, CTRL+X.</span></span>  
  
    -   <span data-ttu-id="e3e58-114">В меню **Правка** укажите пункт **IntelliSense**и выберите **Вставить фрагмент**.</span><span class="sxs-lookup"><span data-stu-id="e3e58-114">On the **Edit** menu, point to **IntelliSense**, then click **Insert Snippet**.</span></span>  
  
    -   <span data-ttu-id="e3e58-115">Щелкните правой кнопкой мыши и выберите из контекстного меню команду **Вставить фрагмент** .</span><span class="sxs-lookup"><span data-stu-id="e3e58-115">Right-click the mouse and then select the **Insert Snippet** command from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="e3e58-116">Дважды щелкните фрагмент или выберите фрагмент из захваченных и нажмите клавишу TAB или ВВОД.</span><span class="sxs-lookup"><span data-stu-id="e3e58-116">Double-click the snippet, or select the snippet from the snippet picker and then press TAB or ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3e58-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="e3e58-117">See Also</span></span>  
 [<span data-ttu-id="e3e58-118">Вставка фрагментов кода окружения Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3e58-118">Insert Surround-with Transact-SQL snippets</span></span>](insert-surround-with-transact-sql-snippets.md)  
  
  
