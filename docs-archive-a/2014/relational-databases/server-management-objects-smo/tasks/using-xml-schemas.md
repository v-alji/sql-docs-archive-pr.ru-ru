---
title: Использование схем XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- XML [SMO]
ms.assetid: 9d04de01-efeb-4b2d-8c28-3234bc7ff2f3
author: stevestein
ms.author: sstein
ms.openlocfilehash: a0e5c58bb05da7025651a4e55e29541d694ba1ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750575"
---
# <a name="using-xml-schemas"></a><span data-ttu-id="569f1-102">Использование схем XML</span><span class="sxs-lookup"><span data-stu-id="569f1-102">Using XML Schemas</span></span>
  <span data-ttu-id="569f1-103">Программирование XML в SMO ограничено предоставлением типов данных XML, пространств имен XML и простым индексированием по столбцам данных XML.</span><span class="sxs-lookup"><span data-stu-id="569f1-103">XML programming in SMO is limited to providing XML data types, XML namespaces, and simple indexing on XML data type columns.</span></span>  
  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="569f1-104">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]предоставляет собственное хранилище для экземпляров XML-документов.</span><span class="sxs-lookup"><span data-stu-id="569f1-104">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provides native storage for XML document instances.</span></span> <span data-ttu-id="569f1-105">Схемы XML позволяют определять сложные типы данных XML, которые можно использовать для проверки XML-документов с целью обеспечения целостности данных.</span><span class="sxs-lookup"><span data-stu-id="569f1-105">XML schemas let you define complex XML data types, which can be used to validate XML documents to ensure data integrity.</span></span> <span data-ttu-id="569f1-106">Схема XML определяется в объекте <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>.</span><span class="sxs-lookup"><span data-stu-id="569f1-106">The XML schema is defined in the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="569f1-107">Пример</span><span class="sxs-lookup"><span data-stu-id="569f1-107">Example</span></span>  
 <span data-ttu-id="569f1-108">Чтобы использовать какой-либо из представленных примеров кода, нужно выбрать среду, шаблон и язык программирования, с помощью которых будет создаваться приложение.</span><span class="sxs-lookup"><span data-stu-id="569f1-108">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="569f1-109">Дополнительные сведения см. в статьях [Создание проекта Visual Basic SMO в Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) или [Создание проекта Visual C&#35; SMO в Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="569f1-109">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-an-xml-schema-in-visual-basic"></a><span data-ttu-id="569f1-110">Создание схемы XML на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="569f1-110">Creating an XML Schema in Visual Basic</span></span>  
 <span data-ttu-id="569f1-111">В этом примере кода показано создание схемы XML с помощью объекта <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>.</span><span class="sxs-lookup"><span data-stu-id="569f1-111">This code example shows how to create an XML schema by using the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span> <span data-ttu-id="569f1-112">Свойство <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A>, определяющее коллекцию схем XML, содержит несколько двойных кавычек.</span><span class="sxs-lookup"><span data-stu-id="569f1-112">The <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> property, which defines the XML schema collection, contains several double quotation marks.</span></span> <span data-ttu-id="569f1-113">Они заменяются строкой `chr(34)` .</span><span class="sxs-lookup"><span data-stu-id="569f1-113">These are replaced by the `chr(34)` string.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBXMLSchema1](SMO How to#SMO_VBXMLSchema1)]  -->  
  
## <a name="creating-an-xml-schema-in-visual-c"></a><span data-ttu-id="569f1-114">Создание схемы XML на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="569f1-114">Creating an XML Schema in Visual C#</span></span>  
 <span data-ttu-id="569f1-115">В этом примере кода показано создание схемы XML с помощью объекта <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>.</span><span class="sxs-lookup"><span data-stu-id="569f1-115">This code example shows how to create an XML schema by using the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span> <span data-ttu-id="569f1-116">Свойство <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A>, определяющее коллекцию схем XML, содержит несколько двойных кавычек.</span><span class="sxs-lookup"><span data-stu-id="569f1-116">The <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> property, which defines the XML schema collection, contains several double quotation marks.</span></span> <span data-ttu-id="569f1-117">Они заменяются строкой `chr(34)` .</span><span class="sxs-lookup"><span data-stu-id="569f1-117">These are replaced by the `chr(34)` string.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = default(Server);  
            srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db = default(Database);  
            db = srv.Databases["AdventureWorks2012"];  
            //Define an XmlSchemaCollection object by supplying the parent  
            // database and name arguments in the constructor.   
            XmlSchemaCollection xsc = default(XmlSchemaCollection);  
            xsc = new XmlSchemaCollection(db, "MySampleCollection");  
            xsc.Text = "<schema xmlns=" + Strings.Chr(34) + "http://www.w3.org/2001/XMLSchema" + Strings.Chr(34) + " xmlns:ns=" + Strings.Chr(34) + "http://ns" + Strings.Chr(34) + "><element name=" + Strings.Chr(34) + "e" + Strings.Chr(34) + " type=" + Strings.Chr(34) + "dateTime" + Strings.Chr(34) + "/></schema>";  
            //Create the XML schema collection on the instance of SQL Server.   
            xsc.Create();  
        }  
```  
  
## <a name="creating-an-xml-schema-in-powershell"></a><span data-ttu-id="569f1-118">Создание схемы XML в PowerShell</span><span class="sxs-lookup"><span data-stu-id="569f1-118">Creating an XML Schema in PowerShell</span></span>  
 <span data-ttu-id="569f1-119">В этом примере кода показано создание схемы XML с помощью объекта <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>.</span><span class="sxs-lookup"><span data-stu-id="569f1-119">This code example shows how to create an XML schema by using the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span> <span data-ttu-id="569f1-120">Свойство <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A>, определяющее коллекцию схем XML, содержит несколько двойных кавычек.</span><span class="sxs-lookup"><span data-stu-id="569f1-120">The <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> property, which defines the XML schema collection, contains several double quotation marks.</span></span> <span data-ttu-id="569f1-121">Они заменяются строкой `chr(34)` .</span><span class="sxs-lookup"><span data-stu-id="569f1-121">These are replaced by the `chr(34)` string.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance replace LocalMachine with the physical server  
cd \sql\LocalHost  
$srv = Get-Item default  
  
#Reference the AdventureWorks database.  
$db = $srv.Databases["AdventureWorks2012"]  
  
#Create a new schema collection  
$xsc = New-Object -TypeName Microsoft.SqlServer.Management.SMO.XmlSchemaCollection `  
-argumentlist $db,"MySampleCollection"  
  
#Add the xml  
$dq = '"' # the double quote character  
$xsc.Text = "<schema xmlns=" + $dq + "http://www.w3.org/2001/XMLSchema" + $dq + `  
"  xmlns:ns=" + $dq + "http://ns" + $dq + "><element name=" + $dq + "e" + $dq +`  
 " type=" + $dq + "dateTime" + $dq + "/></schema>"  
  
#Create the XML schema collection on the instance of SQL Server.  
$xsc.Create()  
```  
