---
title: Обработка XML на стороне клиента (управляемые классы SQLXML) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- processing XML on client side [SQLXML]
- client-side XML formatting
- Managed Classes [SQLXML], client-side XML formatting
- SQLXML Managed Classes, client-side XML formatting
- ClientSideXml property
ms.assetid: 5e7ecf18-66fc-49ff-bc50-83635cd7ac0b
author: rothja
ms.author: jroth
ms.openlocfilehash: fb90f7c5c823c750b64f47d0c9df9551b9f857b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655015"
---
# <a name="processing-xml-on-the-client-side-sqlxml-managed-classes"></a><span data-ttu-id="05f1c-102">Обработка XML-кода на стороне клиента (управляемые классы SQLXML)</span><span class="sxs-lookup"><span data-stu-id="05f1c-102">Processing XML on the Client Side (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="05f1c-103">В этом примере показано использование свойства Клиентсидексмл.</span><span class="sxs-lookup"><span data-stu-id="05f1c-103">This example illustrates the use of the ClientSideXml property.</span></span> <span data-ttu-id="05f1c-104">Приложение выполняет хранимую процедуру на сервере.</span><span class="sxs-lookup"><span data-stu-id="05f1c-104">The application executes a stored procedure on the server.</span></span> <span data-ttu-id="05f1c-105">Результат хранимой процедуры (набор строк из двух столбцов) обрабатывается на стороне клиента для создания XML-документа.</span><span class="sxs-lookup"><span data-stu-id="05f1c-105">The result of the stored procedure (a two-column rowset) is processed on the client side to produce an XML document.</span></span>  
  
 <span data-ttu-id="05f1c-106">Следующая хранимая процедура "связи" возвращает " **FirstName** " и " **LastName** " сотрудников в таблице Person. Contact в базе данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="05f1c-106">The following GetContacts stored procedure returns **FirstName** and **LastName** of employees in the Person.Contact table in the AdventureWorks database.</span></span>  
  
```  
USE AdventureWorks  
CREATE PROCEDURE GetContacts @LastName varchar(20)  
AS  
SELECT FirstName, LastName  
FROM   Person.Contact  
WHERE LastName = @LastName  
Go  
```  
  
 <span data-ttu-id="05f1c-107">Это приложение C# выполняет хранимую процедуру и задает параметр FOR XML AUTO в указании значения CommandText.</span><span class="sxs-lookup"><span data-stu-id="05f1c-107">This C# application executes the stored procedure and specifies the FOR XML AUTO option in specifying the CommandText value.</span></span> <span data-ttu-id="05f1c-108">В приложении свойству Клиентсидексмл объекта SqlXmlCommand присваивается значение true.</span><span class="sxs-lookup"><span data-stu-id="05f1c-108">In the application, the ClientSideXml property of the SqlXmlCommand object is set to true.</span></span> <span data-ttu-id="05f1c-109">Это позволяет выполнять существующие хранимые процедуры, возвращающие наборы строк, и применить к ним преобразование XML на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="05f1c-109">This allows you to execute preexisting stored procedures that return a rowset and apply an XML transformation to it on the client.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="05f1c-110">В коде необходимо задать имя экземпляра Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в строке соединения.</span><span class="sxs-lookup"><span data-stu-id="05f1c-110">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
    static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testParams()  
      {  
         //Stream strm;  
         SqlXmlParameter p;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.ClientSideXml = true;  
         cmd.CommandText = "EXEC GetContacts ? FOR XML NESTED";  
         p = cmd.CreateParameter();  
         p.Value = "Achong";  
         using (Stream strm = cmd.ExecuteStream())   
         {  
            using (StreamReader sr = new StreamReader(strm))  
                  {  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         return 0;  
      }  
  
public static int Main(String[] args)  
{  
    testParams();  
    return 0;  
}  
}  
```  
  
 <span data-ttu-id="05f1c-111">Чтобы проверить этот пример, необходимо установить на компьютер платформу [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="05f1c-111">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="05f1c-112">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="05f1c-112">To test the application</span></span>  
  
1.  <span data-ttu-id="05f1c-113">Создайте хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="05f1c-113">Create the stored procedure.</span></span>  
  
2.  <span data-ttu-id="05f1c-114">Сохраните в папке код C# (файл DocSample.cs), приведенный в этом примере.</span><span class="sxs-lookup"><span data-stu-id="05f1c-114">Save the C# code (DocSample.cs) that is provided in this example in a folder.</span></span> <span data-ttu-id="05f1c-115">Измените этот код, указав нужные имя входа и пароль.</span><span class="sxs-lookup"><span data-stu-id="05f1c-115">Edit the code to specify appropriate login and password information.</span></span>  
  
3.  <span data-ttu-id="05f1c-116">Скомпилируйте код.</span><span class="sxs-lookup"><span data-stu-id="05f1c-116">Compile the code.</span></span> <span data-ttu-id="05f1c-117">Чтобы скомпилировать код из командной строки, введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="05f1c-117">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="05f1c-118">Будет создан исполняемый файл (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="05f1c-118">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="05f1c-119">Запустите файл DocSample.exe из командной строки.</span><span class="sxs-lookup"><span data-stu-id="05f1c-119">At the command prompt, execute DocSample.exe.</span></span>  
  
  
