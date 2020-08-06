---
title: Метод GenerateDatabaseRightsScript (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseRightsScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseRightsScript method
ms.assetid: f2e6dcc9-978f-4c2c-bafe-36c330247fd0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 768e73d13d3b06f7913c3c816fded1b28c56199f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737766"
---
# <a name="generatedatabaserightsscript-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="22019-102">Метод GenerateDatabaseRightsScript (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="22019-102">GenerateDatabaseRightsScript Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="22019-103">Создает скрипт SQL, с помощью которого пользователям могут предоставляться права доступа к базе данных сервера отчетов и другим базам данных, необходимым для работы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="22019-103">Generates a SQL Script that can be used to grant a user rights to the report server database and other databases required for a report server to run.</span></span> <span data-ttu-id="22019-104">Ожидается, что участник соединится с базой данных сервера отчетов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и выполнит скрипт.</span><span class="sxs-lookup"><span data-stu-id="22019-104">The caller is expected to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database server and execute the script.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22019-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22019-105">Syntax</span></span>  
  
```vb  
Public Sub GenerateDatabaseRightsScript(ByVal UserName As String, _  
    ByVal DatabaseName As String, ByVal IsRemote As Boolean, _  
    ByVal IsWindowsUser As Boolean, ByRef Script As String, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GenerateDatabaseRightsScript(string UserName, string DatabaseName, bool IsRemote, bool IsWindowsUser, out string Script,   
out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22019-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="22019-106">Parameters</span></span>  
 <span data-ttu-id="22019-107">*UserName*</span><span class="sxs-lookup"><span data-stu-id="22019-107">*UserName*</span></span>  
 <span data-ttu-id="22019-108">Имя пользователя или идентификатор безопасности Windows пользователя, которому скрипт предоставляет права.</span><span class="sxs-lookup"><span data-stu-id="22019-108">The user name or Windows security identifier (SID) of the user to which the script will grant rights.</span></span>  
  
 <span data-ttu-id="22019-109">*DatabaseName*</span><span class="sxs-lookup"><span data-stu-id="22019-109">*DatabaseName*</span></span>  
 <span data-ttu-id="22019-110">Имя базы данных, доступ к которой скрипт предоставит пользователю.</span><span class="sxs-lookup"><span data-stu-id="22019-110">The database name to which the script will grant access to the user.</span></span>  
  
 <span data-ttu-id="22019-111">*IsRemote*</span><span class="sxs-lookup"><span data-stu-id="22019-111">*IsRemote*</span></span>  
 <span data-ttu-id="22019-112">Логическое значение. Показывает, является ли база данных удаленной по отношению к серверу отчетов.</span><span class="sxs-lookup"><span data-stu-id="22019-112">A Boolean value to indicating whether the database is remote from the report server.</span></span>  
  
 <span data-ttu-id="22019-113">*IsWindowsUser*</span><span class="sxs-lookup"><span data-stu-id="22019-113">*IsWindowsUser*</span></span>  
 <span data-ttu-id="22019-114">Логическое значение, которое показывает тип пользователя для указанного имени пользователя: Windows или [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="22019-114">A Boolean value indicating whether the specified user name is a Windows user or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user.</span></span>  
  
 <span data-ttu-id="22019-115">*Скрипт*</span><span class="sxs-lookup"><span data-stu-id="22019-115">*Script*</span></span>  
 <span data-ttu-id="22019-116">[out] Строка, которая содержит созданный скрипт [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="22019-116">[out] A string containing the generated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] script.</span></span>  
  
 <span data-ttu-id="22019-117">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="22019-117">*HRESULT*</span></span>  
 <span data-ttu-id="22019-118">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="22019-118">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22019-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="22019-119">Return Value</span></span>  
 <span data-ttu-id="22019-120">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="22019-120">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="22019-121">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="22019-121">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="22019-122">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="22019-122">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22019-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="22019-123">Remarks</span></span>  
 <span data-ttu-id="22019-124">Если параметр *DatabaseName* пуст, *IsRemote* пропускается и значение файла конфигурации сервера отчетов используется в качестве имени базы данных.</span><span class="sxs-lookup"><span data-stu-id="22019-124">If *DatabaseName* is empty then *IsRemote* is ignored and the report server configuration file value is used for the database name.</span></span>  
  
 <span data-ttu-id="22019-125">Если *параметр IsWindowsUser* имеет значение `true` , то *имя пользователя* должно быть в формате \<domain> \\<имя пользователя \> .</span><span class="sxs-lookup"><span data-stu-id="22019-125">If *IsWindowsUser* is set to `true`, *UserName* should be in the format \<domain>\\<username\>.</span></span>  
  
 <span data-ttu-id="22019-126">Если для *параметр IsWindowsUser* задано значение `true` , созданный скрипт предоставляет пользователю права на вход в систему [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , задание базы данных сервера отчетов в качестве базы данных по умолчанию и предоставляет роль **RSExec** в базе данных сервера отчетов, временной базе данных сервера отчетов, базе данных master и системной базе данных msdb.</span><span class="sxs-lookup"><span data-stu-id="22019-126">When *IsWindowsUser* is set to `true`, the generated script grants login rights to the user for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], setting the report server database as the default database, and grants the **RSExec** role on the report server database, the report server temporary database, the master database and the MSDB system database.</span></span>  
  
 <span data-ttu-id="22019-127">Если для *параметр IsWindowsUser* задано значение `true` , метод принимает в качестве входных данных стандартные идентификаторы безопасности Windows.</span><span class="sxs-lookup"><span data-stu-id="22019-127">When *IsWindowsUser* is set to `true`, the method accepts standard Windows SIDs as input.</span></span> <span data-ttu-id="22019-128">Если предоставлен стандартный идентификатор безопасности Windows или имя учетной записи службы, то они переводятся в строку имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="22019-128">When a standard Windows SID or service account name is supplied, it is translated to a user name string.</span></span> <span data-ttu-id="22019-129">Если база данных локальная, то учетная запись переводится в соответствии с представлением текущего языкового стандарта учетной записи.</span><span class="sxs-lookup"><span data-stu-id="22019-129">If the database is local, the account is translated to the correct localized representation of the account.</span></span> <span data-ttu-id="22019-130">Если база данных удаленная, то учетная запись представляется как учетная запись компьютера.</span><span class="sxs-lookup"><span data-stu-id="22019-130">If the database is remote, the account is represented as the computer's account.</span></span>  
  
 <span data-ttu-id="22019-131">В приведенной ниже таблице показаны переведенные учетные записи и их удаленное представление.</span><span class="sxs-lookup"><span data-stu-id="22019-131">The following table shows accounts that are translated and their remote representation.</span></span>  
  
|<span data-ttu-id="22019-132">Переведенная учетная запись/идентификатор безопасности</span><span class="sxs-lookup"><span data-stu-id="22019-132">Account / SID that is translated</span></span>|<span data-ttu-id="22019-133">Общее имя</span><span class="sxs-lookup"><span data-stu-id="22019-133">Common Name</span></span>|<span data-ttu-id="22019-134">Удаленное имя</span><span class="sxs-lookup"><span data-stu-id="22019-134">Remote Name</span></span>|  
|---------------------------------------|-----------------|-----------------|  
|<span data-ttu-id="22019-135">(S-1-5-18)</span><span class="sxs-lookup"><span data-stu-id="22019-135">(S-1-5-18)</span></span>|<span data-ttu-id="22019-136">Локальная система</span><span class="sxs-lookup"><span data-stu-id="22019-136">Local System</span></span>|<span data-ttu-id="22019-137">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="22019-137">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="22019-138">.\LocalSystem</span><span class="sxs-lookup"><span data-stu-id="22019-138">.\LocalSystem</span></span>|<span data-ttu-id="22019-139">Локальная система</span><span class="sxs-lookup"><span data-stu-id="22019-139">Local System</span></span>|<span data-ttu-id="22019-140">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="22019-140">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="22019-141">ComputerName\LocalSystem</span><span class="sxs-lookup"><span data-stu-id="22019-141">ComputerName\LocalSystem</span></span>|<span data-ttu-id="22019-142">Локальная система</span><span class="sxs-lookup"><span data-stu-id="22019-142">Local System</span></span>|<span data-ttu-id="22019-143">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="22019-143">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="22019-144">локальная система;</span><span class="sxs-lookup"><span data-stu-id="22019-144">LocalSystem</span></span>|<span data-ttu-id="22019-145">Локальная система</span><span class="sxs-lookup"><span data-stu-id="22019-145">Local System</span></span>|<span data-ttu-id="22019-146">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="22019-146">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="22019-147">(S-1-5-20)</span><span class="sxs-lookup"><span data-stu-id="22019-147">(S-1-5-20)</span></span>|<span data-ttu-id="22019-148">Сетевая служба.</span><span class="sxs-lookup"><span data-stu-id="22019-148">Network Service</span></span>|<span data-ttu-id="22019-149">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="22019-149">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="22019-150">NT AUTHORITY\NetworkService</span><span class="sxs-lookup"><span data-stu-id="22019-150">NT AUTHORITY\NetworkService</span></span>|<span data-ttu-id="22019-151">Сетевая служба.</span><span class="sxs-lookup"><span data-stu-id="22019-151">Network Service</span></span>|<span data-ttu-id="22019-152">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="22019-152">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="22019-153">(S-1-5-19)</span><span class="sxs-lookup"><span data-stu-id="22019-153">(S-1-5-19)</span></span>|<span data-ttu-id="22019-154">Локальная служба.</span><span class="sxs-lookup"><span data-stu-id="22019-154">Local Service</span></span>|<span data-ttu-id="22019-155">Ошибка — см. ниже.</span><span class="sxs-lookup"><span data-stu-id="22019-155">Error - see below.</span></span>|  
|<span data-ttu-id="22019-156">NT AUTHORITY\LocalService</span><span class="sxs-lookup"><span data-stu-id="22019-156">NT AUTHORITY\LocalService</span></span>|<span data-ttu-id="22019-157">Локальная служба.</span><span class="sxs-lookup"><span data-stu-id="22019-157">Local Service</span></span>|<span data-ttu-id="22019-158">Ошибка — см. ниже.</span><span class="sxs-lookup"><span data-stu-id="22019-158">Error - see below.</span></span>|  
  
 <span data-ttu-id="22019-159">Если в [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)]используется встроенная учетная запись, а база данных сервера отчетов удаленная, то возвращается сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="22019-159">On [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)], if you are using a built-in account and the report server database is remote, an error is returned.</span></span>  
  
 <span data-ttu-id="22019-160">Если указана встроенная учетная запись `LocalService` и база данных сервера отчетов удаленная, то возвращается сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="22019-160">If the `LocalService` built-in account is specified and the report server database is remote, an error is returned.</span></span>  
  
 <span data-ttu-id="22019-161">Если параметр *IsWindowsUser* имеет значение true, а значение параметра *UserName* требует перевода, то поставщик WMI определяет, на каком компьютере находится база данных сервера отчетов: на этом же или на удаленном.</span><span class="sxs-lookup"><span data-stu-id="22019-161">When *IsWindowsUser* is true and the value supplied in *UserName* needs to be translated, the WMI provider determines whether the report server database is located on the same computer or on a remote computer.</span></span> <span data-ttu-id="22019-162">Чтобы определить, что установка локальная, поставщик WMI проверяет свойство DatabaseServerName на значения из приведенного ниже списка.</span><span class="sxs-lookup"><span data-stu-id="22019-162">To determine if the installation is local, the WMI provider evaluates the DatabaseServerName property against the following list of values.</span></span> <span data-ttu-id="22019-163">Если одно из значений совпадает, то база данных локальная.</span><span class="sxs-lookup"><span data-stu-id="22019-163">If a match is found, the database is local.</span></span> <span data-ttu-id="22019-164">В противном случае она является удаленной.</span><span class="sxs-lookup"><span data-stu-id="22019-164">Otherwise, it is remote.</span></span> <span data-ttu-id="22019-165">При сравнении учитывается регистр букв.</span><span class="sxs-lookup"><span data-stu-id="22019-165">The comparison is case-insensitive.</span></span>  
  
|<span data-ttu-id="22019-166">Значение параметра DatabaseServerName</span><span class="sxs-lookup"><span data-stu-id="22019-166">Value of DatabaseServerName</span></span>|<span data-ttu-id="22019-167">Пример</span><span class="sxs-lookup"><span data-stu-id="22019-167">Example</span></span>|  
|---------------------------------|-------------|  
|<span data-ttu-id="22019-168">"."</span><span class="sxs-lookup"><span data-stu-id="22019-168">"."</span></span>||  
|<span data-ttu-id="22019-169">"(local)"</span><span class="sxs-lookup"><span data-stu-id="22019-169">"(local)"</span></span>||  
|<span data-ttu-id="22019-170">"LOCAL"</span><span class="sxs-lookup"><span data-stu-id="22019-170">"LOCAL"</span></span>||  
|<span data-ttu-id="22019-171">localhost</span><span class="sxs-lookup"><span data-stu-id="22019-171">localhost</span></span>||  
|\<Machinename>|<span data-ttu-id="22019-172">testlab14</span><span class="sxs-lookup"><span data-stu-id="22019-172">testlab14</span></span>|  
|\<MachineFQDN>|<span data-ttu-id="22019-173">example.redmond.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="22019-173">example.redmond.microsoft.com</span></span>|  
|\<IPAddress>|<span data-ttu-id="22019-174">180.012.345,678</span><span class="sxs-lookup"><span data-stu-id="22019-174">180.012.345,678</span></span>|  
  
 <span data-ttu-id="22019-175">Если для *параметр IsWindowsUser* задано значение `true` , поставщик WMI вызывает LookupAccountName, чтобы получить идентификатор безопасности для учетной записи, а затем вызывает LookupAccountSID, чтобы получить имя, помещаемое в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] скрипт.</span><span class="sxs-lookup"><span data-stu-id="22019-175">When *IsWindowsUser* is set to `true`, the WMI provider calls LookupAccountName to get the SID for the account and then calls LookupAccountSID to get the name to put in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] script.</span></span> <span data-ttu-id="22019-176">Это гарантирует, что имя учетной записи успешно пройдет проверку [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="22019-176">This ensures that the account name used will pass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] validation.</span></span>  
  
 <span data-ttu-id="22019-177">Если для *параметр IsWindowsUser* задано значение `false` , то созданный скрипт предоставляет роль **RSExec** в базе данных сервера отчетов, временной базе данных сервера отчетов и базе данных msdb.</span><span class="sxs-lookup"><span data-stu-id="22019-177">When *IsWindowsUser* is set to `false`, the generated script grants the **RSExec** role on the report server database, the report server temporary database, and the MSDB database.</span></span>  
  
 <span data-ttu-id="22019-178">Если *параметр IsWindowsUser* имеет значение `false` , то [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для успешного выполнения скрипта SQL Server пользователь должен уже существовать в.</span><span class="sxs-lookup"><span data-stu-id="22019-178">When *IsWindowsUser* is set to `false`, the SQL Server user must already exist on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the script to run successfully.</span></span>  
  
 <span data-ttu-id="22019-179">Если для сервера отчетов не задана база данных сервера отчетов, то при вызове метода GrantRightsToDatabaseUser возвращается ошибка.</span><span class="sxs-lookup"><span data-stu-id="22019-179">If the report server does not have a report server database specified, calling GrantRightsToDatabaseUser returns an error.</span></span>  
  
 <span data-ttu-id="22019-180">Созданный скрипт поддерживает [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 и [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22019-180">The generated script supports [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005, and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22019-181">Требования</span><span class="sxs-lookup"><span data-stu-id="22019-181">Requirements</span></span>  
 <span data-ttu-id="22019-182">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22019-182">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22019-183">См. также:</span><span class="sxs-lookup"><span data-stu-id="22019-183">See Also</span></span>  
 [<span data-ttu-id="22019-184">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="22019-184">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
