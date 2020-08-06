---
title: Запуск файлов шаблонов с помощью свойства CommandText | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], executing template files
- SQLXML Managed Classes, executing template files
- templates [SQLXML], SQLXML Managed Classes
- executing template files [SQLXML]
- CommandText property
ms.assetid: f1b1278d-252d-4a06-836e-4ef77f338ef9
author: rothja
ms.author: jroth
ms.openlocfilehash: f5507e84daf57ca4646fae3efe78c6105af35700
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654125"
---
# <a name="executing-template-files-by-using-the-commandtext-property"></a><span data-ttu-id="b11a8-102">Выполнение файлов шаблонов с использованием свойства CommandText</span><span class="sxs-lookup"><span data-stu-id="b11a8-102">Executing Template Files by Using the CommandText Property</span></span>
  <span data-ttu-id="b11a8-103">В этом примере показано, как можно указать файлы шаблонов, состоящие из запросов SQL или XPath, с помощью Коммандтекстпроперти.</span><span class="sxs-lookup"><span data-stu-id="b11a8-103">This example illustrates how template files that consist of SQL or XPath queries can be specified by using the CommandTextproperty.</span></span> <span data-ttu-id="b11a8-104">Вместо указания запроса SQL или XPath в качестве значения CommandText можно указать имя файла в качестве значения.</span><span class="sxs-lookup"><span data-stu-id="b11a8-104">Instead of specifying the SQL or XPath query as the value of CommandText, you can specify a file name as the value.</span></span> <span data-ttu-id="b11a8-105">В следующем примере свойство CommandType указано как Склксмлкоммандтипе. TemplateFile.</span><span class="sxs-lookup"><span data-stu-id="b11a8-105">In the following example, the CommandType property is specified as SqlXmlCommandType.TemplateFile.</span></span>  
  
 <span data-ttu-id="b11a8-106">Образец приложения выполняет следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="b11a8-106">The sample application executes this template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
    SELECT TOP 2 ContactID, FirstName, LastName   
    FROM   Person.Contact  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="b11a8-107">Это образец приложения на языке C#.</span><span class="sxs-lookup"><span data-stu-id="b11a8-107">This is the C# sample application.</span></span> <span data-ttu-id="b11a8-108">Чтобы проверить приложение, сохраните шаблон (файл TemplateFile.xml), а затем выполните приложение.</span><span class="sxs-lookup"><span data-stu-id="b11a8-108">To test the application, save the template (TemplateFile.xml) and then execute the application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b11a8-109">В коде необходимо задать имя экземпляра Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в строке соединения.</span><span class="sxs-lookup"><span data-stu-id="b11a8-109">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
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
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandType = SqlXmlCommandType.TemplateFile;  
         cmd.CommandText = "TemplateFile.xml";  
         using (Stream strm = cmd.ExecuteStream()){  
            using (StreamReader sr = new StreamReader(strm)){  
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
  
### <a name="to-test-the-application"></a><span data-ttu-id="b11a8-110">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="b11a8-110">To test the application</span></span>  
  
1.  <span data-ttu-id="b11a8-111">Убедитесь, что на компьютере установлена платформа [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b11a8-111">Make sure that you have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
2.  <span data-ttu-id="b11a8-112">Сохраните в папке XML-шаблон (файл TemplateFile.xml), приведенный в этом примере.</span><span class="sxs-lookup"><span data-stu-id="b11a8-112">Save the XML template (TemplateFile.xml) that is provided in this example in a folder.</span></span>  
  
3.  <span data-ttu-id="b11a8-113">Сохраните код на языке C# (файл DocSample.cs), приведенный в этом разделе, в той папке, где сохранена схема</span><span class="sxs-lookup"><span data-stu-id="b11a8-113">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="b11a8-114">(если сохранить файлы в разных папках, то придется изменить код, указав путь к каталогу, в котором находится схема сопоставления).</span><span class="sxs-lookup"><span data-stu-id="b11a8-114">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
4.  <span data-ttu-id="b11a8-115">Скомпилируйте код.</span><span class="sxs-lookup"><span data-stu-id="b11a8-115">Compile the code.</span></span> <span data-ttu-id="b11a8-116">Чтобы скомпилировать код из командной строки, введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b11a8-116">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="b11a8-117">Будет создан исполняемый файл (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="b11a8-117">This creates an executable (DocSample.exe).</span></span>  
  
5.  <span data-ttu-id="b11a8-118">Запустите файл DocSample.exe из командной строки.</span><span class="sxs-lookup"><span data-stu-id="b11a8-118">At the command prompt, execute DocSample.exe.</span></span>  
  
 <span data-ttu-id="b11a8-119">При передаче параметра в шаблон имя параметра должно начинаться с символа @. Например, p.Name = " @ContactID ", где p — это объект SqlXmlParameter.</span><span class="sxs-lookup"><span data-stu-id="b11a8-119">If you pass a parameter to a template, the parameter name must begin with at sign (@); for example, p.Name="@ContactID", where p is a SqlXmlParameter object.</span></span>  
  
 <span data-ttu-id="b11a8-120">Это обновленный шаблон, который принимает один параметр.</span><span class="sxs-lookup"><span data-stu-id="b11a8-120">This is the updated template which takes one parameter.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:header>  
     <sql:param name='ContactID'>1</sql:param>    
  </sql:header>  
  <sql:query>  
    SELECT ContactID, FirstName, LastName  
    FROM   Person.Contact  
    WHERE  ContactID=@ContactID  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="b11a8-121">Это обновленный код, в который передается параметр для выполнения шаблона.</span><span class="sxs-lookup"><span data-stu-id="b11a8-121">This is the updated code in which a parameter is passed in to execute the template.</span></span>  
  
```  
public static int testParams()  
{  
  
   Stream strm;  
   SqlXmlParameter p;  
  
   SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
   cmd.CommandType = SqlXmlCommandType.TemplateFile;  
   cmd.CommandText = "TemplateFile.xml";  
   p = cmd.CreateParameter();  
   p.Name="@ContactID";  
   p.Value = "1";  
   strm = cmd.ExecuteStream();  
   StreamReader sw = new StreamReader(strm);  
   Console.WriteLine(sw.ReadToEnd());  
   return 0;        
}  
```  
  
  
