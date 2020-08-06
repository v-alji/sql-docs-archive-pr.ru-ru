---
title: Создание пользовательских шаблонов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- tql
- templates [Transact-SQL], creating
- templates [Transact-SQL]
ms.assetid: 41098e78-b482-410e-bfe8-2ac10769ac4a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 771547b9c47672d2c075b5e7215d78744fe5f18e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733402"
---
# <a name="create-custom-templates"></a><span data-ttu-id="b052c-102">Создание пользовательских шаблонов</span><span class="sxs-lookup"><span data-stu-id="b052c-102">Create Custom Templates</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="b052c-103">поставляется с шаблонами, с помощью которых можно решить многие стандартные задачи, однако реальная эффективность шаблонов заключается в возможности создания пользовательского шаблона для часто используемых сложных скриптов.</span><span class="sxs-lookup"><span data-stu-id="b052c-103">comes with templates for many common tasks, but the real power of templates lies in the ability to create a custom template for a complex script that you must create frequently.</span></span> <span data-ttu-id="b052c-104">В этом практическом задании будет создан простой скрипт с несколькими параметрами, однако шаблоны применимы и для длинных скриптов с повторениями.</span><span class="sxs-lookup"><span data-stu-id="b052c-104">In this practice you will create a simple script with few parameters, but templates are useful for long, repetitive scripts, too.</span></span>  
  
## <a name="using-custom-templates"></a><span data-ttu-id="b052c-105">Использование пользовательских шаблонов</span><span class="sxs-lookup"><span data-stu-id="b052c-105">Using Custom Templates</span></span>  
  
#### <a name="to-create-a-custom-template"></a><span data-ttu-id="b052c-106">Использование пользовательских шаблонов</span><span class="sxs-lookup"><span data-stu-id="b052c-106">To create a custom template</span></span>  
  
1.  <span data-ttu-id="b052c-107">В обозревателе шаблонов разверните узел **Шаблоны SQL Server**, щелкните правой кнопкой мыши элемент **Хранимая процедура**, наведите указатель на пункт **Создать**и выберите пункт **Папка**.</span><span class="sxs-lookup"><span data-stu-id="b052c-107">In Template Explorer, expand **SQL Server Templates**, right-click **Stored Procedure**, point to **New**, and then click **Folder**.</span></span>  
  
2.  <span data-ttu-id="b052c-108">Введите **Пользовательская** в качестве имени новой папки шаблона и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="b052c-108">Type **Custom** as the name of your new template folder, and then press ENTER.</span></span>  
  
3.  <span data-ttu-id="b052c-109">Щелкните правой кнопкой мыши папку **Пользовательская**, наведите указатель на пункт **Создать**и выберите пункт **Шаблон**.</span><span class="sxs-lookup"><span data-stu-id="b052c-109">Right-click **Custom**, point to **New**, and then click **Template**.</span></span>  
  
4.  <span data-ttu-id="b052c-110">Введите **WorkOrdersProc** в качестве имени нового шаблона и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="b052c-110">Type **WorkOrdersProc** as the name of your new template, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="b052c-111">Щелкните правой кнопкой мыши значок **WorkOrdersProc**и выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="b052c-111">Right-click **WorkOrdersProc**, and then click **Edit**.</span></span>  
  
6.  <span data-ttu-id="b052c-112">В диалоговом окне **Подключиться к ядру СУБД** проверьте сведения о соединении и нажмите кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="b052c-112">In the **Connect to Database Engine** dialog box, verify the connection information and then click **Connect**.</span></span>  
  
7.  <span data-ttu-id="b052c-113">В редакторе запросов введите следующий скрипт, чтобы создать хранимую процедуру, выполняющую поиск заказов для нужной детали, в данном случае роликовых коньков.</span><span class="sxs-lookup"><span data-stu-id="b052c-113">In Query Editor, type the following script to create a stored procedure that looks up orders for a particular part, in this case the Blade.</span></span> <span data-ttu-id="b052c-114">Код сценария можно скопировать из учебника.</span><span class="sxs-lookup"><span data-stu-id="b052c-114">(You can copy and paste the code from the Tutorial window.)</span></span>  
  
    ```  
    USE AdventureWorks20012;  
    GO  
    IF EXISTS (  
    SELECT *   
       FROM INFORMATION_SCHEMA.ROUTINES   
       WHERE SPECIFIC_NAME = 'WorkOrdersForBlade')  
       DROP PROCEDURE dbo.WorkOrdersForBlade;  
    GO  
    CREATE PROCEDURE dbo.WorkOrdersForBlade  
    AS  
    SELECT Name, WorkOrderID   
    FROM Production.WorkOrder AS WO  
    JOIN Production.Product AS Prod  
    ON WO.ProductID = Prod.ProductID  
    WHERE Name = 'Blade';  
    GO  
    ```  
  
8.  <span data-ttu-id="b052c-115">Нажмите клавишу F5, чтобы выполнить скрипт и создать процедуру **WorkOrdersForBlade** .</span><span class="sxs-lookup"><span data-stu-id="b052c-115">Press F5 to execute this script, creating the **WorkOrdersForBlade** procedure.</span></span>  
  
9. <span data-ttu-id="b052c-116">В обозревателе объектов щелкните правой кнопкой мыши свой сервер и выберите команду **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b052c-116">In Object Explorer, right-click your server, and then click **New Query**.</span></span> <span data-ttu-id="b052c-117">Будет открыто новое окно редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="b052c-117">A new Query Editor window opens.</span></span>  
  
10. <span data-ttu-id="b052c-118">В редакторе запросов введите **EXECUTE dbo.WorkOrdersForBlade**и нажмите клавишу F5, чтобы выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="b052c-118">In Query Editor, type **EXECUTE dbo.WorkOrdersForBlade**, and then press F5 to execute the query.</span></span> <span data-ttu-id="b052c-119">Убедитесь в том, что на панели **Результаты** отображается список заказов на производство роликовых коньков.</span><span class="sxs-lookup"><span data-stu-id="b052c-119">Confirm that the **Results** pane returns a list of work orders for blades.</span></span>  
  
11. <span data-ttu-id="b052c-120">Измените скрипт шаблона (сценарий на шаге 7), заменив колонку название продукта параметром <strong> *<* product_name</strong>, `nvarchar(50)` , <strong> *>* Name</strong>, в четырех местах.</span><span class="sxs-lookup"><span data-stu-id="b052c-120">Edit the template script (the script in step 7), replacing the product name Blade with the parameter <strong>*<* product_name</strong>, `nvarchar(50)`, <strong>name*>*</strong>, in four places.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b052c-121">Для параметра необходимо указать три элемента: имя замещаемого параметра, тип данных параметра, значение параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b052c-121">Parameters require three elements: the name of the parameter that you want to replace, the data type of the parameter, and a default value for the parameter.</span></span>  
  
12. <span data-ttu-id="b052c-122">Скрипт должен иметь следующий вид:</span><span class="sxs-lookup"><span data-stu-id="b052c-122">Now the script should look like:</span></span>  
  
    ```  
    USE AdventureWorks20012;  
    GO  
    IF EXISTS (  
    SELECT *   
       FROM INFORMATION_SCHEMA.ROUTINES   
       WHERE SPECIFIC_NAME = 'WorkOrdersFor<product_name, nvarchar(50), name>')  
       DROP PROCEDURE dbo.WorkOrdersFor<product_name, nvarchar(50), name>;  
    GO  
    CREATE PROCEDURE dbo.WorkOrdersFor<product_name, nvarchar(50), name>  
    AS  
    SELECT Name, WorkOrderID   
    FROM Production.WorkOrder AS WO  
    JOIN Production.Product AS Prod  
    ON WO.ProductID = Prod.ProductID  
    WHERE Name = '<product_name, nvarchar(50), name>';  
    GO  
    ```  
  
13. <span data-ttu-id="b052c-123">В меню **Файл** выберите команду **Сохранить WorkOrdersProc.sql** , чтобы сохранить шаблон.</span><span class="sxs-lookup"><span data-stu-id="b052c-123">On the **File** menu, click **Save WorkOrdersProc.sql** to save your template.</span></span>  
  
#### <a name="to-test-the-custom-template"></a><span data-ttu-id="b052c-124">Проверка пользовательского шаблона</span><span class="sxs-lookup"><span data-stu-id="b052c-124">To test the custom template</span></span>  
  
1.  <span data-ttu-id="b052c-125">В обозревателе шаблонов последовательно разверните элементы **Хранимая процедура**и **Пользовательская**, а затем дважды щелкните шаблон **WorkOrderProc**.</span><span class="sxs-lookup"><span data-stu-id="b052c-125">In Template Explorer, expand **Stored Procedure**, expand **Custom**, and then double-click **WorkOrderProc**.</span></span>  
  
2.  <span data-ttu-id="b052c-126">В диалоговом окне **Подключиться к ядру СУБД** введите сведения о соединении и нажмите кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="b052c-126">In the **Connect to Database Engine** dialog box, complete the connection information and then click **Connect**.</span></span> <span data-ttu-id="b052c-127">Откроется новое окно редактора запросов, в котором приводится содержимое шаблона **WorkOrderProc** .</span><span class="sxs-lookup"><span data-stu-id="b052c-127">A new Query Editor window opens, containing the contents of the **WorkOrderProc** template.</span></span>  
  
3.  <span data-ttu-id="b052c-128">В меню **Запрос** выберите пункт **Указать значения для параметров шаблона**.</span><span class="sxs-lookup"><span data-stu-id="b052c-128">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
4.  <span data-ttu-id="b052c-129">В диалоговом окне **Замена параметров шаблона** в поле `product_name` значение введите **Freewheel** (перезапись содержимого по умолчанию), а затем нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Замена параметров шаблона** и изменить скрипт в редакторе запросов.</span><span class="sxs-lookup"><span data-stu-id="b052c-129">In the **Replace Template Parameters** dialog box, for the `product_name` value, type **FreeWheel** (overwriting the default contents), and then click **OK** to close the **Replace Template Parameters** dialog box and modify the script in the Query Editor.</span></span>  
  
5.  <span data-ttu-id="b052c-130">Нажмите F5, чтобы выполнить запрос и создать процедуру.</span><span class="sxs-lookup"><span data-stu-id="b052c-130">Press F5 to execute the query, creating the procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b052c-131">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="b052c-131">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b052c-132">Сохранение скриптов в виде проектов или решений</span><span class="sxs-lookup"><span data-stu-id="b052c-132">Save Scripts as Projects or Solutions</span></span>](lesson-3-3-save-scripts-as-projects-or-solutions.md)  
  
  
