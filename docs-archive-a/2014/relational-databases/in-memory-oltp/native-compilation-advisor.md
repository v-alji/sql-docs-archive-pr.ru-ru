---
title: Помощник по компиляции в собственный код | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
f1_keywords:
- sql12.swb.nativecompilationwizard.f1
- swb.nativecompilationwizard.f1
ms.assetid: d3898a47-2985-4a08-bc70-fd8331a01b7b
author: rothja
ms.author: jroth
ms.openlocfilehash: b2182d89489af5da8bc3b85b89484fbbf72e4dfa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750963"
---
# <a name="native-compilation-advisor"></a><span data-ttu-id="99c98-102">Помощник по собственной компиляции</span><span class="sxs-lookup"><span data-stu-id="99c98-102">Native Compilation Advisor</span></span>
  <span data-ttu-id="99c98-103">Средство создания отчетов о производительности транзакций (см. [Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)) информирует о том, какие интерпретируемые хранимые процедуры в базе данных смогут воспользоваться преимуществами перехода на компиляцию в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="99c98-103">Transaction performance reports tool (see [Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)) informs you about which interpreted stored procedures in your database will benefit if ported to use native compilation.</span></span> <span data-ttu-id="99c98-104">После определения хранимой процедуры, для которой вы собираетесь использовать собственную компиляцию, можно запустить помощник по собственной компиляции, который облегчит миграцию интерпретированной хранимой процедуры для собственной компиляции.</span><span class="sxs-lookup"><span data-stu-id="99c98-104">After you identify a stored procedure that you would like to port to use native compilation, you can use the native compilation advisor to help you migrate the interpreted stored procedure to native compilation.</span></span> <span data-ttu-id="99c98-105">Дополнительные сведения о скомпилированных в собственном коде хранимых процедурах см. в разделе [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="99c98-105">For more information about natively compiled stored procedures, see [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="99c98-106">Чтобы начать, подключитесь к экземпляру, содержащему интерпретированную хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="99c98-106">To begin, connect to the instance that contains the interpreted stored procedure.</span></span> <span data-ttu-id="99c98-107">Можно подключиться к экземпляру [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]или [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99c98-107">You can connect to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], or [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] instance.</span></span> <span data-ttu-id="99c98-108">Однако если необходимо выполнить операцию миграции с помощником, необходимо подключиться к экземпляру [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] , на котором включена функциональность In-Memory OLTP.</span><span class="sxs-lookup"><span data-stu-id="99c98-108">However, if you wish to perform a migration operation with the advisor, you must connect to a [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] instance on which In-Memory OLTP functionality is enabled.</span></span> <span data-ttu-id="99c98-109">Дополнительные сведения о требованиях In-Memory OLTP см. в разделе [Requirements for Using Memory-Optimized Tables](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="99c98-109">For more information about In-Memory OLTP requirements, see [Requirements for Using Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="99c98-110">Дополнительные сведения о методологиях миграции см. в разделе [Выполняемая в памяти OLTP — стандартные шаблоны рабочей нагрузки и вопросы миграции](https://msdn.microsoft.com/library/dn673538.aspx).</span><span class="sxs-lookup"><span data-stu-id="99c98-110">For information about migration methodologies, see [In-Memory OLTP - Common Workload Patterns and Migration Considerations](https://msdn.microsoft.com/library/dn673538.aspx).</span></span>  
  
## <a name="walkthrough-using-the-native-compilation-advisor"></a><span data-ttu-id="99c98-111">Пошаговое руководство по использованию помощника по собственной компиляции</span><span class="sxs-lookup"><span data-stu-id="99c98-111">Walkthrough Using the Native Compilation Advisor</span></span>  
 <span data-ttu-id="99c98-112">В **обозревателе объектов**щелкните правой кнопкой мыши хранимую процедуру, которую необходимо преобразовать, и выберите пункт **Помощник по собственной компиляции**.</span><span class="sxs-lookup"><span data-stu-id="99c98-112">In **Object Explorer**, right click the stored procedure you want to convert, and select **Native Compilation Advisor**.</span></span> <span data-ttu-id="99c98-113">Появится стартовая страница для **помощника по собственной компиляции хранимых процедур**.</span><span class="sxs-lookup"><span data-stu-id="99c98-113">This will display the welcome page for the **Stored Procedure Native Compilation Advisor**.</span></span> <span data-ttu-id="99c98-114">Чтобы продолжить, нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="99c98-114">Click **Next** to continue.</span></span>  
  
### <a name="stored-procedure-validation"></a><span data-ttu-id="99c98-115">Проверка хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="99c98-115">Stored Procedure Validation</span></span>  
 <span data-ttu-id="99c98-116">Эта страница сообщает, использует ли хранимая процедура какие-либо конструкции, несовместимые с собственной компиляцией.</span><span class="sxs-lookup"><span data-stu-id="99c98-116">This page will report if the stored procedure uses any constructs that are not compatible with native compilation.</span></span> <span data-ttu-id="99c98-117">Можно нажать кнопку **Далее** , чтобы просмотреть данные.</span><span class="sxs-lookup"><span data-stu-id="99c98-117">You can click **Next** to see details.</span></span> <span data-ttu-id="99c98-118">Если найдены конструкции, несовместимые с собственной компиляцией, можно нажать кнопку **Далее** , чтобы просмотреть подробности.</span><span class="sxs-lookup"><span data-stu-id="99c98-118">If there are constructs that are not compatible with native compilation, you can click **Next** to see details.</span></span>  
  
### <a name="stored-procedure-validation-result"></a><span data-ttu-id="99c98-119">Результат проверки хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="99c98-119">Stored Procedure Validation Result</span></span>  
 <span data-ttu-id="99c98-120">При наличии конструкций, несовместимых с собственной компиляцией, на странице **Результат проверки хранимой процедуры** будут выведены подробности.</span><span class="sxs-lookup"><span data-stu-id="99c98-120">If there are constructs that are not compatible with native compilation, the **Stored Procedure Validation Result** page will display details.</span></span> <span data-ttu-id="99c98-121">Можно создать отчет (нажав **Создание отчета**), выйти из **помощника по собственной компиляции**и изменить код таким образом, чтобы он был совместим с собственной компиляцией.</span><span class="sxs-lookup"><span data-stu-id="99c98-121">You can generate a report (click **Generate Report**), exit the **Native Compilation Advisor**, and update your code so that it is compatible with native compilation.</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="99c98-122">Образец кода</span><span class="sxs-lookup"><span data-stu-id="99c98-122">Code Sample</span></span>  
 <span data-ttu-id="99c98-123">В следующем примере показана интерпретированная хранимая процедура и эквивалентная хранимая процедура для собственной компиляции.</span><span class="sxs-lookup"><span data-stu-id="99c98-123">The following sample shows an interpreted stored procedure and the equivalent stored procedure for native compilation.</span></span> <span data-ttu-id="99c98-124">В примере подразумевается каталог c:\data.</span><span class="sxs-lookup"><span data-stu-id="99c98-124">The sample assumes a directory called c:\data.</span></span>  
  
```sql  
CREATE DATABASE Demo  
ON  
PRIMARY(NAME = [Demo_data],  
FILENAME = 'C:\DATA\Demo_data.mdf', size=500MB)  
, FILEGROUP [Demo_fg] CONTAINS MEMORY_OPTIMIZED_DATA(  
NAME = [Demo_dir],  
FILENAME = 'C:\DATA\Demo_dir')  
LOG ON (name = [Demo_log], Filename='C:\DATA\Demo_log.ldf', size=500MB)  
COLLATE Latin1_General_100_BIN2;  
GO  
USE Demo;  
GO  
  
CREATE TABLE [dbo].[SalesOrders]  
(  
     [order_id] [int] NOT NULL,  
     [order_date] [datetime] NOT NULL,  
     [order_status] [tinyint] NOT NULL  
  
CONSTRAINT [PK_SalesOrders] PRIMARY KEY NONCLUSTERED HASH   
(  
     [order_id]  
)WITH ( BUCKET_COUNT = 2097152)  
)WITH ( MEMORY_OPTIMIZED = ON )  
  
go  
  
CREATE PROCEDURE [dbo].[InsertOrder] @id INT, @date DATETIME2, @status TINYINT  
AS   
BEGIN   
  
  INSERT dbo.SalesOrders VALUES (@id, @date, @status)  
  
END  
  
go  
  
CREATE PROCEDURE [dbo].[InsertOrderXTP] @id INT, @date DATETIME2, @status TINYINT  
  WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS   
BEGIN ATOMIC WITH   
(    TRANSACTION ISOLATION LEVEL = SNAPSHOT,  
     LANGUAGE = N'us_english')  
  
  INSERT dbo.SalesOrders VALUES (@id, @date, @status)  
  
END  
go  
  
select * from SalesOrders  
go  
exec dbo.InsertOrder @id= 10, @date = '1956-01-01 12:00:00', @status = 1 ;  
exec dbo.InsertOrderXTP @id= 11, @date = '1956-01-01 12:01:00', @status = 2 ;  
select * from SalesOrders  
```  
  
## <a name="see-also"></a><span data-ttu-id="99c98-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="99c98-125">See Also</span></span>  
 [<span data-ttu-id="99c98-126">Миграция в In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="99c98-126">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
