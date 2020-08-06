---
title: Применение преобразования XSL (поставщик SQLXMLOLEDB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, applying XSL transformations
- applying XSL transformations [SQLXML]
- xsl property
- Base Path property
- XSL Transformations [SQLXML]
ms.assetid: cb5e41ab-dd20-4873-af20-f417bd1bbf6d
author: rothja
ms.author: jroth
ms.openlocfilehash: 7fbb427a95d9f2308bf65724758a4a1563b42575
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665255"
---
# <a name="applying-an-xsl-transformation-sqlxmloledb-provider"></a><span data-ttu-id="efddf-102">Применение преобразования XSL (поставщик SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="efddf-102">Applying an XSL Transformation (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="efddf-103">В этом образце приложения ADO выполняется SQL-запрос, и к результату применяется преобразование XSL.</span><span class="sxs-lookup"><span data-stu-id="efddf-103">In this sample ADO application, an SQL query is executed, and an XSL transformation is applied to the result.</span></span> <span data-ttu-id="efddf-104">Присвоение свойству Клиентсидексмл значения true обеспечивает обработку набора строк на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="efddf-104">Setting the ClientSideXML property to True enforces the processing of the rowset on the client side.</span></span> <span data-ttu-id="efddf-105">Диалект команды имеет значение {5d531cb2-e6ed-11d2-b252-00c04f681b71}, поскольку SQL-запрос задан в шаблоне, а при выполнении шаблона должен указываться этот диалект.</span><span class="sxs-lookup"><span data-stu-id="efddf-105">The command dialect is set to {5d531cb2-e6ed-11d2-b252-00c04f681b71}, because the SQL query is specified in a template and this dialect must be specified when executing a template.</span></span> <span data-ttu-id="efddf-106">Свойство XSL определяет XSL-файл, используемый для применения преобразования.</span><span class="sxs-lookup"><span data-stu-id="efddf-106">The xsl property specifies the XSL file to use to apply the transformation.</span></span> <span data-ttu-id="efddf-107">Значение свойства базового пути используется для поиска XSL-файла.</span><span class="sxs-lookup"><span data-stu-id="efddf-107">The value of Base Path property is used to search for the XSL file.</span></span> <span data-ttu-id="efddf-108">Если указать путь в значении свойства XSL, то путь будет относиться к пути, указанному в свойстве базового пути.</span><span class="sxs-lookup"><span data-stu-id="efddf-108">If you specify a path in the value of the xsl property, the path is relative to the path that is specified in the Base Path property.</span></span>  
  
 <span data-ttu-id="efddf-109">В этом примере показано, как использовать следующие свойства, определяемые поставщиком SQLXMLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="efddf-109">This example shows how to use the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   <span data-ttu-id="efddf-110">клиентсидексмл</span><span class="sxs-lookup"><span data-stu-id="efddf-110">ClientSideXML</span></span>  
  
-   <span data-ttu-id="efddf-111">xsl</span><span class="sxs-lookup"><span data-stu-id="efddf-111">xsl</span></span>  
  
 <span data-ttu-id="efddf-112">В этом образце клиентского приложения ADO на сервере выполняется XML-шаблон, содержащий SQL-запрос.</span><span class="sxs-lookup"><span data-stu-id="efddf-112">In this client-side ADO sample application, an XML template that consists of an SQL query is executed on the server.</span></span>  
  
 <span data-ttu-id="efddf-113">Так как свойство Клиентсидексмл имеет значение true, инструкция SELECT без предложения FOR XML отправляется на сервер.</span><span class="sxs-lookup"><span data-stu-id="efddf-113">Because the ClientSideXML property is set to True, the SELECT statement without the FOR XML clause is sent to the server.</span></span> <span data-ttu-id="efddf-114">Сервер выполняет запрос и возвращает клиенту набор строк.</span><span class="sxs-lookup"><span data-stu-id="efddf-114">The server executes the query and returns a rowset to the client.</span></span> <span data-ttu-id="efddf-115">Затем клиент применяет к набору строк преобразование FOR XML и создает XML-документ.</span><span class="sxs-lookup"><span data-stu-id="efddf-115">The client then applies the FOR XML transformation to the rowset and produces the XML document.</span></span>  
  
 <span data-ttu-id="efddf-116">Свойство XSL задается в приложении; Таким образом, преобразование «XSL» применяется к XML-документу, созданному на стороне клиента, а результатом является таблица с двумя столбцами.</span><span class="sxs-lookup"><span data-stu-id="efddf-116">The xsl property is specified in the application; therefore, the XSL transformation is applied to the XML document that is generated on the client, and the result is a two-column table.</span></span>  
  
 <span data-ttu-id="efddf-117">Чтобы выполнить команду шаблона, необходимо указать диалект XML-шаблона — {5d531cb2-e6ed-11d2-b252-00c04f681b71}.</span><span class="sxs-lookup"><span data-stu-id="efddf-117">To execute the template command, the XML template dialect - {5d531cb2-e6ed-11d2-b252-00c04f681b71} - must be specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="efddf-118">В коде необходимо задать имя экземпляра Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в строке соединения.</span><span class="sxs-lookup"><span data-stu-id="efddf-118">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="efddf-119">Кроме того, в данном примере указано использование собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в качестве поставщика данных, для чего требуется установка дополнительного клиентского сетевого ПО.</span><span class="sxs-lookup"><span data-stu-id="efddf-119">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client for the data provider which requires additional network client software to be installed.</span></span> <span data-ttu-id="efddf-120">Дополнительные сведения см. в разделе [требования к системе для SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="efddf-120">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub main()  
Dim oTestStream As New ADODB.Stream  
Dim oTestConnection As New ADODB.Connection  
Dim oTestCommand As New ADODB.Command  
oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security=SSPI;"  
Set oTestCommand.ActiveConnection = oTestConnection  
oTestCommand.Properties("ClientSideXML") = True  
oTestCommand.CommandText = _  
        "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql' >" & _  
       " <sql:query> " & _  
        "   SELECT TOP 25 FirstName, LastName FROM Person.Contact FOR XML AUTO " & _  
        "   </sql:query> " & _  
        " </ROOT> "  
oTestStream.Open  
' You need the dialect if you are executing a template.  
oTestCommand.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
oTestCommand.Properties("Output Stream").Value = oTestStream  
oTestCommand.Properties("Base Path").Value = "c:\Schemas\SQLXML4\ExecuteTemplateWithXSL\"  
oTestCommand.Properties("xsl").Value = "myxsl.xsl"  
oTestCommand.Execute , , adExecuteStream  
  
oTestStream.Position = 0  
oTestStream.Charset = "utf-8"  
Debug.Print oTestStream.ReadText(adReadAll)  
End Sub  
Sub Form_Load()  
 main  
End Sub  
```  
  
 <span data-ttu-id="efddf-121">Ниже приведен XSL-шаблон.</span><span class="sxs-lookup"><span data-stu-id="efddf-121">The XSL template follows.</span></span> <span data-ttu-id="efddf-122">Результатом его применения является таблица из двух столбцов.</span><span class="sxs-lookup"><span data-stu-id="efddf-122">The result of applying this XSL template is a two-column table.</span></span>  
  
```  
<?xml version='1.0' encoding='UTF-8'?>            
 <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">   
  
    <xsl:template match = 'Person.Contact'>  
       <TR>  
         <TD><xsl:value-of select = '@FirstName' /></TD>  
         <TD><B><xsl:value-of select = '@LastName' /></B></TD>  
       </TR>  
    </xsl:template>  
    <xsl:template match = '/'>  
      <HTML>  
        <HEAD>  
           <STYLE>th { background-color: #CCCCCC }</STYLE>  
        </HEAD>  
        <BODY>  
         <TABLE border='1' style='width:300;'>  
           <TR><TH colspan='2'>Contacts</TH></TR>  
           <TR>  
              <TH >First name</TH>  
              <TH>Last name</TH>  
           </TR>  
           <xsl:apply-templates select = 'ROOT' />  
         </TABLE>  
        </BODY>  
      </HTML>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
  
