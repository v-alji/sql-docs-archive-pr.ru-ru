---
title: Редактор задачи «Выполнение SQL» (страница «результирующий набор») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executesqltask.resultset.f1
helpviewer_keywords:
- Execute SQL Task Editor
ms.assetid: d27000c8-8d91-4e1c-b45e-bca9a3c12f6d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 027f3c77e84b47958e9fb6567acdb308c14eb1e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657836"
---
# <a name="execute-sql-task-editor-result-set-page"></a><span data-ttu-id="e6a21-102">Редактор задачи «Выполнение SQL» (страница «Результирующий набор»)</span><span class="sxs-lookup"><span data-stu-id="e6a21-102">Execute SQL Task Editor (Result Set Page)</span></span>
  <span data-ttu-id="e6a21-103">Страница **Результирующий набор** диалогового окна **Редактор задачи «Выполнение SQL»** применяется для сопоставления результатов инструкции SQL с новыми или существующими переменными.</span><span class="sxs-lookup"><span data-stu-id="e6a21-103">Use the **Result Set** page of the **Execute SQL Task Editor** dialog to map the result of the SQL statement to new or existing variables.</span></span> <span data-ttu-id="e6a21-104">Эти параметры в диалоговом окне отключены, если параметр **Результирующий набор** на странице «Общие» установлен в **Нет**.</span><span class="sxs-lookup"><span data-stu-id="e6a21-104">The options in this dialog box are disabled if **ResultSet** on the General page is set to **None**.</span></span>  
  
 <span data-ttu-id="e6a21-105">Дополнительные сведения об этой задаче см. в разделах [Задача "Выполнение SQL"](control-flow/execute-sql-task.md) и [Результирующие наборы в задаче "Выполнение SQL"](../../2014/integration-services/result-sets-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="e6a21-105">For more information about this task, see [Execute SQL Task](control-flow/execute-sql-task.md) and [Result Sets in the Execute SQL Task](../../2014/integration-services/result-sets-in-the-execute-sql-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e6a21-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e6a21-106">Options</span></span>  
 <span data-ttu-id="e6a21-107">**Имя результата**</span><span class="sxs-lookup"><span data-stu-id="e6a21-107">**Result Name**</span></span>  
 <span data-ttu-id="e6a21-108">После того как с помощью кнопки **Добавить**было добавлено сопоставление результирующего набора, укажите имя результата.</span><span class="sxs-lookup"><span data-stu-id="e6a21-108">After you have added a result set mapping set by clicking **Add**, provide a name for the result.</span></span> <span data-ttu-id="e6a21-109">В зависимости от типа результирующего набора необходимо использовать определенные имена результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="e6a21-109">Depending on the result set type, you must use specific result names.</span></span>  
  
 <span data-ttu-id="e6a21-110">Если тип результирующего набора **Одна строка**, то можно использовать имя столбца, возвращаемого запросом, или число, указывающее положение столбца в списке столбцов, возвращаемых запросом.</span><span class="sxs-lookup"><span data-stu-id="e6a21-110">If the result set type is **Single row**, you can use either the name of a column returned by the query or the number that represents the position of a column in the column list of a column returned by the query.</span></span>  
  
 <span data-ttu-id="e6a21-111">Если результирующий набор имеет тип **Полный результирующий набор** или **XML**, то в качестве имени результирующего набора необходимо использовать 0.</span><span class="sxs-lookup"><span data-stu-id="e6a21-111">If the result set type is **Full result set** or **XML**, you must use 0 as the result set name.</span></span>  
  
 <span data-ttu-id="e6a21-112">**См. также:**[Настройка результирующих наборов в задаче "Выполнение SQL"](../../2014/integration-services/result-sets-in-the-execute-sql-task.md)</span><span class="sxs-lookup"><span data-stu-id="e6a21-112">**Related Topics**: [Result Sets in the Execute SQL Task](../../2014/integration-services/result-sets-in-the-execute-sql-task.md)</span></span>  
  
 <span data-ttu-id="e6a21-113">**Имя переменной**</span><span class="sxs-lookup"><span data-stu-id="e6a21-113">**Variable Name**</span></span>  
 <span data-ttu-id="e6a21-114">Для сопоставления результирующего набора с переменной выберите ее или щелкните \<**New variable...**>, чтобы добавить новую переменную с помощью диалогового окна **Добавление переменной**.</span><span class="sxs-lookup"><span data-stu-id="e6a21-114">Map the result set to a variable by selecting a variable or click \<**New variable...**> to add a new variable by using the **Add Variable** dialog box.</span></span>  
  
 <span data-ttu-id="e6a21-115">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="e6a21-115">**Add**</span></span>  
 <span data-ttu-id="e6a21-116">Нажмите кнопку, чтобы добавить сопоставление результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="e6a21-116">Click to add a result set mapping.</span></span>  
  
 <span data-ttu-id="e6a21-117">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="e6a21-117">**Remove**</span></span>  
 <span data-ttu-id="e6a21-118">Выберите в списке сопоставление результирующего набора и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="e6a21-118">Select a result set mapping in the list and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6a21-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6a21-119">See Also</span></span>  
 <span data-ttu-id="e6a21-120">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="e6a21-120">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="e6a21-121">[Редактор задачи «Выполнение SQL» &#40;страница «Общие»&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="e6a21-121">[Execute SQL Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="e6a21-122">[Редактор задачи "Выполнение SQL" &#40;страница "Сопоставление параметров"&#41;](../../2014/integration-services/execute-sql-task-editor-parameter-mapping-page.md) </span><span class="sxs-lookup"><span data-stu-id="e6a21-122">[Execute SQL Task Editor &#40;Parameter Mapping Page&#41;](../../2014/integration-services/execute-sql-task-editor-parameter-mapping-page.md) </span></span>  
 [<span data-ttu-id="e6a21-123">Справочник по Transact-SQL &#40;ядро СУБД&#41;</span><span class="sxs-lookup"><span data-stu-id="e6a21-123">Transact-SQL Reference &#40;Database Engine&#41;</span></span>](/sql/t-sql/language-reference)  
  
  
