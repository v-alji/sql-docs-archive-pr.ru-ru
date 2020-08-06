---
title: Триггеры CLR | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- inserted tables
- database objects [CLR integration], triggers
- common language runtime [SQL Server], triggers
- updated columns
- building database objects [CLR integration], triggers
- triggers [CLR integration]
- deleted tables
- EventData property
- SqlTriggerContext class
- transactions [CLR integration]
ms.assetid: 302a4e4a-3172-42b6-9cc0-4a971ab49c1c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 91f12b0d97d2e2065c5bb08d175253c22dffb032
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657251"
---
# <a name="clr-triggers"></a><span data-ttu-id="e7b13-102">Триггеры CLR</span><span class="sxs-lookup"><span data-stu-id="e7b13-102">CLR Triggers</span></span>
  <span data-ttu-id="e7b13-103">Благодаря тому что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] интегрирован со средой [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR, для создания триггеров CLR можно использовать любой язык [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7b13-103">Because of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integration with the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] common language runtime (CLR), you can use any [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] language to create CLR triggers.</span></span> <span data-ttu-id="e7b13-104">В настоящем разделе рассматриваются сведения, касающиеся реализации триггеров в условиях интеграции со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="e7b13-104">This section covers information specific to triggers implemented with CLR integration.</span></span> <span data-ttu-id="e7b13-105">Полное описание триггеров см. в разделе [триггеры DDL](../../relational-databases/triggers/ddl-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="e7b13-105">For a complete discussion of triggers, see [DDL Triggers](../../relational-databases/triggers/ddl-triggers.md).</span></span>  
  
## <a name="what-are-triggers"></a><span data-ttu-id="e7b13-106">Что такое триггеры?</span><span class="sxs-lookup"><span data-stu-id="e7b13-106">What Are Triggers?</span></span>  
 <span data-ttu-id="e7b13-107">Триггером называют хранимую процедуру особого типа, которая автоматически выполняется при возникновении языкового события.</span><span class="sxs-lookup"><span data-stu-id="e7b13-107">A trigger is a special type of stored procedure that automatically runs when a language event executes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="e7b13-108">включает два общих типа триггеров: триггеры языка обработки данных DML и DDL.</span><span class="sxs-lookup"><span data-stu-id="e7b13-108">includes two general types of triggers: data manipulation language (DML) and data definition language (DDL) triggers.</span></span> <span data-ttu-id="e7b13-109">Триггеры DML можно использовать, когда инструкция `INSERT`, `UPDATE` или `DELETE` изменяет данные в указанной таблице или представлении.</span><span class="sxs-lookup"><span data-stu-id="e7b13-109">DML triggers can be used when `INSERT`, `UPDATE`, or `DELETE` statements modify data in a specified table or view.</span></span> <span data-ttu-id="e7b13-110">Триггеры DDL вызывают срабатывание хранимых процедур в ответ на самые разнообразные инструкции DDL. Как правило, это инструкции, начинающиеся со слов `CREATE`, `ALTER` и `DROP`.</span><span class="sxs-lookup"><span data-stu-id="e7b13-110">DDL triggers fire stored procedures in response to a variety of DDL statements, which are primarily statements that begin with `CREATE`, `ALTER`, and `DROP`.</span></span> <span data-ttu-id="e7b13-111">Триггеры DDL могут быть использованы в административных задачах, таких как аудит и регулирование операций базы данных.</span><span class="sxs-lookup"><span data-stu-id="e7b13-111">DDL triggers can be used for administrative tasks, such as auditing and regulating database operations.</span></span>  
  
## <a name="unique-capabilities-of-clr-triggers"></a><span data-ttu-id="e7b13-112">Уникальные возможности триггеров CLR</span><span class="sxs-lookup"><span data-stu-id="e7b13-112">Unique Capabilities of CLR Triggers</span></span>  
 <span data-ttu-id="e7b13-113">Триггеры, код которых написан на языке [!INCLUDE[tsql](../../includes/tsql-md.md)], позволяют определить обновленные столбцы в представлении или таблице, активизировавшей триггер, с помощью функций `UPDATE(column)` и `COLUMNS_UPDATED()`.</span><span class="sxs-lookup"><span data-stu-id="e7b13-113">Triggers written in [!INCLUDE[tsql](../../includes/tsql-md.md)] have the capability of determining which columns from the firing view or table have been updated by using the `UPDATE(column)` and `COLUMNS_UPDATED()` functions.</span></span>  
  
 <span data-ttu-id="e7b13-114">Триггеры, код которых написан на одном из языков среды CLR, отличаются от других объектов интеграции со средой CLR в нескольких существенных чертах.</span><span class="sxs-lookup"><span data-stu-id="e7b13-114">Triggers written in a CLR language differ from other CLR integration objects in several significant ways.</span></span> <span data-ttu-id="e7b13-115">Триггеры CLR позволяют:</span><span class="sxs-lookup"><span data-stu-id="e7b13-115">CLR triggers can:</span></span>  
  
-   <span data-ttu-id="e7b13-116">ссылаться на данные в таблицах `INSERTED` и `DELETED`;</span><span class="sxs-lookup"><span data-stu-id="e7b13-116">Reference data in the `INSERTED` and `DELETED` tables</span></span>  
  
-   <span data-ttu-id="e7b13-117">определять, какие столбцы были изменены в результате операции `UPDATE`;</span><span class="sxs-lookup"><span data-stu-id="e7b13-117">Determine which columns have been modified as a result of an `UPDATE` operation</span></span>  
  
-   <span data-ttu-id="e7b13-118">получать доступ к сведениям об объектах базы данных, затронутых в результате выполнения инструкций языка DDL.</span><span class="sxs-lookup"><span data-stu-id="e7b13-118">Access information about database objects affected by the execution of DDL statements.</span></span>  
  
 <span data-ttu-id="e7b13-119">Эти возможности предоставляются непосредственно в языке запросов или с помощью класса `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="e7b13-119">These capabilities are provided inherently in the query language, or by the `SqlTriggerContext` class.</span></span> <span data-ttu-id="e7b13-120">Сведения о преимуществах интеграции со средой CLR и выборе между управляемым кодом и [!INCLUDE[tsql](../../includes/tsql-md.md)] см. в разделе [Обзор интеграции со средой CLR](../../relational-databases/clr-integration/clr-integration-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e7b13-120">For information about the advantages of CLR integration and choosing between managed code and [!INCLUDE[tsql](../../includes/tsql-md.md)], see [Overview of CLR Integration](../../relational-databases/clr-integration/clr-integration-overview.md).</span></span>  
  
## <a name="using-the-sqltriggercontext-class"></a><span data-ttu-id="e7b13-121">Использование класса SqlTriggerContext</span><span class="sxs-lookup"><span data-stu-id="e7b13-121">Using the SqlTriggerContext Class</span></span>  
 <span data-ttu-id="e7b13-122">Класс `SqlTriggerContext` не может быть создан как общедоступный и может быть получен только путем доступа к свойству `SqlContext.TriggerContext` в коде триггера CLR.</span><span class="sxs-lookup"><span data-stu-id="e7b13-122">The `SqlTriggerContext` class cannot be publicly constructed and can only be obtained by accessing the `SqlContext.TriggerContext` property within the body of a CLR trigger.</span></span> <span data-ttu-id="e7b13-123">Класс `SqlTriggerContext` можно получить из активного контекста `SqlContext` путем вызова свойства `SqlContext.TriggerContext`:</span><span class="sxs-lookup"><span data-stu-id="e7b13-123">The `SqlTriggerContext` class can be obtained from the active `SqlContext` by calling the `SqlContext.TriggerContext` property:</span></span>  
  
 `SqlTriggerContext myTriggerContext = SqlContext.TriggerContext;`  
  
 <span data-ttu-id="e7b13-124">Класс `SqlTriggerContext` предоставляет сведения контекста о триггере.</span><span class="sxs-lookup"><span data-stu-id="e7b13-124">The `SqlTriggerContext` class provides context information about the trigger.</span></span> <span data-ttu-id="e7b13-125">К этим контекстным сведениям относится тип действия, которое вызвало запуск триггера, столбцы, измененные в операции UPDATE, а в случае триггера DDL — структура XML `EventData`, описывающая операцию запуска триггера.</span><span class="sxs-lookup"><span data-stu-id="e7b13-125">This contextual information includes the type of action that caused the trigger to fire, which columns were modified in an UPDATE operation, and, in the case of a DDL trigger, an XML `EventData` structure which describes the triggering operation.</span></span> <span data-ttu-id="e7b13-126">Дополнительные сведения см. в разделе [EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e7b13-126">For more information, see [EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql).</span></span>  
  
### <a name="determining-the-trigger-action"></a><span data-ttu-id="e7b13-127">Определение триггерного действия</span><span class="sxs-lookup"><span data-stu-id="e7b13-127">Determining the Trigger Action</span></span>  
 <span data-ttu-id="e7b13-128">После получения значения `SqlTriggerContext` его можно использовать для определения типа действия, которое вызвало запуск триггера.</span><span class="sxs-lookup"><span data-stu-id="e7b13-128">Once you have obtained a `SqlTriggerContext`, you can use it to determine the type of action that caused the trigger to fire.</span></span> <span data-ttu-id="e7b13-129">К этим данным можно обращаться с помощью свойства `TriggerAction` класса `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="e7b13-129">This information is available through the `TriggerAction` property of the `SqlTriggerContext` class.</span></span>  
  
 <span data-ttu-id="e7b13-130">Что касается триггеров DML, то свойство `TriggerAction` может иметь одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="e7b13-130">For DML triggers, the `TriggerAction` property can be one of the following values:</span></span>  
  
-   <span data-ttu-id="e7b13-131">TriggerAction.Update (0x1)</span><span class="sxs-lookup"><span data-stu-id="e7b13-131">TriggerAction.Update (0x1)</span></span>  
  
-   <span data-ttu-id="e7b13-132">TriggerAction.Insert (0x2)</span><span class="sxs-lookup"><span data-stu-id="e7b13-132">TriggerAction.Insert (0x2)</span></span>  
  
-   <span data-ttu-id="e7b13-133">TriggerAction.Delete (0x3)</span><span class="sxs-lookup"><span data-stu-id="e7b13-133">TriggerAction.Delete(0x3)</span></span>  
  
-   <span data-ttu-id="e7b13-134">Что касается триггеров DDL, то список возможных значений TriggerAction намного больше.</span><span class="sxs-lookup"><span data-stu-id="e7b13-134">For DDL triggers, the list of possible TriggerAction values is considerably longer.</span></span> <span data-ttu-id="e7b13-135">Дополнительные сведения см. в разделе «Перечисления TriggerAction» пакета SDK для платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7b13-135">Please see "TriggerAction Enumeration" in the .NET Framework SDK for more information.</span></span>  
  
### <a name="using-the-inserted-and-deleted-tables"></a><span data-ttu-id="e7b13-136">Использование таблиц inserted и deleted</span><span class="sxs-lookup"><span data-stu-id="e7b13-136">Using the Inserted and Deleted Tables</span></span>  
 <span data-ttu-id="e7b13-137">В инструкциях триггеров DML используются две специальные таблицы: таблица **inserted** и таблица **deleted** .</span><span class="sxs-lookup"><span data-stu-id="e7b13-137">Two special tables are used in DML trigger statements: the **inserted** table and the **deleted** table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e7b13-138">автоматически создает эти таблицы и управляет ими.</span><span class="sxs-lookup"><span data-stu-id="e7b13-138">automatically creates and manages these tables.</span></span> <span data-ttu-id="e7b13-139">Указанные временные таблицы можно использовать для проверки эффективности определенных операций модификации данных и для задания условий выполнения некоторых действий триггера DML; однако изменять данные в этих таблицах напрямую нельзя.</span><span class="sxs-lookup"><span data-stu-id="e7b13-139">You can use these temporary tables to test the effects of certain data modifications and to set conditions for DML trigger actions; however, you cannot alter the data in the tables directly.</span></span>  
  
 <span data-ttu-id="e7b13-140">Триггеры CLR могут обращаться к таблицам **inserted** и **deleted** через внутрипроцессный поставщик CLR.</span><span class="sxs-lookup"><span data-stu-id="e7b13-140">CLR triggers can access the **inserted** and **deleted** tables through the CLR in-process provider.</span></span> <span data-ttu-id="e7b13-141">Это осуществляется путем получения объекта `SqlCommand` из объекта SqlContext.</span><span class="sxs-lookup"><span data-stu-id="e7b13-141">This is done by obtaining a `SqlCommand` object from the SqlContext object.</span></span> <span data-ttu-id="e7b13-142">Пример:</span><span class="sxs-lookup"><span data-stu-id="e7b13-142">For example:</span></span>  
  
 <span data-ttu-id="e7b13-143">C#</span><span class="sxs-lookup"><span data-stu-id="e7b13-143">C#</span></span>  
  
```  
SqlConnection connection = new SqlConnection ("context connection = true");  
connection.Open();  
SqlCommand command = connection.CreateCommand();  
command.CommandText = "SELECT * from " + "inserted";  
```  
  
 <span data-ttu-id="e7b13-144">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7b13-144">Visual Basic</span></span>  
  
```  
Dim connection As New SqlConnection("context connection=true")  
Dim command As SqlCommand  
connection.Open()  
command = connection.CreateCommand()  
command.CommandText = "SELECT * FROM " + "inserted"  
```  
  
### <a name="determining-updated-columns"></a><span data-ttu-id="e7b13-145">Определение обновленных столбцов</span><span class="sxs-lookup"><span data-stu-id="e7b13-145">Determining Updated Columns</span></span>  
 <span data-ttu-id="e7b13-146">Определить количество столбцов, которые были изменены операцией UPDATE, можно с помощью свойства `ColumnCount` объекта `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="e7b13-146">You can determine the number of columns that were modified by an UPDATE operation by using the `ColumnCount` property of the `SqlTriggerContext` object.</span></span> <span data-ttu-id="e7b13-147">Чтобы определить, был ли обновлен столбец, можно использовать метод `IsUpdatedColumn`, принимающий в качестве входного параметра порядковый номер столбца.</span><span class="sxs-lookup"><span data-stu-id="e7b13-147">You can use the `IsUpdatedColumn` method, which takes the column ordinal as an input parameter, to determine whether the column was updated.</span></span> <span data-ttu-id="e7b13-148">Значение `True` указывает, что столбец был обновлен.</span><span class="sxs-lookup"><span data-stu-id="e7b13-148">A `True` value indicates that the column has been updated.</span></span>  
  
 <span data-ttu-id="e7b13-149">Например, этот фрагмент кода (из триггера EmailAudit, приведенного далее в этом разделе) перечисляет все обновляемые столбцы:</span><span class="sxs-lookup"><span data-stu-id="e7b13-149">For example, this code snippet (from the EmailAudit trigger later in this topic) lists all of the columns updated:</span></span>  
  
 <span data-ttu-id="e7b13-150">C#</span><span class="sxs-lookup"><span data-stu-id="e7b13-150">C#</span></span>  
  
```  
reader = command.ExecuteReader();  
reader.Read();  
for (int columnNumber = 0; columnNumber < triggContext.ColumnCount; columnNumber++)  
{  
   pipe.Send("Updated column "  
      + reader.GetName(columnNumber) + "? "  
   + triggContext.IsUpdatedColumn(columnNumber).ToString());  
 }  
  
 reader.Close();  
```  
  
 <span data-ttu-id="e7b13-151">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7b13-151">Visual Basic</span></span>  
  
```  
reader = command.ExecuteReader()  
reader.Read()  
Dim columnNumber As Integer  
  
For columnNumber=0 To triggContext.ColumnCount-1  
  
   pipe.Send("Updated column " & reader.GetName(columnNumber) & _  
   "? " & triggContext.IsUpdatedColumn(columnNumber).ToString() )  
  
Next  
  
reader.Close()  
```  
  
### <a name="accessing-eventdata-for-clr-ddl-triggers"></a><span data-ttu-id="e7b13-152">Доступ к функции EventData для триггеров CLR DDL</span><span class="sxs-lookup"><span data-stu-id="e7b13-152">Accessing EventData for CLR DDL Triggers</span></span>  
 <span data-ttu-id="e7b13-153">Триггеры DDL, как и обычные триггеры, вызывают срабатывание хранимых процедур в ответ на событие.</span><span class="sxs-lookup"><span data-stu-id="e7b13-153">DDL triggers, like regular triggers, fire stored procedures in response to an event.</span></span> <span data-ttu-id="e7b13-154">Однако, в отличие от триггеров DML, они не срабатывают в ответ на инструкции UPDATE, INSERT или DELETE для таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="e7b13-154">But unlike DML triggers, they do not fire in response to UPDATE, INSERT, or DELETE statements on a table or view.</span></span> <span data-ttu-id="e7b13-155">Вместо этого они запускаются в ответ на выполнение целого ряда инструкций DDL, которые главным образом представляют собой инструкции, начинающиеся с ключевых слов CREATE, ALTER и DROP.</span><span class="sxs-lookup"><span data-stu-id="e7b13-155">Instead, they fire in response to a variety of DDL statements, which are primarily statements that begin with CREATE, ALTER, and DROP.</span></span> <span data-ttu-id="e7b13-156">Триггеры DDL могут использоваться для выполнения таких административных задач, как аудит и контроль над выполнением операций базы данных и изменения схемы.</span><span class="sxs-lookup"><span data-stu-id="e7b13-156">DDL triggers can be used for administrative tasks, such as auditing and monitoring of database operations and schema changes.</span></span>  
  
 <span data-ttu-id="e7b13-157">Сведения о событии, запускающем триггер DDL, доступны в свойстве `EventData` класса `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="e7b13-157">Information about an event that fires a DDL trigger is available in the `EventData` property of the `SqlTriggerContext` class.</span></span> <span data-ttu-id="e7b13-158">Это свойство содержит значение `xml`.</span><span class="sxs-lookup"><span data-stu-id="e7b13-158">This property contains an `xml` value.</span></span> <span data-ttu-id="e7b13-159">Эта XML-схема включает следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="e7b13-159">The xml schema includes information about:</span></span>  
  
-   <span data-ttu-id="e7b13-160">время формирования события;</span><span class="sxs-lookup"><span data-stu-id="e7b13-160">The time of the event.</span></span>  
  
-   <span data-ttu-id="e7b13-161">идентификатор системного процесса (SPID) для соединения, во время которого был выполнен триггер;</span><span class="sxs-lookup"><span data-stu-id="e7b13-161">The System Process ID (SPID) of the connection during which the trigger executed.</span></span>  
  
-   <span data-ttu-id="e7b13-162">тип события, которое привело к срабатыванию триггера.</span><span class="sxs-lookup"><span data-stu-id="e7b13-162">The type of event that fired the trigger.</span></span>  
  
 <span data-ttu-id="e7b13-163">В зависимости от типа события эта схема включает также дополнительные сведения, такие как сведения о базе данных, в которой было сформировано событие, об объекте, в контексте которого оно было сформировано, и о команде [!INCLUDE[tsql](../../includes/tsql-md.md)], сформировавшей событие.</span><span class="sxs-lookup"><span data-stu-id="e7b13-163">Then, depending on the event type, the schema includes additional information, such as the database in which the event occurred, the object against which the event occurred, and the [!INCLUDE[tsql](../../includes/tsql-md.md)] command of the event.</span></span>  
  
 <span data-ttu-id="e7b13-164">В следующем примере следующий триггер DDL возвращает необработанное значение свойства `EventData`.</span><span class="sxs-lookup"><span data-stu-id="e7b13-164">In the following example, the following DDL trigger returns the raw `EventData` property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e7b13-165">В этом примере отправка результатов и сообщений через объект `SqlPipe` показана только в иллюстративных целях и, как правило, не рекомендуется для применения в коде производственного назначения при программировании триггеров CLR.</span><span class="sxs-lookup"><span data-stu-id="e7b13-165">Sending results and messages through the `SqlPipe` object is shown here for illustrative purposes only and is generally discouraged for production code when programming CLR triggers.</span></span> <span data-ttu-id="e7b13-166">Возврат дополнительных данных может оказаться непредвиденным и привести к ошибкам приложения.</span><span class="sxs-lookup"><span data-stu-id="e7b13-166">Additional data returned may be unexpected and lead to application errors.</span></span>  
  
 <span data-ttu-id="e7b13-167">C#</span><span class="sxs-lookup"><span data-stu-id="e7b13-167">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.Sql;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Xml;  
using System.Text.RegularExpressions;  
  
public class CLRTriggers  
{  
   public static void DropTableTrigger()  
   {  
       SqlTriggerContext triggContext = SqlContext.TriggerContext;             
  
       switch(triggContext.TriggerAction)  
       {  
           case TriggerAction.DropTable:  
           SqlContext.Pipe.Send("Table dropped! Here's the EventData:");  
           SqlContext.Pipe.Send(triggContext.EventData.Value);  
           break;  
  
           default:  
           SqlContext.Pipe.Send("Something happened! Here's the EventData:");  
           SqlContext.Pipe.Send(triggContext.EventData.Value);  
           break;  
       }  
   }  
}  
```  
  
 <span data-ttu-id="e7b13-168">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7b13-168">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class CLRTriggers   
  
    Public Shared Sub DropTableTrigger()  
        Dim triggContext As SqlTriggerContext  
        triggContext = SqlContext.TriggerContext  
  
        Select Case triggContext.TriggerAction  
           Case TriggerAction.DropTable  
              SqlContext.Pipe.Send("Table dropped! Here's the EventData:")  
              SqlContext.Pipe.Send(triggContext.EventData.Value)  
  
           Case Else  
              SqlContext.Pipe.Send("Something else happened! Here's the EventData:")  
              SqlContext.Pipe.Send(triggContext.EventData.Value)  
  
        End Select  
    End Sub  
End Class     
```  
  
 <span data-ttu-id="e7b13-169">Следующая выходная выборка является значением свойства `EventData` после того, как событие `CREATE TABLE` вызвало срабатывание триггера DDL:</span><span class="sxs-lookup"><span data-stu-id="e7b13-169">The following sample output is the `EventData` property value after a DDL trigger fired by a `CREATE TABLE` event:</span></span>  
  
 `<EVENT_INSTANCE><PostTime>2004-04-16T21:17:16.160</PostTime><SPID>58</SPID><EventType>CREATE_TABLE</EventType><ServerName>MACHINENAME</ServerName><LoginName>MYDOMAIN\myname</LoginName><UserName>MYDOMAIN\myname</UserName><DatabaseName>AdventureWorks</DatabaseName><SchemaName>dbo</SchemaName><ObjectName>UserName</ObjectName><ObjectType>TABLE</ObjectType><TSQLCommand><SetOptions ANSI_NULLS="ON" ANSI_NULL_DEFAULT="ON" ANSI_PADDING="ON" QUOTED_IDENTIFIER="ON" ENCRYPTED="FALSE" /><CommandText>create table dbo.UserName  
(  
 UserName varchar(50),  
 RealName varchar(50)  
)  
</CommandText></TSQLCommand></EVENT_INSTANCE>`  
  
 <span data-ttu-id="e7b13-170">Помимо сведений, доступ к которым можно получить через класс `SqlTriggerContext`, запросы могут также ссылаться на `COLUMNS_UPDATED` и inserted/deleted в тексте команды, выполняемой внутри процесса.</span><span class="sxs-lookup"><span data-stu-id="e7b13-170">In addition to the information accessible through the `SqlTriggerContext` class, queries can still refer to `COLUMNS_UPDATED` and inserted/deleted within the text of a command executed in-process.</span></span>  
  
## <a name="sample-clr-trigger"></a><span data-ttu-id="e7b13-171">Образец триггера CLR</span><span class="sxs-lookup"><span data-stu-id="e7b13-171">Sample CLR Trigger</span></span>  
 <span data-ttu-id="e7b13-172">В этом примере рассматривается сценарий, в котором пользователю предоставляется возможность выбрать любой идентификатор, но требуется определить, какие именно пользователи ввели в качестве идентификатора адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e7b13-172">In this example, consider the scenario in which you let the user choose any ID they want, but you want to know the users that specifically entered an e-mail address as an ID.</span></span> <span data-ttu-id="e7b13-173">Описанный ниже триггер обнаруживает эти данные и регистрирует их в таблице аудита.</span><span class="sxs-lookup"><span data-stu-id="e7b13-173">The following trigger would detect that information and log it to an audit table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e7b13-174">В этом примере отправка результатов и сообщений через объект `SqlPipe` показана только в иллюстративных целях и, как правило, не рекомендуется для применения в коде производственного назначения.</span><span class="sxs-lookup"><span data-stu-id="e7b13-174">Sending results and messages through the `SqlPipe` object is shown here for illustrative purposes only and is generally discouraged for production code.</span></span> <span data-ttu-id="e7b13-175">Возврат дополнительных данных может оказаться непредвиденным и привести к ошибкам приложения.</span><span class="sxs-lookup"><span data-stu-id="e7b13-175">Additional data returned may be unexpected and lead to application errors</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.Sql;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Xml;  
using System.Text.RegularExpressions;  
  
public class CLRTriggers  
{  
   [SqlTrigger(Name = @"EmailAudit", Target = "[dbo].[Users]", Event = "FOR INSERT, UPDATE, DELETE")]  
   public static void EmailAudit()  
   {  
      string userName;  
      string realName;  
      SqlCommand command;  
      SqlTriggerContext triggContext = SqlContext.TriggerContext;  
      SqlPipe pipe = SqlContext.Pipe;  
      SqlDataReader reader;  
  
      switch (triggContext.TriggerAction)  
      {  
         case TriggerAction.Insert:  
         // Retrieve the connection that the trigger is using  
         using (SqlConnection connection  
            = new SqlConnection(@"context connection=true"))  
         {  
            connection.Open();  
            command = new SqlCommand(@"SELECT * FROM INSERTED;",  
               connection);  
            reader = command.ExecuteReader();  
            reader.Read();  
            userName = (string)reader[0];  
            realName = (string)reader[1];  
            reader.Close();  
  
            if (IsValidEMailAddress(userName))  
            {  
               command = new SqlCommand(  
                  @"INSERT [dbo].[UserNameAudit] VALUES ('"  
                  + userName + @"', '" + realName + @"');",  
                  connection);  
               pipe.Send(command.CommandText);  
               command.ExecuteNonQuery();  
               pipe.Send("You inserted: " + userName);  
            }  
         }  
  
         break;  
  
         case TriggerAction.Update:  
         // Retrieve the connection that the trigger is using  
         using (SqlConnection connection  
            = new SqlConnection(@"context connection=true"))  
         {  
            connection.Open();  
            command = new SqlCommand(@"SELECT * FROM INSERTED;",  
               connection);  
            reader = command.ExecuteReader();  
            reader.Read();  
  
            userName = (string)reader[0];  
            realName = (string)reader[1];  
  
            pipe.Send(@"You updated: '" + userName + @"' - '"  
               + realName + @"'");  
  
            for (int columnNumber = 0; columnNumber < triggContext.ColumnCount; columnNumber++)  
            {  
               pipe.Send("Updated column "  
                  + reader.GetName(columnNumber) + "? "  
                  + triggContext.IsUpdatedColumn(columnNumber).ToString());  
            }  
  
            reader.Close();  
         }  
  
         break;  
  
         case TriggerAction.Delete:  
            using (SqlConnection connection  
               = new SqlConnection(@"context connection=true"))  
               {  
                  connection.Open();  
                  command = new SqlCommand(@"SELECT * FROM DELETED;",  
                     connection);  
                  reader = command.ExecuteReader();  
  
                  if (reader.HasRows)  
                  {  
                     pipe.Send(@"You deleted the following rows:");  
                     while (reader.Read())  
                     {  
                        pipe.Send(@"'" + reader.GetString(0)  
                        + @"', '" + reader.GetString(1) + @"'");  
                     }  
  
                     reader.Close();  
  
                     //alternately, to just send a tabular resultset back:  
                     //pipe.ExecuteAndSend(command);  
                  }  
                  else  
                  {  
                     pipe.Send("No rows affected.");  
                  }  
               }  
  
               break;  
            }  
        }  
  
     public static bool IsValidEMailAddress(string email)  
     {  
         return Regex.IsMatch(email, @"^([\w-]+\.)*?[\w-]+@[\w-]+\.([\w-]+\.)*?[\w]+$");  
     }  
}  
```  
  
 <span data-ttu-id="e7b13-176">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7b13-176">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
Imports System.Text.RegularExpressions  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class CLRTriggers   
  
    <SqlTrigger(Name:="EmailAudit", Target:="[dbo].[Users]", Event:="FOR INSERT, UPDATE, DELETE")> _  
    Public Shared Sub EmailAudit()  
        Dim userName As String  
        Dim realName As String  
        Dim command As SqlCommand  
        Dim triggContext As SqlTriggerContext  
        Dim pipe As SqlPipe  
        Dim reader As SqlDataReader    
  
        triggContext = SqlContext.TriggerContext      
        pipe = SqlContext.Pipe    
  
        Select Case triggContext.TriggerAction  
           Case TriggerAction.Insert  
              Using connection As New SqlConnection("context connection=true")  
                 connection.Open()  
                 command = new SqlCommand("SELECT * FROM INSERTED;", connection)  
  
                 reader = command.ExecuteReader()  
                 reader.Read()  
  
                 userName = CType(reader(0), String)  
                 realName = CType(reader(1), String)  
  
                 reader.Close()  
  
                 If IsValidEmailAddress(userName) Then  
                     command = New SqlCommand("INSERT [dbo].[UserNameAudit] VALUES ('" & _  
                       userName & "', '" & realName & "');", connection)  
  
                    pipe.Send(command.CommandText)  
                    command.ExecuteNonQuery()  
                    pipe.Send("You inserted: " & userName)  
  
                 End If  
              End Using  
  
           Case TriggerAction.Update  
              Using connection As New SqlConnection("context connection=true")  
                 connection.Open()  
                 command = new SqlCommand("SELECT * FROM INSERTED;", connection)  
  
                 reader = command.ExecuteReader()  
                 reader.Read()  
  
                 userName = CType(reader(0), String)  
                 realName = CType(reader(1), String)  
  
                 pipe.Send("You updated: " & userName & " - " & realName)  
  
                 Dim columnNumber As Integer  
  
                 For columnNumber=0 To triggContext.ColumnCount-1  
  
                    pipe.Send("Updated column " & reader.GetName(columnNumber) & _  
                      "? " & triggContext.IsUpdatedColumn(columnNumber).ToString() )  
  
                 Next  
  
                 reader.Close()  
              End Using  
  
           Case TriggerAction.Delete  
              Using connection As New SqlConnection("context connection=true")  
                 connection.Open()  
                 command = new SqlCommand("SELECT * FROM DELETED;", connection)  
  
                 reader = command.ExecuteReader()  
  
                 If reader.HasRows Then  
                    pipe.Send("You deleted the following rows:")  
  
                    While reader.Read()  
  
                       pipe.Send( reader.GetString(0) & ", " & reader.GetString(1) )  
  
                    End While   
  
                    reader.Close()  
  
                    ' Alternately, just send a tabular resultset back:  
                    ' pipe.ExecuteAndSend(command)  
  
                 Else  
                   pipe.Send("No rows affected.")  
                 End If  
  
              End Using   
        End Select  
    End Sub  
  
    Public Shared Function IsValidEMailAddress(emailAddress As String) As Boolean  
  
       return Regex.IsMatch(emailAddress, "^([\w-]+\.)*?[\w-]+@[\w-]+\.([\w-]+\.)*?[\w]+$")  
    End Function      
End Class  
```  
  
 <span data-ttu-id="e7b13-177">Предположим, что в базе данных имеются две таблицы со следующими определениями:</span><span class="sxs-lookup"><span data-stu-id="e7b13-177">Assuming two tables exist with the following definitions:</span></span>  
  
```  
CREATE TABLE Users  
(  
    UserName nvarchar(200) NOT NULL,  
    RealName nvarchar(200) NOT NULL  
);  
GO CREATE TABLE UserNameAudit  
(  
    UserName nvarchar(200) NOT NULL,  
    RealName nvarchar(200) NOT NULL  
)  
```  
  
 <span data-ttu-id="e7b13-178">[!INCLUDE[tsql](../../includes/tsql-md.md)]Инструкция, создающая триггер в, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имеет следующий вид, и предполагается, что сборка **склклртест** уже зарегистрирована в текущей [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] базе данных.</span><span class="sxs-lookup"><span data-stu-id="e7b13-178">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that creates the trigger in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is as follows, and assumes assembly **SQLCLRTest** is already registered in the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
```  
CREATE TRIGGER EmailAudit  
ON Users  
FOR INSERT, UPDATE, DELETE  
AS  
EXTERNAL NAME SQLCLRTest.CLRTriggers.EmailAudit  
```  
  
## <a name="validating-and-canceling-invalid-transactions"></a><span data-ttu-id="e7b13-179">Проверка и отмена недопустимых транзакций</span><span class="sxs-lookup"><span data-stu-id="e7b13-179">Validating and Canceling Invalid Transactions</span></span>  
 <span data-ttu-id="e7b13-180">Применение триггеров для проверки и отмены недопустимых транзакций INSERT, UPDATE или DELETE либо для предотвращения изменения схемы базы данных является стандартным.</span><span class="sxs-lookup"><span data-stu-id="e7b13-180">Using triggers to validate and cancel invalid INSERT, UPDATE, or DELETE transactions or to prevent changes to your database schema is common.</span></span> <span data-ttu-id="e7b13-181">Достигается это за счет внедрения логики проверки в код триггера и отката текущей транзакции, если действие не удовлетворяет критериям проверки.</span><span class="sxs-lookup"><span data-stu-id="e7b13-181">This can be accomplished by incorporating validation logic into your trigger and then rolling back the current transaction if the action does not meet the validation criteria.</span></span>  
  
 <span data-ttu-id="e7b13-182">При вызове метода `Transaction.Rollback` или SqlCommand внутри триггера с текстом команды «TRANSACTION ROLLBACK» возникает исключение с неоднозначным сообщением об ошибке; этот метод необходимо упаковать в блок TRY/CATCH.</span><span class="sxs-lookup"><span data-stu-id="e7b13-182">When called within a trigger, the `Transaction.Rollback` method or a SqlCommand with the command text "TRANSACTION ROLLBACK" throws an exception with an ambiguous error message and must be wrapped in a try/catch block.</span></span> <span data-ttu-id="e7b13-183">Отображается примерно следующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="e7b13-183">The error message you see is similar to the following:</span></span>  
  
```  
Msg 6549, Level 16, State 1, Procedure trig_InsertValidator, Line 0  
A .NET Framework error occurred during execution of user defined routine or aggregate 'trig_InsertValidator':   
System.Data.SqlClient.SqlException: Transaction is not allowed to roll back inside a user defined routine, trigger or aggregate because the transaction is not started in that CLR level. Change application logic to enforce strict transaction nesting... User transaction, if any, will be rolled back.  
```  
  
 <span data-ttu-id="e7b13-184">Это ожидаемое исключение, поэтому для продолжения выполнения кода необходим блок try-catch.</span><span class="sxs-lookup"><span data-stu-id="e7b13-184">This exception is expected and the try/catch block is necessary for code execution to continue.</span></span> <span data-ttu-id="e7b13-185">По завершении выполнения кода триггера возникает еще одно исключение.</span><span class="sxs-lookup"><span data-stu-id="e7b13-185">When the trigger code finishes execution, another exception is raised</span></span>  
  
```  
Msg 3991, Level 16, State 1, Procedure trig_InsertValidator, Line 1   
The context transaction which was active before entering user defined routine, trigger or aggregate "trig_InsertValidator" has been ended inside of it, which is not allowed. Change application logic to enforce strict transaction nesting.  
The statement has been terminated.  
```  
  
 <span data-ttu-id="e7b13-186">Это исключение также является ожидаемым, а блок TRY/CATCH вокруг инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)], которая выполняет действие, вызывающее срабатывание триггера, необходим, чтобы выполнение продолжилось.</span><span class="sxs-lookup"><span data-stu-id="e7b13-186">This exception is also expected, and a try/catch block around the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that performs the action that fires the trigger is necessary so that execution can continue.</span></span> <span data-ttu-id="e7b13-187">Несмотря на возникновение двух исключений, откат транзакции выполняется, а изменения не фиксируются в таблицу.</span><span class="sxs-lookup"><span data-stu-id="e7b13-187">Despite the two exceptions thrown, the transaction is rolled back and the changes are not committed to the table.</span></span> <span data-ttu-id="e7b13-188">Основная разница между триггерами CLR и триггерами [!INCLUDE[tsql](../../includes/tsql-md.md)] состоит в том, что триггеры [!INCLUDE[tsql](../../includes/tsql-md.md)] могут продолжать работать после выполнения отката.</span><span class="sxs-lookup"><span data-stu-id="e7b13-188">A major difference between CLR triggers and [!INCLUDE[tsql](../../includes/tsql-md.md)] triggers is that [!INCLUDE[tsql](../../includes/tsql-md.md)] triggers can continue to perform more work after the transaction is rolled back.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e7b13-189">Пример</span><span class="sxs-lookup"><span data-stu-id="e7b13-189">Example</span></span>  
 <span data-ttu-id="e7b13-190">Следующий триггер выполняет простую проверку инструкций INSERT для таблицы.</span><span class="sxs-lookup"><span data-stu-id="e7b13-190">The following trigger performs simple validation of INSERT statements on a table.</span></span> <span data-ttu-id="e7b13-191">Если вставляемое целое значение равно единице, будет выполнен откат транзакции, а значение не будет вставлено в таблицу.</span><span class="sxs-lookup"><span data-stu-id="e7b13-191">If the inserted integer value is equal to one, the transaction is rolled back and the value is not inserted into the table.</span></span> <span data-ttu-id="e7b13-192">Все остальные целые значения будут вставлены в таблицу.</span><span class="sxs-lookup"><span data-stu-id="e7b13-192">All other integer values are inserted into the table.</span></span> <span data-ttu-id="e7b13-193">Заметьте, что вокруг метода `Transaction.Rollback` расположен блок TRY/CATCH.</span><span class="sxs-lookup"><span data-stu-id="e7b13-193">Note the try/catch block around the `Transaction.Rollback` method.</span></span> <span data-ttu-id="e7b13-194">Скрипт [!INCLUDE[tsql](../../includes/tsql-md.md)] создает тестовую таблицу, сборку и управляемую хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="e7b13-194">The [!INCLUDE[tsql](../../includes/tsql-md.md)] script creates a test table, assembly, and managed stored procedure.</span></span> <span data-ttu-id="e7b13-195">Следует отметить, что две инструкции INSERT упакованы в блок TRY/CATCH с тем, чтобы перехватить исключения, которые возникают при завершении выполнения триггера.</span><span class="sxs-lookup"><span data-stu-id="e7b13-195">Note that the two INSERT statements are wrapped in a try/catch block so that the exception thrown when the trigger finishes execution is caught.</span></span>  
  
 <span data-ttu-id="e7b13-196">C#</span><span class="sxs-lookup"><span data-stu-id="e7b13-196">C#</span></span>  
  
```  
using System;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;  
using System.Transactions;  
  
public partial class Triggers  
{  
    // Enter existing table or view for the target and uncomment the attribute line  
    // [Microsoft.SqlServer.Server.SqlTrigger (Name="trig_InsertValidator", Target="Table1", Event="FOR INSERT")]  
    public static void trig_InsertValidator()  
    {  
        using (SqlConnection connection = new SqlConnection(@"context connection=true"))  
        {  
            SqlCommand command;  
            SqlDataReader reader;  
            int value;  
  
            // Open the connection.  
            connection.Open();  
  
            // Get the inserted value.  
            command = new SqlCommand(@"SELECT * FROM INSERTED", connection);  
            reader = command.ExecuteReader();  
            reader.Read();  
            value = (int)reader[0];  
            reader.Close();  
  
            // Rollback the transaction if a value of 1 was inserted.  
            if (1 == value)  
            {  
                try  
                {  
                    // Get the current transaction and roll it back.  
                    Transaction trans = Transaction.Current;  
                    trans.Rollback();                      
                }  
                catch (SqlException ex)  
                {  
                    // Catch the expected exception.                      
                }  
            }  
            else  
            {  
                // Perform other actions here.  
            }  
  
            // Close the connection.  
            connection.Close();              
        }  
    }  
}  
```  
  
 <span data-ttu-id="e7b13-197">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7b13-197">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Transactions  
  
Partial Public Class Triggers  
' Enter existing table or view for the target and uncomment the attribute line  
' <Microsoft.SqlServer.Server.SqlTrigger(Name:="trig_InsertValidator", Target:="Table1", Event:="FOR INSERT")> _  
Public Shared Sub  trig_InsertValidator ()  
    Using connection As New SqlConnection("context connection=true")  
  
        Dim command As SqlCommand  
        Dim reader As SqlDataReader  
        Dim value As Integer  
  
        ' Open the connection.  
        connection.Open()  
  
        ' Get the inserted value.  
        command = New SqlCommand("SELECT * FROM INSERTED", connection)  
        reader = command.ExecuteReader()  
        reader.Read()  
        value = CType(reader(0), Integer)  
        reader.Close()  
  
        ' Rollback the transaction if a value of 1 was inserted.  
        If value = 1 Then  
  
            Try  
                ' Get the current transaction and roll it back.  
                Dim trans As Transaction  
                trans = Transaction.Current  
                trans.Rollback()  
  
            Catch ex As SqlException  
  
                ' Catch the exception.                      
            End Try  
        Else  
  
            ' Perform other actions here.  
        End If  
  
        ' Close the connection.  
        connection.Close()  
    End Using  
End Sub  
End Class  
```  
  
 <span data-ttu-id="e7b13-198">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7b13-198">Transact-SQL</span></span>  
  
```  
-- Create the test table, assembly, and trigger.  
CREATE TABLE Table1(c1 int);  
go  
  
CREATE ASSEMBLY ValidationTriggers from 'E:\programming\ ValidationTriggers.dll';  
go  
  
CREATE TRIGGER trig_InsertValidator  
ON Table1  
FOR INSERT  
AS EXTERNAL NAME ValidationTriggers.Triggers.trig_InsertValidator;  
go  
  
-- Use a Try/Catch block to catch the expected exception  
BEGIN TRY  
   INSERT INTO Table1 VALUES(42)  
   INSERT INTO Table1 VALUES(1)  
END TRY  
BEGIN CATCH  
  SELECT ERROR_NUMBER() AS ErrorNum, ERROR_MESSAGE() AS ErrorMessage  
END CATCH;  
  
-- Clean up.  
DROP TRIGGER trig_InsertValidator;  
DROP ASSEMBLY ValidationTriggers;  
DROP TABLE Table1;  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7b13-199">См. также:</span><span class="sxs-lookup"><span data-stu-id="e7b13-199">See Also</span></span>  
 <span data-ttu-id="e7b13-200">[CREATE TRIGGER (Transact-SQL)](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e7b13-200">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="e7b13-201">[Триггеры DML](../../relational-databases/triggers/dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="e7b13-201">[DML Triggers](../../relational-databases/triggers/dml-triggers.md) </span></span>  
 <span data-ttu-id="e7b13-202">[Триггеры DDL](../../relational-databases/triggers/ddl-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="e7b13-202">[DDL Triggers](../../relational-databases/triggers/ddl-triggers.md) </span></span>  
 <span data-ttu-id="e7b13-203">[TRY...CATCH (Transact-SQL)](/sql/t-sql/language-elements/try-catch-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e7b13-203">[TRY...CATCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/try-catch-transact-sql) </span></span>  
 <span data-ttu-id="e7b13-204">[Создание объектов базы данных с помощью среды CLR &#40;интеграция&#41; CLR](../../relational-databases/clr-integration/database-objects/building-database-objects-with-common-language-runtime-clr-integration.md) </span><span class="sxs-lookup"><span data-stu-id="e7b13-204">[Building Database Objects with Common Language Runtime &#40;CLR&#41; Integration](../../relational-databases/clr-integration/database-objects/building-database-objects-with-common-language-runtime-clr-integration.md) </span></span>  
 [<span data-ttu-id="e7b13-205">EVENTDATA (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e7b13-205">EVENTDATA &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/eventdata-transact-sql)  
  
  
