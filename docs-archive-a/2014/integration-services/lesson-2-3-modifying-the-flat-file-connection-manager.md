---
title: Шаг 3. Изменение диспетчера соединений с неструктурированными файлами | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 459e3995-2116-4f15-aaa2-32f26113869c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b897f9412a8f2978ebe4137e3e79bf1d28c97844
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655828"
---
# <a name="step-3-modifying-the-flat-file-connection-manager"></a><span data-ttu-id="e8522-102">Шаг 3. Изменение диспетчера соединений с неструктурированными файлами</span><span class="sxs-lookup"><span data-stu-id="e8522-102">Step 3: Modifying the Flat File Connection Manager</span></span>
  <span data-ttu-id="e8522-103">В этом задании требуется модифицировать диспетчер соединений с неструктурированными файлами, созданный и настроенный на занятии 1.</span><span class="sxs-lookup"><span data-stu-id="e8522-103">In this task, you will modify the Flat File connection manager that you created and configured in Lesson 1.</span></span> <span data-ttu-id="e8522-104">При создании диспетчера соединений неструктурированных файлов он был настроен на статическую загрузку отдельного файла.</span><span class="sxs-lookup"><span data-stu-id="e8522-104">When originally created, the Flat File connection manager was configured to statically load a single file.</span></span> <span data-ttu-id="e8522-105">Чтобы диспетчер соединений с неструктурированными файлами мог последовательно загружать файлы, необходимо изменить свойство ConnectionString диспетчера соединений таким образом, чтобы он принимал пользовательскую переменную `User:varFileName`, содержащую путь к файлу, который должен быть загружен в процессе выполнения.</span><span class="sxs-lookup"><span data-stu-id="e8522-105">To enable the Flat File connection manager to iteratively load files, you must modify the ConnectionString property of the connection manager to accept the user-defined variable `User:varFileName`, which contains the path of the file to be loaded at run time.</span></span>  
  
 <span data-ttu-id="e8522-106">Изменив диспетчер соединений таким образом, чтобы для заполнения свойства ConnectionString использовалось значение пользовательской переменной `User::varFileName`, можно добиться того, чтобы диспетчер соединений подключался к различным неструктурированным файлам.</span><span class="sxs-lookup"><span data-stu-id="e8522-106">By modifying the connection manager to use the value of the user-defined variable, `User::varFileName`, to populate the ConnectionString property of the connection manager, the connection manager will be able to connect to different flat files.</span></span> <span data-ttu-id="e8522-107">При выполнении каждой итерации контейнера «цикл по каждому элементу» будет динамически обновляться переменная `User::varFileName` .</span><span class="sxs-lookup"><span data-stu-id="e8522-107">At run time, each iteration of the Foreach Loop container will dynamically update the `User::varFileName` variable.</span></span> <span data-ttu-id="e8522-108">Обновление переменной в свою очередь вызовет соединение диспетчера со следующим неструктурированным файлом и обработку следующего набора данных задачей потока данных.</span><span class="sxs-lookup"><span data-stu-id="e8522-108">Updating the variable, in turn, causes the connection manager to connect to a different flat file, and the data flow task to process a different set of data.</span></span>  
  
### <a name="to-configure-the-flat-file-connection-manager-to-use-a-variable-for-the-connection-string"></a><span data-ttu-id="e8522-109">Настройка диспетчера соединений с неструктурированными файлами для использования переменной в качестве строки соединения</span><span class="sxs-lookup"><span data-stu-id="e8522-109">To configure the Flat File connection manager to use a variable for the connection string</span></span>  
  
1.  <span data-ttu-id="e8522-110">На панели **Диспетчеры соединений** щелкните правой кнопкой мыши **Образец источника данных "неструктурированный файл"** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e8522-110">In the **Connection Managers** pane, right-click **Sample Flat File Source Data**, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="e8522-111">В окно свойств для **выражения**щелкните пустую ячейку, а затем нажмите кнопку с многоточием **(...)**.</span><span class="sxs-lookup"><span data-stu-id="e8522-111">In the Properties window, for **Expressions**, click in the empty cell, and then click the ellipsis button **(...)**.</span></span>  
  
3.  <span data-ttu-id="e8522-112">В диалоговом окне **Редактор выражений свойств** в столбце **свойство** введите или выберите `ConnectionString` .</span><span class="sxs-lookup"><span data-stu-id="e8522-112">In the **Property Expressions Editor** dialog box, in the **Property** column, type or select `ConnectionString`.</span></span>  
  
4.  <span data-ttu-id="e8522-113">В столбце **выражение** нажмите кнопку с многоточием **(...)** , чтобы открыть диалоговое окно **Построитель выражений** .</span><span class="sxs-lookup"><span data-stu-id="e8522-113">In the **Expression** column, click the ellipsis button **(...)** to open the **Expression Builder** dialog box.</span></span>  
  
5.  <span data-ttu-id="e8522-114">В диалоговом окне **Построитель выражений** разверните узел **Переменные** .</span><span class="sxs-lookup"><span data-stu-id="e8522-114">In the **Expression Builder** dialog box, expand the **Variables** node.</span></span>  
  
6.  <span data-ttu-id="e8522-115">Перетащите переменную **User:: varFileName**в поле **выражение** .</span><span class="sxs-lookup"><span data-stu-id="e8522-115">Drag the variable, **User::varFileName**, into the **Expression** box.</span></span>  
  
7.  <span data-ttu-id="e8522-116">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Построитель выражений** .</span><span class="sxs-lookup"><span data-stu-id="e8522-116">Click **OK** to close the **Expression Builder** dialog box.</span></span>  
  
8.  <span data-ttu-id="e8522-117">Еще раз нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Редактор выражений свойств** .</span><span class="sxs-lookup"><span data-stu-id="e8522-117">Click **OK** again to close the **Property Expressions Editor** dialog box.</span></span>  
  
## <a name="next-lesson-task"></a><span data-ttu-id="e8522-118">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="e8522-118">Next Lesson Task</span></span>  
 [<span data-ttu-id="e8522-119">Шаг 4. Проверка учебного пакета, созданного на занятии 2</span><span class="sxs-lookup"><span data-stu-id="e8522-119">Step 4: Testing the Lesson 2 Tutorial Package</span></span>](../integration-services/lesson-2-4-testing-the-lesson-2-tutorial-package.md)  
  
  
