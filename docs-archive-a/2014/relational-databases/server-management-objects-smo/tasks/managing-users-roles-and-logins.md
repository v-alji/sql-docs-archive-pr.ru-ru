---
title: Управление пользователями, ролями и именами входа | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- logins [SMO]
- roles [SMO]
- users [SMO]
ms.assetid: 74e411fa-74ed-49ec-ab58-68c250f2280e
author: stevestein
ms.author: sstein
ms.openlocfilehash: bb53e7b4a5748e46c7cb147e1cda50652d8b8805
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666468"
---
# <a name="managing-users-roles-and-logins"></a><span data-ttu-id="702ba-102">Управление пользователями, ролями и именами входа</span><span class="sxs-lookup"><span data-stu-id="702ba-102">Managing Users, Roles, and Logins</span></span>
  <span data-ttu-id="702ba-103">В SMO имена входа представлены объектом <xref:Microsoft.SqlServer.Management.Smo.Login>.</span><span class="sxs-lookup"><span data-stu-id="702ba-103">In SMO, logins are represented by the <xref:Microsoft.SqlServer.Management.Smo.Login> object.</span></span> <span data-ttu-id="702ba-104">Если имя входа существует в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], его можно добавить в роль сервера.</span><span class="sxs-lookup"><span data-stu-id="702ba-104">When the logon exists in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], it can be added to a server role.</span></span> <span data-ttu-id="702ba-105">Роль сервера представлена объектом <xref:Microsoft.SqlServer.Management.Smo.ServerRole>.</span><span class="sxs-lookup"><span data-stu-id="702ba-105">The server role is represented by the <xref:Microsoft.SqlServer.Management.Smo.ServerRole> object.</span></span> <span data-ttu-id="702ba-106">Роль базы данных представлена объектом <xref:Microsoft.SqlServer.Management.Smo.DatabaseRole>, а роль приложения представлена объектом <xref:Microsoft.SqlServer.Management.Smo.ApplicationRole>.</span><span class="sxs-lookup"><span data-stu-id="702ba-106">The database role is represented by the <xref:Microsoft.SqlServer.Management.Smo.DatabaseRole> object and the application role is represented by the <xref:Microsoft.SqlServer.Management.Smo.ApplicationRole> object.</span></span>  
  
 <span data-ttu-id="702ba-107">Права доступа уровня сервера перечислены в виде свойств объекта <xref:Microsoft.SqlServer.Management.Smo.ServerPermission>.</span><span class="sxs-lookup"><span data-stu-id="702ba-107">Privileges associated with the server level are listed as properties of the <xref:Microsoft.SqlServer.Management.Smo.ServerPermission> object.</span></span> <span data-ttu-id="702ba-108">Права доступа уровня сервера можно предоставлять, запрещать или отзывать для отдельных учетных записей входа.</span><span class="sxs-lookup"><span data-stu-id="702ba-108">The server level privileges can be granted to, denied to, or revoked from individual logon accounts.</span></span>  
  
 <span data-ttu-id="702ba-109">У каждого объекта <xref:Microsoft.SqlServer.Management.Smo.Database> есть объект <xref:Microsoft.SqlServer.Management.Smo.UserCollection>, в котором указываются все пользователи базы данных.</span><span class="sxs-lookup"><span data-stu-id="702ba-109">Every <xref:Microsoft.SqlServer.Management.Smo.Database> object has a <xref:Microsoft.SqlServer.Management.Smo.UserCollection> object that specifies all users in the database.</span></span> <span data-ttu-id="702ba-110">С каждым пользователем связано имя входа.</span><span class="sxs-lookup"><span data-stu-id="702ba-110">Each user is associated with a logon.</span></span> <span data-ttu-id="702ba-111">Одно имя входа может быть связано с пользователями в нескольких базах данных.</span><span class="sxs-lookup"><span data-stu-id="702ba-111">One logon can be associated with users in more than one database.</span></span> <span data-ttu-id="702ba-112">Метод <xref:Microsoft.SqlServer.Management.Smo.Login> объекта <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> используется для перечисления всех пользователей во всех базах данных, связанных с именем входа.</span><span class="sxs-lookup"><span data-stu-id="702ba-112">The <xref:Microsoft.SqlServer.Management.Smo.Login> object's <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method can be used to list all users in every database that is associated with the logon.</span></span> <span data-ttu-id="702ba-113">И наоборот, свойство <xref:Microsoft.SqlServer.Management.Smo.User> объекта <xref:Microsoft.SqlServer.Management.Smo.Login> содержит имя входа, связанное с пользователем.</span><span class="sxs-lookup"><span data-stu-id="702ba-113">Alternatively, the <xref:Microsoft.SqlServer.Management.Smo.User> object's <xref:Microsoft.SqlServer.Management.Smo.Login> property specifies the logon that is associated with the user.</span></span>  
  
 <span data-ttu-id="702ba-114">В базах данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] также есть роли, которые определяют набор прав доступа уровня базы данных, позволяющих пользователям выполнять определенные задачи.</span><span class="sxs-lookup"><span data-stu-id="702ba-114">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases also have roles that specify a set of database level privileges that let a user perform specific tasks.</span></span> <span data-ttu-id="702ba-115">В отличие от ролей сервера, роли базы данных не являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="702ba-115">Unlike server roles, database roles are not fixed.</span></span> <span data-ttu-id="702ba-116">Их можно создавать, изменять и удалять.</span><span class="sxs-lookup"><span data-stu-id="702ba-116">They can be created, modified, and removed.</span></span> <span data-ttu-id="702ba-117">Права доступа и пользователей можно назначать роли базы данных для пакетного администрирования.</span><span class="sxs-lookup"><span data-stu-id="702ba-117">Privileges and users can be assigned to a database role for bulk administration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="702ba-118">Пример</span><span class="sxs-lookup"><span data-stu-id="702ba-118">Example</span></span>  
 <span data-ttu-id="702ba-119">В следующем примере кода для создания приложения необходимо выбрать среду программирования, шаблон программирования и язык программирования.</span><span class="sxs-lookup"><span data-stu-id="702ba-119">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="702ba-120">Дополнительные сведения см. в статьях [Создание проекта Visual Basic SMO в Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) и [Создание проекта Visual C&#35; SMO в Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="702ba-120">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="enumerating-logins-and-associated-users-in-visual-basic"></a><span data-ttu-id="702ba-121">Перечисление имен входа и связанных пользователей на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="702ba-121">Enumerating Logins and Associated Users in Visual Basic</span></span>  
 <span data-ttu-id="702ba-122">Каждый пользователь базы данных связан с именем входа.</span><span class="sxs-lookup"><span data-stu-id="702ba-122">Every user in a database is associated with a logon.</span></span> <span data-ttu-id="702ba-123">Имя входа может быть связано с пользователями в нескольких базах данных.</span><span class="sxs-lookup"><span data-stu-id="702ba-123">The logon can be associated with users in more than one database.</span></span> <span data-ttu-id="702ba-124">В этом примере кода показан вызов метода <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> объекта <xref:Microsoft.SqlServer.Management.Smo.Login> для перечисления всех пользователей базы данных, связанных с именем входа.</span><span class="sxs-lookup"><span data-stu-id="702ba-124">The code example shows how to call the <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Login> object to list all the database users who are associated with the logon.</span></span> <span data-ttu-id="702ba-125">В примере создается имя входа и пользователь в базе данных [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] , чтобы обеспечить сведения о сопоставлении для перечисления.</span><span class="sxs-lookup"><span data-stu-id="702ba-125">The example creates a logon and user in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database to make sure there is mapping information to enumerate.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBLogins1](SMO How to#SMO_VBLogins1)]  -->  
  
## <a name="enumerating-logins-and-associated-users-in-visual-c"></a><span data-ttu-id="702ba-126">Перечисление имен входа и связанных пользователей на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="702ba-126">Enumerating Logins and Associated Users in Visual C#</span></span>  
 <span data-ttu-id="702ba-127">Каждый пользователь базы данных связан с именем входа.</span><span class="sxs-lookup"><span data-stu-id="702ba-127">Every user in a database is associated with a logon.</span></span> <span data-ttu-id="702ba-128">Имя входа может быть связано с пользователями в нескольких базах данных.</span><span class="sxs-lookup"><span data-stu-id="702ba-128">The logon can be associated with users in more than one database.</span></span> <span data-ttu-id="702ba-129">В этом примере кода показан вызов метода <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> объекта <xref:Microsoft.SqlServer.Management.Smo.Login> для перечисления всех пользователей базы данных, связанных с именем входа.</span><span class="sxs-lookup"><span data-stu-id="702ba-129">The code example shows how to call the <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Login> object to list all the database users who are associated with the logon.</span></span> <span data-ttu-id="702ba-130">В примере создается имя входа и пользователь в базе данных [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] , чтобы обеспечить сведения о сопоставлении для перечисления.</span><span class="sxs-lookup"><span data-stu-id="702ba-130">The example creates a logon and user in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database to make sure there is mapping information to enumerate.</span></span>  
  
```csharp
{   
Server srv = new Server();   
//Iterate through each database and display.   
  
foreach ( Database db in srv.Databases) {   
   Console.WriteLine("========");   
   Console.WriteLine("Login Mappings for the database: " + db.Name);   
   Console.WriteLine(" ");   
   //Run the EnumLoginMappings method and return details of database user-login mappings to a DataTable object variable.   
   DataTable d;  
   d = db.EnumLoginMappings();   
   //Display the mapping information.   
   foreach (DataRow r in d.Rows) {   
      foreach (DataColumn c in r.Table.Columns) {   
         Console.WriteLine(c.ColumnName + " = " + r[c]);   
      }   
      Console.WriteLine(" ");   
   }   
}   
}  
```  
  
## <a name="enumerating-logins-and-associated-users-in-powershell"></a><span data-ttu-id="702ba-131">Перечисление имен входа и связанных пользователей в PowerShell</span><span class="sxs-lookup"><span data-stu-id="702ba-131">Enumerating Logins and Associated Users in PowerShell</span></span>  
 <span data-ttu-id="702ba-132">Каждый пользователь базы данных связан с именем входа.</span><span class="sxs-lookup"><span data-stu-id="702ba-132">Every user in a database is associated with a logon.</span></span> <span data-ttu-id="702ba-133">Имя входа может быть связано с пользователями в нескольких базах данных.</span><span class="sxs-lookup"><span data-stu-id="702ba-133">The logon can be associated with users in more than one database.</span></span> <span data-ttu-id="702ba-134">В этом примере кода показан вызов метода <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> объекта <xref:Microsoft.SqlServer.Management.Smo.Login> для перечисления всех пользователей базы данных, связанных с именем входа.</span><span class="sxs-lookup"><span data-stu-id="702ba-134">The code example shows how to call the <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Login> object to list all the database users who are associated with the logon.</span></span> <span data-ttu-id="702ba-135">В примере создается имя входа и пользователь в базе данных [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] , чтобы обеспечить сведения о сопоставлении для перечисления.</span><span class="sxs-lookup"><span data-stu-id="702ba-135">The example creates a logon and user in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database to make sure there is mapping information to enumerate.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\Default\Databases  
  
#Iterate through all databases  
 foreach ($db in Get-ChildItem)  
 {  
 "====="  
 "Login Mappings for the database: "+ $db.Name  
  
 #get the datatable containing the mapping from the smo database object  
 $dt = $db.EnumLoginMappings()  
  
 #display the results  
 foreach($row in $dt.Rows)  
     {  
        foreach($col in $row.Table.Columns)  
      {  
        $col.ColumnName + "=" + $row[$col]  
       }
     }  
 }  
```  
  
## <a name="managing-roles-and-users"></a><span data-ttu-id="702ba-136">Управление ролями и пользователями</span><span class="sxs-lookup"><span data-stu-id="702ba-136">Managing Roles and Users</span></span>  
 <span data-ttu-id="702ba-137">Этот образец демонстрирует методы управления ролями и пользователями.</span><span class="sxs-lookup"><span data-stu-id="702ba-137">This sample demonstrates how to how to manage roles and users.</span></span> <span data-ttu-id="702ba-138">В первом образце используется язык C#, во втором — Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="702ba-138">The first sample uses C#, the second Visual Basic.</span></span> <span data-ttu-id="702ba-139">В образцы необходимо включить ссылки на следующие сборки:</span><span class="sxs-lookup"><span data-stu-id="702ba-139">These samples need to reference the following assemblies:</span></span>  
  
-   <span data-ttu-id="702ba-140">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="702ba-140">Microsoft.SqlServer.Smo.dll</span></span>  
  
-   <span data-ttu-id="702ba-141">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span><span class="sxs-lookup"><span data-stu-id="702ba-141">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span></span>  
  
-   <span data-ttu-id="702ba-142">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="702ba-142">Microsoft.SqlServer.ConnectionInfo.dll</span></span>  
  
-   <span data-ttu-id="702ba-143">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="702ba-143">Microsoft.SqlServer.SqlEnum.dll</span></span>  
  
```csharp
using Microsoft.SqlServer.Management.Smo;  
using System;  
  
public class A {  
   public static void Main() {  
      Server svr = new Server();  
      Database db = new Database(svr, "TESTDB");  
      db.Create();  
  
      // Creating Logins  
      Login login = new Login(svr, "Login1");  
      login.LoginType = LoginType.SqlLogin;  
      login.Create("password@1");  
  
      Login login2 = new Login(svr, "Login2");  
      login2.LoginType = LoginType.SqlLogin;  
      login2.Create("password@1");  
  
      // Creating Users in the database for the logins created  
      User user1 = new User(db, "User1");  
      user1.Login = "Login1";  
      user1.Create();  
  
      User user2 = new User(db, "User2");  
      user2.Login = "Login2";  
      user2.Create();  
  
      // Creating database permission Sets  
      DatabasePermissionSet dbPermSet = new DatabasePermissionSet(DatabasePermission.AlterAnySchema);  
      dbPermSet.Add(DatabasePermission.AlterAnyUser);  
  
      DatabasePermissionSet dbPermSet2 = new DatabasePermissionSet(DatabasePermission.CreateType);  
      dbPermSet2.Add(DatabasePermission.CreateSchema);  
      dbPermSet2.Add(DatabasePermission.CreateTable);  
  
      // Creating Database roles  
      DatabaseRole role1 = new DatabaseRole(db, "Role1");  
      role1.Create();  
  
      DatabaseRole role2 = new DatabaseRole(db, "Role2");  
      role2.Create();  
  
      // Granting Database Permission Sets to Roles  
      db.Grant(dbPermSet, role1.Name);  
      db.Grant(dbPermSet2, role2.Name);  
  
      // Adding members (Users / Roles) to Role  
      role1.AddMember("User1");  
  
      role2.AddMember("User2");  
  
      // Role1 becomes a member of Role2  
      role2.AddMember("Role1");  
  
      // Enumerating through explicit permissions granted to Role1  
      // enumerates all database permissions for the Grantee  
      DatabasePermissionInfo[] dbPermsRole1 = db.EnumDatabasePermissions("Role1");     
      foreach (DatabasePermissionInfo dbp in dbPermsRole1) {  
         Console.WriteLine(dbp.Grantee + " has " + dbp.PermissionType.ToString() + " permission.");  
      }  
      Console.WriteLine(" ");  
   }  
}  
```  
  
 <span data-ttu-id="702ba-144">Далее приведена версия этого образца на языке Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="702ba-144">This is the Visual Basic version:</span></span>  
  
```vb
Imports Microsoft.SqlServer.Management.Smo  
  
Public Class A  
   Public Shared Sub Main()  
      Dim svr As New Server()  
      Dim db As New Database(svr, "TESTDB")  
      db.Create()  
  
      ' Creating Logins  
      Dim login As New Login(svr, "Login1")  
      login.LoginType = LoginType.SqlLogin  
      login.Create("password@1")  
  
      Dim login2 As New Login(svr, "Login2")  
      login2.LoginType = LoginType.SqlLogin  
      login2.Create("password@1")  
  
      ' Creating Users in the database for the logins created  
      Dim user1 As New User(db, "User1")  
      user1.Login = "Login1"  
      user1.Create()  
  
      Dim user2 As New User(db, "User2")  
      user2.Login = "Login2"  
      user2.Create()  
  
      ' Creating database permission Sets  
      Dim dbPermSet As New DatabasePermissionSet(DatabasePermission.AlterAnySchema)  
      dbPermSet.Add(DatabasePermission.AlterAnyUser)  
  
      Dim dbPermSet2 As New DatabasePermissionSet(DatabasePermission.CreateType)  
      dbPermSet2.Add(DatabasePermission.CreateSchema)  
      dbPermSet2.Add(DatabasePermission.CreateTable)  
  
      ' Creating Database roles  
      Dim role1 As New DatabaseRole(db, "Role1")  
      role1.Create()  
  
      Dim role2 As New DatabaseRole(db, "Role2")  
      role2.Create()  
  
      ' Granting Database Permission Sets to Roles  
      db.Grant(dbPermSet, role1.Name)  
      db.Grant(dbPermSet2, role2.Name)  
  
      ' Adding members (Users / Roles) to Role  
      role1.AddMember("User1")  
  
      role2.AddMember("User2")  
  
      ' Role1 becomes a member of Role2  
      role2.AddMember("Role1")  
  
      ' Enumerating through explicit permissions granted to Role1  
      ' enumerates all database permissions for the Grantee  
      Dim dbPermsRole1 As DatabasePermissionInfo() = db.EnumDatabasePermissions("Role1")  
      For Each dbp As DatabasePermissionInfo In dbPermsRole1  
         Console.WriteLine(dbp.Grantee + " has " & dbp.PermissionType.ToString() & " permission.")  
      Next  
      Console.WriteLine(" ")  
   End Sub  
End Class  
```  
