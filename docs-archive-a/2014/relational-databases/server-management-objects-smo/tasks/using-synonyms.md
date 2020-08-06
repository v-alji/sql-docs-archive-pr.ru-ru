---
title: Использование синонимов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- synonyms [SMO]
ms.assetid: db0a9022-9549-43e5-b6b3-deb236f05fb8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5e8416dc3daea3b173fae92e5454a8a65c399e53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668728"
---
# <a name="using-synonyms"></a><span data-ttu-id="4cc20-102">Использование синонимов</span><span class="sxs-lookup"><span data-stu-id="4cc20-102">Using Synonyms</span></span>
  <span data-ttu-id="4cc20-103">Синоним — это альтернативное имя, которое дается объекту в области схемы.</span><span class="sxs-lookup"><span data-stu-id="4cc20-103">A synonym is an alternative name for a schema-scoped object.</span></span> <span data-ttu-id="4cc20-104">В SMO синонимы представлены объектом <xref:Microsoft.SqlServer.Management.Smo.Synonym>.</span><span class="sxs-lookup"><span data-stu-id="4cc20-104">In SMO, synonyms are represented by the <xref:Microsoft.SqlServer.Management.Smo.Synonym> object.</span></span> <span data-ttu-id="4cc20-105">Объект <xref:Microsoft.SqlServer.Management.Smo.Synonym> является дочерним для объекта <xref:Microsoft.SqlServer.Management.Smo.Database>.</span><span class="sxs-lookup"><span data-stu-id="4cc20-105">The <xref:Microsoft.SqlServer.Management.Smo.Synonym> object is a child of the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span> <span data-ttu-id="4cc20-106">Это означает, что синонимы действительны только в пределах базы данных, в которой они определены.</span><span class="sxs-lookup"><span data-stu-id="4cc20-106">This means that synonyms are valid only within the scope of the database in which they are defined.</span></span> <span data-ttu-id="4cc20-107">Однако синоним может относиться к объектам другой базы данных или к удаленному экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cc20-107">However, the synonym can refer to objects on another database, or on a remote instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4cc20-108">Объект, которому дано альтернативное имя, известен как базовый объект.</span><span class="sxs-lookup"><span data-stu-id="4cc20-108">The object that is given an alternative name is known as the base object.</span></span> <span data-ttu-id="4cc20-109">Свойство имени объекта <xref:Microsoft.SqlServer.Management.Smo.Synonym> служит альтернативным именем базового объекта.</span><span class="sxs-lookup"><span data-stu-id="4cc20-109">The name property of the <xref:Microsoft.SqlServer.Management.Smo.Synonym> object is the alternative name given to the base object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cc20-110">Пример</span><span class="sxs-lookup"><span data-stu-id="4cc20-110">Example</span></span>  
 <span data-ttu-id="4cc20-111">В следующем примере кода для создания приложения необходимо выбрать среду программирования, шаблон программирования и язык программирования.</span><span class="sxs-lookup"><span data-stu-id="4cc20-111">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="4cc20-112">Дополнительные сведения см. в статьях [Создание проекта Visual Basic SMO в Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) и [Создание проекта Visual C&#35; SMO в Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="4cc20-112">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-synonym-in-visual-basic"></a><span data-ttu-id="4cc20-113">Создание синонима на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4cc20-113">Creating a Synonym in Visual Basic</span></span>  
 <span data-ttu-id="4cc20-114">Этот пример кода показывает, как создать синоним или альтернативное имя для объекта из области схемы.</span><span class="sxs-lookup"><span data-stu-id="4cc20-114">The code example shows how to create a synonym or an alternate name for a schema scoped object.</span></span> <span data-ttu-id="4cc20-115">Клиентские приложения для ссылки на базовый объект могут использовать одну ссылку на него через синоним вместо использования имени, состоящего из нескольких частей.</span><span class="sxs-lookup"><span data-stu-id="4cc20-115">Client applications can use a single reference for the base object via a synonym instead of using a multiple part name to reference the base object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBSynonyms1](SMO How to#SMO_VBSynonyms1)]  -->  
  
## <a name="creating-a-synonym-in-visual-c"></a><span data-ttu-id="4cc20-116">Создание синонима на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="4cc20-116">Creating a Synonym in Visual C#</span></span>  
 <span data-ttu-id="4cc20-117">Этот пример кода показывает, как создать синоним или альтернативное имя для объекта из области схемы.</span><span class="sxs-lookup"><span data-stu-id="4cc20-117">The code example shows how to create a synonym or an alternate name for a schema scoped object.</span></span> <span data-ttu-id="4cc20-118">Клиентские приложения для ссылки на базовый объект могут использовать одну ссылку на него через синоним вместо использования имени, состоящего из нескольких частей.</span><span class="sxs-lookup"><span data-stu-id="4cc20-118">Client applications can use a single reference for the base object via a synonym instead of using a multiple part name to reference the base object.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
  
            //Reference the AdventureWorks2012 database.   
            Database db = srv.Databases["AdventureWorks2012"];  
  
            //Define a Synonym object variable by supplying the   
            //parent database, name, and schema arguments in the constructor.   
            //The name is also a synonym of the name of the base object.   
            Synonym syn = new Synonym(db, "Shop", "Sales");  
  
            //Specify the base object, which is the object on which   
            //the synonym is based.   
            syn.BaseDatabase = "AdventureWorks2012";  
            syn.BaseSchema = "Sales";  
            syn.BaseObject = "Store";  
            syn.BaseServer = srv.Name;  
  
            //Create the synonym on the instance of SQL Server.   
            syn.Create();  
        }  
```  
  
## <a name="creating-a-synonym-in-powershell"></a><span data-ttu-id="4cc20-119">Создание синонима в PowerShell</span><span class="sxs-lookup"><span data-stu-id="4cc20-119">Creating a Synonym in PowerShell</span></span>  
 <span data-ttu-id="4cc20-120">Этот пример кода показывает, как создать синоним или альтернативное имя для объекта из области схемы.</span><span class="sxs-lookup"><span data-stu-id="4cc20-120">The code example shows how to create a synonym or an alternate name for a schema scoped object.</span></span> <span data-ttu-id="4cc20-121">Клиентские приложения для ссылки на базовый объект могут использовать одну ссылку на него через синоним вместо использования имени, состоящего из нескольких частей.</span><span class="sxs-lookup"><span data-stu-id="4cc20-121">Client applications can use a single reference for the base object via a synonym instead of using a multiple part name to reference the base object.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#And the database object corresponding to Adventureworks  
$db = $srv.Databases["AdventureWorks2012"]  
  
$syn = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Synonym -ArgumentList $db, "Shop", "Sales"  
  
#Specify the base object, which is the object on which the synonym is based.  
$syn.BaseDatabase = "AdventureWorks2012"  
$syn.BaseSchema = "Sales"  
$syn.BaseObject = "Store"  
$syn.BaseServer = $srv.Name  
  
#Create the synonym on the instance of SQL Server.  
$syn.Create()  
```  
  
## <a name="see-also"></a><span data-ttu-id="4cc20-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="4cc20-122">See Also</span></span>  
 [<span data-ttu-id="4cc20-123">CREATE SYNONYM (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4cc20-123">CREATE SYNONYM &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-synonym-transact-sql)  
