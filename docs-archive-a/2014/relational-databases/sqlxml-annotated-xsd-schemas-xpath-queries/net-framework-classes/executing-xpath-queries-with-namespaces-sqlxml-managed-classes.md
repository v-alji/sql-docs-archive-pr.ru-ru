---
title: Исполнение запросов XPath с пространствами имен (управляемые классы SQLXML) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- namespaces property
- XPath queries [SQLXML], SQLXML Managed Classes
- queries [SQLXML], SQLXML Managed Classes
- XPath queries [SQLXML], namespaces
- Managed Classes [SQLXML], executing XPath queries
- SQLXML Managed Classes, executing XPath queries
- namespaces [SQLXML], XPath queries
ms.assetid: c6fc46d8-6b42-4992-a8f1-a8d4b8886e6e
author: rothja
ms.author: jroth
ms.openlocfilehash: a2d726de95929709c1ae958ee22388df3195bc84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654123"
---
# <a name="executing-xpath-queries-with-namespaces-sqlxml-managed-classes"></a><span data-ttu-id="7ed9e-102">Выполнение запросов XPath с пространствами имен (управляемые классы SQLXML)</span><span class="sxs-lookup"><span data-stu-id="7ed9e-102">Executing XPath Queries with Namespaces (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="7ed9e-103">В запросы XPath могут быть включены пространства имен.</span><span class="sxs-lookup"><span data-stu-id="7ed9e-103">XPath queries can include namespaces.</span></span> <span data-ttu-id="7ed9e-104">Если имена элементов схемы уточнены именем пространства имен (используйте целевое пространство имен), оно должно быть указано в запросах XPath к этой схеме.</span><span class="sxs-lookup"><span data-stu-id="7ed9e-104">If the schema elements are namespace-qualified (use a target namespace), the XPath queries against the schema must specify the namespace.</span></span>  
  
 <span data-ttu-id="7ed9e-105">Поскольку символ-шаблон (\*) в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 не поддерживается, запрос XPath нужно задавать с указанием префикса пространства имен.</span><span class="sxs-lookup"><span data-stu-id="7ed9e-105">Because the wildcard character (\*) is not supported in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, you must specify the XPath query by using a namespace prefix.</span></span> <span data-ttu-id="7ed9e-106">Для разрешения префикса используйте свойство namespaces, чтобы указать привязку пространства имен.</span><span class="sxs-lookup"><span data-stu-id="7ed9e-106">To resolve the prefix, use the namespaces property to specify the namespace binding.</span></span>  
  
 <span data-ttu-id="7ed9e-107">В следующем примере запрос XPath задает пространства имен, используя подстановочный знак ( \* ) и функции XPath local-name () и Namespace-URI ().</span><span class="sxs-lookup"><span data-stu-id="7ed9e-107">In the following example, the XPath query specifies namespaces by using the wildcard character (\*) and the local-name() and namespace-uri() XPath functions.</span></span> <span data-ttu-id="7ed9e-108">Этот запрос XPath возвращает все элементы с местным именем `Employee` и URI-кодом пространства имен `urn:myschema:Contacts`:</span><span class="sxs-lookup"><span data-stu-id="7ed9e-108">This XPath query returns all the elements where the local name is `Employee` and the namespace URI is `urn:myschema:Contacts`:</span></span>  
  
```  
/*[local-name() = 'Contact' and namespace-uri() = 'urn:myschema:Contacts']  
```  
  
 <span data-ttu-id="7ed9e-109">В SQLXML 4.0 этот запрос XPath необходимо указывать с префиксом пространства имен.</span><span class="sxs-lookup"><span data-stu-id="7ed9e-109">In SQLXML 4.0, specify this XPath query with a namespace prefix.</span></span> <span data-ttu-id="7ed9e-110">Примером служит запись `x:Contact`, где `x` представляет префикс пространства имен.</span><span class="sxs-lookup"><span data-stu-id="7ed9e-110">An example is `x:Contact`, where `x` is the namespace prefix.</span></span> <span data-ttu-id="7ed9e-111">Рассмотрим следующую схему XSD.</span><span class="sxs-lookup"><span data-stu-id="7ed9e-111">Consider the following XSD schema:</span></span>  
  
```  
<schema xmlns="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
            xmlns:con="urn:myschema:Contacts"  
            targetNamespace="urn:myschema:Contacts">  
<complexType name="ContactType">  
  <attribute name="CID" sql:field="ContactID" type="ID"/>  
  <attribute name="FName" sql:field="FirstName" type="string"/>  
  <attribute name="LName" sql:field="LastName"/>   
</complexType>  
<element name="Contact" type="con:ContactType" sql:relation="Person.Contact"/>  
</schema>  
```  
  
 <span data-ttu-id="7ed9e-112">Поскольку эта схема задает целевое пространство имен, запрос XPath к этой схеме (например, «Employee») должен содержать пространство имен.</span><span class="sxs-lookup"><span data-stu-id="7ed9e-112">Because this schema defines the target namespace, an XPath query (such as "Employee") against this schema must include the namespace.</span></span>  
  
 <span data-ttu-id="7ed9e-113">Следующие образец приложения на C# исполняет запрос XPath к предыдущей схеме XSD (MySchema.xml).</span><span class="sxs-lookup"><span data-stu-id="7ed9e-113">The following C# sample application executes an XPath query against the preceding XSD schema (MySchema.xml).</span></span> <span data-ttu-id="7ed9e-114">Чтобы разрешить префикс, укажите привязку пространства имен с помощью свойства Namespaces объекта SqlXmlCommand.</span><span class="sxs-lookup"><span data-stu-id="7ed9e-114">To resolve the prefix, specify the namespace binding by using the Namespaces property of the SqlXmlCommand object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7ed9e-115">В коде необходимо задать имя экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в строке соединения.</span><span class="sxs-lookup"><span data-stu-id="7ed9e-115">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testXPath()  
      {  
         //Stream strm;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandText = "x:Contact[@CID='1']";  
         cmd.CommandType = SqlXmlCommandType.XPath;  
         cmd.RootTag = "ROOT";  
         cmd.Namespaces = "xmlns:x='urn:myschema:Contacts'";  
         cmd.SchemaPath = "MySchema.xml";  
         using (Stream strm = cmd.ExecuteStream()){  
            using (StreamReader sr = new StreamReader(strm)){  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         return 0;  
      }  
      public static int Main(String[] args)  
      {  
         testXPath();  
         return 0;  
      }  
   }  
```  
  
 <span data-ttu-id="7ed9e-116">Чтобы проверить этот пример, необходимо установить на компьютер платформу [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7ed9e-116">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="7ed9e-117">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="7ed9e-117">To test the application</span></span>  
  
1.  <span data-ttu-id="7ed9e-118">Сохраните в папке приведенную в этом примере схему XSD (MySchema.xml).</span><span class="sxs-lookup"><span data-stu-id="7ed9e-118">Save the XSD schema (MySchema.xml) that is provided in this example in a folder.</span></span>  
  
2.  <span data-ttu-id="7ed9e-119">Сохраните код на языке C# (файл DocSample.cs), приведенный в этом разделе, в той папке, где сохранена схема</span><span class="sxs-lookup"><span data-stu-id="7ed9e-119">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="7ed9e-120">(если сохранить файлы в разных папках, то придется изменить код, указав путь к каталогу, в котором находится схема сопоставления).</span><span class="sxs-lookup"><span data-stu-id="7ed9e-120">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
3.  <span data-ttu-id="7ed9e-121">Скомпилируйте код.</span><span class="sxs-lookup"><span data-stu-id="7ed9e-121">Compile the code.</span></span> <span data-ttu-id="7ed9e-122">Чтобы скомпилировать код из командной строки, введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="7ed9e-122">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="7ed9e-123">Будет создан исполняемый файл (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="7ed9e-123">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="7ed9e-124">Запустите файл DocSample.exe из командной строки.</span><span class="sxs-lookup"><span data-stu-id="7ed9e-124">At the command prompt, execute DocSample.exe.</span></span>  
  
  
