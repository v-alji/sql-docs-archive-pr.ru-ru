---
title: Проверка разрешений в пользовательских сборках | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- secure calls [Reporting Services]
- custom assemblies [Reporting Services], permissions
- permission sets [Reporting Services]
- asserting permissions
- permissions [Reporting Services], custom assemblies
- limited permission sets
- security configuration files [Reporting Services]
ms.assetid: 3afb9631-f15e-405e-990b-ee102828f298
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cba3c0b74712b6b4d0f6b5c58925cfd562f0df77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654054"
---
# <a name="asserting-permissions-in-custom-assemblies"></a><span data-ttu-id="b0ab1-102">Проверка предположений о наличии разрешений в пользовательских сборках</span><span class="sxs-lookup"><span data-stu-id="b0ab1-102">Asserting Permissions in Custom Assemblies</span></span>
  <span data-ttu-id="b0ab1-103">По умолчанию код пользовательской сборки выполняется с ограниченным набором разрешений **Execution**.</span><span class="sxs-lookup"><span data-stu-id="b0ab1-103">By default, custom assembly code runs with the limited **Execution** permission set.</span></span> <span data-ttu-id="b0ab1-104">В некоторых случаях требуется реализация пользовательских сборок, выполняющих безопасные вызовы к защищенным ресурсам внутри системы безопасности (например, к файлу или реестру).</span><span class="sxs-lookup"><span data-stu-id="b0ab1-104">In some cases, you may wish to implement a custom assembly that makes secured calls to protected resources within your security system (such as a file or the registry).</span></span> <span data-ttu-id="b0ab1-105">Для этого необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b0ab1-105">In order to accomplish this, you must do the following:</span></span>  
  
1.  <span data-ttu-id="b0ab1-106">Определить, какие именно разрешения необходимы, чтобы в коде можно было выполнить безопасный вызов.</span><span class="sxs-lookup"><span data-stu-id="b0ab1-106">Identify the exact permissions that your code needs in order to make the secured call.</span></span> <span data-ttu-id="b0ab1-107">Если этот метод является частью [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] библиотеки, эти сведения следует добавить в документацию по методу.</span><span class="sxs-lookup"><span data-stu-id="b0ab1-107">If this method is part of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] library, this information should be included in the method documentation.</span></span>  
  
2.  <span data-ttu-id="b0ab1-108">Предоставить пользовательской сборке необходимые разрешения путем внесения изменений в файлы конфигурации политики сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="b0ab1-108">Modify the report server policy configuration files in order to grant the custom assembly the required permissions.</span></span> <span data-ttu-id="b0ab1-109">Дополнительные сведения о файлах конфигурации политик безопасности см. в разделе [Использование файлов политики безопасности служб Reporting Services](../extensions/secure-development/using-reporting-services-security-policy-files.md).</span><span class="sxs-lookup"><span data-stu-id="b0ab1-109">For more information about the security policy configuration files, see [Using Reporting Services Security Policy Files](../extensions/secure-development/using-reporting-services-security-policy-files.md).</span></span>  
  
3.  <span data-ttu-id="b0ab1-110">Предположить, что требуемые разрешения являются частью метода, в котором выполняется безопасный вызов.</span><span class="sxs-lookup"><span data-stu-id="b0ab1-110">Assert the required permissions as part of the method in which the secure call is made.</span></span> <span data-ttu-id="b0ab1-111">Этот шаг является обязательным, так как код пользовательской сборки, вызываемый сервером отчетов, является частью хранилища сборки выражений отчета, которое по умолчанию используется с разрешением **Execution**.</span><span class="sxs-lookup"><span data-stu-id="b0ab1-111">This is required because the custom assembly code that is called by the report server is part of the report expression host assembly, which runs with **Execution** permission by default.</span></span> <span data-ttu-id="b0ab1-112">Набор разрешений **Execution** разрешает выполнение кода, но не использование защищенных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b0ab1-112">The **Execution** permission set enables code to run, but not to use protected resources.</span></span>  
  
4.  <span data-ttu-id="b0ab1-113">Обозначьте пользовательскую сборку атрибутом **AllowPartiallyTrustedCallersAttribute**, если она подписана строгим именем.</span><span class="sxs-lookup"><span data-stu-id="b0ab1-113">Mark the custom assembly with **AllowPartiallyTrustedCallersAttribute** if it is signed with a strong name.</span></span> <span data-ttu-id="b0ab1-114">Это необходимо по той причине, что пользовательские сборки вызываются из выражения отчета, которое является частью хранилища сборки выражений отчета, а ему по умолчанию не предоставляются права **FullTrust**. Таким образом, этот вызывающий код рассматривается как "частично доверенный".</span><span class="sxs-lookup"><span data-stu-id="b0ab1-114">This is required because custom assemblies are called from a report expression that is part of the report expression host assembly, which, by default, is not granted **FullTrust**; thus it is a "partially trusted" caller.</span></span> <span data-ttu-id="b0ab1-115">Дополнительные сведения см. в статье [Использование пользовательских сборок со строгими именами](using-strong-named-custom-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="b0ab1-115">For more information, see [Using Strong-Named Custom Assemblies](using-strong-named-custom-assemblies.md).</span></span>  
  
## <a name="implementing-a-secure-call"></a><span data-ttu-id="b0ab1-116">Реализация безопасного вызова</span><span class="sxs-lookup"><span data-stu-id="b0ab1-116">Implementing a Secure Call</span></span>  
 <span data-ttu-id="b0ab1-117">Можно предоставить сборке конкретные разрешения путем изменения файлов конфигурации политик.</span><span class="sxs-lookup"><span data-stu-id="b0ab1-117">You can modify the policy configuration files to grant your assembly specific permissions.</span></span> <span data-ttu-id="b0ab1-118">Например, если создается пользовательская сборка для конвертирования валют, может потребоваться обеспечить чтение курсов валют из файла.</span><span class="sxs-lookup"><span data-stu-id="b0ab1-118">For example, if you were writing a custom assembly to handle currency conversion, you might need to read the current currency exchange rates from a file.</span></span> <span data-ttu-id="b0ab1-119">Чтобы получить сведения о курсах, потребуется добавить к уже заданным разрешениям сборки дополнительное право доступа **FileIOPermission**.</span><span class="sxs-lookup"><span data-stu-id="b0ab1-119">To retrieve the rate information, you would need to add an additional security permission, **FileIOPermission**, to your permission set for the assembly.</span></span> <span data-ttu-id="b0ab1-120">Внесите в файл конфигурации политики следующую дополнительную запись.</span><span class="sxs-lookup"><span data-stu-id="b0ab1-120">You can make the following additional entry in the policy configuration file:</span></span>  
  
```  
<PermissionSet class="NamedPermissionSet"  
   version="1"  
   Name="CurrencyRatesFilePermissionSet"  
   Description="A special permission set that grants read access to my currency rates file.">  
      <IPermission class="FileIOPermission"  
         version="1"  
         Read="C:\CurrencyRates.xml"/>  
      <IPermission class="SecurityPermission"  
         version="1"  
         Flags="Execution, Assertion"/>  
</PermissionSet>  
```  
  
 <span data-ttu-id="b0ab1-121">Затем добавьте группу кода, которая ссылается на этот набор разрешений.</span><span class="sxs-lookup"><span data-stu-id="b0ab1-121">You then add a code group that references that permission set:</span></span>  
  
```  
<CodeGroup class="UnionCodeGroup"  
   version="1"  
   PermissionSetName="CurrencyRatesFilePermissionSet"  
   Name="MyNewCodeGroup"  
   Description="A special code group for my custom assembly.">  
   <IMembershipCondition class="UrlMembershipCondition"  
      version="1"  
      Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\MSSQL\Reporting Services\ReportServer\bin\CurrencyConversion.dll"/>  
</CodeGroup>  
```  
  
 <span data-ttu-id="b0ab1-122">Чтобы код получил соответствующее разрешение, необходимо подтвердить это разрешение в коде пользовательской сборки.</span><span class="sxs-lookup"><span data-stu-id="b0ab1-122">In order for your code to acquire the appropriate permission, you must assert the permission within your custom assembly code.</span></span> <span data-ttu-id="b0ab1-123">Например, если требуется предусмотреть доступ только для чтения XML-файла C:\CurrencyRates.xml, то в метод следует добавить приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="b0ab1-123">For example, if you want to add read-only access to an XML file, C:\CurrencyRates.xml, you must add the following code to your method:</span></span>  
  
```  
// C#  
FileIOPermission permission = new FileIOPermission(FileIOPermissionAccess.Read, @"C:\CurrencyRates.xml");  
try  
{  
   permission.Assert();  
   // Load the XML currency rates file  
   XmlDocument doc = new XmlDocument();  
   doc.Load(@"C:\CurrencyRates.xml");  
...  
```  
  
 <span data-ttu-id="b0ab1-124">Кроме того, подтверждение можно добавить и в качестве атрибута метода.</span><span class="sxs-lookup"><span data-stu-id="b0ab1-124">You can also add the assertion as a method attribute:</span></span>  
  
```  
[FileIOPermissionAttribute(SecurityAction.Assert, Read=@"C:\CurrencyRates.xml")]  
```  
  
 <span data-ttu-id="b0ab1-125">Дополнительные сведения см. в разделе «Безопасность .NET Framework» документа «Руководство разработчика для платформы .NET Framework».</span><span class="sxs-lookup"><span data-stu-id="b0ab1-125">For more information, see ".NET Framework Security" in the .NET Framework Developer's Guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0ab1-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="b0ab1-126">See Also</span></span>  
 [<span data-ttu-id="b0ab1-127">Использование пользовательских сборок с отчетами</span><span class="sxs-lookup"><span data-stu-id="b0ab1-127">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
