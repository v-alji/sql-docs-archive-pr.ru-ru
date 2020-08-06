---
title: Редактор задачи «Выполнение SQL» (страница «Сопоставление параметров») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executesqltask.parametermapping.f1
helpviewer_keywords:
- Execute SQL Task Editor
ms.assetid: 8ebe020a-7921-46b2-8823-398748f379b2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cfbb4468cb69947dfa54fb519b7698286393d578
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657837"
---
# <a name="execute-sql-task-editor-parameter-mapping-page"></a><span data-ttu-id="adcc3-102">Редактор задачи «Выполнение SQL» (страница «Сопоставление параметров»)</span><span class="sxs-lookup"><span data-stu-id="adcc3-102">Execute SQL Task Editor (Parameter Mapping Page)</span></span>
  <span data-ttu-id="adcc3-103">Используйте страницу **Сопоставление параметров** диалогового окна **Редактор задачи «Выполнение SQL»** для сопоставления переменных с параметрами в инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="adcc3-103">Use the **Parameter Mapping** page of the **Execute SQL Task Editor** dialog box to map variables to parameters in the SQL statement.</span></span>  
  
 <span data-ttu-id="adcc3-104">Сведения об этой задаче см. в разделах [Задача "Выполнение SQL"](control-flow/execute-sql-task.md) и [Параметры и коды возврата в задаче "Выполнение SQL"](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="adcc3-104">To learn about this task, see [Execute SQL Task](control-flow/execute-sql-task.md) and [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="adcc3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="adcc3-105">Options</span></span>  
 <span data-ttu-id="adcc3-106">**Имя переменной**</span><span class="sxs-lookup"><span data-stu-id="adcc3-106">**Variable Name**</span></span>  
 <span data-ttu-id="adcc3-107">Добавив сопоставление параметров нажатием кнопки **Добавить**, выберите системную или определяемую пользователем переменную в списке или щелкните \<**New variable...**> для добавления новой переменной с помощью диалогового окна **Добавление переменной**.</span><span class="sxs-lookup"><span data-stu-id="adcc3-107">After you have added a parameter mapping by clicking **Add**, select a system or user-defined variable from the list or click \<**New variable...**> to add a new variable by using the **Add Variable** dialog box.</span></span>  
  
 <span data-ttu-id="adcc3-108">**См. также:** [Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md)</span><span class="sxs-lookup"><span data-stu-id="adcc3-108">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md)</span></span>  
  
 <span data-ttu-id="adcc3-109">**Направление**</span><span class="sxs-lookup"><span data-stu-id="adcc3-109">**Direction**</span></span>  
 <span data-ttu-id="adcc3-110">Выбор направления для параметра.</span><span class="sxs-lookup"><span data-stu-id="adcc3-110">Select the direction of the parameter.</span></span> <span data-ttu-id="adcc3-111">Сопоставьте каждую переменную с входным параметром, выходным параметром или кодом возврата.</span><span class="sxs-lookup"><span data-stu-id="adcc3-111">Map each variable to an input parameter, output parameter, or a return code.</span></span>  
  
 <span data-ttu-id="adcc3-112">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="adcc3-112">**Data Type**</span></span>  
 <span data-ttu-id="adcc3-113">Выберите тип данных для параметра.</span><span class="sxs-lookup"><span data-stu-id="adcc3-113">Select the data type of the parameter.</span></span> <span data-ttu-id="adcc3-114">Список доступных типов данных зависит от поставщика, который был выбран в диспетчере соединений, используемом задачей.</span><span class="sxs-lookup"><span data-stu-id="adcc3-114">The list of available data types is specific to the provider selected in the connection manager used by the task.</span></span>  
  
 <span data-ttu-id="adcc3-115">**Имя параметра**</span><span class="sxs-lookup"><span data-stu-id="adcc3-115">**Parameter Name**</span></span>  
 <span data-ttu-id="adcc3-116">Введите имя параметра.</span><span class="sxs-lookup"><span data-stu-id="adcc3-116">Provide a parameter name.</span></span>  
  
 <span data-ttu-id="adcc3-117">В зависимости от типа диспетчера соединений, используемого задачей, необходимо использовать числа или имена параметра.</span><span class="sxs-lookup"><span data-stu-id="adcc3-117">Depending on the connection manager type that the task uses, you must use numbers or parameter names.</span></span> <span data-ttu-id="adcc3-118">Для некоторых типов диспетчеров соединений требуется, чтобы в качестве первого символа имени параметра использовался символ \@, а в качестве имен параметров использовались определенные имена, например \@Param1, или имена столбцов.</span><span class="sxs-lookup"><span data-stu-id="adcc3-118">Some connection manager types require that the first character of the parameter name is the \@ sign , specific names like \@Param1, or column names as parameter names.</span></span>  
  
 <span data-ttu-id="adcc3-119">**См. также:** [Параметры и коды возврата в задаче "Выполнение SQL"](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md)</span><span class="sxs-lookup"><span data-stu-id="adcc3-119">**Related Topics:** [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md)</span></span>  
  
 <span data-ttu-id="adcc3-120">**Размер параметра**</span><span class="sxs-lookup"><span data-stu-id="adcc3-120">**Parameter Size**</span></span>  
 <span data-ttu-id="adcc3-121">Укажите размер для параметров, имеющих переменную длину, например, строк и двоичных полей.</span><span class="sxs-lookup"><span data-stu-id="adcc3-121">Provide the size of parameters that have variable length, such as strings and binary fields.</span></span>  
  
 <span data-ttu-id="adcc3-122">Эта настройка гарантирует, что поставщик выделит достаточное пространство для значений параметров изменяемой длины.</span><span class="sxs-lookup"><span data-stu-id="adcc3-122">This setting ensures that the provider allocates sufficient space for variable-length parameter values.</span></span>  
  
 <span data-ttu-id="adcc3-123">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="adcc3-123">**Add**</span></span>  
 <span data-ttu-id="adcc3-124">Нажмите для добавления сопоставления параметра.</span><span class="sxs-lookup"><span data-stu-id="adcc3-124">Click to add a parameter mapping.</span></span>  
  
 <span data-ttu-id="adcc3-125">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="adcc3-125">**Remove**</span></span>  
 <span data-ttu-id="adcc3-126">Выберите сопоставление параметра из списка, затем нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="adcc3-126">Select a parameter mapping in the list and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adcc3-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="adcc3-127">See Also</span></span>  
 <span data-ttu-id="adcc3-128">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="adcc3-128">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="adcc3-129">[Редактор задачи «Выполнение SQL» &#40;страница «Общие»&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="adcc3-129">[Execute SQL Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="adcc3-130">[Редактор задачи "Выполнение SQL" &#40;страница "результирующий набор"&#41;](../../2014/integration-services/execute-sql-task-editor-result-set-page.md) </span><span class="sxs-lookup"><span data-stu-id="adcc3-130">[Execute SQL Task Editor &#40;Result Set Page&#41;](../../2014/integration-services/execute-sql-task-editor-result-set-page.md) </span></span>  
 [<span data-ttu-id="adcc3-131">Справочник по Transact-SQL &#40;ядро СУБД&#41;</span><span class="sxs-lookup"><span data-stu-id="adcc3-131">Transact-SQL Reference &#40;Database Engine&#41;</span></span>](/sql/t-sql/language-reference)  
  
  
