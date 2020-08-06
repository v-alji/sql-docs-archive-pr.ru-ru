---
title: Исполнение SQL-запросов (управляемые классы SQLXML) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML], SQLXML Managed Classes
- SQLXML Managed Classes, executing SQL queries
- Managed Classes [SQLXML], executing SQL queries
- ExecuteToStream method
- SQL queries [SQLXML]
ms.assetid: a561ae83-a8b6-4b9b-a819-9b86839546b4
author: rothja
ms.author: jroth
ms.openlocfilehash: d869e45de359e602b2451b9f66fa3046f6823c1e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664790"
---
# <a name="executing-sql-queries-sqlxml-managed-classes"></a><span data-ttu-id="1921b-102">Выполнение запросов SQL (управляемые классы SQLXML)</span><span class="sxs-lookup"><span data-stu-id="1921b-102">Executing SQL Queries (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="1921b-103">В этом примере показано следующее.</span><span class="sxs-lookup"><span data-stu-id="1921b-103">This example demonstrates:</span></span>  
  
-   <span data-ttu-id="1921b-104">Создание параметров (объекты SqlXmlParameter).</span><span class="sxs-lookup"><span data-stu-id="1921b-104">Creating parameters (SqlXmlParameter objects).</span></span>  
  
-   <span data-ttu-id="1921b-105">Присвоение значений свойствам (имени и значению) объектов SqlXmlParameter.</span><span class="sxs-lookup"><span data-stu-id="1921b-105">Assigning values to the properties (Name and Value) of SqlXmlParameter objects.</span></span>  
  
 <span data-ttu-id="1921b-106">В этом примере выполняется простой SQL-запрос, который получает фамилию, имя и дату рождения сотрудника, чья фамилия передается в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="1921b-106">In this example, a simple SQL query is executed to retrieve the first name, last name, and birth date of the employee whose last name value is passed as a parameter.</span></span> <span data-ttu-id="1921b-107">При указании параметра (*LastName*) задается только свойство Value.</span><span class="sxs-lookup"><span data-stu-id="1921b-107">In specifying the parameter (*LastName*), only the Value property is set.</span></span> <span data-ttu-id="1921b-108">Свойство Name не задано, так как в этом запросе параметр является позиционированным, а имя не требуется.</span><span class="sxs-lookup"><span data-stu-id="1921b-108">The Name property is not set, because in this query the parameter is positional and no name is required.</span></span>  
  
 <span data-ttu-id="1921b-109">Свойство CommandType объекта SqlXmlCommand по умолчанию имеет значение **SQL**.</span><span class="sxs-lookup"><span data-stu-id="1921b-109">The CommandType property of the SqlXmlCommand object by default is **Sql**.</span></span> <span data-ttu-id="1921b-110">Поэтому ему явно не присваивается значение.</span><span class="sxs-lookup"><span data-stu-id="1921b-110">Therefore, the property is not explicitly set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1921b-111">В коде необходимо задать имя экземпляра Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в строке соединения.</span><span class="sxs-lookup"><span data-stu-id="1921b-111">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
 <span data-ttu-id="1921b-112">Далее приведен код C#.</span><span class="sxs-lookup"><span data-stu-id="1921b-112">This is the C# code:</span></span>  
  
```  
using System;  
  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testParams()  
      {  
         Stream strm;  
         SqlXmlParameter p;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);        
         cmd.CommandText = "SELECT FirstName, LastName FROM Person.Contact WHERE LastName=? For XML Auto";  
         p = cmd.CreateParameter();  
         p.Value = "Achong";  
         string strResult;  
         try   
         {  
            strm = cmd.ExecuteStream();  
            strm.Position = 0;  
            using(StreamReader sr = new StreamReader(strm))  
            {  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         catch (SqlXmlException e)  
         {  
            //in case of an error, this prints error returned.  
            e.ErrorStream.Position=0;  
            strResult=new StreamReader(e.ErrorStream).ReadToEnd();  
            System.Console.WriteLine(strResult);  
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
  
### <a name="to-test-the-application"></a><span data-ttu-id="1921b-113">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="1921b-113">To test the application</span></span>  
  
1.  <span data-ttu-id="1921b-114">Сохраните код C# (DocSample.cs), представленный в этом разделе, в папке.</span><span class="sxs-lookup"><span data-stu-id="1921b-114">Save the C# code (DocSample.cs) provided in this topic in a folder.</span></span>  
  
2.  <span data-ttu-id="1921b-115">Скомпилируйте код.</span><span class="sxs-lookup"><span data-stu-id="1921b-115">Compile the code.</span></span> <span data-ttu-id="1921b-116">Чтобы скомпилировать код из командной строки, введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="1921b-116">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="1921b-117">Будет создан исполняемый файл (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="1921b-117">This creates an executable (DocSample.exe).</span></span>  
  
3.  <span data-ttu-id="1921b-118">Запустите файл DocSample.exe из командной строки.</span><span class="sxs-lookup"><span data-stu-id="1921b-118">At the command prompt, execute DocSample.exe.</span></span>  
  
 <span data-ttu-id="1921b-119">Чтобы проверить этот пример, необходимо установить на компьютер платформу [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1921b-119">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
 <span data-ttu-id="1921b-120">Вместо указания запросов SQL в виде текста команды можно задать шаблон (как показано в следующем фрагменте кода), который выполняет диаграмму обновления (также шаблон) для вставки пользовательской записи.</span><span class="sxs-lookup"><span data-stu-id="1921b-120">Instead of specifying SQL queries as the command text, you can specify a template (as shown in the following code fragment) that executes an updategram (which is also a template) to insert a customer record.</span></span> <span data-ttu-id="1921b-121">Можно задать шаблоны и диаграммы обновления в файлах и выполнить эти файлы.</span><span class="sxs-lookup"><span data-stu-id="1921b-121">You can specify templates and updategrams in files and execute files.</span></span> <span data-ttu-id="1921b-122">Дополнительные сведения см. [в разделе исполнение файлов шаблонов с помощью свойства CommandText](executing-template-files-by-using-the-commandtext-property.md).</span><span class="sxs-lookup"><span data-stu-id="1921b-122">For more information, see [Executing Template Files by Using the CommandText Property](executing-template-files-by-using-the-commandtext-property.md).</span></span>  
  
```  
SqlXmlCommand cmd = new SqlXmlCommand("Provider=SQLOLEDB;Data Source=SqlServerName;Initial Catalog=Database; Integrated Security=SSPI;");  
Stream stm;  
cmd.CommandType = SqlXmlCommandType.UpdateGram;  
cmd.CommandText = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql' xmlns:updg='urn:schemas-microsoft-com:xml-updategram'>" +  
      "<updg:sync>" +  
       "<updg:before/>" +  
       "<updg:after>" +  
         "<Customer CustomerID='aaaaa' CustomerName='Some Name' CustomerTitle='SomeTitle' />" +  
       "</updg:after>" +  
       "</updg:sync>" +  
       "</ROOT>";  
  
stm = cmd.ExecuteStream();  
stm = null;  
cmd = null;  
```  
  
## <a name="using-executetostream"></a><span data-ttu-id="1921b-123">Использование ExecuteToStream</span><span class="sxs-lookup"><span data-stu-id="1921b-123">Using ExecuteToStream</span></span>  
 <span data-ttu-id="1921b-124">При наличии существующего потока можно использовать метод Ексекутетостреам вместо создания объекта потока и использования метода Execute.</span><span class="sxs-lookup"><span data-stu-id="1921b-124">If you have an existing stream, you can use the ExecuteToStream method instead of creating a Stream object and using the Execute method.</span></span> <span data-ttu-id="1921b-125">Код из предыдущего примера изменен здесь для использования метода Ексекутетостреам:</span><span class="sxs-lookup"><span data-stu-id="1921b-125">The code from the preceding example is revised here to use the ExecuteToStream method:</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=SqlServerName;database=AdventureWorks;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      SqlXmlParameter p;  
      MemoryStream ms = new MemoryStream();  
      StreamReader sr = new StreamReader(ms);  
      ms.Position = 0;  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.CommandText = "select FirstName, LastName from Person.Contact where LastName = ? For XML Auto";  
      p = cmd.CreateParameter();  
      p.Value = "Achong";  
      cmd.ExecuteToStream(ms);  
      ms.Position = 0;  
      Console.WriteLine(sr.ReadToEnd());  
      return 0;        
   }  
   public static int Main(String[] args)  
   {  
      testParams();     
      return 0;  
   }  
}  
```  
  
> [!NOTE]  
>  <span data-ttu-id="1921b-126">Можно также использовать Ексекутексмлреадермесод, который возвращает объект XmlReader.</span><span class="sxs-lookup"><span data-stu-id="1921b-126">You can also use the ExecuteXMLReadermethod that returns an XmlReader object.</span></span> <span data-ttu-id="1921b-127">Дополнительные сведения см. [в разделе исполнение SQL запросов с помощью метода ExecuteXMLReader](executing-sql-queries-by-using-the-executexmlreader-method.md).</span><span class="sxs-lookup"><span data-stu-id="1921b-127">For more information, see [Executing SQL Queries by Using the ExecuteXMLReader Method](executing-sql-queries-by-using-the-executexmlreader-method.md).</span></span>  
  
  
