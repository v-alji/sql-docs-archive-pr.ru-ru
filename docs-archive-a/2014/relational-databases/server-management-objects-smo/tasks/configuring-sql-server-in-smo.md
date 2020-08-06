---
title: Настройка SQL Server в SMO | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server, configuring
- configuration options [SMO]
ms.assetid: 0a372643-15cb-45a7-8665-04f1215df8ed
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6da1bca0aec650c01553b42bc2f3628b0bf7282e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739674"
---
# <a name="configuring-sql-server-in-smo"></a><span data-ttu-id="b3a2f-102">Настройка SQL Server в SMO</span><span class="sxs-lookup"><span data-stu-id="b3a2f-102">Configuring SQL Server in SMO</span></span>
  <span data-ttu-id="b3a2f-103">В объектах SMO объект, объект, объект <xref:Microsoft.SqlServer.Management.Smo.Information> <xref:Microsoft.SqlServer.Management.Smo.Settings> <xref:Microsoft.SqlServer.Management.Smo.UserOptions> и <xref:Microsoft.SqlServer.Management.Smo.Configuration> объект содержат параметры и сведения для экземпляра [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3a2f-103">In SMO, the <xref:Microsoft.SqlServer.Management.Smo.Information> object, the <xref:Microsoft.SqlServer.Management.Smo.Settings> object, the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object, and the <xref:Microsoft.SqlServer.Management.Smo.Configuration> object contain settings and information for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b3a2f-104">В [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] имеется множество свойств, описывающих поведение установленного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-104">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] has numerous properties that describe the behavior of the installed instance.</span></span> <span data-ttu-id="b3a2f-105">Эти свойства описывают параметры запуска, используемые по умолчанию параметры сервера, файлы и каталоги, сведения о системе и процессоре, о продукте и версиях, сведения о соединении, параметры памяти, выбранные язык и параметры сортировки, а также режим проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-105">The properties describe the startup options, the server defaults, files and directories, system and processor information, product and versions, connection information, memory options, language and collation selections, and the authentication mode.</span></span>  
  
## <a name="sql-server-configuration"></a><span data-ttu-id="b3a2f-106">Настройка SQL Server</span><span class="sxs-lookup"><span data-stu-id="b3a2f-106">SQL Server Configuration</span></span>  
 <span data-ttu-id="b3a2f-107">В свойствах объекта <xref:Microsoft.SqlServer.Management.Smo.Information> содержатся такие сведения об экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], как процессор и платформа.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-107">The <xref:Microsoft.SqlServer.Management.Smo.Information> object properties contain information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], such as processor and platform.</span></span>  
  
 <span data-ttu-id="b3a2f-108">Свойства объекта <xref:Microsoft.SqlServer.Management.Smo.Settings> содержат сведения об экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3a2f-108">The <xref:Microsoft.SqlServer.Management.Smo.Settings> object properties contain information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b3a2f-109">Помимо свойств Mail Profile и Server Account можно изменить используемые по умолчанию файл базы данных и каталог.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-109">The default database file and directory can be modified in addition to the Mail Profile and the Server Account.</span></span> <span data-ttu-id="b3a2f-110">Эти свойства сохраняются на протяжении всего соединения.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-110">These properties remain for the duration of the connection.</span></span>  
  
 <span data-ttu-id="b3a2f-111">В свойствах объекта <xref:Microsoft.SqlServer.Management.Smo.UserOptions> содержатся сведения о текущем поведении соединения, связанном с выполняемыми вычислениями, применяемыми стандартами ANSI и осуществляемыми транзакциями.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-111">The <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object properties contain information about the current connections behavior relating to arithmetic, ANSI standards, and transactions.</span></span>  
  
 <span data-ttu-id="b3a2f-112">Помимо этого имеется также ряд параметров конфигурации, представленных объектом <xref:Microsoft.SqlServer.Management.Smo.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-112">There is also a set of configuration options that is represented by the <xref:Microsoft.SqlServer.Management.Smo.Configuration> object.</span></span> <span data-ttu-id="b3a2f-113">Он содержит набор свойств, представляющих параметры, которые можно изменить с помощью хранимой процедуры `sp_configure`.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-113">It contains a set of properties that represent the options that can be modified by the `sp_configure` stored procedure.</span></span> <span data-ttu-id="b3a2f-114">Такие параметры, как **повышение приоритета**, **интервал восстановления** и **Размер сетевого пакета**, контролируют производительность экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3a2f-114">Options such as **Priority Boost**, **Recovery Interval** and **Network Packet Size**control the performance of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b3a2f-115">Многие из этих параметров можно менять динамически, но в некоторых случаях значение сначала надо настроить, а затем изменить при перезапуске экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3a2f-115">Many of these options can be changed dynamically, but in some cases the value is first configured and then changed when the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is restarted.</span></span>  
  
 <span data-ttu-id="b3a2f-116">Для каждого параметра конфигурации существует свойство объекта <xref:Microsoft.SqlServer.Management.Smo.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-116">There is a <xref:Microsoft.SqlServer.Management.Smo.Configuration> object property for every configuration option.</span></span> <span data-ttu-id="b3a2f-117">С помощью объекта <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty> можно изменить глобальные настройки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-117">Using the <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty> object you can modify the global configuration setting.</span></span> <span data-ttu-id="b3a2f-118">У многих свойств есть максимальное и минимальное значения, которые также хранятся как свойства <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty>.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-118">Many properties have maximum and minimum values that are also stored as <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty> properties.</span></span> <span data-ttu-id="b3a2f-119">Для этих свойств требуется, <xref:Microsoft.SqlServer.Management.Smo.ConfigurationBase.Alter%2A> чтобы метод зафиксировал изменения в экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3a2f-119">These properties require the <xref:Microsoft.SqlServer.Management.Smo.ConfigurationBase.Alter%2A> method to commit the change to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b3a2f-120">Все параметры конфигурации в объекте <xref:Microsoft.SqlServer.Management.Smo.Configuration> должен изменять системный администратор.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-120">All of the configuration options in the <xref:Microsoft.SqlServer.Management.Smo.Configuration> object must be changed by the system administrator.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b3a2f-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="b3a2f-121">Examples</span></span>  
 <span data-ttu-id="b3a2f-122">В следующих примерах кода для создания приложения необходимо выбрать среду программирования, шаблон программирования и язык программирования.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-122">For the following code examples, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="b3a2f-123">Дополнительные сведения см. в статьях [Создание проекта Visual Basic SMO в Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) и [Создание проекта Visual C&#35; SMO в Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="b3a2f-123">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="modifying-sql-server-configuration-options-in-visual-basic"></a><span data-ttu-id="b3a2f-124">Изменение параметров конфигурации SQL Server на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b3a2f-124">Modifying SQL Server Configuration Options in Visual Basic</span></span>  
 <span data-ttu-id="b3a2f-125">Этот пример кода показывает, как обновить параметр конфигурации на языке Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-125">The code example shows how to update a configuration option in Visual Basic .NET.</span></span> <span data-ttu-id="b3a2f-126">Он также возвращает и отображает сведения о максимальном и минимальном значениях указанного параметра конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-126">It also retrieves and displays information about maximum and minimum values for the specified configuration option.</span></span> <span data-ttu-id="b3a2f-127">Наконец, программа извещает пользователя, выполнено ли изменение динамически или оно будет храниться до тех пор, пока не произойдет перезагрузка экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3a2f-127">Finally, the program informs the user if the change has been made dynamically, or if it is stored until the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is restarted.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBConfigure2](SMO How to#SMO_VBConfigure2)]  -->  
  
## <a name="modifying-sql-server-settings-in-visual-basic"></a><span data-ttu-id="b3a2f-128">Изменение параметров SQL Server на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b3a2f-128">Modifying SQL Server Settings in Visual Basic</span></span>  
 <span data-ttu-id="b3a2f-129">В примере кода выводятся сведения об экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в <xref:Microsoft.SqlServer.Management.Smo.Information> и <xref:Microsoft.SqlServer.Management.Smo.Settings> , а также изменяются параметры в <xref:Microsoft.SqlServer.Management.Smo.Settings> <xref:Microsoft.SqlServer.Management.Smo.UserOptions> свойствах объекта и.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-129">The code example displays information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> and <xref:Microsoft.SqlServer.Management.Smo.Settings>, and modifies settings in <xref:Microsoft.SqlServer.Management.Smo.Settings> and <xref:Microsoft.SqlServer.Management.Smo.UserOptions>object properties.</span></span>  
  
 <span data-ttu-id="b3a2f-130">В этом примере оба объекта, <xref:Microsoft.SqlServer.Management.Smo.UserOptions> и <xref:Microsoft.SqlServer.Management.Smo.Settings>, обладают методом <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-130">In the example the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object and the <xref:Microsoft.SqlServer.Management.Smo.Settings> object both have an <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="b3a2f-131">Для них можно отдельно запустить методы <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-131">You can run the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> methods for these individually.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBConfigure1](SMO How to#SMO_VBConfigure1)]  -->  
  
## <a name="modifying-sql-server-settings-in-visual-c"></a><span data-ttu-id="b3a2f-132">Изменение параметров SQL Server на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="b3a2f-132">Modifying SQL Server Settings in Visual C#</span></span>  
 <span data-ttu-id="b3a2f-133">В примере кода выводятся сведения об экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в <xref:Microsoft.SqlServer.Management.Smo.Information> и <xref:Microsoft.SqlServer.Management.Smo.Settings> , а также изменяются параметры в <xref:Microsoft.SqlServer.Management.Smo.Settings> <xref:Microsoft.SqlServer.Management.Smo.UserOptions> свойствах объекта и.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-133">The code example displays information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> and <xref:Microsoft.SqlServer.Management.Smo.Settings>, and modifies settings in <xref:Microsoft.SqlServer.Management.Smo.Settings> and <xref:Microsoft.SqlServer.Management.Smo.UserOptions>object properties.</span></span>  
  
 <span data-ttu-id="b3a2f-134">В этом примере оба объекта, <xref:Microsoft.SqlServer.Management.Smo.UserOptions> и <xref:Microsoft.SqlServer.Management.Smo.Settings>, обладают методом <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-134">In the example the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object and the <xref:Microsoft.SqlServer.Management.Smo.Settings> object both have an <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="b3a2f-135">Для них можно отдельно запустить методы <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-135">You can run the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> methods for these individually.</span></span>  
  
 `//Connect to the local, default instance of SQL Server.`  
  
```csharp
{  
            Server srv = new Server();  
            //Display all the configuration options.   
  
            foreach (ConfigProperty p in srv.Configuration.Properties)  
            {  
                Console.WriteLine(p.DisplayName);  
            }  
            Console.WriteLine("There are " + srv.Configuration.Properties.Count.ToString() + " configuration options.");  
            //Display the maximum and minimum values for ShowAdvancedOptions.   
            int min = 0;  
            int max = 0;  
            min = srv.Configuration.ShowAdvancedOptions.Minimum;  
            max = srv.Configuration.ShowAdvancedOptions.Maximum;  
            Console.WriteLine("Minimum and Maximum values are " + min + " and " + max + ".");  
            //Modify the value of ShowAdvancedOptions and run the Alter method.   
            srv.Configuration.ShowAdvancedOptions.ConfigValue = 0;  
            srv.Configuration.Alter();  
            //Display when the change takes place according to the IsDynamic property.   
            if (srv.Configuration.ShowAdvancedOptions.IsDynamic == true)  
            {  
                Console.WriteLine("Configuration option has been updated.");  
            }  
            else  
            {  
                Console.WriteLine("Configuration option will be updated when SQL Server is restarted.");  
            }  
        }  
```  
  
## <a name="modifying-sql-server-settings-in-powershell"></a><span data-ttu-id="b3a2f-136">Изменение параметров SQL Server в PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3a2f-136">Modifying SQL Server Settings in PowerShell</span></span>  
 <span data-ttu-id="b3a2f-137">В примере кода выводятся сведения об экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в <xref:Microsoft.SqlServer.Management.Smo.Information> и <xref:Microsoft.SqlServer.Management.Smo.Settings> , а также изменяются параметры в <xref:Microsoft.SqlServer.Management.Smo.Settings> <xref:Microsoft.SqlServer.Management.Smo.UserOptions> свойствах объекта и.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-137">The code example displays information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> and <xref:Microsoft.SqlServer.Management.Smo.Settings>, and modifies settings in <xref:Microsoft.SqlServer.Management.Smo.Settings> and <xref:Microsoft.SqlServer.Management.Smo.UserOptions>object properties.</span></span>  
  
 <span data-ttu-id="b3a2f-138">В этом примере оба объекта, <xref:Microsoft.SqlServer.Management.Smo.UserOptions> и <xref:Microsoft.SqlServer.Management.Smo.Settings>, обладают методом <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-138">In the example the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object and the <xref:Microsoft.SqlServer.Management.Smo.Settings> object both have an <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="b3a2f-139">Для них можно отдельно запустить методы <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-139">You can run the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> methods for these individually.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = Get-Item default  
  
#Display information about the instance of SQL Server in Information and Settings.  
"OS Version = " + $srv.Information.OSVersion  
"State = "+ $srv.Settings.State.ToString()  
  
#Display information specific to the current user in UserOptions.  
"Quoted Identifier support = " + $srv.UserOptions.QuotedIdentifier  
  
#Modify server settings in Settings.  
$srv.Settings.LoginMode = [Microsoft.SqlServer.Management.SMO.ServerLoginMode]::Integrated  
  
#Modify settings specific to the current connection in UserOptions.  
$srv.UserOptions.AbortOnArithmeticErrors = $true  
  
#Run the Alter method to make the changes on the instance of SQL Server.  
$srv.Alter()  
```  
  
## <a name="modifying-sql-server-configuration-options-in-powershell"></a><span data-ttu-id="b3a2f-140">Изменение параметров конфигурации SQL Server в PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3a2f-140">Modifying SQL Server Configuration Options in PowerShell</span></span>  
 <span data-ttu-id="b3a2f-141">Этот пример кода показывает, как обновить параметр конфигурации на языке Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-141">The code example shows how to update a configuration option in Visual Basic .NET.</span></span> <span data-ttu-id="b3a2f-142">Он также возвращает и отображает сведения о максимальном и минимальном значениях указанного параметра конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b3a2f-142">It also retrieves and displays information about maximum and minimum values for the specified configuration option.</span></span> <span data-ttu-id="b3a2f-143">Наконец, программа извещает пользователя, выполнено ли изменение динамически или оно будет храниться до тех пор, пока не произойдет перезагрузка экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3a2f-143">Finally, the program informs the user if the change has been made dynamically, or if it is stored until the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is restarted.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance replace LocalMachine with the physical server  
cd \sql\LocalMachine  
$svr = Get-Item default  
  
#enumerate its properties  
foreach ($Item in $Svr.Configuration.Properties)   
{  
 $Item.DisplayName  
}  
  
"There are " + $svr.Configuration.Properties.Count.ToString() + " configuration options."  
  
#Display the maximum and minimum values for ShowAdvancedOptions.  
$min = $svr.Configuration.ShowAdvancedOptions.Minimum  
$max = $svr.Configuration.ShowAdvancedOptions.Maximum  
"Minimum and Maximum values are " + $min.ToString() + " and " + $max.ToString() + "."  
  
#Modify the value of ShowAdvancedOptions and run the Alter method.  
$svr.Configuration.ShowAdvancedOptions.ConfigValue = 0  
$svr.Configuration.Alter()  
  
#Display when the change takes place according to the IsDynamic property.  
If ($svr.Configuration.ShowAdvancedOptions.IsDynamic -eq $true)  
 {
   "Configuration option has been updated."  
 }  
Else  
 {  
    "Configuration option will be updated when SQL Server is restarted."  
 }  
```  
