---
title: Доступ к функциям SQLXML в среде .NET | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], accessing SQLXML functionality
- SQLXML Managed Classes, accessing SQLXML functionality
- DiffGrams [SQLXML], accessing SQLXML functionality
- .NET Framework [SQLXML], accessing SQLXML functionality
ms.assetid: 74744535-2945-414d-9a5b-7e8cc363953a
author: rothja
ms.author: jroth
ms.openlocfilehash: a2ba0a54310833c0a1a1315aa94d78fe5650d480
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664808"
---
# <a name="accessing-sqlxml-functionality-in-the-net-environment"></a><span data-ttu-id="ea0c5-102">Доступ к функциональным возможностям SQLXML в среде .NET</span><span class="sxs-lookup"><span data-stu-id="ea0c5-102">Accessing SQLXML Functionality in the .NET Environment</span></span>
  <span data-ttu-id="ea0c5-103">В этом примере показаны следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="ea0c5-103">This example shows:</span></span>  
  
-   <span data-ttu-id="ea0c5-104">Использование [!INCLUDE[msCoName](../../../includes/msconame-md.md)] управляемых классов SQLXML (Microsoft. Data. SQLXML) для доступа к Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] среде .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ea0c5-104">How to use [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML Managed Classes (Microsoft.Data.SqlXml) to access Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework environment.</span></span>  
  
-   <span data-ttu-id="ea0c5-105">Как дельты, сформированные в среде .NET Framework, могут применять изменения данных к таблицам [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea0c5-105">How DiffGrams that are generated in the .NET Framework environment can apply data updates to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables.</span></span>  
  
 <span data-ttu-id="ea0c5-106">В этом приложении запрос XPath выполняется применительно к схеме XSD.</span><span class="sxs-lookup"><span data-stu-id="ea0c5-106">In this application, an XPath query is executed against an XSD schema.</span></span> <span data-ttu-id="ea0c5-107">Выполнение запроса XPath возвращает XML-документ, состоящий из контактных данных (**FirstName**, **LastName**).</span><span class="sxs-lookup"><span data-stu-id="ea0c5-107">The execution of the XPath query returns an XML document that consists of contact data (**FirstName**, **LastName**).</span></span> <span data-ttu-id="ea0c5-108">Приложение загружает XML-документ в набор данных в среде .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ea0c5-108">The application loads the XML document in the dataset in the .NET Framework environment.</span></span> <span data-ttu-id="ea0c5-109">Данные в наборе данных изменяются: имя первого контакта в наборе данных меняется на «Сьюзен».</span><span class="sxs-lookup"><span data-stu-id="ea0c5-109">The data in the dataset is modified: the contact's first name is changed to "Susan" for the first contact in the dataset.</span></span> <span data-ttu-id="ea0c5-110">Из набора данных создается дельта, и обновление, заданное в дельте (изменение имени сотрудника), применяется к таблице Person.Contact.</span><span class="sxs-lookup"><span data-stu-id="ea0c5-110">The DiffGram is generated from the dataset, and the update that is specified in the DiffGram (the change in the employee's first name) is then applied to the Person.Contact table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea0c5-111">В коде необходимо задать имя экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в строке соединения.</span><span class="sxs-lookup"><span data-stu-id="ea0c5-111">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using System.Data;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=SqlServerName;database=AdventureWorks;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      DataRow row;  
      SqlXmlAdapter ad;  
      //need a memory stream to hold diff gram temporarily  
      MemoryStream ms = new MemoryStream();  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.RootTag = "ROOT";  
      cmd.CommandText = "Con";  
      cmd.CommandType = SqlXmlCommandType.XPath;  
      cmd.SchemaPath = "MySchema.xml";  
      //load data set  
      DataSet ds = new DataSet();  
      ad = new SqlXmlAdapter(cmd);  
      ad.Fill(ds);  
      row = ds.Tables["Con"].Rows[0];  
      row["FName"] = "Susan";  
      ad.Update(ds);  
      return 0;  
   }  
   public static int Main(String[] args)  
   {  
      testParams();  
      return 0;  
   }  
}  
```  
  
 <span data-ttu-id="ea0c5-112">**Проверка этого примера**</span><span class="sxs-lookup"><span data-stu-id="ea0c5-112">**To test the example:**</span></span>  
  
 <span data-ttu-id="ea0c5-113">Чтобы проверить этот пример, необходимо установить на компьютер платформу [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ea0c5-113">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
1.  <span data-ttu-id="ea0c5-114">Сохраните эту схему XSD (MySchema.xml) в папке.</span><span class="sxs-lookup"><span data-stu-id="ea0c5-114">Save this XSD schema (MySchema.xml) in a folder:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="Con" sql:relation="Person.Contact" >  
       <xsd:complexType>  
         <xsd:sequence>  
            <xsd:element name="FName"    
                         sql:field="FirstName"   
                         type="xsd:string" />   
            <xsd:element name="LName"    
                         sql:field="LastName"    
                         type="xsd:string" />  
         </xsd:sequence>  
         <xsd:attribute name="ContactID" type="xsd:integer" />  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
2.  <span data-ttu-id="ea0c5-115">Сохраните код на языке C# (файл DocSample.cs), приведенный в этом примере, в той папке, где хранится схема</span><span class="sxs-lookup"><span data-stu-id="ea0c5-115">Save the C# code (DocSample.cs) provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="ea0c5-116">(если сохранить файлы в разных папках, то придется изменить код, указав путь к каталогу, в котором находится схема сопоставления).</span><span class="sxs-lookup"><span data-stu-id="ea0c5-116">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
3.  <span data-ttu-id="ea0c5-117">Скомпилируйте код.</span><span class="sxs-lookup"><span data-stu-id="ea0c5-117">Compile the code.</span></span> <span data-ttu-id="ea0c5-118">Чтобы скомпилировать код из командной строки, введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="ea0c5-118">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="ea0c5-119">Будет создан исполняемый файл (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="ea0c5-119">This creates an executable (DocSample.exe).</span></span>  
  
 <span data-ttu-id="ea0c5-120">Запустите файл DocSample.exe из командной строки.</span><span class="sxs-lookup"><span data-stu-id="ea0c5-120">At the command prompt, execute DocSample.exe.</span></span>  
  
  
