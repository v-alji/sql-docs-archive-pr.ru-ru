---
title: Создание инструкции SQL (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, statements
- statements [ODBC], constructing
- ODBC applications, statements
ms.assetid: 0acc71e2-8004-4dd8-8592-05c022bdd692
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c454f936c49335555ca09b190e4d604c9fbad64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655132"
---
# <a name="constructing-an-sql-statement-odbc"></a><span data-ttu-id="9763f-102">Конструирование инструкций SQL (ODBC)</span><span class="sxs-lookup"><span data-stu-id="9763f-102">Constructing an SQL Statement (ODBC)</span></span>
  <span data-ttu-id="9763f-103">Приложения ODBC почти всегда осуществляют доступ к базе данных, выполняя инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9763f-103">ODBC applications perform almost all of their database access by executing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="9763f-104">Формат инструкций зависит от требования приложения.</span><span class="sxs-lookup"><span data-stu-id="9763f-104">The form of these statements depends on the application requirements.</span></span> <span data-ttu-id="9763f-105">Инструкции SQL можно создавать следующими способами.</span><span class="sxs-lookup"><span data-stu-id="9763f-105">SQL statements can be constructed in the following ways:</span></span>  
  
-   <span data-ttu-id="9763f-106">Жестко запрограммированные</span><span class="sxs-lookup"><span data-stu-id="9763f-106">Hard-coded</span></span>  
  
     <span data-ttu-id="9763f-107">Статические инструкции, которые приложение выполняет в виде фиксированной задачи.</span><span class="sxs-lookup"><span data-stu-id="9763f-107">Static statements performed by an application as a fixed task.</span></span>  
  
-   <span data-ttu-id="9763f-108">Сформированные во время выполнения</span><span class="sxs-lookup"><span data-stu-id="9763f-108">Constructed at run time</span></span>  
  
     <span data-ttu-id="9763f-109">Инструкции SQL, сформированные во время выполнения, дают возможность пользователю приспосабливать инструкцию, используя широко распространенные предложения, например SELECT, WHERE и ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="9763f-109">SQL statements constructed at run time that enable the user to tailor the statement by using common clauses, such as SELECT, WHERE, and ORDER BY.</span></span> <span data-ttu-id="9763f-110">Это включает нерегламентированные запросы, вводимые пользователем.</span><span class="sxs-lookup"><span data-stu-id="9763f-110">This includes ad hoc queries entered by users.</span></span>  
  
 <span data-ttu-id="9763f-111">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Драйвер ODBC клиента анализирует инструкции SQL только для синтаксиса ODBC и ISO, который не поддерживается напрямую [!INCLUDE[ssDE](../../includes/ssde-md.md)] , который преобразует драйвер в [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9763f-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client ODBC driver parses SQL statements only for ODBC and ISO syntax not directly supported by the [!INCLUDE[ssDE](../../includes/ssde-md.md)], which the driver transforms into [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="9763f-112">Все остальные синтаксисы SQL передаются в [!INCLUDE[ssDE](../../includes/ssde-md.md)] без изменений, где определит, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] является ли он допустимым [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9763f-112">All other SQL syntax is passed to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] unchanged, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will determine if it is valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9763f-113">Такой подход имеет следующие два преимущества.</span><span class="sxs-lookup"><span data-stu-id="9763f-113">This approach yields two benefits:</span></span>  
  
-   <span data-ttu-id="9763f-114">Сокращение издержек</span><span class="sxs-lookup"><span data-stu-id="9763f-114">Reduced overhead</span></span>  
  
     <span data-ttu-id="9763f-115">Издержки при обработке сведены к минимуму, поскольку драйверу приходится просматривать лишь небольшой набор предложений ODBC и ISO.</span><span class="sxs-lookup"><span data-stu-id="9763f-115">Processing overhead for the driver is minimized because it only has to scan for a small set of ODBC and ISO clauses.</span></span>  
  
-   <span data-ttu-id="9763f-116">Гибкость</span><span class="sxs-lookup"><span data-stu-id="9763f-116">Flexibility</span></span>  
  
     <span data-ttu-id="9763f-117">Программисты могут адаптировать переносимость своих приложений.</span><span class="sxs-lookup"><span data-stu-id="9763f-117">Programmers can tailor the portability of their applications.</span></span> <span data-ttu-id="9763f-118">Чтобы расширить переносимость для различных баз данных, используется прежде всего синтаксис ODBC и ISO.</span><span class="sxs-lookup"><span data-stu-id="9763f-118">To enhance portability against multiple databases, use primarily ODBC and ISO syntax.</span></span> <span data-ttu-id="9763f-119">Для расширений [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используется соответствующий синтаксис [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9763f-119">To use enhancements specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use the appropriate [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax.</span></span> <span data-ttu-id="9763f-120">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента поддерживает полный [!INCLUDE[tsql](../../includes/tsql-md.md)] синтаксис, поэтому приложения на основе ODBC могут воспользоваться всеми функциями в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9763f-120">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports the complete [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax so ODBC-based applications can take advantage of all the features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9763f-121">Список столбцов в инструкции SELECT должен содержать только столбцы, необходимые для выполнения текущей задачи.</span><span class="sxs-lookup"><span data-stu-id="9763f-121">The column list in a SELECT statement should contain only the columns required to perform the current task.</span></span> <span data-ttu-id="9763f-122">Это не только сокращает объем данных, отправляемых по сети, но и снижает эффект изменений в базе данных на приложение.</span><span class="sxs-lookup"><span data-stu-id="9763f-122">Not only does this reduce the amount of data sent across the network, but also it reduces the effect of database changes on the application.</span></span> <span data-ttu-id="9763f-123">Если приложение не ссылается на столбец в таблице, то оно не затрагивается никакими изменениями, сделанными в этом столбце.</span><span class="sxs-lookup"><span data-stu-id="9763f-123">If an application does not reference a column from a table, then the application is not affected by any changes made to that column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9763f-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="9763f-124">See Also</span></span>  
 [<span data-ttu-id="9763f-125">Выполняя запросы &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="9763f-125">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
