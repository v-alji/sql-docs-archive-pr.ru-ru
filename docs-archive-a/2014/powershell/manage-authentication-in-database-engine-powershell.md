---
title: Управление аутентификацией в PowerShell (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: ab9212a6-6628-4f08-a38c-d3156e05ddea
author: stevestein
ms.author: sstein
ms.openlocfilehash: 018a2698a43148af971622f54c8418bf23c2c781
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729546"
---
# <a name="manage-authentication-in-database-engine-powershell"></a><span data-ttu-id="155ec-102">Управление проверкой подлинности в компонент Database Engine PowerShell</span><span class="sxs-lookup"><span data-stu-id="155ec-102">Manage Authentication in Database Engine PowerShell</span></span>
  <span data-ttu-id="155ec-103">По умолчанию компоненты [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell используют при установлении соединения с компонентом [!INCLUDE[ssDE](../includes/ssde-md.md)]проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="155ec-103">By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell components use Windows Authentication when connecting to an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="155ec-104">Для использования проверки подлинности SQL Server необходимо либо определить виртуальный диск PowerShell, либо указать параметры `-Username` и `-Password` для `Invoke-Sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="155ec-104">You can use SQL Server Authentication by either defining a PowerShell virtual drive, or by specifying the `-Username` and `-Password` parameters for `Invoke-Sqlcmd`.</span></span>  
  
1.  <span data-ttu-id="155ec-105">**Перед началом работы**  [Разрешения](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="155ec-105">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
2.  <span data-ttu-id="155ec-106">**To set authentication, using:**  [A Virtual Drive](#SQLAuthVirtDrv), [Invoke-Sqlcmd](#SQLAuthInvSqlCmd)</span><span class="sxs-lookup"><span data-stu-id="155ec-106">**To set authentication, using:**  [A Virtual Drive](#SQLAuthVirtDrv), [Invoke-Sqlcmd](#SQLAuthInvSqlCmd)</span></span>  
  
##  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="155ec-107">Permissions</span><span class="sxs-lookup"><span data-stu-id="155ec-107">Permissions</span></span>  
 <span data-ttu-id="155ec-108">Все действия, которые могут быть выполнены на экземпляре компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] , определяются разрешениями, предоставляемыми учетным данным, которые использовались при подключении к экземпляру.</span><span class="sxs-lookup"><span data-stu-id="155ec-108">All actions you can perform in an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] are controlled by the permissions granted to the authentication credentials used to connect to the instance.</span></span> <span data-ttu-id="155ec-109">По умолчанию для подключения к компоненту [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] с проверкой подлинности Windows поставщик [!INCLUDE[ssDE](../includes/ssde-md.md)]и командлеты используют учетную запись Windows, под которой они работают.</span><span class="sxs-lookup"><span data-stu-id="155ec-109">By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider and cmdlets use the Windows account under which it is running to make a Windows Authentication connection to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="155ec-110">Для подключения с проверкой подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] необходимо указать идентификатор имени входа и пароль проверки подлинности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="155ec-110">To make a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication connection you must supply a SQL Server Authentication login ID and password.</span></span> <span data-ttu-id="155ec-111">При использовании [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] поставщика необходимо связать [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] учетные данные входа с виртуальным диском, а затем использовать команду Change Directory ( `cd` ) для подключения к этому диску.</span><span class="sxs-lookup"><span data-stu-id="155ec-111">When using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider, you must associate the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login credentials with a virtual drive, and then use the change directory command (`cd`) to connect to that drive.</span></span> <span data-ttu-id="155ec-112">В Windows PowerShell учетные данные безопасности можно связывать только с виртуальными дисками.</span><span class="sxs-lookup"><span data-stu-id="155ec-112">In Windows PowerShell, security credentials can only be associated with virtual drives.</span></span>  
  
##  <a name="sql-server-authentication-using-a-virtual-drive"></a><a name="SQLAuthVirtDrv"></a> <span data-ttu-id="155ec-113">Проверка подлинности SQL Server с помощью виртуального диска</span><span class="sxs-lookup"><span data-stu-id="155ec-113">SQL Server Authentication Using a Virtual Drive</span></span>  
 <span data-ttu-id="155ec-114">**Создание виртуального диска с именем входа для проверки подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="155ec-114">**To create a virtual drive associated with a SQL Server Authentication login**</span></span>  
  
1.  <span data-ttu-id="155ec-115">Создайте функцию, которая:</span><span class="sxs-lookup"><span data-stu-id="155ec-115">Create a function that:</span></span>  
  
    1.  <span data-ttu-id="155ec-116">Имеет параметры для имени, назначаемого виртуальному диску, идентификатора имени входа и пути поставщика, который будет связан с виртуальным диском.</span><span class="sxs-lookup"><span data-stu-id="155ec-116">Has parameters for the name to give the virtual drive, the login ID, and the provider path to associate with the virtual drive.</span></span>  
  
    2.  <span data-ttu-id="155ec-117">Использует `read-host` для запроса ввода пароля.</span><span class="sxs-lookup"><span data-stu-id="155ec-117">Uses `read-host` to prompt the user for the password.</span></span>  
  
    3.  <span data-ttu-id="155ec-118">Использует `new-object` для создания объекта учетных данных.</span><span class="sxs-lookup"><span data-stu-id="155ec-118">Uses `new-object` to create a credentials object.</span></span>  
  
    4.  <span data-ttu-id="155ec-119">Использует `new-psdrive` для создания виртуального диска с указанными учетными данными.</span><span class="sxs-lookup"><span data-stu-id="155ec-119">Uses `new-psdrive` to create a virtual drive with the supplied credentials.</span></span>  
  
2.  <span data-ttu-id="155ec-120">Вызовите функцию, чтобы создать виртуальный диск с указанными учетными данными.</span><span class="sxs-lookup"><span data-stu-id="155ec-120">Invoke the function to create a virtual drive with the supplied credentials.</span></span>  
  
### <a name="example-virtual-drive"></a><span data-ttu-id="155ec-121">Пример (виртуальный диск)</span><span class="sxs-lookup"><span data-stu-id="155ec-121">Example (Virtual Drive)</span></span>  
 <span data-ttu-id="155ec-122">В этом примере показано создание функции **sqldrive** для создания виртуального диска, который затем будет связан с указанным именем входа для проверки подлинности и экземпляром [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="155ec-122">This example creates a function named **sqldrive** that you can use to create a virtual drive that is associated with the specified [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication login and instance.</span></span>  
  
 <span data-ttu-id="155ec-123">Функция **sqldrive** запрашивает ввод пароля для имени входа, скрывая символы пароля при их вводе.</span><span class="sxs-lookup"><span data-stu-id="155ec-123">The **sqldrive** function prompts you to enter the password for your login, masking the password as you type it in.</span></span> <span data-ttu-id="155ec-124">Затем, когда вы используете команду Change Directory ( `cd` ) для подключения к пути с помощью имени виртуального диска, все операции выполняются с использованием [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] учетных данных входа для проверки подлинности, которые были указаны при создании диска.</span><span class="sxs-lookup"><span data-stu-id="155ec-124">Then, whenever you use the change directory command (`cd`) to connect to a path by using the virtual drive name, all operations are performed by using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication login credentials that you supplied when you created the drive.</span></span>  
  
```powershell
## Create a function that specifies the login and prompts for the password.  
  
function sqldrive  
{  
    param( [string]$name, [string]$login = "MyLogin", [string]$root = "SQLSERVER:\SQL\MyComputer\MyInstance" )  
    $pwd = Read-Host -AsSecureString -Prompt "Password"  
    $cred = New-Object System.Management.Automation.PSCredential -argumentlist $login, $pwd  
    New-PSDrive $name -PSProvider SqlServer -Root $root -Credential $cred -Scope 1  
}  
  
## Use the sqldrive function to create a SQLAuth virtual drive.  
sqldrive SQLAuth  
  
## CD to the virtual drive, which invokes the supplied authentication credentials.  
cd SQLAuth  
```  
  
##  <a name="sql-server-authentication-using-invoke-sqlcmd"></a><a name="SQLAuthInvSqlCmd"></a> <span data-ttu-id="155ec-125">Проверка подлинности SQL Server с использованием Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="155ec-125">SQL Server Authentication Using Invoke-Sqlcmd</span></span>  
 <span data-ttu-id="155ec-126">**Использование Invoke-Sqlcmd для проверки подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="155ec-126">**To use Invoke-Sqlcmd with SQL Server Authentication**</span></span>  
  
1.  <span data-ttu-id="155ec-127">Укажите идентификатор имени входа с помощью параметра `-Username`, а связанный с ним пароль — с помощью параметра `-Password`.</span><span class="sxs-lookup"><span data-stu-id="155ec-127">Use the `-Username` parameter to specify a login ID, and the `-Password` parameter to specify the associated password.</span></span>  
  
### <a name="example-invoke-sqlcmd"></a><span data-ttu-id="155ec-128">Пример (Invoke-Sqlcmd)</span><span class="sxs-lookup"><span data-stu-id="155ec-128">Example (Invoke-Sqlcmd)</span></span>  
 <span data-ttu-id="155ec-129">В этом примере командлет read-host используется для запроса ввода пароля с последующим подключением с проверкой подлинности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="155ec-129">This example uses the read-host cmdlet to prompt the user for a password, and then connects using SQL Server Authentication.</span></span>  
  
```powershell
## Prompt the user for their password.  
$pwd = Read-Host -AsSecureString -Prompt "Password"  
  
Invoke-Sqlcmd -Query "SELECT GETDATE() AS TimeOfQuery;" -ServerInstance "MyComputer\MyInstance" -Username "MyLogin" -Password $pwd  
```  
  
## <a name="see-also"></a><span data-ttu-id="155ec-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="155ec-130">See Also</span></span>  
 <span data-ttu-id="155ec-131">[SQL Server PowerShell](sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="155ec-131">[SQL Server PowerShell](sql-server-powershell.md) </span></span>  
 <span data-ttu-id="155ec-132">[Поставщик SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="155ec-132">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="155ec-133">Invoke-Sqlcmd, командлет</span><span class="sxs-lookup"><span data-stu-id="155ec-133">Invoke-Sqlcmd cmdlet</span></span>](../database-engine/invoke-sqlcmd-cmdlet.md)  
