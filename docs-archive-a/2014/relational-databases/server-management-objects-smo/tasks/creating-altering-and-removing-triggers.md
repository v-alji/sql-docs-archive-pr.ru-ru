---
title: Создание, изменение и удаление триггеров | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- triggers [SMO]
ms.assetid: 8ddbe23b-6e31-4f8e-8a70-17bd5072413e
author: stevestein
ms.author: sstein
ms.openlocfilehash: c2cdd1573c488fbe7b2309f656cd6bf42e82a527
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668199"
---
# <a name="creating-altering-and-removing-triggers"></a><span data-ttu-id="a9b3f-102">Создание, изменение и удаление триггеров</span><span class="sxs-lookup"><span data-stu-id="a9b3f-102">Creating, Altering, and Removing Triggers</span></span>
  <span data-ttu-id="a9b3f-103">В SMO триггеры представлены объектом <xref:Microsoft.SqlServer.Management.Smo.Trigger>.</span><span class="sxs-lookup"><span data-stu-id="a9b3f-103">In SMO, triggers are represented by using the <xref:Microsoft.SqlServer.Management.Smo.Trigger> object.</span></span> <span data-ttu-id="a9b3f-104">[!INCLUDE[tsql](../../../includes/tsql-md.md)]Код, выполняемый при срабатывании триггера, задается <xref:Microsoft.SqlServer.Management.Smo.Trigger.TextBody%2A> свойством объекта триггера.</span><span class="sxs-lookup"><span data-stu-id="a9b3f-104">The [!INCLUDE[tsql](../../../includes/tsql-md.md)] code that runs when the trigger that is fired is set by the <xref:Microsoft.SqlServer.Management.Smo.Trigger.TextBody%2A> property of the Trigger object.</span></span> <span data-ttu-id="a9b3f-105">Тип триггера определяется другими свойствами объекта <xref:Microsoft.SqlServer.Management.Smo.Trigger>, например свойством <xref:Microsoft.SqlServer.Management.Smo.Trigger.Update%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9b3f-105">The type of trigger is set by using other properties of the <xref:Microsoft.SqlServer.Management.Smo.Trigger> object, such as the <xref:Microsoft.SqlServer.Management.Smo.Trigger.Update%2A> property.</span></span> <span data-ttu-id="a9b3f-106">Это логическое свойство, которое указывает, срабатывает ли триггер при выполнении инструкции `UPDATE` для записей в родительской таблице.</span><span class="sxs-lookup"><span data-stu-id="a9b3f-106">This is a Boolean property that specifies whether the trigger is fired by an `UPDATE` of records on the parent table.</span></span>  
  
 <span data-ttu-id="a9b3f-107">Объект <xref:Microsoft.SqlServer.Management.Smo.Trigger> представляет обычные триггеры языка обработки данных DML.</span><span class="sxs-lookup"><span data-stu-id="a9b3f-107">The <xref:Microsoft.SqlServer.Management.Smo.Trigger> object represents traditional, data manipulation language (DML) triggers.</span></span> <span data-ttu-id="a9b3f-108">В [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] и более поздних версиях также поддерживаются триггеры языка определения данных DDL.</span><span class="sxs-lookup"><span data-stu-id="a9b3f-108">In [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] and later versions, data definition language (DDL) triggers are also supported.</span></span> <span data-ttu-id="a9b3f-109">Триггеры DDL представлены объектом <xref:Microsoft.SqlServer.Management.Smo.DatabaseDdlTrigger> и объектом <xref:Microsoft.SqlServer.Management.Smo.ServerDdlTrigger>.</span><span class="sxs-lookup"><span data-stu-id="a9b3f-109">DDL triggers are represented by the <xref:Microsoft.SqlServer.Management.Smo.DatabaseDdlTrigger> object and the <xref:Microsoft.SqlServer.Management.Smo.ServerDdlTrigger> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9b3f-110">Пример</span><span class="sxs-lookup"><span data-stu-id="a9b3f-110">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="creating-altering-and-removing-a-trigger-in-visual-basic"></a><span data-ttu-id="a9b3f-111">Создание, изменение и удаление триггера на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a9b3f-111">Creating, Altering, and Removing a Trigger in Visual Basic</span></span>  
 <span data-ttu-id="a9b3f-112">В этом примере кода показано, как создать и вставить триггер Update в существующую таблицу с именем `Sales`в базе данных [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a9b3f-112">This code example shows how to create and insert an update trigger on an existing table, named `Sales`, in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="a9b3f-113">Триггер отправляет сообщение с напоминанием при обновлении таблицы или вставке новой записи.</span><span class="sxs-lookup"><span data-stu-id="a9b3f-113">The trigger sends a reminder message when the table is updated or a new record is inserted.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBTriggers1](SMO How to#SMO_VBTriggers1)]  -->  
  
## <a name="creating-altering-and-removing-a-trigger-in-visual-c"></a><span data-ttu-id="a9b3f-114">Создание, изменение и удаление триггера на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="a9b3f-114">Creating, Altering, and Removing a Trigger in Visual C#</span></span>  
 <span data-ttu-id="a9b3f-115">В этом примере кода показано, как создать и вставить триггер Update в существующую таблицу с именем `Sales`в базе данных [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a9b3f-115">This code example shows how to create and insert an update trigger on an existing table, named `Sales`, in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="a9b3f-116">Триггер отправляет сообщение с напоминанием при обновлении таблицы или вставке новой записи.</span><span class="sxs-lookup"><span data-stu-id="a9b3f-116">The trigger sends a reminder message when the table is updated or a new record is inserted.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server mysrv;  
            mysrv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database mydb;  
            mydb = mysrv.Databases["AdventureWorks2012"];  
            //Declare a Table object variable and reference the Customer table.   
            Table mytab;  
            mytab = mydb.Tables["Customer", "Sales"];  
            //Define a Trigger object variable by supplying the parent table, schema ,and name in the constructor.   
            Trigger tr;  
            tr = new Trigger(mytab, "Sales");  
            //Set TextMode property to False, then set other properties to define the trigger.   
            tr.TextMode = false;  
            tr.Insert = true;  
            tr.Update = true;  
            tr.InsertOrder = ActivationOrder.First;  
            string stmt;  
            stmt = " RAISERROR('Notify Customer Relations',16,10) ";  
            tr.TextBody = stmt;  
            tr.ImplementationType = ImplementationType.TransactSql;  
            //Create the trigger on the instance of SQL Server.   
            tr.Create();  
            //Remove the trigger.   
            tr.Drop();  
        }  
```  
  
## <a name="creating-altering-and-removing-a-trigger-in-powershell"></a><span data-ttu-id="a9b3f-117">Создание, изменение и удаление триггера в PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9b3f-117">Creating, Altering, and Removing a Trigger in PowerShell</span></span>  
 <span data-ttu-id="a9b3f-118">В этом примере кода показано, как создать и вставить триггер Update в существующую таблицу с именем `Sales`в базе данных [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a9b3f-118">This code example shows how to create and insert an update trigger on an existing table, named `Sales`, in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="a9b3f-119">Триггер отправляет сообщение с напоминанием при обновлении таблицы или вставке новой записи.</span><span class="sxs-lookup"><span data-stu-id="a9b3f-119">The trigger sends a reminder message when the table is updated or a new record is inserted.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and to the  
#database tables in Adventureworks2012  
CD \sql\localhost\default\databases\AdventureWorks2012\Tables\  
  
#Get reference to the trigger's target table  
$mytab = Get-Item Sales.Customer  
  
# Define a Trigger object variable by supplying the parent table, schema ,and name in the constructor.  
$tr = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Trigger -argumentlist $mytab, "Sales"  
  
# Set TextMode property to False, then set other properties to define the trigger.
$tr.TextMode = $false  
$tr.Insert = $true  
$tr.Update = $true  
$tr.InsertOrder = [Microsoft.SqlServer.Management.SMO.Agent.ActivationOrder]::First  
$tr.TextBody = " RAISERROR('Notify Customer Relations',16,10) "  
$tr.ImplementationType = [Microsoft.SqlServer.Management.SMO.ImplementationType]::TransactSql  
  
# Create the trigger on the instance of SQL Server.
$tr.Create()  
  
#Remove the trigger.
$tr.Drop()  
```  
