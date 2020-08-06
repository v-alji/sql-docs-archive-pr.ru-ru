---
title: Задача "Выполнение инструкции T-SQL" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executetsqlstatementtask.f1
helpviewer_keywords:
- Transact-SQL statements, SSIS
- statements [Integration Services]
- Execute T-SQL Statement task [Integration Services]
ms.assetid: 7e9086ca-d27e-46c0-bfad-d61333ebd55e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7ebc73ad843ac7fcf1dfbe7699ecd8ea53edcdad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729705"
---
# <a name="execute-t-sql-statement-task"></a><span data-ttu-id="5b13c-102">Задача «Выполнение инструкции T-SQL»</span><span class="sxs-lookup"><span data-stu-id="5b13c-102">Execute T-SQL Statement Task</span></span>
  <span data-ttu-id="5b13c-103">Задача «Выполнение инструкции T-SQL» запускает инструкции Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="5b13c-103">The Execute T-SQL Statement task runs Transact-SQL statements.</span></span> <span data-ttu-id="5b13c-104">Дополнительные сведения см. в разделах [Справочник по Transact-SQL (компонент Database Engine)](/sql/t-sql/language-reference) и [Запросы в службах Integration Services (SSIS)](../integration-services-ssis-queries.md).</span><span class="sxs-lookup"><span data-stu-id="5b13c-104">For more information, see [Transact-SQL Reference &#40;Database Engine&#41;](/sql/t-sql/language-reference) and [Integration Services &#40;SSIS&#41; Queries](../integration-services-ssis-queries.md).</span></span>  
  
 <span data-ttu-id="5b13c-105">Эта задача аналогична задаче «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="5b13c-105">This task is similar to the Execute SQL task.</span></span> <span data-ttu-id="5b13c-106">Тем не менее задача «Выполнение инструкции T-SQL» поддерживает только версию Transact-SQL языка SQL, и недопустимо использовать эту задачу для запуска инструкций на серверах, использующих другие разновидности языка SQL.</span><span class="sxs-lookup"><span data-stu-id="5b13c-106">However, the Execute T-SQL Statement task supports only the Transact-SQL version of the SQL language and you cannot use this task to run statements on servers that use other dialects of the SQL language.</span></span> <span data-ttu-id="5b13c-107">Для запуска параметризованных запросов, сохранения результатов запроса в переменную или использования выражений свойств необходимо использовать задачу «Выполнение SQL» вместо задачи «Выполнение инструкций T-SQL».</span><span class="sxs-lookup"><span data-stu-id="5b13c-107">If you need to run parameterized queries, save the query results to variables, or use property expressions, you should use the Execute SQL task instead of the Execute T-SQL Statement task.</span></span> <span data-ttu-id="5b13c-108">Дополнительные сведения см. в разделе [Execute SQL Task](execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="5b13c-108">For more information, see [Execute SQL Task](execute-sql-task.md).</span></span>  
  
## <a name="configuration-of-the-execute-t-sql-task"></a><span data-ttu-id="5b13c-109">Настройка задачи «Выполнение T-SQL»</span><span class="sxs-lookup"><span data-stu-id="5b13c-109">Configuration of the Execute T-SQL Task</span></span>  
 <span data-ttu-id="5b13c-110">Свойства задаются с помощью конструктора служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b13c-110">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="5b13c-111">Эта задача находится в разделе **Задачи плана обслуживания** **области элементов** в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b13c-111">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="5b13c-112">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="5b13c-112">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="5b13c-113">Задача "Выполнение инструкции T-SQL" (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="5b13c-113">Execute T-SQL Statement Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/execute-t-sql-statement-task-maintenance-plan.md)  
  
 <span data-ttu-id="5b13c-114">Дополнительные сведения об установке этих свойств в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="5b13c-114">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="5b13c-115">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="5b13c-115">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="5b13c-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="5b13c-116">See Also</span></span>  
 <span data-ttu-id="5b13c-117">[Задачи служб Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="5b13c-117">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 <span data-ttu-id="5b13c-118">[Поток управления](control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="5b13c-118">[Control Flow](control-flow.md) </span></span>  
 [<span data-ttu-id="5b13c-119">Предложение MERGE в пакетах служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="5b13c-119">MERGE in Integration Services Packages</span></span>](merge-in-integration-services-packages.md)  
  
  
