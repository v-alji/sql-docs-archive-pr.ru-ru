---
title: Запуск файлов шаблонов с помощью свойства CommandStream | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], executing template files
- SQLXML Managed Classes, executing template files
- templates [SQLXML], SQLXML Managed Classes
- CommandStream property
ms.assetid: 55c564e3-56d1-4d85-bcaa-703e2905dd57
author: rothja
ms.author: jroth
ms.openlocfilehash: c57a2ab2f3780a8bc75b53b0cceeee0799fcfcc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654126"
---
# <a name="executing-template-files-by-using-the-commandstream-property"></a><span data-ttu-id="e4387-102">Выполнение файлов шаблонов через свойство CommandStream</span><span class="sxs-lookup"><span data-stu-id="e4387-102">Executing Template Files by Using the CommandStream Property</span></span>
  <span data-ttu-id="e4387-103">В этом примере показано, как можно указать файлы шаблонов, состоящие из запросов SQL или XPath, с помощью свойства CommandStream объекта SqlXmlCommand.</span><span class="sxs-lookup"><span data-stu-id="e4387-103">This example illustrates how template files that consist of SQL or XPath queries can be specified by using the CommandStream property of the SqlXmlCommand object.</span></span> <span data-ttu-id="e4387-104">В этом приложении открывается Филестреамобжект для командного файла, а файловый поток назначается как выполняемый CommandStream.</span><span class="sxs-lookup"><span data-stu-id="e4387-104">In this application, a FileStreamobject is opened for a command file, and the file stream is assigned as the CommandStream that is executed.</span></span>  
  
 <span data-ttu-id="e4387-105">В следующем примере свойство CommandType указано как Склксмлкоммандтипе. Template (не AS TemplateFile).</span><span class="sxs-lookup"><span data-stu-id="e4387-105">In the following example, the CommandType property is specified as SqlXmlCommandType.Template (not as TemplateFile).</span></span>  
  
 <span data-ttu-id="e4387-106">Образец XML-шаблона:</span><span class="sxs-lookup"><span data-stu-id="e4387-106">This is the sample XML template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
    SELECT TOP 2 ContactID, FirstName, LastName   
    FROM   Person.Contact  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="e4387-107">Образец приложения C#.</span><span class="sxs-lookup"><span data-stu-id="e4387-107">This is the sample C# application.</span></span> <span data-ttu-id="e4387-108">Чтобы проверить приложение, сохраните шаблон (файл TemplateFile.xml), а затем выполните приложение.</span><span class="sxs-lookup"><span data-stu-id="e4387-108">To test the application, save the template (TemplateFile.xml) and then execute the application.</span></span> <span data-ttu-id="e4387-109">Приложение выполняет запрос, указанный в XML-шаблоне, и отображает созданный XML-документ на экране.</span><span class="sxs-lookup"><span data-stu-id="e4387-109">The application executes the query that is specified in the XML template and displays the XML document that is generated on the screen.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e4387-110">В коде необходимо задать имя экземпляра Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в строке соединения.</span><span class="sxs-lookup"><span data-stu-id="e4387-110">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
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
         MemoryStream ms = new MemoryStream();  
         StreamWriter sw = new StreamWriter(ms);  
         ms.Position = 0;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandStream = new FileStream("TemplateFile.xml", FileMode.Open, FileAccess.Read);  
         cmd.CommandType = SqlXmlCommandType.Template;  
         using (Stream strm = cmd.ExecuteStream())  
         {  
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
  
### <a name="to-test-the-application"></a><span data-ttu-id="e4387-111">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="e4387-111">To test the application</span></span>  
  
1.  <span data-ttu-id="e4387-112">Сохраните в папке XML-шаблон (файл TemplateFile.xml), приведенный в этом примере.</span><span class="sxs-lookup"><span data-stu-id="e4387-112">Save the XML template (TemplateFile.xml) that is provided in this example in a folder.</span></span>  
  
2.  <span data-ttu-id="e4387-113">Сохраните код на языке C# (файл DocSample.cs), приведенный в этом разделе, в той папке, где сохранена схема</span><span class="sxs-lookup"><span data-stu-id="e4387-113">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="e4387-114">(если сохранить файлы в разных папках, то придется изменить код, указав путь к каталогу, в котором находится схема сопоставления).</span><span class="sxs-lookup"><span data-stu-id="e4387-114">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
3.  <span data-ttu-id="e4387-115">Скомпилируйте код.</span><span class="sxs-lookup"><span data-stu-id="e4387-115">Compile the code.</span></span> <span data-ttu-id="e4387-116">Чтобы скомпилировать код из командной строки, введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="e4387-116">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="e4387-117">Будет создан исполняемый файл (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="e4387-117">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="e4387-118">Запустите файл DocSample.exe из командной строки.</span><span class="sxs-lookup"><span data-stu-id="e4387-118">At the command prompt, execute DocSample.exe.</span></span>  
  
  
