---
title: Выполнение файлов скрипта Transact-SQL с использованием программы sqlcmd
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- transact sql scripts
ms.assetid: 90067eb8-ca3e-44e8-bb1a-bf7d1a359423
author: rothja
ms.author: jroth
ms.openlocfilehash: cd34b089fc4e971cac9e5713cbe303192a7a48c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656300"
---
# <a name="run-transact-sql-script-files-using-sqlcmd"></a><span data-ttu-id="413a2-102">Выполнение файлов скрипта Transact-SQL с использованием программы sqlcmd</span><span class="sxs-lookup"><span data-stu-id="413a2-102">Run Transact-SQL Script Files Using sqlcmd</span></span>
  <span data-ttu-id="413a2-103">Для запуска файла скрипта [!INCLUDE[tsql](../../includes/tsql-md.md)] можно использовать программу командной строки `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="413a2-103">You can use `sqlcmd` to run a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="413a2-104">Файл скрипта [!INCLUDE[tsql](../../includes/tsql-md.md)] является текстовым файлом, содержащим сочетание инструкций языка [!INCLUDE[tsql](../../includes/tsql-md.md)], команд `sqlcmd` и переменных скрипта.</span><span class="sxs-lookup"><span data-stu-id="413a2-104">A [!INCLUDE[tsql](../../includes/tsql-md.md)] script file is a text file that can contain a combination of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, `sqlcmd` commands, and scripting variables.</span></span>  
  
 <span data-ttu-id="413a2-105">Чтобы создать простой файл скрипта [!INCLUDE[tsql](../../includes/tsql-md.md)] , используя приложение «Блокнот», следуйте перечисленным ниже шагам.</span><span class="sxs-lookup"><span data-stu-id="413a2-105">To create a simple [!INCLUDE[tsql](../../includes/tsql-md.md)] script file by using Notepad, follow these steps:</span></span>  
  
1.  <span data-ttu-id="413a2-106">Нажмите кнопку **Пуск**, последовательно укажите пункты **Все программы**, **Стандартные**и выберите пункт **Блокнот**.</span><span class="sxs-lookup"><span data-stu-id="413a2-106">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Notepad**.</span></span>  
  
2.  <span data-ttu-id="413a2-107">Скопируйте и вставьте следующий код языка [!INCLUDE[tsql](../../includes/tsql-md.md)] в приложение «Блокнот»:</span><span class="sxs-lookup"><span data-stu-id="413a2-107">Copy and paste the following [!INCLUDE[tsql](../../includes/tsql-md.md)] code into Notepad:</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT p.FirstName + ' ' + p.LastName AS 'Employee Name',  
    a.AddressLine1, a.AddressLine2 , a.City, a.PostalCode   
    FROM Person.Person AS p   
       INNER JOIN HumanResources.Employee AS e   
            ON p.BusinessEntityID = e.BusinessEntityID  
        INNER JOIN Person.BusinessEntityAddress bea   
            ON bea.BusinessEntityID = e.BusinessEntityID  
        INNER JOIN Person.Address AS a   
            ON a.AddressID = bea.AddressID;  
    GO  
    ```  
  
3.  <span data-ttu-id="413a2-108">Сохраните файл под именем **myScript.sql** на диске C.</span><span class="sxs-lookup"><span data-stu-id="413a2-108">Save the file as **myScript.sql** in the C drive.</span></span>  
  
### <a name="to-run-the-script-file"></a><span data-ttu-id="413a2-109">Выполнение файла скрипта</span><span class="sxs-lookup"><span data-stu-id="413a2-109">To run the script file</span></span>  
  
1.  <span data-ttu-id="413a2-110">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="413a2-110">Open a command prompt window.</span></span>  
  
2.  <span data-ttu-id="413a2-111">В окне командной строки введите: `sqlcmd -S myServer\instanceName -i C:\myScript.sql`</span><span class="sxs-lookup"><span data-stu-id="413a2-111">In the Command Prompt window, type: `sqlcmd -S myServer\instanceName -i C:\myScript.sql`</span></span>  
  
3.  <span data-ttu-id="413a2-112">Нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="413a2-112">Press ENTER.</span></span>  
  
 <span data-ttu-id="413a2-113">В окне командной строки будет выведен список имен и адресов сотрудников [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="413a2-113">A list of [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] employee names and addresses is written to the command prompt window.</span></span>  
  
### <a name="to-save-this-output-to-a-text-file"></a><span data-ttu-id="413a2-114">Сохранение результата в текстовом файле</span><span class="sxs-lookup"><span data-stu-id="413a2-114">To save this output to a text file</span></span>  
  
1.  <span data-ttu-id="413a2-115">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="413a2-115">Open a command prompt window.</span></span>  
  
2.  <span data-ttu-id="413a2-116">В окне командной строки введите: `sqlcmd -S myServer\instanceName -i C:\myScript.sql -o C:\EmpAdds.txt`</span><span class="sxs-lookup"><span data-stu-id="413a2-116">In the Command Prompt window, type: `sqlcmd -S myServer\instanceName -i C:\myScript.sql -o C:\EmpAdds.txt`</span></span>  
  
3.  <span data-ttu-id="413a2-117">Нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="413a2-117">Press ENTER.</span></span>  
  
 <span data-ttu-id="413a2-118">Результат не будет выведен в окне командной строки.</span><span class="sxs-lookup"><span data-stu-id="413a2-118">No output is returned in the Command Prompt window.</span></span> <span data-ttu-id="413a2-119">Он будет записан в файл EmpAdds.txt.</span><span class="sxs-lookup"><span data-stu-id="413a2-119">Instead, the output is sent to the EmpAdds.txt file.</span></span> <span data-ttu-id="413a2-120">Можно проверить полученные результаты, открыв файл EmpAdds.txt.</span><span class="sxs-lookup"><span data-stu-id="413a2-120">You can verify this output by opening the EmpAdds.txt file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="413a2-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="413a2-121">See Also</span></span>  
 <span data-ttu-id="413a2-122">[Запуск программы sqlcmd](sqlcmd-start-the-utility.md) </span><span class="sxs-lookup"><span data-stu-id="413a2-122">[Start the sqlcmd Utility](sqlcmd-start-the-utility.md) </span></span>  
 [<span data-ttu-id="413a2-123">Программа sqlcmd</span><span class="sxs-lookup"><span data-stu-id="413a2-123">sqlcmd Utility</span></span>](../../tools/sqlcmd-utility.md)  
  
  
