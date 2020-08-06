---
title: Удаление сборки | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- removing assemblies
- DROP ASSEMBLY statement
- assemblies [CLR integration], removing
- dropping assemblies
ms.assetid: 03481034-dc91-4488-ab24-ba44243e2690
author: rothja
ms.author: jroth
ms.openlocfilehash: 45d02cbb57459a4c1c11330446021c32dc897353
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735330"
---
# <a name="dropping-an-assembly"></a><span data-ttu-id="c267b-102">Удаление сборки</span><span class="sxs-lookup"><span data-stu-id="c267b-102">Dropping an Assembly</span></span>
  <span data-ttu-id="c267b-103">Сборки, зарегистрированные в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с помощью инструкции CREATE ASSEMBLY, могут быть удалены, если предоставляемые ими функциональные возможности больше не требуются.</span><span class="sxs-lookup"><span data-stu-id="c267b-103">Assemblies that have been registered in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] using the CREATE ASSEMBLY statement can be deleted, or dropped, when the functionality they provide is no longer needed.</span></span> <span data-ttu-id="c267b-104">При удалении сборки из базы данных удаляются и все связанные с ней файлы, такие как файлы отладки.</span><span class="sxs-lookup"><span data-stu-id="c267b-104">Dropping an assembly removes the assembly and all of its associated files, such as debug files, from the database.</span></span> <span data-ttu-id="c267b-105">Чтобы удалить сборку, используйте инструкцию DROP ASSEMBLY со следующим синтаксисом:</span><span class="sxs-lookup"><span data-stu-id="c267b-105">To drop an assembly, use the DROP ASSEMBLY statement with the following syntax:</span></span>  
  
```  
DROP ASSEMBLY MyDotNETAssembly  
```  
  
 <span data-ttu-id="c267b-106">Инструкция DROP ASSEMBLY не влияет на код, ссылающийся на работающую в данный момент сборку, но после ее выполнения любые попытки вызова кода сборки завершатся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c267b-106">DROP ASSEMBLY does not interfere with any code referencing the assembly that is currently running, but after DROP ASSEMBLY executes, any attempts to invoke the assembly code fail.</span></span>  
  
 <span data-ttu-id="c267b-107">Инструкция DROP ASSEMBLY возвращает ошибку, если на сборку ссылается другая существующая в базе данных сборка или если она используется функциями среды CLR, процедурами, триггерами, определенными пользователем типами или статистическими функциями в текущей базе данных.</span><span class="sxs-lookup"><span data-stu-id="c267b-107">DROP ASSEMBLY returns an error if the assembly is referenced by another assembly that exists in the database, or if it is used by common language runtime (CLR) functions, procedures, triggers, user-defined types (UDTs), or user-defined aggregates (UDAs) in the current database.</span></span> <span data-ttu-id="c267b-108">Сначала используйте инструкции DROP AGGREGATE, DROP FUNCTION, DROP PROCEDURE, DROP TRIGGER и DROP TYPE, чтобы удалить все управляемые объекты базы данных, содержащиеся в сборке.</span><span class="sxs-lookup"><span data-stu-id="c267b-108">First use the DROP AGGREGATE, DROP FUNCTION, DROP PROCEDURE, DROP TRIGGER, and DROP TYPE statements to delete any managed database objects contained in the assembly.</span></span>  
  
## <a name="removing-a-udt-from-the-database"></a><span data-ttu-id="c267b-109">Удаление определяемого пользователем типа из базы данных</span><span class="sxs-lookup"><span data-stu-id="c267b-109">Removing a UDT from the Database</span></span>  
 <span data-ttu-id="c267b-110">Инструкция DROP TYPE удаляет определяемый пользователем тип из текущей базы данных.</span><span class="sxs-lookup"><span data-stu-id="c267b-110">The DROP TYPE statement removes a UDT from the current database.</span></span> <span data-ttu-id="c267b-111">После удаления определяемого пользователем типа можно инструкцией DROP ASSEMBLY удалить сборку из базы данных.</span><span class="sxs-lookup"><span data-stu-id="c267b-111">Once a UDT is dropped, you can use the DROP ASSEMBLY statement to drop the assembly from the database.</span></span>  
  
 <span data-ttu-id="c267b-112">Инструкция DROP TYPE завершается с ошибкой, если объекты зависят от определяемого пользователем типа, как, например, в следующих ситуациях.</span><span class="sxs-lookup"><span data-stu-id="c267b-112">The DROP TYPE statement fails if objects depend on the UDT, as in the following situations:</span></span>  
  
-   <span data-ttu-id="c267b-113">Таблицы в базе данных, которые содержат столбцы, определенные с помощью определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="c267b-113">Tables in the database that contain columns defined using the UDT.</span></span>  
  
-   <span data-ttu-id="c267b-114">Функции, хранимые процедуры или триггеры, которые используют переменные или параметры определяемого пользователем типа и созданы в базе данных с помощью предложения WITH SCHEMABINDING.</span><span class="sxs-lookup"><span data-stu-id="c267b-114">Functions, stored procedures, or triggers that use variables or parameters of the UDT, created in the database with the WITH SCHEMABINDING clause.</span></span>  
  
### <a name="finding-udt-dependencies"></a><span data-ttu-id="c267b-115">Поиск зависимостей определяемого пользователем типа</span><span class="sxs-lookup"><span data-stu-id="c267b-115">Finding UDT Dependencies</span></span>  
 <span data-ttu-id="c267b-116">Сначала необходимо удалить все зависимые объекты, а затем выполнить инструкцию DROP TYPE.</span><span class="sxs-lookup"><span data-stu-id="c267b-116">You must first drop all dependent objects, and then execute the DROP TYPE statement.</span></span> <span data-ttu-id="c267b-117">Следующий [!INCLUDE[tsql](../../../includes/tsql-md.md)] запрос находит все столбцы и параметры, которые используют определяемый пользователем тип в базе данных **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="c267b-117">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] query locates all of the columns and parameters that use a UDT in the **AdventureWorks** database.</span></span>  
  
```  
USE Adventureworks;  
SELECT o.name AS major_name, o.type_desc AS major_type_desc  
     , c.name AS minor_name, c.type_desc AS minor_type_desc  
     , at.assembly_class  
  FROM (  
        SELECT object_id, name, user_type_id, 'SQL_COLUMN' AS type_desc  
          FROM sys.columns  
     UNION ALL  
        SELECT object_id, name, user_type_id, 'SQL_PROCEDURE_PARAMETER'  
          FROM sys.parameters  
     ) AS c  
  JOIN sys.objects AS o  
    ON o.object_id = c.object_id  
  JOIN sys.assembly_types AS at  
    ON at.user_type_id = c.user_type_id;   
```  
  
## <a name="see-also"></a><span data-ttu-id="c267b-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="c267b-118">See Also</span></span>  
 <span data-ttu-id="c267b-119">[Управление сборками интеграции со средой CLR](managing-clr-integration-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="c267b-119">[Managing CLR Integration Assemblies](managing-clr-integration-assemblies.md) </span></span>  
 <span data-ttu-id="c267b-120">[Изменение сборки](altering-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="c267b-120">[Altering an Assembly](altering-an-assembly.md) </span></span>  
 <span data-ttu-id="c267b-121">[Создание сборки](creating-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="c267b-121">[Creating an Assembly](creating-an-assembly.md) </span></span>  
 <span data-ttu-id="c267b-122">[DROP АГРЕГАТная &#40;&#41;Transact-SQL](/sql/t-sql/statements/drop-aggregate-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c267b-122">[DROP AGGREGATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-aggregate-transact-sql) </span></span>  
 <span data-ttu-id="c267b-123">[DROP FUNCTION (Transact-SQL)](/sql/t-sql/statements/drop-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c267b-123">[DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql) </span></span>  
 <span data-ttu-id="c267b-124">[УДАЛИТЬ процедуру &#40;языке Transact-SQL&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c267b-124">[DROP PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span></span>  
 <span data-ttu-id="c267b-125">[DROP TRIGGER (Transact-SQL)](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c267b-125">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 [<span data-ttu-id="c267b-126">DROP TYPE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c267b-126">DROP TYPE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-type-transact-sql)  
  
  
