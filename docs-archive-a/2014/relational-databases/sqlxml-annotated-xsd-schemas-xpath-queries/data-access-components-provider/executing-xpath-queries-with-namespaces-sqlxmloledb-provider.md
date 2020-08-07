---
title: Исполнение запросов XPath с пространствами имен (поставщик SQLXMLOLEDB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, executing XPath queries
- namespaces property
- queries [SQLXML], SQLXMLOLEDB Provider
- XPath queries [SQLXML], namespaces
- XPath queries [SQLXML], SQLXMLOLEDB Provider
- namespaces [SQLXML], XPath queries
ms.assetid: 024a4b7d-435d-47ba-9e80-2c2f640108f5
author: rothja
ms.author: jroth
ms.openlocfilehash: ff692b49a4c32c14655af3a9eb07071dc60ba2a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732470"
---
# <a name="executing-xpath-queries-with-namespaces-sqlxmloledb-provider"></a><span data-ttu-id="51b81-102">Выполнение запросов XPath с пространствами имен (поставщик SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="51b81-102">Executing XPath Queries with Namespaces (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="51b81-103">В запросы XPath могут быть включены пространства имен.</span><span class="sxs-lookup"><span data-stu-id="51b81-103">XPath queries can include namespaces.</span></span> <span data-ttu-id="51b81-104">Если для элементов схемы указано пространство имен (то есть в случае включения целевого пространства имен), то запросы XPath к схеме должны указывать данное пространство имен.</span><span class="sxs-lookup"><span data-stu-id="51b81-104">If the schema elements are namespace qualified (that is, if they include a target namespace), XPath queries against the schema must specify this namespace.</span></span>  
  
 <span data-ttu-id="51b81-105">Так как использование символа-шаблона (\*) не поддерживается в SQLXML 4.0, необходимо указать запрос XPath с помощью префикса пространства имен.</span><span class="sxs-lookup"><span data-stu-id="51b81-105">Because using the wildcard character (\*) is not supported in SQLXML 4.0, you must specify the XPath query by using a namespace prefix.</span></span> <span data-ttu-id="51b81-106">Для разрешения этого префикса используйте свойство namespaces, чтобы указать привязку пространства имен.</span><span class="sxs-lookup"><span data-stu-id="51b81-106">To resolve this prefix, use the namespaces property to specify the namespace binding.</span></span>  
  
 <span data-ttu-id="51b81-107">В следующем примере запрос XPath задает пространства имен, используя подстановочный знак ( \* ) и функции XPath local-name () и Namespace-URI ().</span><span class="sxs-lookup"><span data-stu-id="51b81-107">In the following example, the XPath query specifies namespaces by using the wildcard character (\*) and the local-name() and namespace-uri() XPath functions.</span></span> <span data-ttu-id="51b81-108">Этот запрос XPath возвращает все элементы с локальным именем `Contact` и с URI-кодом пространства имен `urn:myschema:Contacts`.</span><span class="sxs-lookup"><span data-stu-id="51b81-108">This XPath query returns all the elements where the local name is `Contact` and the namespace URI is `urn:myschema:Contacts`.</span></span>  
  
```  
/*[local-name() = 'Contact' and namespace-uri() = 'urn:myschema:Contacts']  
```  
  
 <span data-ttu-id="51b81-109">В SQLXML 4.0 данный запрос XPath должен указываться с префиксом пространства имен.</span><span class="sxs-lookup"><span data-stu-id="51b81-109">In SQLXML 4.0, this XPath query must be specified with a namespace prefix.</span></span> <span data-ttu-id="51b81-110">Примером служит запись `x:Contact`, где `x` представляет префикс пространства имен.</span><span class="sxs-lookup"><span data-stu-id="51b81-110">An example is `x:Contact`, where `x` is the namespace prefix.</span></span> <span data-ttu-id="51b81-111">Рассмотрим следующую схему XSD.</span><span class="sxs-lookup"><span data-stu-id="51b81-111">Consider the following XSD schema:</span></span>  
  
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
  
 <span data-ttu-id="51b81-112">Поскольку эта схема определяет целевое пространство имен, запрос XPath (например «Employee») к схеме должен включать пространство имен.</span><span class="sxs-lookup"><span data-stu-id="51b81-112">Because this schema defines the target namespace, an XPath query (such as "Employee") against the schema must include the namespace.</span></span>  
  
 <span data-ttu-id="51b81-113">Это образец приложения [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic, которое выполняет запрос XPath (x:Сотрудник) к предыдущей схеме XSD.</span><span class="sxs-lookup"><span data-stu-id="51b81-113">This is a sample [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic application that executes an XPath query (x:Employee) against the preceding XSD schema.</span></span> <span data-ttu-id="51b81-114">Для разрешения префикса привязка пространства имен задается с помощью свойства Namespaces.</span><span class="sxs-lookup"><span data-stu-id="51b81-114">To resolve the prefix, the namespace binding is specified by using the namespaces property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="51b81-115">В коде необходимо задать имя экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в строке соединения.</span><span class="sxs-lookup"><span data-stu-id="51b81-115">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="51b81-116">Кроме того, в данном примере задается использование собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SQLNCLI11) для поставщика данных, для которого необходимо установить дополнительное клиентское сетевое ПО.</span><span class="sxs-lookup"><span data-stu-id="51b81-116">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider, which requires additional network client software to be installed.</span></span> <span data-ttu-id="51b81-117">Дополнительные сведения см. в разделе [требования к системе для SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="51b81-117">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Private Sub Form_Load()  
    Dim con As New ADODB.Connection  
    Dim cmd As New ADODB.Command  
    Dim stm As New ADODB.Stream  
    con.Open "provider=SQLXMLOLEDB.4.0;Data Provider=SQLNCLI11;Data Source=SqlServerName;Initial Catalog=AdventureWorks;Integrated Security=SSPI;"  
    Set cmd.ActiveConnection = con  
    stm.Open  
    cmd.Properties("Output Stream").Value = stm  
    cmd.Properties("Output Encoding") = "utf-8"  
    cmd.Properties("Mapping schema") = "C:\DirectoryPath\con-ex.xml"  
    cmd.Properties("namespaces") = "xmlns:x='urn:myschema:Contacts'"  
    '  Debug.Print "Set Command Dialect to DBGUID_XPATH"  
    cmd.Dialect = "{ec2a4293-e898-11d2-b1b7-00c04f680c56}"  
    cmd.CommandText = "x:Contact"  
    cmd.Execute , , adExecuteStream   
    stm.Position = 0  
    Debug.Print stm.ReadText(adReadAll)  
End Sub  
```  
  
### <a name="to-test-this-application"></a><span data-ttu-id="51b81-118">Проверка данного приложения</span><span class="sxs-lookup"><span data-stu-id="51b81-118">To test this application</span></span>  
  
1.  <span data-ttu-id="51b81-119">Сохраните в папке образец схемы XSD.</span><span class="sxs-lookup"><span data-stu-id="51b81-119">Save the sample XSD schema in a folder.</span></span>  
  
2.  <span data-ttu-id="51b81-120">Создайте исполняемый проект Visual Basic и скопируйте в него код.</span><span class="sxs-lookup"><span data-stu-id="51b81-120">Create a Visual Basic executable project, and copy the code into it.</span></span> <span data-ttu-id="51b81-121">При необходимости измените путь к указанному каталогу.</span><span class="sxs-lookup"><span data-stu-id="51b81-121">Change the specified directory path as appropriate.</span></span>  
  
3.  <span data-ttu-id="51b81-122">Добавьте следующую ссылку на проект:</span><span class="sxs-lookup"><span data-stu-id="51b81-122">Add the following project reference:</span></span>  
  
    ```  
    "Microsoft ActiveX Data Objects 2.8 Library"  
    ```  
  
4.  <span data-ttu-id="51b81-123">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="51b81-123">Execute the application.</span></span>  
  
 <span data-ttu-id="51b81-124">Частичный результат:</span><span class="sxs-lookup"><span data-stu-id="51b81-124">This is the partial result:</span></span>  
  
```  
<y0:Employee xmlns:y0="urn:myschema:Contacts"   
             LName="Achong" CID="1" FName="Gustavo"/>  
<y0:Employee xmlns:y0="urn:myschema:Employees"   
             LName="Abel" CID="2" FName="Catherine"/>  
```  
  
 <span data-ttu-id="51b81-125">Префиксы, сформированные в XML-документе, произвольны, но соответствуют этому же пространству имен.</span><span class="sxs-lookup"><span data-stu-id="51b81-125">The prefixes that are generated in the XML document are arbitrary, but they map to the same namespace.</span></span>  
  
  
