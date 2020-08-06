---
title: Создание базы данных (учебник) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- tutorial creating a database
ms.assetid: e1e2c83f-dfad-4bb8-aa7a-09d3f69517ae
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 99d5439c289b5d4e71786d4c6734f158f6bba371
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665701"
---
# <a name="creating-a-database-tutorial"></a><span data-ttu-id="45072-102">Создание базы данных (учебник)</span><span class="sxs-lookup"><span data-stu-id="45072-102">Creating a Database (Tutorial)</span></span>
  <span data-ttu-id="45072-103">Как и у многих инструкций языка [!INCLUDE[tsql](../includes/tsql-md.md)] , у инструкции CREATE DATABASE имеется обязательный параметр: имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="45072-103">Like many [!INCLUDE[tsql](../includes/tsql-md.md)] statements, the CREATE DATABASE statement has a required parameter: the name of the database.</span></span> <span data-ttu-id="45072-104">Кроме этого, у инструкции CREATE DATABASE имеется ряд необязательных параметров, таких как расположение на диске, где требуется хранить файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="45072-104">CREATE DATABASE also has many optional parameters, such as the disk location where you want to put the database files.</span></span> <span data-ttu-id="45072-105">При выполнении инструкции CREATE DATABASE без дополнительных параметров, для многих из них [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] использует значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="45072-105">When you execute CREATE DATABASE without the optional parameters, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] uses default values for many of these parameters.</span></span> <span data-ttu-id="45072-106">В этом учебнике используются лишь некоторые дополнительные синтаксические параметры.</span><span class="sxs-lookup"><span data-stu-id="45072-106">This tutorial uses very few of the optional syntax parameters.</span></span>  
  
### <a name="to-create-a-database"></a><span data-ttu-id="45072-107">Создание базы данных</span><span class="sxs-lookup"><span data-stu-id="45072-107">To create a database</span></span>  
  
1.  <span data-ttu-id="45072-108">В окне редактора запросов введите, но не выполняйте, следующий код:</span><span class="sxs-lookup"><span data-stu-id="45072-108">In a Query Editor window, type but do not execute the following code:</span></span>  
  
    ```  
    CREATE DATABASE TestData  
    GO  
    ```  
  
2.  <span data-ttu-id="45072-109">С помощью указателя выделите слова `CREATE DATABASE`и нажмите клавишу **F1**.</span><span class="sxs-lookup"><span data-stu-id="45072-109">Use the pointer to select the words `CREATE DATABASE`, and then press **F1**.</span></span> <span data-ttu-id="45072-110">Должен открыться раздел CREATE DATABASE электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="45072-110">The CREATE DATABASE topic in SQL Server Books Online should open.</span></span> <span data-ttu-id="45072-111">Таким же способом можно найти полный синтаксис инструкции CREATE DATABASE и других инструкций, используемых в данном учебнике.</span><span class="sxs-lookup"><span data-stu-id="45072-111">You can use this technique to find the complete syntax for CREATE DATABASE and for the other statements that are used in this tutorial.</span></span>  
  
3.  <span data-ttu-id="45072-112">В редакторе запросов нажмите клавишу **F5** , чтобы выполнить инструкцию и создать базу данных с именем `TestData`.</span><span class="sxs-lookup"><span data-stu-id="45072-112">In Query Editor, press **F5** to execute the statement and create a database named `TestData`.</span></span>  
  
 <span data-ttu-id="45072-113">При создании базы данных сервер [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] создает копию базы данных **model** и присваивает ей указанное имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="45072-113">When you create a database, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] makes a copy of the **model** database, and renames the copy to the database name.</span></span> <span data-ttu-id="45072-114">Эта операция обычно занимает несколько секунд, если только с помощью дополнительного параметра не указан большой исходный размер базы данных.</span><span class="sxs-lookup"><span data-stu-id="45072-114">This operation should only take several seconds, unless you specify a large initial size of the database as an optional parameter.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45072-115">Когда в одном пакете представлено несколько инструкций, они разделяются с помощью ключевого слова GO.</span><span class="sxs-lookup"><span data-stu-id="45072-115">The keyword GO separates statements when more than one statement is submitted in a single batch.</span></span> <span data-ttu-id="45072-116">Ключевое слово GO является необязательным, если в пакете содержится только одна инструкция.</span><span class="sxs-lookup"><span data-stu-id="45072-116">GO is optional when the batch contains only one statement.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="45072-117">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="45072-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="45072-118">Создание таблицы (учебник)</span><span class="sxs-lookup"><span data-stu-id="45072-118">Creating a Table &#40;Tutorial&#41;</span></span>](lesson-1-2-creating-a-table.md)  
  
## <a name="see-also"></a><span data-ttu-id="45072-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="45072-119">See Also</span></span>  
 [<span data-ttu-id="45072-120">CREATE DATABASE (SQL Server Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="45072-120">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  
