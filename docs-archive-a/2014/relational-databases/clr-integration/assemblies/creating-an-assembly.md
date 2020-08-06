---
title: Создание сборки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- creating assemblies
- UNSAFE assemblies
- CREATE ASSEMBLY statement
- SAFE assemblies
- EXTERNAL_ACCESS assemblies
- assemblies [CLR integration], creating
ms.assetid: a2bc503d-b6b2-4963-8beb-c11c323f18e0
author: rothja
ms.author: jroth
ms.openlocfilehash: 9dea1f8fe57691f05274cac353a1064420309e06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735334"
---
# <a name="creating-an-assembly"></a><span data-ttu-id="94b69-102">Создание сборки</span><span class="sxs-lookup"><span data-stu-id="94b69-102">Creating an Assembly</span></span>
  <span data-ttu-id="94b69-103">Управляемые объекты базы данных, например хранимые процедуры или триггеры, компилируются и развертываются в единицах, называемых сборками.</span><span class="sxs-lookup"><span data-stu-id="94b69-103">Managed database objects, such as stored procedures or triggers, are compiled and then deployed in units called an assembly.</span></span> <span data-ttu-id="94b69-104">Управляемые сборки DLL должны быть зарегистрированы в, [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] прежде чем можно будет использовать функциональные возможности, предоставляемые сборкой.</span><span class="sxs-lookup"><span data-stu-id="94b69-104">Managed DLL assemblies must be registered in [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] before the functionality the assembly provides can be used.</span></span> <span data-ttu-id="94b69-105">Для регистрации сборки в базе данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] используется инструкция CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="94b69-105">To register an assembly in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, use the CREATE ASSEMBLY statement.</span></span> <span data-ttu-id="94b69-106">В этом разделе описывается регистрация сборки с помощью инструкции CREATE ASSEMBLY и способы указания параметров безопасности для сборки.</span><span class="sxs-lookup"><span data-stu-id="94b69-106">This topic discusses how to register an assembly in a database using the CREATE ASSEMBLY statement, and how to specify the security settings for the assembly.</span></span>  
  
## <a name="the-create-assembly-statement"></a><span data-ttu-id="94b69-107">Инструкция CREATE ASSEMBLY</span><span class="sxs-lookup"><span data-stu-id="94b69-107">The CREATE ASSEMBLY Statement</span></span>  
 <span data-ttu-id="94b69-108">Инструкция CREATE ASSEMBLY используется для создания сборки в базе данных.</span><span class="sxs-lookup"><span data-stu-id="94b69-108">The CREATE ASSEMBLY statement is used to create an assembly in a database.</span></span> <span data-ttu-id="94b69-109">Например:</span><span class="sxs-lookup"><span data-stu-id="94b69-109">Here is an example:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll';  
```  
  
 <span data-ttu-id="94b69-110">Предложение FROM задает путь к создаваемой сборке.</span><span class="sxs-lookup"><span data-stu-id="94b69-110">The FROM clause specifies the pathname of the assembly to create.</span></span> <span data-ttu-id="94b69-111">Путь может указываться в формате UNC или быть локальным физическим путем к файлу.</span><span class="sxs-lookup"><span data-stu-id="94b69-111">This path can either be a Universal Naming Convention (UNC) path or a physical file path that is local to the machine.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="94b69-112">не дает возможность регистрировать различные версии сборок с одинаковыми именами, культурой и открытыми ключами.</span><span class="sxs-lookup"><span data-stu-id="94b69-112">does not allow registering different versions of an assembly with the same name, culture and public key.</span></span>  
  
 <span data-ttu-id="94b69-113">Можно создавать сборки, ссылающиеся на другие сборки.</span><span class="sxs-lookup"><span data-stu-id="94b69-113">It is possible to create assemblies that reference other assemblies.</span></span> <span data-ttu-id="94b69-114">При создании сборки в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] также создает сборки, на которые ссылается сборка корневого уровня, если сборки, на которые имеются ссылки, еще не созданы в базе данных.</span><span class="sxs-lookup"><span data-stu-id="94b69-114">When an assembly is created in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] also creates the assemblies referenced by the root-level assembly, if the referenced assemblies are not already created into the database.</span></span>  
  
 <span data-ttu-id="94b69-115">Пользователям базы данных или ролям пользователей предоставляются разрешения на создание в базе данных сборок, владельцами которых они будут.</span><span class="sxs-lookup"><span data-stu-id="94b69-115">Database users or user roles are given permissions to create, and thereby own, assemblies in a database.</span></span> <span data-ttu-id="94b69-116">Чтобы создавать сборки, пользователь или роль базы данных должны иметь разрешение CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="94b69-116">In order to create assemblies, the database user or role should have the CREATE ASSEMBLY permission.</span></span>  
  
 <span data-ttu-id="94b69-117">Сборка может успешно ссылаться на другие сборки только при следующих условиях.</span><span class="sxs-lookup"><span data-stu-id="94b69-117">An assembly can only succeed in referencing other assemblies if:</span></span>  
  
-   <span data-ttu-id="94b69-118">Владельцем сборки, которую вызывает или на которую ссылается пользователь или роль, является этот пользователь или роль.</span><span class="sxs-lookup"><span data-stu-id="94b69-118">The assembly that is called or referenced is owned by the same user or role.</span></span>  
  
-   <span data-ttu-id="94b69-119">Сборка, которая вызывается или на которую указывает ссылка, была создана в этой базе данных.</span><span class="sxs-lookup"><span data-stu-id="94b69-119">The assembly that is called or referenced was created in the same database.</span></span>  
  
## <a name="specifying-security-when-creating-assemblies"></a><span data-ttu-id="94b69-120">Уровни безопасности при создании сборки</span><span class="sxs-lookup"><span data-stu-id="94b69-120">Specifying Security When Creating Assemblies</span></span>  
 <span data-ttu-id="94b69-121">При создании сборки в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] базе данных можно указать один из трех уровней безопасности, в которых может выполняться код: `SAFE` , `EXTERNAL_ACCESS` или `UNSAFE` .</span><span class="sxs-lookup"><span data-stu-id="94b69-121">When creating an assembly into a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, you can specify one of three different levels of security in which your code can run: `SAFE`, `EXTERNAL_ACCESS`, or `UNSAFE`.</span></span> <span data-ttu-id="94b69-122">При вызове инструкции `CREATE ASSEMBLY` в коде сборки выполняются определенные проверки, в результате которых сборка может быть не зарегистрирована на сервере.</span><span class="sxs-lookup"><span data-stu-id="94b69-122">When the `CREATE ASSEMBLY` statement is run, certain checks are performed on the code assembly which may cause the assembly to fail to register on the server.</span></span> <span data-ttu-id="94b69-123">Дополнительные сведения см. в примере олицетворения на [сайте CodePlex](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="94b69-123">For more information, see the Impersonation sample on [CodePlex](https://msftengprodsamples.codeplex.com/).</span></span>  
  
 <span data-ttu-id="94b69-124">`SAFE` является набором разрешений по умолчанию и работает в большинстве сценариев.</span><span class="sxs-lookup"><span data-stu-id="94b69-124">`SAFE` is the default permission set and works for the majority of scenarios.</span></span> <span data-ttu-id="94b69-125">Чтобы задать определенный уровень безопасности, измените синтаксис инструкции CREATE ASSEMBLY следующим образом.</span><span class="sxs-lookup"><span data-stu-id="94b69-125">To specify a given security level, you modify the syntax of the CREATE ASSEMBLY statement as follows:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
WITH PERMISSION_SET = SAFE;  
```  
  
 <span data-ttu-id="94b69-126">Также можно создать сборку с разрешением `SAFE`, просто опустив третью строку приведенного выше кода.</span><span class="sxs-lookup"><span data-stu-id="94b69-126">It is also possible to create an assembly with the `SAFE` permission set by simply omitting the third line of code above:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll';  
```  
  
 <span data-ttu-id="94b69-127">Если код сборки запускается с набором разрешений `SAFE`, он может только выполнять вычисления и получать доступ на сервере с помощью внутрипроцессного управляемого поставщика.</span><span class="sxs-lookup"><span data-stu-id="94b69-127">When code in an assembly runs under the `SAFE` permission set, it can only do computation and data access within the server through the in-process managed provider.</span></span>  
  
### <a name="creating-external_access-and-unsafe-assemblies"></a><span data-ttu-id="94b69-128">Создание сборок EXTERNAL_ACCESS и UNSAFE</span><span class="sxs-lookup"><span data-stu-id="94b69-128">Creating EXTERNAL_ACCESS and UNSAFE Assemblies</span></span>  
 <span data-ttu-id="94b69-129">Сборка `EXTERNAL_ACCESS` предназначена для сценариев, в которых коду требуется получить доступ к ресурсам, внешним по отношению к серверу, например к файлам, сети, реестру или переменным среды.</span><span class="sxs-lookup"><span data-stu-id="94b69-129">`EXTERNAL_ACCESS` addresses scenarios in which the code needs to access resources outside the server, such as files, network, registry, and environment variables.</span></span> <span data-ttu-id="94b69-130">Каждый раз, когда сервер получает доступ к внешним ресурсам, он олицетворяет контекст безопасности пользователя, вызывающего управляемый код.</span><span class="sxs-lookup"><span data-stu-id="94b69-130">Whenever the server accesses an external resource, it impersonates the security context of the user calling the managed code.</span></span>  
  
 <span data-ttu-id="94b69-131">Разрешение кода `UNSAFE` предназначено для тех случаев, когда сборка не проверялась на безопасность или нуждается в дополнительном доступе к ресурсам, на которые существуют ограничения, например к API-интерфейсу [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32.</span><span class="sxs-lookup"><span data-stu-id="94b69-131">`UNSAFE` code permission is for those situations in which an assembly is not verifiably safe or requires additional access to restricted resources, such as the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32 API.</span></span>  
  
 <span data-ttu-id="94b69-132">Чтобы создать сборку `EXTERNAL_ACCESS` или `UNSAFE` в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], необходимо, чтобы выполнялось одно из двух следующих условий.</span><span class="sxs-lookup"><span data-stu-id="94b69-132">To create an `EXTERNAL_ACCESS` or `UNSAFE` assembly in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], one of the following two conditions must be met:</span></span>  
  
1.  <span data-ttu-id="94b69-133">Сборка должна иметь строгое имя, подписанное обычной подписью или кодом Authenticode с сертификатом.</span><span class="sxs-lookup"><span data-stu-id="94b69-133">The assembly is strong name signed or Authenticode signed with a certificate.</span></span> <span data-ttu-id="94b69-134">Это строгое имя (или удостоверение) создается в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] как ассиметричный ключ (или сертификат) и имеет соответствующую учетную запись с разрешением `EXTERNAL ACCESS ASSEMBLY` (для сборок внешнего доступа) или `UNSAFE ASSEMBLY` (для небезопасных сборок).</span><span class="sxs-lookup"><span data-stu-id="94b69-134">This strong name (or certificate) is created inside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as an asymmetric key (or certificate), and has a corresponding login with `EXTERNAL ACCESS ASSEMBLY` permission (for external access assemblies) or `UNSAFE ASSEMBLY` permission (for unsafe assemblies).</span></span>  
  
2.  <span data-ttu-id="94b69-135">Владелец базы данных (DBO) имеет `EXTERNAL ACCESS ASSEMBLY` разрешение (для `EXTERNAL ACCESS` сборок) или `UNSAFE ASSEMBLY` (для `UNSAFE` сборок), а для базы данных [свойство базы данных TRUSTWORTHY](../../security/trustworthy-database-property.md) имеет значение `ON` .</span><span class="sxs-lookup"><span data-stu-id="94b69-135">The database owner (DBO) has `EXTERNAL ACCESS ASSEMBLY` (for `EXTERNAL ACCESS` assemblies) or `UNSAFE ASSEMBLY` (for `UNSAFE` assemblies) permission, and the database has the [TRUSTWORTHY Database Property](../../security/trustworthy-database-property.md) set to `ON`.</span></span>  
  
 <span data-ttu-id="94b69-136">Два приведенных выше условия также проверяются при загрузке сборки (которая включает выполнение).</span><span class="sxs-lookup"><span data-stu-id="94b69-136">The two conditions listed above are also checked at assembly load time (which includes execution).</span></span> <span data-ttu-id="94b69-137">Чтобы загрузить сборку, должно выполняться хотя бы одно условие.</span><span class="sxs-lookup"><span data-stu-id="94b69-137">At least one of the conditions must be met in order to load the assembly.</span></span>  
  
 <span data-ttu-id="94b69-138">Рекомендуется, чтобы [свойство базы данных TRUSTWORTHY](../../security/trustworthy-database-property.md) в базе данных не было настроено для `ON` выполнения кода среды CLR в серверном процессе.</span><span class="sxs-lookup"><span data-stu-id="94b69-138">We recommend that the [TRUSTWORTHY Database Property](../../security/trustworthy-database-property.md) on a database not be set to `ON` only to run common language runtime (CLR) code in the server process.</span></span> <span data-ttu-id="94b69-139">Вместо этого рекомендуется создать асимметричный ключ из файла сборки в главной базе данных.</span><span class="sxs-lookup"><span data-stu-id="94b69-139">Instead, we recommend that an asymmetric key be created from the assembly file in the master database.</span></span> <span data-ttu-id="94b69-140">Необходимо создать имя входа, сопоставляемое с этим асимметричным ключом, которому будет предоставлено разрешение `EXTERNAL ACCESS ASSEMBLY` или `UNSAFE ASSEMBLY`.</span><span class="sxs-lookup"><span data-stu-id="94b69-140">A login mapped to this asymmetric key must then be created, and the login must be granted `EXTERNAL ACCESS ASSEMBLY` or `UNSAFE ASSEMBLY` permission.</span></span>  
  
 <span data-ttu-id="94b69-141">Следующие [!INCLUDE[tsql](../../../includes/tsql-md.md)] инструкции перед выполнением инструкции CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="94b69-141">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements before running the CREATE ASSEMBLY statement.</span></span>  
  
```  
USE master;   
GO    
  
CREATE ASYMMETRIC KEY SQLCLRTestKey FROM EXECUTABLE FILE = 'C:\MyDBApp\SQLCLRTest.dll'     
CREATE LOGIN SQLCLRTestLogin FROM ASYMMETRIC KEY SQLCLRTestKey     
GRANT EXTERNAL ACCESS ASSEMBLY TO SQLCLRTestLogin;   
GO   
```  
  
> [!NOTE]  
>  <span data-ttu-id="94b69-142">Необходимо создать новое имя входа для сопоставления с асимметричным ключом.</span><span class="sxs-lookup"><span data-stu-id="94b69-142">You must create a new login to associate with the asymmetric key.</span></span> <span data-ttu-id="94b69-143">Это имя входа используется только для предоставления разрешений и не должно сопоставляться с пользователем или использоваться в приложении.</span><span class="sxs-lookup"><span data-stu-id="94b69-143">This login is only used to grant permissions; it does not have to be associated with a user, or used within the application.</span></span>  
  
 <span data-ttu-id="94b69-144">Для создания сборки `EXTERNAL ACCESS` создатель должен иметь разрешение `EXTERNAL ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="94b69-144">To create an `EXTERNAL ACCESS` assembly, the creator needs to have `EXTERNAL ACCESS` permission.</span></span> <span data-ttu-id="94b69-145">Оно задается при создании сборки.</span><span class="sxs-lookup"><span data-stu-id="94b69-145">This is specified when creating the assembly:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
WITH PERMISSION_SET = EXTERNAL_ACCESS;  
```  
  
 <span data-ttu-id="94b69-146">Следующие [!INCLUDE[tsql](../../../includes/tsql-md.md)] инструкции перед выполнением инструкции CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="94b69-146">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements before running the CREATE ASSEMBLY statement.</span></span>  
  
```  
USE master;   
GO    
  
CREATE ASYMMETRIC KEY SQLCLRTestKey FROM EXECUTABLE FILE = 'C:\MyDBApp\SQLCLRTest.dll';     
CREATE LOGIN SQLCLRTestLogin FROM ASYMMETRIC KEY SQLCLRTestKey ;    
GRANT UNSAFE ASSEMBLY TO SQLCLRTestLogin ;  
GO  
```  
  
 <span data-ttu-id="94b69-147">Чтобы указать, что сборка загружается с разрешением `UNSAFE`, необходимо задать набор разрешений `UNSAFE` при загрузке сборки на сервер.</span><span class="sxs-lookup"><span data-stu-id="94b69-147">To specify that an assembly loads with `UNSAFE` permission, you specify the `UNSAFE` permission set when loading the assembly into the server:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
WITH PERMISSION_SET = UNSAFE;  
```  
  
 <span data-ttu-id="94b69-148">Дополнительные сведения о разрешениях для каждого из параметров см. в разделе [безопасность интеграции со средой CLR](../security/clr-integration-security.md).</span><span class="sxs-lookup"><span data-stu-id="94b69-148">For more details about the permissions for each of the settings, see [CLR Integration Security](../security/clr-integration-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94b69-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="94b69-149">See Also</span></span>  
 <span data-ttu-id="94b69-150">[Управление сборками интеграции со средой CLR](managing-clr-integration-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="94b69-150">[Managing CLR Integration Assemblies](managing-clr-integration-assemblies.md) </span></span>  
 <span data-ttu-id="94b69-151">[Изменение сборки](altering-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="94b69-151">[Altering an Assembly](altering-an-assembly.md) </span></span>  
 <span data-ttu-id="94b69-152">[Удаление сборки](dropping-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="94b69-152">[Dropping an Assembly](dropping-an-assembly.md) </span></span>  
 <span data-ttu-id="94b69-153">[Безопасность доступа к коду при интеграции со средой CLR](../security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="94b69-153">[CLR Integration Code Access Security](../security/clr-integration-code-access-security.md) </span></span>  
 <span data-ttu-id="94b69-154">[Свойство базы данных TRUSTWORTHY](../../security/trustworthy-database-property.md) </span><span class="sxs-lookup"><span data-stu-id="94b69-154">[TRUSTWORTHY Database Property](../../security/trustworthy-database-property.md) </span></span>  
 [<span data-ttu-id="94b69-155">Частично доверенный вызывающий код</span><span class="sxs-lookup"><span data-stu-id="94b69-155">Allowing Partially Trusted Callers</span></span>](../../../database-engine/dev-guide/allowing-partially-trusted-callers.md)  
  
