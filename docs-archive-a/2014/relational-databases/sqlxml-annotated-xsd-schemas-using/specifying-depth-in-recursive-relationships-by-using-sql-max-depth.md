---
title: 'Указание глубины рекурсивных связей с помощью SQL: max-depth | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- max-depth annotation
- XPath queries [SQLXML], recursive relationships
- depth in recursive relationships [SQLXML]
- annotated XSD schemas, recursive relationships
- relationships [SQLXML], recursive relationships
- self joins
- recursive relationships [SQLXML]
- recursion [SQLXML]
- sql:max-depth
- recursive joins [SQLXML]
ms.assetid: 0ffdd57d-dc30-44d9-a8a0-f21cadedb327
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e3ccb2de9c7b2ac8f8702b52aa990d755620e46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665263"
---
# <a name="specifying-depth-in-recursive-relationships-by-using-sqlmax-depth"></a><span data-ttu-id="75a4f-102">Задание глубины рекурсивных связей с использованием sql:max-depth</span><span class="sxs-lookup"><span data-stu-id="75a4f-102">Specifying Depth in Recursive Relationships by Using sql:max-depth</span></span>
  <span data-ttu-id="75a4f-103">В реляционных базах данных участие таблицы в связи с самой собой называется рекурсивной связью.</span><span class="sxs-lookup"><span data-stu-id="75a4f-103">In relational databases, when a table is involved in a relationship with itself, it is called a recursive relationship.</span></span> <span data-ttu-id="75a4f-104">Например, таблица, в которой содержатся записи о сотрудниках и возможны связи «начальник-подчиненный», участвует в связи сама с собой.</span><span class="sxs-lookup"><span data-stu-id="75a4f-104">For example, in a supervisor-supervisee relationship, a table storing employee records is involved in a relationship with itself.</span></span> <span data-ttu-id="75a4f-105">В этом случае таблица сотрудников выполняет роль начальника на одной стороне связи и та же таблица выполняет роль подчиненного на другой стороне.</span><span class="sxs-lookup"><span data-stu-id="75a4f-105">In this case, the employees table plays a role of supervisor on one side of the relationship, and the same table plays a role of supervisee on the other side.</span></span>  
  
 <span data-ttu-id="75a4f-106">Схемы сопоставления могут включать рекурсивные связи, в которых элемент и его предок относятся к одному типу.</span><span class="sxs-lookup"><span data-stu-id="75a4f-106">Mapping schemas can include recursive relationships where an element and its ancestor are of the same type.</span></span>  
  
## <a name="example-a"></a><span data-ttu-id="75a4f-107">Пример A</span><span class="sxs-lookup"><span data-stu-id="75a4f-107">Example A</span></span>  
 <span data-ttu-id="75a4f-108">Рассмотрим следующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="75a4f-108">Consider the following table:</span></span>  
  
```  
Emp (EmployeeID, FirstName, LastName, ReportsTo)  
```  
  
 <span data-ttu-id="75a4f-109">В этой таблице столбец ReportsTo содержит идентификатор служащего для менеджера.</span><span class="sxs-lookup"><span data-stu-id="75a4f-109">In this table, the ReportsTo column stores the employee ID of the manager.</span></span>  
  
 <span data-ttu-id="75a4f-110">Предположим, что нужно сформировать XML-иерархию служащих, на вершине которой находится менеджер, а служащие, подчиненные менеджеру, отображаются в соответствующей иерархии, как показано в следующем образце XML-фрагмента.</span><span class="sxs-lookup"><span data-stu-id="75a4f-110">Assume that you want to generate an XML hierarchy of employees in which the manager employee is at the top of the hierarchy, and in which the employees that report to that manager appear in the corresponding hierarchy as shown in the following sample XML fragment.</span></span> <span data-ttu-id="75a4f-111">Этот фрагмент показывает *рекурсивное дерево* для сотрудника 1.</span><span class="sxs-lookup"><span data-stu-id="75a4f-111">What this fragment shows is the *recursive tree* for employee 1.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <Emp FirstName="Nancy" EmployeeID="1" LastName="Devolio">  
     <Emp FirstName="Andrew" EmployeeID="2" LastName="Fuller" />   
     <Emp FirstName="Janet" EmployeeID="3" LastName="Leverling">  
        <Emp FirstName="Margaret" EmployeeID="4" LastName="Peacock">  
          <Emp FirstName="Steven" EmployeeID="5" LastName="Devolio">  
...  
...  
</root>  
```  
  
 <span data-ttu-id="75a4f-112">В этом фрагменте служащий 5 подчинен служащему 4, служащий 4 подчинен служащему 3, а служащие 3 и 2 подчинены служащему 1.</span><span class="sxs-lookup"><span data-stu-id="75a4f-112">In this fragment, employee 5 reports to employee 4, employee 4 reports to employee 3, and employees 3 and 2 reports to employee 1.</span></span>  
  
 <span data-ttu-id="75a4f-113">Чтобы получить этот результат, можно использовать следующую схему XSD и указать запрос XPath к ней.</span><span class="sxs-lookup"><span data-stu-id="75a4f-113">To produce this result, you can use the following XSD schema and specify an XPath query against it.</span></span> <span data-ttu-id="75a4f-114">Схема описывает **\<Emp>** элемент типа типсотрудника, состоящий из **\<Emp>** дочернего элемента того же типа, типсотрудника.</span><span class="sxs-lookup"><span data-stu-id="75a4f-114">The schema describes an **\<Emp>** element of type EmployeeType, consisting of an **\<Emp>** child element of the same type, EmployeeType.</span></span> <span data-ttu-id="75a4f-115">Это рекурсивная связь (элемент и его предок относятся к одному типу).</span><span class="sxs-lookup"><span data-stu-id="75a4f-115">This is a recursive relationship (the element and its ancestor are of the same type).</span></span> <span data-ttu-id="75a4f-116">Кроме того, схема использует **\<sql:relationship>** для описания связи «родители-потомки» между супервизором и администратором.</span><span class="sxs-lookup"><span data-stu-id="75a4f-116">In addition, the schema uses a **\<sql:relationship>** to describe the parent-child relationship between the supervisor and supervisee.</span></span> <span data-ttu-id="75a4f-117">Обратите внимание, что в этом **\<sql:relationship>** случае EMP является родительской и дочерней таблицей.</span><span class="sxs-lookup"><span data-stu-id="75a4f-117">Note that in this **\<sql:relationship>**, Emp is both the parent and the child table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"  
                                  parent="Emp"  
                                  parent-key="EmployeeID"  
                                  child="Emp"  
                                  child-key="ReportsTo" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp" type="EmployeeType"   
                          sql:relation="Emp"   
                          sql:key-fields="EmployeeID"   
                          sql:limit-field="ReportsTo" />  
  <xsd:complexType name="EmployeeType">  
    <xsd:sequence>  
      <xsd:element name="Emp" type="EmployeeType"   
                              sql:relation="Emp"   
                              sql:key-fields="EmployeeID"  
                              sql:relationship="SupervisorSupervisee"  
                              sql:max-depth="6" />  
    </xsd:sequence>   
    <xsd:attribute name="EmployeeID" type="xsd:ID" />  
    <xsd:attribute name="FirstName" type="xsd:string"/>  
    <xsd:attribute name="LastName" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="75a4f-118">Поскольку связь рекурсивная, необходимо каким-то образом указать глубину рекурсии в схеме.</span><span class="sxs-lookup"><span data-stu-id="75a4f-118">Because the relationship is recursive, you need some way to specify the depth of recursion in the schema.</span></span> <span data-ttu-id="75a4f-119">В противном случае результатом будет бесконечная рекурсия (служащий, подчиненный служащему, подчиненному служащему, и т. д.).</span><span class="sxs-lookup"><span data-stu-id="75a4f-119">Otherwise, the result will be an endless recursion (employee reporting to employee reporting to employee, and so on).</span></span> <span data-ttu-id="75a4f-120">Заметка `sql:max-depth` позволяет указать максимальную глубину рекурсии.</span><span class="sxs-lookup"><span data-stu-id="75a4f-120">The `sql:max-depth` annotation allows you to specify how deep in the recursion to go.</span></span> <span data-ttu-id="75a4f-121">В данном конкретном примере, чтобы указать значение `sql:max-depth`, необходимо знать глубину иерархии менеджмента в компании.</span><span class="sxs-lookup"><span data-stu-id="75a4f-121">In this particular example, to specify a value for `sql:max-depth`, you must know how deep the management hierarchy goes in the company.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="75a4f-122">Схема задает заметку `sql:limit-field`, но не содержит заметку `sql:limit-value`.</span><span class="sxs-lookup"><span data-stu-id="75a4f-122">The schema specifies the `sql:limit-field` annotation, but does not specify the `sql:limit-value` annotation.</span></span> <span data-ttu-id="75a4f-123">Это ограничивает верхний узел в результирующей иерархии только служащими, которые не подчиняются никому.</span><span class="sxs-lookup"><span data-stu-id="75a4f-123">This limits the top node in the resulting hierarchy to only those employees who do not report to anyone.</span></span> <span data-ttu-id="75a4f-124">(Подчиняется NULL.) При указании `sql:limit-field` и не указании `sql:limit-value` (значение по умолчанию NULL) это достигается.</span><span class="sxs-lookup"><span data-stu-id="75a4f-124">(ReportsTo is NULL.) Specifying `sql:limit-field` and not specifying `sql:limit-value` (which defaults to NULL) annotation accomplishes this.</span></span> <span data-ttu-id="75a4f-125">Если нужно, чтобы результирующий XML включал все возможные деревья подчиненности (дерево подчиненности для каждого служащего в таблице), удалите заметку `sql:limit-field` из схемы.</span><span class="sxs-lookup"><span data-stu-id="75a4f-125">If you want the resulting XML to include every possible reporting tree (the reporting tree for every employee in the table), remove the `sql:limit-field` annotation from the schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="75a4f-126">В следующей процедуре используется база данных tempdb.</span><span class="sxs-lookup"><span data-stu-id="75a4f-126">The following procedure uses the tempdb database.</span></span>  
  
#### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="75a4f-127">Проверка образца запроса XPath к схеме</span><span class="sxs-lookup"><span data-stu-id="75a4f-127">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="75a4f-128">Создайте образец таблицы с именем Emp в базе данных tempdb, на которую указывает виртуальный корневой каталог.</span><span class="sxs-lookup"><span data-stu-id="75a4f-128">Create a sample table called Emp in the tempdb database to which the virtual root points.</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Emp (  
           EmployeeID int primary key,   
           FirstName  varchar(20),   
           LastName   varchar(20),   
           ReportsTo int)  
    ```  
  
2.  <span data-ttu-id="75a4f-129">Добавьте следующий образец данных:</span><span class="sxs-lookup"><span data-stu-id="75a4f-129">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Emp values (1, 'Nancy', 'Devolio',NULL)  
    INSERT INTO Emp values (2, 'Andrew', 'Fuller',1)  
    INSERT INTO Emp values (3, 'Janet', 'Leverling',1)  
    INSERT INTO Emp values (4, 'Margaret', 'Peacock',3)  
    INSERT INTO Emp values (5, 'Steven', 'Devolio',4)  
    INSERT INTO Emp values (6, 'Nancy', 'Buchanan',5)  
    INSERT INTO Emp values (7, 'Michael', 'Suyama',6)  
    ```  
  
3.  <span data-ttu-id="75a4f-130">Скопируйте приведенный выше код схемы и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="75a4f-130">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="75a4f-131">Сохраните файл под именем maxDepth.xml.</span><span class="sxs-lookup"><span data-stu-id="75a4f-131">Save the file as maxDepth.xml.</span></span>  
  
4.  <span data-ttu-id="75a4f-132">Скопируйте следующий шаблон и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="75a4f-132">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="75a4f-133">Сохраните файл под именем maxDepthT.xml в том же каталоге, где был сохранен файл maxDepth.xml.</span><span class="sxs-lookup"><span data-stu-id="75a4f-133">Save the file as maxDepthT.xml in the same directory where you saved maxDepth.xml.</span></span> <span data-ttu-id="75a4f-134">Запрос в шаблоне возвращает всех сотрудников в таблице Emp.</span><span class="sxs-lookup"><span data-stu-id="75a4f-134">The query in the template returns all the employees in the Emp table.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="maxDepth.xml">  
        /Emp  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="75a4f-135">Путь к каталогу схемы сопоставления (файл maxDepth.xml) задается относительно каталога, в котором сохранен шаблон.</span><span class="sxs-lookup"><span data-stu-id="75a4f-135">The directory path specified for the mapping schema (maxDepth.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="75a4f-136">Можно также задать абсолютный путь, например:</span><span class="sxs-lookup"><span data-stu-id="75a4f-136">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\maxDepth.xml"  
    ```  
  
5.  <span data-ttu-id="75a4f-137">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="75a4f-137">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span> <span data-ttu-id="75a4f-138">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="75a4f-138">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="75a4f-139">Результат:</span><span class="sxs-lookup"><span data-stu-id="75a4f-139">This is the result:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <Emp FirstName="Nancy" EmployeeID="1" LastName="Devolio">  
  <Emp FirstName="Andrew" EmployeeID="2" LastName="Fuller" />   
    <Emp FirstName="Janet" EmployeeID="3" LastName="Leverling">  
      <Emp FirstName="Margaret" EmployeeID="4" LastName="Peacock">  
        <Emp FirstName="Steven" EmployeeID="5" LastName="Devolio">  
          <Emp FirstName="Nancy" EmployeeID="6" LastName="Buchanan">  
            <Emp FirstName="Michael" EmployeeID="7" LastName="Suyama" />   
          </Emp>  
        </Emp>  
      </Emp>  
    </Emp>  
  </Emp>  
</root>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="75a4f-140">Чтобы получить различные глубины иерархий в результате, измените значение заметки `sql:max-depth` в схеме и вновь выполните шаблон после каждого изменения.</span><span class="sxs-lookup"><span data-stu-id="75a4f-140">To produce different depths of hierarchies in the result, change the value of the `sql:max-depth` annotation in the schema and execute the template again after each change.</span></span>  
  
 <span data-ttu-id="75a4f-141">В предыдущей схеме все **\<Emp>** элементы имели одинаковый набор атрибутов (**EmployeeID**, **FirstName**и **LastName**).</span><span class="sxs-lookup"><span data-stu-id="75a4f-141">In the previous schema, all the **\<Emp>** elements had exactly the same set of attributes (**EmployeeID**, **FirstName**, and **LastName**).</span></span> <span data-ttu-id="75a4f-142">Следующая схема была немного изменена, чтобы вернуть дополнительный атрибут **подчиняется** для всех **\<Emp>** элементов, подчиненных руководителю.</span><span class="sxs-lookup"><span data-stu-id="75a4f-142">The following schema has been slightly modified to return an additional **ReportsTo** attribute for all the **\<Emp>** elements that report to a manager.</span></span>  
  
 <span data-ttu-id="75a4f-143">Например, этот XML-фрагмент показывает подчиненных служащего 1:</span><span class="sxs-lookup"><span data-stu-id="75a4f-143">For example, this XML fragment shows the subordinates of employee 1:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
<Emp FirstName="Nancy" EmployeeID="1" LastName="Devolio">  
  <Emp FirstName="Andrew" EmployeeID="2"   
       ReportsTo="1" LastName="Fuller" />   
  <Emp FirstName="Janet" EmployeeID="3"   
       ReportsTo="1" LastName="Leverling">  
...  
...  
```  
  
 <span data-ttu-id="75a4f-144">Ниже приведена измененная схема:</span><span class="sxs-lookup"><span data-stu-id="75a4f-144">This is the revised schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:documentation>  
      Customer-Order-Order Details Schema  
      Copyright 2000 Microsoft. All rights reserved.  
    </xsd:documentation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"   
                  parent="Emp"  
                  parent-key="EmployeeID"  
                  child="Emp"  
                  child-key="ReportsTo" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp"   
                   type="EmpType"   
                   sql:relation="Emp"   
                   sql:key-fields="EmployeeID"   
                   sql:limit-field="ReportsTo" />  
  <xsd:complexType name="EmpType">  
    <xsd:sequence>  
       <xsd:element name="Emp"   
                    type="EmpType"   
                    sql:relation="Emp"   
                    sql:key-fields="EmployeeID"  
                    sql:relationship="SupervisorSupervisee"  
                    sql:max-depth="6"/>  
    </xsd:sequence>   
    <xsd:attribute name="EmployeeID" type="xsd:int" />  
    <xsd:attribute name="FirstName" type="xsd:string"/>  
    <xsd:attribute name="LastName" type="xsd:string"/>  
    <xsd:attribute name="ReportsTo" type="xsd:int" />  
  </xsd:complexType>  
</xsd:schema>  
```  
  
## <a name="sqlmax-depth-annotation"></a><span data-ttu-id="75a4f-145">Заметка sql:max-depth</span><span class="sxs-lookup"><span data-stu-id="75a4f-145">sql:max-depth Annotation</span></span>  
 <span data-ttu-id="75a4f-146">В схеме, состоящей из рекурсивных связей, глубина рекурсии должна быть явно указана в схеме.</span><span class="sxs-lookup"><span data-stu-id="75a4f-146">In a schema consisting of recursive relationships, the depth of recursion must be explicitly specified in the schema.</span></span> <span data-ttu-id="75a4f-147">Это необходимо для успешной подготовки соответствующего запроса FOR XML EXPLICIT, который возвращает запрошенные результаты.</span><span class="sxs-lookup"><span data-stu-id="75a4f-147">This is required to successfully produce the corresponding FOR XML EXPLICIT query that returns the requested results.</span></span>  
  
 <span data-ttu-id="75a4f-148">Используйте заметку `sql:max-depth` в схеме, чтобы указать глубину рекурсии в рекурсивной связи, описанной в схеме.</span><span class="sxs-lookup"><span data-stu-id="75a4f-148">Use the `sql:max-depth` annotation in the schema to specify the depth of recursion in a recursive relationship that is described in the schema.</span></span> <span data-ttu-id="75a4f-149">Значением `sql:max-depth` аннотации является положительное целое число (от 1 до 50), которое указывает количество рекурсий: значение 1 останавливает рекурсию в элементе, для которого `sql:max-depth` указана заметка; значение 2 останавливает рекурсию на следующем уровне элемента, где `sql:max-depth` указан, и т. д.</span><span class="sxs-lookup"><span data-stu-id="75a4f-149">The value of the `sql:max-depth` annotation is a positive integer (1 to 50) that indicates the number of recursions:  A value of 1 stops the recursion at the element for which the `sql:max-depth` annotation is specified; a value of 2 stops the recursion at the next level from the element at which `sql:max-depth` is specified; and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="75a4f-150">В базовой реализации запрос XPath, заданный для схемы сопоставления, преобразуется в SELECT... Запрос FOR XML EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="75a4f-150">In the underlying implementation, an XPath query that is specified against a mapping schema is converted to a SELECT ... FOR XML EXPLICIT query.</span></span> <span data-ttu-id="75a4f-151">Для этого запроса необходимо указать конечную глубину рекурсии.</span><span class="sxs-lookup"><span data-stu-id="75a4f-151">This query requires you to specify a finite depth of recursion.</span></span> <span data-ttu-id="75a4f-152">Чем выше значение, указанное для `sql:max-depth`, тем больше формируемый запрос FOR XML EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="75a4f-152">The higher the value that you specify for `sql:max-depth`, the larger the FOR XML EXPLICIT query that is generated.</span></span> <span data-ttu-id="75a4f-153">Это может увеличить время выборки.</span><span class="sxs-lookup"><span data-stu-id="75a4f-153">This might slow the retrieval time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="75a4f-154">Диаграммы обновления и массовая загрузка XML не учитывают заметку max-depth.</span><span class="sxs-lookup"><span data-stu-id="75a4f-154">Updategrams and XML Bulk Load ignore the max-depth annotation.</span></span> <span data-ttu-id="75a4f-155">Это означает, что рекурсивные обновления и вставки будут происходить независимо от значения, заданного для max-depth.</span><span class="sxs-lookup"><span data-stu-id="75a4f-155">This means, recursive updates or insertions will happen regardless of what value you specify for max-depth.</span></span>  
  
## <a name="specifying-sqlmax-depth-on-complex-elements"></a><span data-ttu-id="75a4f-156">Задание sql:max-depth для сложных элементов</span><span class="sxs-lookup"><span data-stu-id="75a4f-156">Specifying sql:max-depth on Complex Elements</span></span>  
 <span data-ttu-id="75a4f-157">Заметка `sql:max-depth` может быть указана в любом сложном элементе содержимого.</span><span class="sxs-lookup"><span data-stu-id="75a4f-157">The `sql:max-depth` annotation can be specified on any complex content element.</span></span>  
  
### <a name="recursive-elements"></a><span data-ttu-id="75a4f-158">Рекурсивные элементы</span><span class="sxs-lookup"><span data-stu-id="75a4f-158">Recursive Elements</span></span>  
 <span data-ttu-id="75a4f-159">Если заметка `sql:max-depth` указана как на родительском элементе, так и на дочернем элементе в рекурсивной связи, то заметка `sql:max-depth` на родительском элементе имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="75a4f-159">If `sql:max-depth` is specified on both the parent element and the child element in a recursive relationship, the `sql:max-depth` annotation specified on the parent takes precedence.</span></span> <span data-ttu-id="75a4f-160">Например, в следующей схеме заметка `sql:max-depth` указана как для родительского, так и для дочернего элемента сотрудников.</span><span class="sxs-lookup"><span data-stu-id="75a4f-160">For example, in the following schema, the `sql:max-depth` annotation is specified on both the parent and the child employee elements.</span></span> <span data-ttu-id="75a4f-161">В этом случае `sql:max-depth=4` приоритет имеет значение, заданное для **\<Emp>** родительского элемента (который играет роль супервизора).</span><span class="sxs-lookup"><span data-stu-id="75a4f-161">In this case, `sql:max-depth=4`, specified on the **\<Emp>** parent element (playing a role of supervisor), takes precedence.</span></span> <span data-ttu-id="75a4f-162">Объект, `sql:max-depth` указанный в дочернем **\<Emp>** элементе (играет роль контролируемого элемента), игнорируется.</span><span class="sxs-lookup"><span data-stu-id="75a4f-162">The `sql:max-depth` specified on the child **\<Emp>** element (playing a role of supervisee) is ignored.</span></span>  
  
#### <a name="example-b"></a><span data-ttu-id="75a4f-163">Пример Б</span><span class="sxs-lookup"><span data-stu-id="75a4f-163">Example B</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"  
                                  parent="Emp"  
                                  parent-key="EmployeeID"  
                                  child="Emp"  
                                  child-key="ReportsTo" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp" type="EmployeeType"   
                          sql:relation="Emp"   
                          sql:key-fields="EmployeeID"   
                          sql:limit-field="ReportsTo"   
                          sql:max-depth="3" />  
  <xsd:complexType name="EmployeeType">  
    <xsd:sequence>  
      <xsd:element name="Emp" type="EmployeeType"   
                              sql:relation="Emp"   
                              sql:key-fields="EmployeeID"  
                              sql:relationship="SupervisorSupervisee"  
                              sql:max-depth="2" />  
    </xsd:sequence>   
    <xsd:attribute name="EmployeeID" type="xsd:ID" />  
    <xsd:attribute name="FirstName" type="xsd:string"/>  
    <xsd:attribute name="LastName" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="75a4f-164">Для проверки этой схемы выполните шаги, приведенные для образца А ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="75a4f-164">To test this schema, follow the steps provided for Sample A, earlier in this topic.</span></span>  
  
### <a name="nonrecursive-elements"></a><span data-ttu-id="75a4f-165">Нерекурсивные элементы</span><span class="sxs-lookup"><span data-stu-id="75a4f-165">Nonrecursive Elements</span></span>  
 <span data-ttu-id="75a4f-166">Заметка `sql:max-depth` не учитывается, если она указана для элемента в схеме, которая не вызывает рекурсии.</span><span class="sxs-lookup"><span data-stu-id="75a4f-166">If the `sql:max-depth` annotation is specified on an element in the schema that does not cause any recursion, it is ignored.</span></span> <span data-ttu-id="75a4f-167">В следующей схеме **\<Emp>** элемент состоит из **\<Constant>** дочернего элемента, который, в свою очередь, имеет **\<Emp>** дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="75a4f-167">In the following schema, an **\<Emp>** element consists of a **\<Constant>** child element, which, in turn, has an **\<Emp>** child element.</span></span>  
  
 <span data-ttu-id="75a4f-168">В этой схеме `sql:max-depth` заметка, указанная в **\<Constant>** элементе, игнорируется, поскольку между **\<Emp>** родительским и **\<Constant>** дочерним элементами отсутствует рекурсия.</span><span class="sxs-lookup"><span data-stu-id="75a4f-168">In this schema, the `sql:max-depth` annotation specified on the **\<Constant>** element is ignored because there is no recursion between the **\<Emp>** parent and the **\<Constant>** child element.</span></span> <span data-ttu-id="75a4f-169">Но существует рекурсия между **\<Emp>** предком и **\<Emp>** дочерним объектом.</span><span class="sxs-lookup"><span data-stu-id="75a4f-169">But there is recursion between the **\<Emp>** ancestor and the **\<Emp>** child.</span></span> <span data-ttu-id="75a4f-170">В схеме заметка `sql:max-depth` указывается для обоих элементов.</span><span class="sxs-lookup"><span data-stu-id="75a4f-170">The schema specifies the `sql:max-depth` annotation on both.</span></span> <span data-ttu-id="75a4f-171">Поэтому `sql:max-depth` приоритет имеет заметку, указанную для предка ( **\<Emp>** в роли супервизора).</span><span class="sxs-lookup"><span data-stu-id="75a4f-171">Therefore, the `sql:max-depth` annotation that is specified on the ancestor (**\<Emp>** in the supervisor role) takes precedence.</span></span>  
  
#### <a name="example-c"></a><span data-ttu-id="75a4f-172">Пример В</span><span class="sxs-lookup"><span data-stu-id="75a4f-172">Example C</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"   
                  parent="Emp"   
                  child="Emp"   
                  parent-key="EmployeeID"   
                  child-key="ReportsTo"/>  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp"   
               sql:relation="Emp"   
               type="EmpType"  
               sql:limit-field="ReportsTo"  
               sql:max-depth="1" />  
    <xsd:complexType name="EmpType" >  
      <xsd:sequence>  
       <xsd:element name="Constant"   
                    sql:is-constant="1"   
                    sql:max-depth="20" >  
         <xsd:complexType >  
           <xsd:sequence>  
            <xsd:element name="Emp"   
                         sql:relation="Emp" type="EmpType"  
                         sql:relationship="SupervisorSupervisee"   
                         sql:max-depth="3" />  
         </xsd:sequence>  
         </xsd:complexType>  
         </xsd:element>  
      </xsd:sequence>  
      <xsd:attribute name="EmployeeID" type="xsd:int" />  
    </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="75a4f-173">Для проверки этой схемы выполните шаги, приведенные для примера А ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="75a4f-173">To test this schema, follow the steps provided for Example A, earlier in this topic.</span></span>  
  
## <a name="complex-types-derived-by-restriction"></a><span data-ttu-id="75a4f-174">Сложные типы, наследуемые по ограничению</span><span class="sxs-lookup"><span data-stu-id="75a4f-174">Complex Types Derived by Restriction</span></span>  
 <span data-ttu-id="75a4f-175">При наличии сложного типа, производного от **\<restriction>** , элементы соответствующего базового сложного типа не могут указать `sql:max-depth` заметку.</span><span class="sxs-lookup"><span data-stu-id="75a4f-175">If you have a complex type derivation by **\<restriction>**, elements of the corresponding base complex type cannot specify the `sql:max-depth` annotation.</span></span> <span data-ttu-id="75a4f-176">В этих случаях заметка `sql:max-depth` может быть добавлена к элементу производного типа.</span><span class="sxs-lookup"><span data-stu-id="75a4f-176">In these cases, the `sql:max-depth` annotation can be added to the element of the derived type.</span></span>  
  
 <span data-ttu-id="75a4f-177">С другой стороны, если имеется сложный тип, производный от **\<extension>** , элементы соответствующего базового сложного типа могут указать `sql:max-depth` заметку.</span><span class="sxs-lookup"><span data-stu-id="75a4f-177">On the other hand, if you have a complex type derivation by **\<extension>**, the elements of the corresponding base complex type can specify the `sql:max-depth` annotation.</span></span>  
  
 <span data-ttu-id="75a4f-178">Например, следующая схема XSD вызывает ошибку, так как заметка `sql:max-depth` указывается в базовом типе.</span><span class="sxs-lookup"><span data-stu-id="75a4f-178">For example, the following XSD schema generates an error because the `sql:max-depth` annotation is specified on the base type.</span></span> <span data-ttu-id="75a4f-179">Эта аннотация не поддерживается для типа, производного **\<restriction>** от другого типа.</span><span class="sxs-lookup"><span data-stu-id="75a4f-179">This annotation is not supported on a type that is derived by **\<restriction>** from another type.</span></span> <span data-ttu-id="75a4f-180">Чтобы устранить эту проблему, необходимо изменить схему и указать заметку `sql:max-depth` в элементе производного типа.</span><span class="sxs-lookup"><span data-stu-id="75a4f-180">To fix this problem, you must change the schema and specify the `sql:max-depth` annotation on element in the derived type.</span></span>  
  
#### <a name="example-d"></a><span data-ttu-id="75a4f-181">Пример Г</span><span class="sxs-lookup"><span data-stu-id="75a4f-181">Example D</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:msdata="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:complexType name="CustomerBaseType">   
    <xsd:sequence>  
       <xsd:element name="CID" msdata:field="CustomerID" />  
       <xsd:element name="CompanyName"/>  
       <xsd:element name="Customers" msdata:max-depth="3">  
         <xsd:annotation>  
           <xsd:appinfo>  
             <msdata:relationship  
                     parent="Customers"  
                     parent-key="CustomerID"  
                     child-key="CustomerID"  
                     child="Customers" />  
           </xsd:appinfo>  
         </xsd:annotation>  
       </xsd:element>  
    </xsd:sequence>  
  </xsd:complexType>  
  <xsd:element name="Customers" type="CustomerType"/>  
  <xsd:complexType name="CustomerType">  
    <xsd:complexContent>  
       <xsd:restriction base="CustomerBaseType">  
          <xsd:sequence>  
            <xsd:element name="CID"   
                         type="xsd:string"/>  
            <xsd:element name="CompanyName"   
                         type="xsd:string"  
                         msdata:field="CName" />  
            <xsd:element name="Customers"   
                         type="CustomerType" />  
          </xsd:sequence>  
       </xsd:restriction>  
    </xsd:complexContent>  
  </xsd:complexType>  
</xsd:schema>   
```  
  
 <span data-ttu-id="75a4f-182">В схеме задана заметка `sql:max-depth` в сложном типе `CustomerBaseType`.</span><span class="sxs-lookup"><span data-stu-id="75a4f-182">In the schema, `sql:max-depth` is specified on a `CustomerBaseType` complex type.</span></span> <span data-ttu-id="75a4f-183">Схема также задает **\<Customer>** элемент типа `CustomerType` , который является производным от `CustomerBaseType` .</span><span class="sxs-lookup"><span data-stu-id="75a4f-183">The schema also specifies a **\<Customer>** element of type `CustomerType`, which is derived from `CustomerBaseType`.</span></span> <span data-ttu-id="75a4f-184">Запрос XPath, указанный для такой схемы, выдаст ошибку, так как заметка `sql:max-depth` не поддерживается в элементе, определенном в базовом типе по ограничению.</span><span class="sxs-lookup"><span data-stu-id="75a4f-184">An XPath query specified on such a schema will generate an error, because `sql:max-depth` is not supported on an element that is defined in a restriction base type.</span></span>  
  
## <a name="schemas-with-a-deep-hierarchy"></a><span data-ttu-id="75a4f-185">Схемы с глубокой иерархией</span><span class="sxs-lookup"><span data-stu-id="75a4f-185">Schemas with a Deep Hierarchy</span></span>  
 <span data-ttu-id="75a4f-186">Схема может иметь глубокую иерархию, в которой элемент содержит дочерний элемент, который в свою очередь содержит другой дочерний элемент, и т. д.</span><span class="sxs-lookup"><span data-stu-id="75a4f-186">You might have a schema that includes a deep hierarchy in which an element contains a child element, which in turn contains another child element, and so on.</span></span> <span data-ttu-id="75a4f-187">Если заметка `sql:max-depth`, указанная в такой схеме, формирует XML-документ, включающий иерархию из более чем 500 уровней (элемент верхнего уровня считается уровнем 1, его потомок считается уровнем 2, и т. д.), то возвращается ошибка.</span><span class="sxs-lookup"><span data-stu-id="75a4f-187">If the `sql:max-depth` annotation specified in such a schema generates an XML document that includes a hierarchy of more than 500 levels (with top-level element at level 1, its child at level 2, and so on), an error is returned.</span></span>  
  
  
