---
title: Командлет Invoke-PolicyEvaluation | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, Invoke-PolicyEvaluation
- Policy-Based Management, PowerShell
- Invoke-PolicyEvaluation cmdlet
- Cmdlets [SQL Server], Invoke-PolicyEvaluation
- PowerShell [SQL Server], Invoke-PolicyEvaluation
ms.assetid: 3e6d4f5a-59b7-4203-b95a-f7e692c0f131
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 656fdffea191c9cf6fc42d860164bc5af1e04561
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730881"
---
# <a name="invoke-policyevaluation-cmdlet"></a><span data-ttu-id="da740-102">Invoke-PolicyEvaluation, командлет</span><span class="sxs-lookup"><span data-stu-id="da740-102">Invoke-PolicyEvaluation cmdlet</span></span>
  <span data-ttu-id="da740-103">**Invoke-PolicyEvaluation** — это командлет [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , который определяет, соответствует ли набор целей объектов SQL Server условиям, заданным в одной или нескольких политиках в системе управления на основе политик.</span><span class="sxs-lookup"><span data-stu-id="da740-103">**Invoke-PolicyEvaluation** is a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlet that reports whether a target set of SQL Server objects complies with the conditions specified in one or more Policy-Based Management policies.</span></span>  
  
## <a name="using-invoke-policyevaluation"></a><span data-ttu-id="da740-104">Использование Invoke-PolicyEvaluation</span><span class="sxs-lookup"><span data-stu-id="da740-104">Using Invoke-PolicyEvaluation</span></span>  
 <span data-ttu-id="da740-105">Командлет**Invoke-PolicyEvaluation** оценивает одну или несколько политик относительно набора объектов SQL Server, который называется целевым.</span><span class="sxs-lookup"><span data-stu-id="da740-105">**Invoke-PolicyEvaluation** evaluates one or more policies against a set of SQL Server objects called the target set.</span></span> <span data-ttu-id="da740-106">Набор целевых объектов поступает от целевого сервера.</span><span class="sxs-lookup"><span data-stu-id="da740-106">The set of target objects comes from a target server.</span></span> <span data-ttu-id="da740-107">Каждая политика определяет условия, которые являются разрешенными состояниями для целевых объектов.</span><span class="sxs-lookup"><span data-stu-id="da740-107">Each policy defines conditions, which are the allowed states for the target objects.</span></span> <span data-ttu-id="da740-108">Например, в соответствии с политикой **Доверенная база данных** для свойства базы данных TRUSTWORTHY должно быть указано значение OFF.</span><span class="sxs-lookup"><span data-stu-id="da740-108">For example, the **Trustworthy Database** policy states that the TRUSTWORTHY database property must be set to OFF.</span></span>  
  
 <span data-ttu-id="da740-109">Параметр **-AdHocPolicyEvaluationMode** определяет выполняемые действия:</span><span class="sxs-lookup"><span data-stu-id="da740-109">The **-AdHocPolicyEvaluationMode** parameter specifies the actions taken:</span></span>  
  
 <span data-ttu-id="da740-110">Проверить</span><span class="sxs-lookup"><span data-stu-id="da740-110">Check</span></span>  
 <span data-ttu-id="da740-111">Сообщает состояние соответствия целевых объектов при помощи учетных данных текущего имени входа.</span><span class="sxs-lookup"><span data-stu-id="da740-111">Report the compliance status of the target objects using the credentials of your current login.</span></span> <span data-ttu-id="da740-112">Не проводите повторную настройку каких-либо объектов.</span><span class="sxs-lookup"><span data-stu-id="da740-112">Do no reconfigure any objects.</span></span> <span data-ttu-id="da740-113">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="da740-113">This is the default setting.</span></span>  
  
 <span data-ttu-id="da740-114">CheckSqlScriptAsProxy</span><span class="sxs-lookup"><span data-stu-id="da740-114">CheckSqlScriptAsProxy</span></span>  
 <span data-ttu-id="da740-115">Сообщите о состоянии соответствия целевых объектов с помощью учетных данных для входа на прокси-сервер **##MS_PolicyTSQLExecutionLogin##** .</span><span class="sxs-lookup"><span data-stu-id="da740-115">Report the compliance status of the target objects using the credentials of the **##MS_PolicyTSQLExecutionLogin##** proxy login.</span></span> <span data-ttu-id="da740-116">Не проводите повторную настройку каких-либо объектов.</span><span class="sxs-lookup"><span data-stu-id="da740-116">Do no reconfigure any objects.</span></span>  
  
 <span data-ttu-id="da740-117">Configure</span><span class="sxs-lookup"><span data-stu-id="da740-117">Configure</span></span>  
 <span data-ttu-id="da740-118">Сообщает состояние соответствия целевых объектов при помощи учетных данных текущего имени входа.</span><span class="sxs-lookup"><span data-stu-id="da740-118">Report the compliance status of the target objects using the credentials of your current login.</span></span> <span data-ttu-id="da740-119">Измените все настраиваемые и детерминированные параметры, которые не соответствуют политикам.</span><span class="sxs-lookup"><span data-stu-id="da740-119">Reconfigure any settable and deterministic options that are not in compliance with the policies.</span></span>  
  
## <a name="specifying-polices"></a><span data-ttu-id="da740-120">Задание политик</span><span class="sxs-lookup"><span data-stu-id="da740-120">Specifying Polices</span></span>  
 <span data-ttu-id="da740-121">Процедура задания политики зависит от того, где она хранится.</span><span class="sxs-lookup"><span data-stu-id="da740-121">How you specify a policy depends on where the policy is stored.</span></span> <span data-ttu-id="da740-122">Политики могут храниться в двух форматах.</span><span class="sxs-lookup"><span data-stu-id="da740-122">Policies can be stored in two formats:</span></span>  
  
-   <span data-ttu-id="da740-123">Они могут быть объектами, находящимися в хранилище политик, таком как экземпляр ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="da740-123">They can be objects stored in a policy store, such as an instance of the Database Engine.</span></span> <span data-ttu-id="da740-124">Для указания места хранения политик в хранилище политик можно использовать папку SQLSERVER:\SQLPolicy.</span><span class="sxs-lookup"><span data-stu-id="da740-124">You can use the SQLSERVER:\SQLPolicy folder to specify the location of policies in a policy store.</span></span> <span data-ttu-id="da740-125">При помощи командлетов Windows PowerShell можно фильтровать входные политики на основе их свойств, например использовать командлет Where-Object, чтобы фильтровать по категории политики, или Get-Item, чтобы фильтровать по имени политики.</span><span class="sxs-lookup"><span data-stu-id="da740-125">You can use Windows PowerShell cmdlets to filter the input polices based on their properties, such as using Where-Object to filter on the policy category or Get-Item to filter on policy name.</span></span>  
  
-   <span data-ttu-id="da740-126">Политики можно экспортировать как XML-файлы.</span><span class="sxs-lookup"><span data-stu-id="da740-126">They can be exported as XML files.</span></span> <span data-ttu-id="da740-127">Можно использовать диск файловой системы, например D:, чтобы указать место для размещения XML-файлов.</span><span class="sxs-lookup"><span data-stu-id="da740-127">You can use a file system drive, such as D:, to specify the location of the XML files.</span></span> <span data-ttu-id="da740-128">При помощи командлетов Windows PowerShell, таких как Where-Object, можно фильтровать политики по таким свойствам файла, как имя.</span><span class="sxs-lookup"><span data-stu-id="da740-128">You can use Windows PowerShell cmdlets such as Where-Object to filter the policies on their file properties, such as file name.</span></span>  
  
 <span data-ttu-id="da740-129">Если политики хранятся в хранилище политик, необходимо передавать набор PSObjects, указывающий на те политики, которые должны быть оценены.</span><span class="sxs-lookup"><span data-stu-id="da740-129">If the policies are stored in a policy store, you must pass in a set of PSObjects pointing to the policies to be evaluated.</span></span> <span data-ttu-id="da740-130">Обычно это делается путем перенаправления вывода командлета, например Get-Item, в командлет **Invoke-PolicyEvaluation**. При этом указывать параметр **-Policy** не нужно.</span><span class="sxs-lookup"><span data-stu-id="da740-130">This is typically done by piping the output of a cmdlet such as Get-Item to **Invoke-PolicyEvaluation**, and does not require that you specify the **-Policy** parameter.</span></span> <span data-ttu-id="da740-131">Например, если политики "Рекомендации корпорации Майкрософт" были импортированы в экземпляр ядра СУБД, оценивать политику **Состояние базы данных** будет следующая команда:</span><span class="sxs-lookup"><span data-stu-id="da740-131">For example, if you have imported the Microsoft Best Practices policies into your instance of the database engine, this command evaluates the **Database Status** policy:</span></span>  
  
```powershell
sl "SQLSERVER:\SQLPolicy\MyComputer\DEFAULT\Policies"  
Get-Item "Database Status" | Invoke-PolicyEvaluation -TargetServerName "MYCOMPUTER"  
```  
  
 <span data-ttu-id="da740-132">В этом примере показано использование командлета Where-Object для фильтрации нескольких политик из хранилища политик на основе свойства **PolicyCategory** .</span><span class="sxs-lookup"><span data-stu-id="da740-132">This example shows using Where-Object to filter multiple policies from a policy store based on their **PolicyCategory** property.</span></span> <span data-ttu-id="da740-133">Объекты из перенаправленного вывода **Where-Object** используются командлетом **Invoke-PolicyEvaluation**.</span><span class="sxs-lookup"><span data-stu-id="da740-133">The objects from the piped output of **Where-Object** is consumed by **Invoke-PolicyEvaluation**.</span></span>  
  
```powershell
sl "SQLSERVER:\SQLPolicy\MyComputer\DEFAULT\Policies"  
gci | Where-Object {$_.PolicyCategory -eq "Microsoft Best Practices: Maintenance"} | Invoke-PolicyEvaluation -TargetServer "MYCOMPUTER"  
```  
  
 <span data-ttu-id="da740-134">Если политики хранятся в виде XML-файлов, вам нужно с помощью параметра **-Policy** указать путь и имя для каждой политики.</span><span class="sxs-lookup"><span data-stu-id="da740-134">If the policies are stored as XML files, you must use the **-Policy** parameter to supply both the path and name for each policy.</span></span> <span data-ttu-id="da740-135">Если вы не укажете путь в параметре **-Policy** , командлет **Invoke-PolicyEvaulation** будет использовать текущий параметр пути **sqlps** .</span><span class="sxs-lookup"><span data-stu-id="da740-135">If you do not specify a path in the **-Policy** parameter, **Invoke-PolicyEvaulation** uses the current setting of the **sqlps** path.</span></span> <span data-ttu-id="da740-136">Например, эта команда оценивает одну из политик «Microsoft Best Practice», установленных с SQL Server, по базе данных по умолчанию для этого имени входа:</span><span class="sxs-lookup"><span data-stu-id="da740-136">For example, this command evaluates one of the Microsoft Best Practice policies installed with SQL Server against the default database for your login:</span></span>  
  
```powershell
Invoke-PolicyEvaluation -Policy "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033\Database Status.xml" -TargetServerName "MYCOMPUTER"  
```  
  
 <span data-ttu-id="da740-137">Эта команда делает то же самое, но в ней для определения местоположения XML-файла политики используется текущий путь **sqlps** :</span><span class="sxs-lookup"><span data-stu-id="da740-137">This command does the same thing, only it uses the current **sqlps** path to establish the location of the policy XML file:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
Invoke-PolicyEvaluation -Policy "Database Status.xml" -TargetServerName "MYCOMPUTER"  
```  
  
 <span data-ttu-id="da740-138">В этом примере показано использование командлета **Get-ChildItem** для извлечения нескольких XML-файлов политик и перенаправления объектов в командлет **Invoke-PolicyEvaluation**:</span><span class="sxs-lookup"><span data-stu-id="da740-138">This example shows using the **Get-ChildItem** cmdlet to retrieve multiple policy XML files and pipe the objects into **Invoke-PolicyEvaluation**:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
gci "Database Status.xml", "Trustworthy Database.xml" | Invoke-PolicyEvaluation -TargetServer "MYCOMPUTER"  
```  
  
## <a name="specifying-the-target-set"></a><span data-ttu-id="da740-139">Указание набора целей</span><span class="sxs-lookup"><span data-stu-id="da740-139">Specifying the Target Set</span></span>  
 <span data-ttu-id="da740-140">Для указания набора целевых объектов используется три параметра.</span><span class="sxs-lookup"><span data-stu-id="da740-140">Use three parameters to specify the set of target objects:</span></span>  
  
-   <span data-ttu-id="da740-141">Параметр **-TargetServerName** определяет экземпляр SQL Server, содержащий целевые объекты.</span><span class="sxs-lookup"><span data-stu-id="da740-141">**-TargetServerName** specifies the instance of SQL Server containing the target objects.</span></span> <span data-ttu-id="da740-142">Сведения можно указать в строке, для которой используется формат, определенный для свойства ConnectionString класса <xref:System.Data.SqlClient.SqlConnection> .</span><span class="sxs-lookup"><span data-stu-id="da740-142">You can specify the information in a string that uses the format defined for the ConnectionString property of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span> <span data-ttu-id="da740-143">Для построения правильно форматированной строки подключения можно использовать класс <xref:System.Data.SqlClient.SqlConnectionStringBuilder> .</span><span class="sxs-lookup"><span data-stu-id="da740-143">You can use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> class to build a correctly formatted connection string.</span></span> <span data-ttu-id="da740-144">Можно также создать объект <xref:Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection> и передать его в параметр **-TargetServer**.</span><span class="sxs-lookup"><span data-stu-id="da740-144">You can also create a <xref:Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection> object and pass it to **-TargetServer**.</span></span> <span data-ttu-id="da740-145">При передаче строки, которая содержит только имя сервера, командлет **Invoke-PolicyEvaluation** для подключения к серверу использует проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="da740-145">If you supply a string that has only the name of the server, **Invoke-PolicyEvaluation** uses Windows Authentication to connect to the server.</span></span>  
  
-   <span data-ttu-id="da740-146">Параметр **-TargetObjects** принимает объект или массив объектов, которые представляют объекты SQL Server в наборе целей.</span><span class="sxs-lookup"><span data-stu-id="da740-146">**-TargetObjects** takes an object or array of objects that represent the SQL Server objects in the target set.</span></span> <span data-ttu-id="da740-147">Например, можно создать массив объектов класса <xref:Microsoft.SqlServer.Management.Smo.Database> для передачи параметру **-TargetObjects**.</span><span class="sxs-lookup"><span data-stu-id="da740-147">For example, you could create an array of <xref:Microsoft.SqlServer.Management.Smo.Database> class objects to pass in to **-TargetObjects**.</span></span>  
  
-   <span data-ttu-id="da740-148">Параметр **-TargetExpressions** принимает строку, содержащую выражение запроса, которое определяет объекты в наборе целей.</span><span class="sxs-lookup"><span data-stu-id="da740-148">**-TargetExpressions** takes a string containing a query expression that specifies the objects in the target set.</span></span> <span data-ttu-id="da740-149">Это выражение запроса состоит из узлов, разделенных символом «/».</span><span class="sxs-lookup"><span data-stu-id="da740-149">The query expression is in the form of nodes separated by the '/' character.</span></span> <span data-ttu-id="da740-150">Каждый узел имеет вид ObjectType[Filter].</span><span class="sxs-lookup"><span data-stu-id="da740-150">Each node is in the form ObjectType[Filter].</span></span> <span data-ttu-id="da740-151">Тип объекта является одним из объектов SQL Server в иерархии объектов SMO.</span><span class="sxs-lookup"><span data-stu-id="da740-151">Object type is one of the objects in a SQL Server Management Object (SMO) object hierarchy.</span></span> <span data-ttu-id="da740-152">Фильтр — это выражение, которое фильтрует объекты в этом узле.</span><span class="sxs-lookup"><span data-stu-id="da740-152">Filter is an expression that filters for objects at that node.</span></span> <span data-ttu-id="da740-153">Дополнительные сведения см. в статье [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span><span class="sxs-lookup"><span data-stu-id="da740-153">For more information, see [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span></span>  
  
 <span data-ttu-id="da740-154">Укажите либо **-TargetObjects** , либо **-TargetExpression**, но не оба параметра.</span><span class="sxs-lookup"><span data-stu-id="da740-154">Specify either **-TargetObjects** or **-TargetExpression**, not both.</span></span>  
  
 <span data-ttu-id="da740-155">В этом примере для указания целевого сервера используется объект Sfc.SqlStoreConnection:</span><span class="sxs-lookup"><span data-stu-id="da740-155">This example uses an Sfc.SqlStoreConnection object to specify the target server:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
$conn = New-Object Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection("server='MYCOMPUTER';Trusted_Connection=True")  
Invoke-PolicyEvaluation -Policy "Database Status.xml" -TargetServerName $conn  
```  
  
 <span data-ttu-id="da740-156">В этом примере для определения базы данных для оценки используется параметр **-TargetExpression** :</span><span class="sxs-lookup"><span data-stu-id="da740-156">This example uses **-TargetExpression** to identify the specific database to evaluate:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
Invoke-PolicyEvaluation -Policy "Database Status.xml" -TargetServerName "MyComputer" -TargetExpression "Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012']"  
```  
  
## <a name="evaluating-analysis-services-policies"></a><span data-ttu-id="da740-157">Оценка политик служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="da740-157">Evaluating Analysis Services Policies</span></span>  
 <span data-ttu-id="da740-158">Чтобы оценить политики относительно экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], необходимо загрузить и зарегистрировать сборку в PowerShell, создать переменную с использованием объекта соединения служб Analysis Services и передать переменную параметру **-TargetObject** .</span><span class="sxs-lookup"><span data-stu-id="da740-158">To evaluate policies against an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], you must load and register an assembly into PowerShell, create a variable with an Analysis Services connection object, and pass the variable to the **-TargetObject** parameter.</span></span> <span data-ttu-id="da740-159">В этом примере показана оценка политики настройки контактной зоны «Рекомендации» для служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="da740-159">This example shows evaluating the Best Practices surface area configuration policy for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\AnalysisServices\1033"  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.AnalysisServices")  
$SSASsvr = New-Object Microsoft.AnalysisServices.Server  
$SSASsvr.Connect("Data Source=Localhost")  
Invoke-PolicyEvaluation -Policy "Surface Area Configuration for Analysis Services Features.xml" -TargetObject $SSASsvr  
```  
  
## <a name="evaluating-reporting-services-policies"></a><span data-ttu-id="da740-160">Оценка политик служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="da740-160">Evaluating Reporting Services Policies</span></span>  
 <span data-ttu-id="da740-161">Чтобы оценить политики служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , необходимо загрузить и зарегистрировать сборку в PowerShell, создать переменную с помощью объекта соединения [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] и передать переменную параметру **-TargetObject** .</span><span class="sxs-lookup"><span data-stu-id="da740-161">To evaluate [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] policies, you must load and register an assembly into PowerShell, create a variable with a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] connection object, and pass the variable to the **-TargetObject** parameter.</span></span> <span data-ttu-id="da740-162">В этом примере показана оценка политики настройки контактной зоны «Рекомендации» для служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="da740-162">This example shows evaluating the Best Practices surface area configuration policy for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\ReportingServices\1033"  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.Dmf.Adapters")  
$SSRSsvr = new-object Microsoft.SqlServer.Management.Adapters.RSContainer('MyComputer')  
Invoke-PolicyEvaluation -Policy "Surface Area Configuration for Reporting Services 2008 Features.xml" -TargetObject $SSRSsvr  
```  
  
## <a name="formatting-output"></a><span data-ttu-id="da740-163">Форматирование выходных данных</span><span class="sxs-lookup"><span data-stu-id="da740-163">Formatting Output</span></span>  
 <span data-ttu-id="da740-164">По умолчанию выходные данные командлета **Invoke-PolicyEvaluation** отображаются в окне командной строки в виде краткого отчета в удобной для чтения форме.</span><span class="sxs-lookup"><span data-stu-id="da740-164">By default, the output of **Invoke-PolicyEvaluation** is displayed in the command prompt window as a concise report in human-readable format.</span></span> <span data-ttu-id="da740-165">С помощью параметра **-OutputXML** можно указать, что командлет должен генерировать подробный отчет в виде XML-файла.</span><span class="sxs-lookup"><span data-stu-id="da740-165">You can use the **-OutputXML** parameter to specify that the cmdlet instead produce a detailed report as an XML file.</span></span> <span data-ttu-id="da740-166">Командлет**Invoke-PolicyEvaluation** использует схему SML-IF, поэтому файл смогут читать модули чтения SML-IF.</span><span class="sxs-lookup"><span data-stu-id="da740-166">**Invoke-PolicyEvaluation** uses the Systems Modeling Language Interchange Format (SML-IF) schema so the file can be read by SML-IF readers.</span></span>  
  
```powershell
sl "SQLSERVER:\SQLPolicy\MyComputer\DEFAULT\Policies"  
Invoke-PolicyEvaluation -Policy "Datbase Status" -TargetServer "MYCOMPUTER" -OutputXML > C:\MyReports\DatabaseStatusReport.xml  
```  
  
## <a name="see-also"></a><span data-ttu-id="da740-167">См. также:</span><span class="sxs-lookup"><span data-stu-id="da740-167">See Also</span></span>  
 [<span data-ttu-id="da740-168">Использование командлетов компонента Database Engine</span><span class="sxs-lookup"><span data-stu-id="da740-168">Use the Database Engine cmdlets</span></span>](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
