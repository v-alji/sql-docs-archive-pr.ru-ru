---
title: Метод SetDatabaseConnection (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetDatabaseConnection (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDatabaseConnection method
ms.assetid: c040aa78-92b8-41e4-9ae2-eff9fcdddc5b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b5c62777edd1fab2b0cb3babc13ab09f7bcf32a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737739"
---
# <a name="setdatabaseconnection-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="fa3fe-102">Метод SetDatabaseConnection (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="fa3fe-102">SetDatabaseConnection Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="fa3fe-103">Задает подключение к определенной базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-103">Sets the report server database connection to a particular report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa3fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa3fe-104">Syntax</span></span>  
  
```vb  
Public Sub SetDatabaseConnection(Server as String, _  
    DatabaseName as string, CredentialsType as Integer, _  
    Username as String, Password as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void BackupEncryptionKey(string Server,   
    string DatabaseName, Int32 CredentialsType,   
    string UserName, string Password, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa3fe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fa3fe-105">Parameters</span></span>  
 <span data-ttu-id="fa3fe-106">*Server*</span><span class="sxs-lookup"><span data-stu-id="fa3fe-106">*Server*</span></span>  
 <span data-ttu-id="fa3fe-107">Имя экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , на котором размещается база данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-107">The name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is used to host the report server database.</span></span>  
  
 <span data-ttu-id="fa3fe-108">*DatabaseName*</span><span class="sxs-lookup"><span data-stu-id="fa3fe-108">*DatabaseName*</span></span>  
 <span data-ttu-id="fa3fe-109">Имя базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-109">The name of the report server database.</span></span>  
  
 <span data-ttu-id="fa3fe-110">*CredentialsType*</span><span class="sxs-lookup"><span data-stu-id="fa3fe-110">*CredentialsType*</span></span>  
 <span data-ttu-id="fa3fe-111">Тип учетных данных, которые используются для соединения.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-111">The type of credentials to use for the connection.</span></span> <span data-ttu-id="fa3fe-112">Значения могут быть такими:</span><span class="sxs-lookup"><span data-stu-id="fa3fe-112">Values can be:</span></span>  
  
-   <span data-ttu-id="fa3fe-113">0 — Windows;</span><span class="sxs-lookup"><span data-stu-id="fa3fe-113">0 - Windows</span></span>  
  
-   <span data-ttu-id="fa3fe-114">1 — [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa3fe-114">1 - [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="fa3fe-115">2 — служба Windows.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-115">2 - Windows Service</span></span>  
  
 <span data-ttu-id="fa3fe-116">*UserName*</span><span class="sxs-lookup"><span data-stu-id="fa3fe-116">*UserName*</span></span>  
 <span data-ttu-id="fa3fe-117">Имя учетной записи, которая используется для соединения с базой данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-117">The account name used to connect to the report server database.</span></span>  
  
 <span data-ttu-id="fa3fe-118">*Пароль*</span><span class="sxs-lookup"><span data-stu-id="fa3fe-118">*Password*</span></span>  
 <span data-ttu-id="fa3fe-119">Пароль, используемый для соединения с базой данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-119">The password used to connect to the report server database.</span></span>  
  
 <span data-ttu-id="fa3fe-120">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="fa3fe-120">*HRESULT*</span></span>  
 <span data-ttu-id="fa3fe-121">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-121">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa3fe-122">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fa3fe-122">Return Value</span></span>  
 <span data-ttu-id="fa3fe-123">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-123">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="fa3fe-124">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-124">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="fa3fe-125">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-125">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa3fe-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="fa3fe-126">Remarks</span></span>  
 <span data-ttu-id="fa3fe-127">Если параметр *CredentialsType* имеет значение 0 (Windows), необходимо указать значения параметров *UserName* и *Password* .</span><span class="sxs-lookup"><span data-stu-id="fa3fe-127">When the *CredentialsType* parameter is set to 0 (Windows), the *UserName* and *Password* parameters must be set.</span></span> <span data-ttu-id="fa3fe-128">Параметр *UserName* должен иметь вид "домен\имя_пользователя", значение должно представлять действующие данные для входа в Windows.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-128">The *UserName* parameter must be in the form "domain\username", and the value must represent a valid Windows logon.</span></span>  
  
 <span data-ttu-id="fa3fe-129">Если параметр *CredentialsType* имеет значение 1 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), то значение, передаваемое в параметре *UserName* , должно соответствовать требованиям, предъявляемым к имени входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fa3fe-129">When the *CredentialsType* parameter is set to 1 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), the value passed in the *UserName* parameter must conform to the requirements of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login name.</span></span>  
  
 <span data-ttu-id="fa3fe-130">Если параметр *CredentialsType* имеет значение 2 (служба Windows), сервер отчетов использует встроенную безопасность для соединения с базой данных сервера отчетов, а параметры *UserName* и *Password* не учитываются.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-130">When the *CredentialsType* parameter is set to 2 (Windows Service), the report server uses integrated security to connect to the report server database and the *UserName* and *Password* parameters are ignored.</span></span> <span data-ttu-id="fa3fe-131">Для доступа к базе данных сервера отчетов веб-служба сервера отчетов использует либо учетную запись [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)], либо учетную запись пула приложений и учетную запись службы Windows.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-131">The Reporting Server Web service will use either the [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] account or an application pool's account and the Windows service account to access the report server database.</span></span>  
  
 <span data-ttu-id="fa3fe-132">При вызове метода SetDatabaseConnection учетные данные и сведения о базе данных зашифровываются и сохраняются в файле конфигурации для указанного сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-132">When called, the SetDatabaseConnection method encrypts and stores the credentials and database information in the configuration file for the specified report server.</span></span>  
  
 <span data-ttu-id="fa3fe-133">Метод SetDatabaseConnection не проверяет, может ли сервер отчетов соединиться с базой данных сервера отчетов с помощью указанных данных.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-133">The SetDatabaseConnection method does not check that the report server can connect to the report server database using the data specified.</span></span>  
  
 <span data-ttu-id="fa3fe-134">В первый раз свойство ConnectionPoolSize устанавливается в зависимости от количества процессоров: ConnectionPoolSize = число процессоров \* 75.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-134">When set for the first time, the ConnectionPoolSize property is set based on the following processors: ConnectionPoolSize = #Processors \* 75.</span></span>  
  
 <span data-ttu-id="fa3fe-135">Метод SetDatabaseConnection не предоставляет разрешения указанным учетным записям.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-135">The SetDatabaseConnection method does not grant permissions to the specified account(s).</span></span> <span data-ttu-id="fa3fe-136">Следует вызвать метод [GenerateDatabaseRightsScript](configurationsetting-method-generatedatabaserightsscript.md) для каждой учетной записи, которой требуется доступ к базе данных сервера отчетов, и запустить получившийся скрипт.</span><span class="sxs-lookup"><span data-stu-id="fa3fe-136">You must call the [GenerateDatabaseRightsScript](configurationsetting-method-generatedatabaserightsscript.md) method for each account that requires access to the report server database and run the resulting script.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa3fe-137">Требования</span><span class="sxs-lookup"><span data-stu-id="fa3fe-137">Requirements</span></span>  
 <span data-ttu-id="fa3fe-138">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa3fe-138">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa3fe-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="fa3fe-139">See Also</span></span>  
 [<span data-ttu-id="fa3fe-140">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="fa3fe-140">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
