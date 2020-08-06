---
title: Программа ssbdiagnose (Service Broker) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- Service Broker, runtime reports
- Service Broker, command prompt utilities
- troubleshooting [Service Broker], conversations
- troubleshooting [Service Broker], configurations
- command prompt utilities [Service Broker]
- Service Broker, troubleshooting
- Service Broker, configuration reports
- Service Broker, tools
- troubleshooting [Service Broker], runtime
- conversations [Service Broker], troubleshooting
- troubleshooting [Service Broker], ssbdiagnose utility
- tools [Service Broker], ssbdiagnose
- Service Broker, ssbdiagnose utility
- ssbdiagnose
ms.assetid: 0c1636e8-a3db-438e-be4c-1ea40d1f4877
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8efc581eebd7d8fa7fa265abb54168af78b57ca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735714"
---
# <a name="ssbdiagnose-utility-service-broker"></a><span data-ttu-id="38086-102">Программа ssbdiagnose (компонент Service Broker)</span><span class="sxs-lookup"><span data-stu-id="38086-102">ssbdiagnose Utility (Service Broker)</span></span>
  <span data-ttu-id="38086-103">Программа **ssbdiagnose** сообщает о проблемах в диалогах [!INCLUDE[ssSB](../../includes/sssb-md.md)] или в конфигурации службы [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38086-103">The **ssbdiagnose** utility reports issues in [!INCLUDE[ssSB](../../includes/sssb-md.md)] conversations or the configuration of [!INCLUDE[ssSB](../../includes/sssb-md.md)] services.</span></span> <span data-ttu-id="38086-104">Проверка конфигурации может быть выполнена для одной или для двух служб.</span><span class="sxs-lookup"><span data-stu-id="38086-104">Configuration checks can be made for either two services or a single service.</span></span> <span data-ttu-id="38086-105">Сведения о неполадках могут выводиться в окне командной строки в виде удобочитаемого текста или в формате XML, который может быть перенаправлен в файл или в другую программу.</span><span class="sxs-lookup"><span data-stu-id="38086-105">Issues are reported either in the command prompt window as human-readable text, or as formatted XML that can be redirected to a file or another program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38086-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38086-106">Syntax</span></span>  
  
```  
  
      ssbdiagnose   
[ [ -XML ]  
    [ -LEVEL { ERROR | WARNING | INFO } ]  
  [-IGNOREerror_id ] [ ...n]  
    [ <baseconnectionoptions> ]  
  { <configurationreport> | <runtimereport> }  
]  
| -?  
  
<configurationreport> ::=  
    CONFIGURATION  
  { [ FROM SERVICEservice_name  
      [ <fromconnectionoptions> ]  
      [ MIRROR <mirrorconnectionoptions> ]  
    ]  
    [ TO SERVICEservice_name[, broker_id ]  
      [ <toconnectionoptions> ]  
      [ MIRROR <mirrorconnectionoptions> ]  
    ]  
  }  
    ON CONTRACTcontract_name  
  [ ENCRYPTION { ON | OFF | ANONYMOUS } ]  
  
<runtime_report> ::=  
    RUNTIME  
    [-SHOWEVENTS ]  
        [ -NEW  
         [ -ID { conversation_handle  
                | conversation_group_id  
                 | conversation_id  
                  }  
        ] [ ...n]  
        ]  
    [ -TIMEOUTtimeout_interval ]  
    [ <runtimeconnectionoptions> ]  
  
<baseconnectionoptions> ::=  
  <connectionoptions>  
  
<fromconnectionoptions> ::=  
  <connectionoptions>  
  
<toconnectionoptions> ::=  
  <connectionoptions>  
  
<mirrorconnectionoptions> ::=  
  <connectionoptions>  
  
<runtimeconnectionoptions> ::=  
  [ CONNECT TO <connectionoptions> ] [ ...n]  
  
<connectionoptions> ::=  
    [ -E | { -Ulogin_id [ -Ppassword ] } ]  
  [ -Sserver_name[\instance_name] ]  
  [ -ddatabase_name ]  
  [ -llogin_timeout ]  
  
```  
  
## <a name="command-line-options"></a><span data-ttu-id="38086-107">Параметры командной строки</span><span class="sxs-lookup"><span data-stu-id="38086-107">Command Line Options</span></span>  
 <span data-ttu-id="38086-108">**-XML**</span><span class="sxs-lookup"><span data-stu-id="38086-108">**-XML**</span></span>  
 <span data-ttu-id="38086-109">Указывает, что вывод **ssbdiagnose** будет создан как форматированный XML,</span><span class="sxs-lookup"><span data-stu-id="38086-109">Specifies that the **ssbdiagnose** output be generated as formatted XML.</span></span> <span data-ttu-id="38086-110">который может быть перенаправлен в файл или в другое приложение.</span><span class="sxs-lookup"><span data-stu-id="38086-110">This can be redirected to a file or to another application.</span></span> <span data-ttu-id="38086-111">Если параметр **-XML** не указан, вывод **ssbdiagnose** форматируется в виде удобочитаемого (для человека) текста.</span><span class="sxs-lookup"><span data-stu-id="38086-111">If **-XML** is not specified, the **ssbdiagnose** output is formatted as human-readable text.</span></span>  
  
 <span data-ttu-id="38086-112">**-LEVEL** { **ERROR** | **WARNING** | **INFO**}</span><span class="sxs-lookup"><span data-stu-id="38086-112">**-LEVEL** { **ERROR** | **WARNING** | **INFO**}</span></span>  
 <span data-ttu-id="38086-113">Определяет, какие типы сообщений включаются в отчет.</span><span class="sxs-lookup"><span data-stu-id="38086-113">Specifies the level of messages to report.</span></span>  
  
 <span data-ttu-id="38086-114">**ERROR**: только сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="38086-114">**ERROR**: report only error messages.</span></span>  
  
 <span data-ttu-id="38086-115">**WARNING**: сообщения об ошибках и предупреждения.</span><span class="sxs-lookup"><span data-stu-id="38086-115">**WARNING**: report error and warning messages.</span></span>  
  
 <span data-ttu-id="38086-116">**INFO**: ошибки, предупреждения и информационные сообщения.</span><span class="sxs-lookup"><span data-stu-id="38086-116">**INFO**: report error, warning, and informational messages.</span></span>  
  
 <span data-ttu-id="38086-117">Значение по умолчанию — **WARNING**.</span><span class="sxs-lookup"><span data-stu-id="38086-117">The default setting is **WARNING**.</span></span>  
  
 <span data-ttu-id="38086-118">**-IGNORE** *идентификатор_ошибки*</span><span class="sxs-lookup"><span data-stu-id="38086-118">**-IGNORE** *error_id*</span></span>  
 <span data-ttu-id="38086-119">Указывает, что ошибки и сообщения, имеющие заданное значение *error_id* , не будут включены в отчет.</span><span class="sxs-lookup"><span data-stu-id="38086-119">Specifies that errors or messages that have the specified *error_id* not be included in reports.</span></span> <span data-ttu-id="38086-120">Параметр **-IGNORE** можно указать несколько раз, чтобы запретить вывод сообщений с различными идентификаторами.</span><span class="sxs-lookup"><span data-stu-id="38086-120">You can specify **-IGNORE** multiple times to suppress multiple message IDs.</span></span>  
  
 **\<baseconnectionoptions>**  
 <span data-ttu-id="38086-121">Задает основные сведения о соединении, которые используются программой **ssbdiagnose** , если параметры соединения не включены в определенное предложение.</span><span class="sxs-lookup"><span data-stu-id="38086-121">Specifies the base connection information that is used by **ssbdiagnose** when connection options are not included in a specific clause.</span></span> <span data-ttu-id="38086-122">Сведения о соединении, заданные в специальном предложении, переопределяют сведения **baseconnectionoption** .</span><span class="sxs-lookup"><span data-stu-id="38086-122">The connection information that is given in a specific clause overrides the **baseconnectionoption** information.</span></span> <span data-ttu-id="38086-123">Приоритеты учитываются по каждому параметру отдельно.</span><span class="sxs-lookup"><span data-stu-id="38086-123">This is performed separately for each parameter.</span></span> <span data-ttu-id="38086-124">Например, если в **baseconnetionoptions** указываются оба параметра **-S** и **-d**, а в **toconnetionoptions** указывается только **-d**, то **ssbdiagnose** использует -S из **baseconnetionoptions** и -d из **toconnetionoptions**.</span><span class="sxs-lookup"><span data-stu-id="38086-124">For example, if both **-S** and **-d** are specified in **baseconnetionoptions**, and only **-d** is specified in **toconnetionoptions**, **ssbdiagnose** uses -S from **baseconnetionoptions** and -d from **toconnetionoptions**.</span></span>  
  
 <span data-ttu-id="38086-125">**CONFIGURATION**</span><span class="sxs-lookup"><span data-stu-id="38086-125">**CONFIGURATION**</span></span>  
 <span data-ttu-id="38086-126">Запрашивает вывод отчета об ошибках конфигурации для одной службы или для пары служб компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38086-126">Requests a report of configuration errors between a pair of [!INCLUDE[ssSB](../../includes/sssb-md.md)] services, or for a single service.</span></span>  
  
 <span data-ttu-id="38086-127">**FROM SERVICE** *имя_службы*</span><span class="sxs-lookup"><span data-stu-id="38086-127">**FROM SERVICE** *service_name*</span></span>  
 <span data-ttu-id="38086-128">Указывает службу, которая является инициатором диалога.</span><span class="sxs-lookup"><span data-stu-id="38086-128">Specifies the service that initiates conversations.</span></span>  
  
 **\<fromconnectionoptions>**  
 <span data-ttu-id="38086-129">Задает сведения, необходимые для соединения с базой данных, в которой находится вызывающая служба.</span><span class="sxs-lookup"><span data-stu-id="38086-129">Specifies the information that is required to connect to the database that holds the initiator service.</span></span> <span data-ttu-id="38086-130">Если параметры **fromconnectionoptions** не указаны, то **ssbdiagnose** использует для подключения к базе данных инициатора сведения о соединении из **baseconnectionoptions** .</span><span class="sxs-lookup"><span data-stu-id="38086-130">If **fromconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions** to connect to the initiator database.</span></span> <span data-ttu-id="38086-131">Если параметры **fromconnectionoptions** задаются, то в них должна быть указана база данных, содержащая службу инициатора.</span><span class="sxs-lookup"><span data-stu-id="38086-131">If **fromconnectionoptions** is specified it must include the database that contains the initiator service.</span></span> <span data-ttu-id="38086-132">Если параметры **fromconnectionoptions** не указываются, в **baseconnectionoptions** необходимо указать базу данных инициатора.</span><span class="sxs-lookup"><span data-stu-id="38086-132">If **fromconnectionoptions** is not specified, the **baseconnectionoptions** must specify the initiator database.</span></span>  
  
 <span data-ttu-id="38086-133">**TO SERVICE** *имя_службы*[, *идентификатор\_брокера* ]</span><span class="sxs-lookup"><span data-stu-id="38086-133">**TO SERVICE** *service_name*[, *broker_id* ]</span></span>  
 <span data-ttu-id="38086-134">Указывает целевую службу для диалогов.</span><span class="sxs-lookup"><span data-stu-id="38086-134">Specifies the service that is the target for the conversations.</span></span>  
  
 <span data-ttu-id="38086-135">*service_name*: задает имя целевой службы.</span><span class="sxs-lookup"><span data-stu-id="38086-135">*service_name*: specifies the name of the target service.</span></span>  
  
 <span data-ttu-id="38086-136">*broker_id*: задает идентификатор [!INCLUDE[ssSB](../../includes/sssb-md.md)] , определяющий целевую базу данных.</span><span class="sxs-lookup"><span data-stu-id="38086-136">*broker_id*: specifies the [!INCLUDE[ssSB](../../includes/sssb-md.md)] ID that identifies the target database.</span></span> <span data-ttu-id="38086-137">*broker_id* — идентификатор GUID.</span><span class="sxs-lookup"><span data-stu-id="38086-137">*broker_id* is a GUID.</span></span> <span data-ttu-id="38086-138">Чтобы выяснить этот идентификатор, можно выполнить в целевой базе данных следующий запрос.</span><span class="sxs-lookup"><span data-stu-id="38086-138">You can run the following query in the target database to find it:</span></span>  
  
```  
SELECT service_broker_guid  
FROM sys.databases  
WHERE database_id = DB_ID();  
```  
  
 **\<toconnectionoptions>**  
 <span data-ttu-id="38086-139">Задает сведения, необходимые для соединения с базой данных, где размещается целевая служба.</span><span class="sxs-lookup"><span data-stu-id="38086-139">Specifies the information that is required to connect the database that holds the target service.</span></span> <span data-ttu-id="38086-140">Если параметры **toconnectionoptions** не указаны, то **ssbdiagnose** использует для подключения к целевой базе данных сведения о соединении из **baseconnectionoptions** .</span><span class="sxs-lookup"><span data-stu-id="38086-140">If **toconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions** to connect to the target database.</span></span>  
  
 <span data-ttu-id="38086-141">**MIRROR**</span><span class="sxs-lookup"><span data-stu-id="38086-141">**MIRROR**</span></span>  
 <span data-ttu-id="38086-142">Указывает, что связанная служба [!INCLUDE[ssSB](../../includes/sssb-md.md)] размещается в зеркальной базе данных.</span><span class="sxs-lookup"><span data-stu-id="38086-142">Specifies that the associated [!INCLUDE[ssSB](../../includes/sssb-md.md)] service is hosted in a mirrored database.</span></span> <span data-ttu-id="38086-143">Программа**ssbdiagnose** проверяет, является ли маршрут к службе зеркальным маршрутом, где в инструкции CREATE ROUTE был указан параметр MIRROR_ADDRESS.</span><span class="sxs-lookup"><span data-stu-id="38086-143">**ssbdiagnose** verifies that the route to the service is a mirrored route, where MIRROR_ADDRESS was specified on CREATE ROUTE.</span></span>  
  
 **\<mirrorconnectionoptions>**  
 <span data-ttu-id="38086-144">Позволяет задать сведения, необходимые для соединения с зеркальной базой данных.</span><span class="sxs-lookup"><span data-stu-id="38086-144">Specifies the information that is required to connect to the mirror database.</span></span> <span data-ttu-id="38086-145">Если параметры **mirrorconnectionoptions** не указаны, то **ssbdiagnose** использует для подключения к зеркальной базе данных сведения о соединении из **baseconnectionoptions** .</span><span class="sxs-lookup"><span data-stu-id="38086-145">If **mirrorconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions** to connect to the mirror database.</span></span>  
  
 <span data-ttu-id="38086-146">**ON CONTRACT** *имя_контракта*</span><span class="sxs-lookup"><span data-stu-id="38086-146">**ON CONTRACT** *contract_name*</span></span>  
 <span data-ttu-id="38086-147">Требует, чтобы программа **ssbdiagnose** проверила только те конфигурации, в которых используется указанный контракт.</span><span class="sxs-lookup"><span data-stu-id="38086-147">Requests that **ssbdiagnose** only check configurations that use the specified contract.</span></span> <span data-ttu-id="38086-148">Если параметр ON CONTRACT не указан, то программа **ssbdiagnose** работает с контрактом DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="38086-148">If ON CONTRACT is not specified, **ssbdiagnose** reports on the contract named DEFAULT.</span></span>  
  
 <span data-ttu-id="38086-149">**ENCRYPTION** { **ON** | **OFF** | **ANONYMOUS** }</span><span class="sxs-lookup"><span data-stu-id="38086-149">**ENCRYPTION** { **ON** | **OFF** | **ANONYMOUS** }</span></span>  
 <span data-ttu-id="38086-150">Запрашивает проверку правильности настройки диалога для заданного уровня шифрования.</span><span class="sxs-lookup"><span data-stu-id="38086-150">Requests verification that the dialog is correctly configured for the specified level of encryption:</span></span>  
  
 <span data-ttu-id="38086-151">**ON**: Параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="38086-151">**ON**: Default setting.</span></span> <span data-ttu-id="38086-152">Настраивается полная защита диалога.</span><span class="sxs-lookup"><span data-stu-id="38086-152">Full dialog security is configured.</span></span> <span data-ttu-id="38086-153">На обеих сторонах диалога производится развертывание сертификатов, присутствует привязка удаленной службы, а в инструкции GRANT SEND для целевой службы указывается вызывающий пользователь.</span><span class="sxs-lookup"><span data-stu-id="38086-153">Certificates have been deployed on both sides of the dialog, a remote service binding is present, and the GRANT SEND statement for the target service specified the initiator user.</span></span>  
  
 <span data-ttu-id="38086-154">**OFF**: защита диалога не настраивается.</span><span class="sxs-lookup"><span data-stu-id="38086-154">**OFF**: No dialog security is configured.</span></span> <span data-ttu-id="38086-155">Развертывание сертификатов не выполняется, привязка удаленной службы не была создана, и в инструкции GRANT SEND для службы инициатора была указана роль **public** .</span><span class="sxs-lookup"><span data-stu-id="38086-155">No certificates have been deployed, no remote service binding was created, and the GRANT SEND for the initiator service specified the **public** role.</span></span>  
  
 <span data-ttu-id="38086-156">**ANONYMOUS**: защита диалога для анонимной работы настраивается.</span><span class="sxs-lookup"><span data-stu-id="38086-156">**ANONYMOUS**: Anonymous dialog security is configured.</span></span> <span data-ttu-id="38086-157">Один сертификат развернут, привязка удаленной службы указала анонимное предложение, а в инструкции GRANT SEND для целевой службы была указана роль **public** .</span><span class="sxs-lookup"><span data-stu-id="38086-157">One certificate has been deployed, the remote service binding specified the anonymous clause, and the GRANT SEND for the target service specified the **public** role.</span></span>  
  
 <span data-ttu-id="38086-158">**RUNTIME**</span><span class="sxs-lookup"><span data-stu-id="38086-158">**RUNTIME**</span></span>  
 <span data-ttu-id="38086-159">Запрашивает отчет о проблемах, вызывающих ошибки времени выполнения в диалоге компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38086-159">Requests a report of issues that cause runtime errors for a [!INCLUDE[ssSB](../../includes/sssb-md.md)] conversation.</span></span> <span data-ttu-id="38086-160">Если не указан ни параметр **-NEW** , ни параметр **-ID** , то программа **ssbdiagnose** наблюдает за всеми диалогами во всех базах данных, указанных в параметрах соединения.</span><span class="sxs-lookup"><span data-stu-id="38086-160">If neither **-NEW** or **-ID** are specified, **ssbdiagnose** monitors all conversations in all databases specified in the connection options.</span></span> <span data-ttu-id="38086-161">Если указан параметр **-NEW** или **-ID** , то программа **ssbdiagnose** создает список идентификаторов, указанных в параметрах.</span><span class="sxs-lookup"><span data-stu-id="38086-161">If **-NEW** or **-ID** are specified, **ssbdiagnose** builds a list of the IDs specified in the parameters.</span></span>  
  
 <span data-ttu-id="38086-162">Во время работы программа **ssbdiagnose** записывает все события [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , которые указывают на ошибки времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="38086-162">While **ssbdiagnose** is running, it records all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] events that indicate runtime errors.</span></span> <span data-ttu-id="38086-163">Регистрируются события, происходящие для заданных идентификаторов, а также события системного уровня.</span><span class="sxs-lookup"><span data-stu-id="38086-163">It records the events that occur for the specified IDs, plus system-level events.</span></span> <span data-ttu-id="38086-164">При обнаружении ошибки времени выполнения программа **ssbdiagnose** запускает отчет по связанной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="38086-164">If runtime errors are encountered, **ssbdiagnose** runs a configuration report on the associated configuration.</span></span>  
  
 <span data-ttu-id="38086-165">По умолчанию в ошибки времени выполнения в выходной отчет не включаются. Отчет содержит только результаты анализа конфигурации.</span><span class="sxs-lookup"><span data-stu-id="38086-165">By default, runtime errors are not included in the output report, only the results of the configuration analysis.</span></span> <span data-ttu-id="38086-166">Чтобы включить в отчет ошибки времени выполнения, укажите параметр **-SHOWEVENTS** .</span><span class="sxs-lookup"><span data-stu-id="38086-166">Use **-SHOWEVENTS** to have the runtime errors included in the report.</span></span>  
  
 <span data-ttu-id="38086-167">**-SHOWEVENTS**</span><span class="sxs-lookup"><span data-stu-id="38086-167">**-SHOWEVENTS**</span></span>  
 <span data-ttu-id="38086-168">Указывает, что при создании отчета RUNTIME программа **ssbdiagnose** включает в него события [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38086-168">Specifies that **ssbdiagnose** report [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] events during a RUNTIME report.</span></span> <span data-ttu-id="38086-169">В отчет включаются только те события, которые считаются ошибками.</span><span class="sxs-lookup"><span data-stu-id="38086-169">Only events that are considered error conditions are reported.</span></span> <span data-ttu-id="38086-170">По умолчанию программа **ssbdiagnose** только наблюдает за событиями ошибок, но не включает их в выходной отчет.</span><span class="sxs-lookup"><span data-stu-id="38086-170">By default, **ssbdiagnose** only monitors error events; it does not report them in the output.</span></span>  
  
 <span data-ttu-id="38086-171">**-NEW**</span><span class="sxs-lookup"><span data-stu-id="38086-171">**-NEW**</span></span>  
 <span data-ttu-id="38086-172">Запрашивает наблюдение за первым диалогом, который запускается после начала работы программы **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="38086-172">Requests runtime monitoring of the first conversation that begins after **ssbdiagnose** starts running.</span></span>  
  
 <span data-ttu-id="38086-173">**-ID**</span><span class="sxs-lookup"><span data-stu-id="38086-173">**-ID**</span></span>  
 <span data-ttu-id="38086-174">Запрашивает мониторинг выполнения указанных элементов диалога.</span><span class="sxs-lookup"><span data-stu-id="38086-174">Requests runtime monitoring of the specified conversation elements.</span></span> <span data-ttu-id="38086-175">Параметр **-ID** можно указывать несколько раз.</span><span class="sxs-lookup"><span data-stu-id="38086-175">You can specify **-ID** multiple times.</span></span>  
  
 <span data-ttu-id="38086-176">Если указан дескриптор диалога, то в отчет будут включены только те события, которые связаны с соответствующей конечной точкой диалога.</span><span class="sxs-lookup"><span data-stu-id="38086-176">If you specify a conversation handle, only events associated with the associated conversation endpoint are reported.</span></span> <span data-ttu-id="38086-177">Если указан идентификатор диалога, то в отчет будут включены все события для этого диалога и его вызывающей и целевой конечных точек.</span><span class="sxs-lookup"><span data-stu-id="38086-177">If you specify a conversation ID, all events for that conversation and its initiator and target endpoints are reported.</span></span> <span data-ttu-id="38086-178">Если задан идентификатор группы сообщений, то в отчет будут включены все события для всех диалогов и конечных точек в этой группе сообщений.</span><span class="sxs-lookup"><span data-stu-id="38086-178">If a conversation group ID is specified, all events for all conversations and endpoints in the conversation group are reported.</span></span>  
  
 <span data-ttu-id="38086-179">*conversation_handle*</span><span class="sxs-lookup"><span data-stu-id="38086-179">*conversation_handle*</span></span>  
 <span data-ttu-id="38086-180">Уникальный идентификатор, определяющий конечную точку диалога в приложении.</span><span class="sxs-lookup"><span data-stu-id="38086-180">A unique identifier that identifies a conversation endpoint in an application.</span></span> <span data-ttu-id="38086-181">Дескрипторы диалога уникальны для одной конечной точки диалога. Вызывающая и целевая конечные точки имеют различные дескрипторы диалога.</span><span class="sxs-lookup"><span data-stu-id="38086-181">Conversation handles are unique to one endpoint of a conversation, the initiator and target endpoints have separate conversation handles.</span></span>  
  
 <span data-ttu-id="38086-182">Дескрипторы диалога возвращаются в приложения с помощью *@dialog_handle* параметра инструкции **BEGIN DIALOG** и `conversation_handle` столбца в результирующем наборе инструкции **Receive** .</span><span class="sxs-lookup"><span data-stu-id="38086-182">Conversation handles are returned to applications by the *@dialog_handle* parameter of the **BEGIN DIALOG** statement, and the `conversation_handle` column in the result set of a **RECEIVE** statement.</span></span>  
  
 <span data-ttu-id="38086-183">Дескрипторы диалога указываются в `conversation_handle` столбце представлений каталога **sys. transmission_queue** и **sys. conversation_endpoints** .</span><span class="sxs-lookup"><span data-stu-id="38086-183">Conversation handles are reported in the `conversation_handle` column of the **sys.transmission_queue** and **sys.conversation_endpoints** catalog views.</span></span>  
  
 <span data-ttu-id="38086-184">*conversation_group_id*</span><span class="sxs-lookup"><span data-stu-id="38086-184">*conversation_group_id*</span></span>  
 <span data-ttu-id="38086-185">Уникальный идентификатор, определяющий группу сообщений.</span><span class="sxs-lookup"><span data-stu-id="38086-185">The unique identifier that identifies a conversation group.</span></span>  
  
 <span data-ttu-id="38086-186">Идентификаторы групп сообщений возвращаются в приложения с помощью *@conversation_group_id* параметра инструкции **GET CONVERSATION GROUP** и `conversation_group_id` столбца в результирующем наборе инструкции **Receive** .</span><span class="sxs-lookup"><span data-stu-id="38086-186">Conversation group IDs are returned to applications by the *@conversation_group_id* parameter of the **GET CONVERSATION GROUP** statement and the `conversation_group_id` column in the result set of a **RECEIVE** statement.</span></span>  
  
 <span data-ttu-id="38086-187">Идентификаторы групп сообщений указываются в `conversation_group_id` столбцах представлений каталога **sys. conversation_groups** и **sys. conversation_endpoints** .</span><span class="sxs-lookup"><span data-stu-id="38086-187">Conversation group IDs are reported in the `conversation_group_id` columns of the **sys.conversation_groups** and **sys.conversation_endpoints** catalog views.</span></span>  
  
 <span data-ttu-id="38086-188">*conversation_id*</span><span class="sxs-lookup"><span data-stu-id="38086-188">*conversation_id*</span></span>  
 <span data-ttu-id="38086-189">Уникальный идентификатор, определяющий диалог.</span><span class="sxs-lookup"><span data-stu-id="38086-189">The unique identifier that identifies a conversation.</span></span> <span data-ttu-id="38086-190">Для вызывающей и целевой конечных точек диалога идентификаторы диалога совпадают.</span><span class="sxs-lookup"><span data-stu-id="38086-190">Conversation IDs are the same for both the initiator and target endpoints of a conversation.</span></span>  
  
 <span data-ttu-id="38086-191">Идентификаторы диалога указываются в `conversation_id` столбце представления каталога **sys. conversation_endpoints** .</span><span class="sxs-lookup"><span data-stu-id="38086-191">Conversation IDs are reported in the `conversation_id` column of the **sys.conversation_endpoints** catalog view.</span></span>  
  
 <span data-ttu-id="38086-192">**-TIMEOUT** *интервал_времени_ожидания*</span><span class="sxs-lookup"><span data-stu-id="38086-192">**-TIMEOUT** *timeout_interval*</span></span>  
 <span data-ttu-id="38086-193">Задает время выполнения отчета **RUNTIME** в секундах.</span><span class="sxs-lookup"><span data-stu-id="38086-193">Specifies the number of seconds for a **RUNTIME** report to run.</span></span> <span data-ttu-id="38086-194">Если параметр **-TIMEOUT** не задан, то отчет может выполняться бесконечно долго.</span><span class="sxs-lookup"><span data-stu-id="38086-194">If **-TIMEOUT** is not specified the runtime report runs indefinitely.</span></span> <span data-ttu-id="38086-195">Параметр **-TIMEOUT** используется только для отчетов **RUNTIME** , а не для отчетов **CONFIGURATION** .</span><span class="sxs-lookup"><span data-stu-id="38086-195">**-TIMEOUT** is used only on **RUNTIME** reports, not **CONFIGURATION** reports.</span></span> <span data-ttu-id="38086-196">Работу программы **ssbdiagnose** можно завершить нажатием клавиш CTRL+C, если параметр **-TIMEOUT** не указан, а также если нужно завершить отчет до истечения времени ожидания **-** .</span><span class="sxs-lookup"><span data-stu-id="38086-196">Use ctrl + C to quit **ssbdiagnose** if **-TIMEOUT** was not specified or to end a runtime report before the time**-** out interval expires.</span></span> <span data-ttu-id="38086-197">Параметр*timeout_interval* должен быть числом от 1 до 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="38086-197">*timeout_interval* must be a number between 1 and 2,147,483,647.</span></span>  
  
 **\<runtimeconnectionoptions>**  
 <span data-ttu-id="38086-198">Задает сведения для соединения с базой данных, где содержатся службы, связанные с отслеживаемыми элементами диалога.</span><span class="sxs-lookup"><span data-stu-id="38086-198">Specifies the connection information for the databases that contain the services associated with conversation elements being monitored.</span></span> <span data-ttu-id="38086-199">Если все службы расположены в одной базе данных, нужно указать только одно предложение **CONNECT TO** .</span><span class="sxs-lookup"><span data-stu-id="38086-199">If all the services are in the same database, you only have to specify one **CONNECT TO** clause.</span></span> <span data-ttu-id="38086-200">Если службы находятся в разных базах данных, то предложение **CONNECT TO** необходимо указать для каждой базы данных.</span><span class="sxs-lookup"><span data-stu-id="38086-200">If the services are in separate databases you must supply a **CONNECT TO** clause for each database.</span></span> <span data-ttu-id="38086-201">Если параметры **runtimeconnectionoptions** не указаны, то **ssbdiagnose** использует сведения о подключении из **baseconnectionoptions**.</span><span class="sxs-lookup"><span data-stu-id="38086-201">If **runtimeconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions**.</span></span>  
  
 <span data-ttu-id="38086-202">**-E**</span><span class="sxs-lookup"><span data-stu-id="38086-202">**-E**</span></span>  
 <span data-ttu-id="38086-203">Откройте соединение с экземпляром компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , использующее проверку подлинности Windows, указав текущую учетную запись Windows в качестве идентификатора входа.</span><span class="sxs-lookup"><span data-stu-id="38086-203">Open a Windows Authentication connection to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by using your current Windows account as the login ID.</span></span> <span data-ttu-id="38086-204">Имя входа должно быть членом предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="38086-204">The login must be a member of the **sysadmin** fixed-server role.</span></span>  
  
 <span data-ttu-id="38086-205">Параметр -E не учитывает имя пользователя и пароль, заданные в переменных среды SQLCMDUSER и SQLCMDPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="38086-205">The -E option ignores the user and password settings of the SQLCMDUSER and SQLCMDPASSWORD environment variables.</span></span>  
  
 <span data-ttu-id="38086-206">Если не указан ни параметр **-E** , ни параметр **-U** , то программа **ssbdiagnose** использует значение из переменной среды SQLCMDUSER.</span><span class="sxs-lookup"><span data-stu-id="38086-206">If neither **-E** nor **-U** is specified, **ssbdiagnose** uses the value from the SQLCMDUSER environment variable.</span></span> <span data-ttu-id="38086-207">Если переменная SQLCMDUSER также не задана, то программа **ssbdiagnose** использует проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="38086-207">If SQLCMDUSER is not set either, **ssbdiagnose** uses Windows Authentication.</span></span>  
  
 <span data-ttu-id="38086-208">Если параметр **-E** используется в сочетании с параметром **-U** или **-P** , выдается сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="38086-208">If the **-E** option is used together with the **-U** option or the **-P** option, an error message is generated.</span></span>  
  
 <span data-ttu-id="38086-209">**-U** *идентификатор_входа*</span><span class="sxs-lookup"><span data-stu-id="38086-209">**-U** *login_id*</span></span>  
 <span data-ttu-id="38086-210">Откройте соединение, использующее проверку подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , с помощью указанного идентификатора входа.</span><span class="sxs-lookup"><span data-stu-id="38086-210">Open a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication connection by using the specified login ID.</span></span> <span data-ttu-id="38086-211">Имя входа должно быть членом предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="38086-211">The login must be a member of the **sysadmin** fixed-server role.</span></span>  
  
 <span data-ttu-id="38086-212">Если не указан ни параметр **-E** , ни параметр **-U** , то программа **ssbdiagnose** использует значение из переменной среды SQLCMDUSER.</span><span class="sxs-lookup"><span data-stu-id="38086-212">If neither **-E** nor **-U** is specified, **ssbdiagnose** uses the value from the SQLCMDUSER environment variable.</span></span> <span data-ttu-id="38086-213">Если переменная SQLCMDUSER также не задана, то программа **ssbdiagnose** пытается установить соединение в режиме проверки подлинности Windows на основании учетных данных Windows пользователя, запустившего программу **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="38086-213">If SQLCMDUSER is not set either, **ssbdiagnose** tries to connect by using Windows Authentication mode based on the Windows account of the user who is running **ssbdiagnose**.</span></span>  
  
 <span data-ttu-id="38086-214">Если параметр **-U** указан одновременно с параметром **-E** , то выдается сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="38086-214">If the **-U** option is used together with the **-E** option, an error message is generated.</span></span> <span data-ttu-id="38086-215">Если после параметра **-U** указано более одного аргумента, выдается сообщение об ошибке и программа завершает работу.</span><span class="sxs-lookup"><span data-stu-id="38086-215">If the **-U** option is followed by more than one argument, an error message is generated and the program exits.</span></span>  
  
 <span data-ttu-id="38086-216">**-P** *пароль*</span><span class="sxs-lookup"><span data-stu-id="38086-216">**-P** *password*</span></span>  
 <span data-ttu-id="38086-217">Указывает пароль для идентификатора имени входа **-U** .</span><span class="sxs-lookup"><span data-stu-id="38086-217">Specifies the password for the **-U** login ID.</span></span> <span data-ttu-id="38086-218">Пароли учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="38086-218">Passwords are case sensitive.</span></span> <span data-ttu-id="38086-219">Если параметр **-U** указан, а параметр **-P** не указан, то программа **ssbdiagnose** использует значение из переменной среды SQLCMDPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="38086-219">If the **-U** option is used and the **-P** option is not used, **ssbdiagnose** uses the value from the SQLCMDPASSWORD environment variable.</span></span> <span data-ttu-id="38086-220">Если переменная SQLCMDPASSWORD также не задана, то программа **ssbdiagnose** запросит пароль у пользователя.</span><span class="sxs-lookup"><span data-stu-id="38086-220">If SQLCMDPASSWORD is not set either, **ssbdiagnose** prompts the user for a password.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="38086-221">Пароль, набираемый при вводе команды SET SQLCMDPASSWORD, будет отображаться на экране в открытом виде.</span><span class="sxs-lookup"><span data-stu-id="38086-221">When you type a SET SQLCMDPASSWORD command, your password will be visible to anyone who can see your monitor.</span></span>  
  
 <span data-ttu-id="38086-222">Если параметр **-P** задан, а пароль не указан, то программа **ssbdiagnose** использует пароль по умолчанию (NULL).</span><span class="sxs-lookup"><span data-stu-id="38086-222">If the **-P** option is specified without a password **ssbdiagnose** uses the default password (NULL).</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteStrongPass](../../includes/ssnotestrongpass-md.md)] <span data-ttu-id="38086-223">Дополнительные сведения см. в разделе [Надежные пароли](../../relational-databases/security/strong-passwords.md).</span><span class="sxs-lookup"><span data-stu-id="38086-223">For more information, see [Strong Passwords](../../relational-databases/security/strong-passwords.md).</span></span>  
  
 <span data-ttu-id="38086-224">Запрос на ввод пароля выводится на консоль следующим образом: `Password:`.</span><span class="sxs-lookup"><span data-stu-id="38086-224">The password prompt is displayed by printing the password prompt to the console, as follows: `Password:`</span></span>  
  
 <span data-ttu-id="38086-225">Вводимые пользователем данные на экране не отображаются,</span><span class="sxs-lookup"><span data-stu-id="38086-225">User input is hidden.</span></span> <span data-ttu-id="38086-226">то есть символы не выводятся и курсор остается на месте.</span><span class="sxs-lookup"><span data-stu-id="38086-226">This means that nothing is displayed and the cursor stays in position.</span></span>  
  
 <span data-ttu-id="38086-227">Если параметр **-P** указан одновременно с параметром **-E** , выдается сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="38086-227">If the **-P** option is used with the **-E** option, an error message is generated.</span></span>  
  
 <span data-ttu-id="38086-228">Если после параметра **-P** указано более одного аргумента, то выдается сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="38086-228">If the **-P** option is followed by more than one argument, an error message is generated.</span></span>  
  
 <span data-ttu-id="38086-229">**-S** *имя_сервера*[\\*имя\_экземпляра*]</span><span class="sxs-lookup"><span data-stu-id="38086-229">**-S** *server_name*[\\*instance_name*]</span></span>  
 <span data-ttu-id="38086-230">Задает экземпляр компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , где размещаются службы компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)] для анализа.</span><span class="sxs-lookup"><span data-stu-id="38086-230">Specifies the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that holds the [!INCLUDE[ssSB](../../includes/sssb-md.md)] services to be analyzed.</span></span>  
  
 <span data-ttu-id="38086-231">Укажите значение *server_name* , чтобы подключиться к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] по умолчанию на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="38086-231">Specify *server_name* to connect to the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on that server.</span></span> <span data-ttu-id="38086-232">Укажите *server_name ***\\*** instance_name* для подключения к именованному экземпляру объекта [!INCLUDE[ssDE](../../includes/ssde-md.md)] на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="38086-232">Specify *server_name***\\***instance_name* to connect to a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on that server.</span></span> <span data-ttu-id="38086-233">Если параметр **-S** не указан, то программа **ssbdiagnose** использует значение переменной среды SQLCMDSERVER.</span><span class="sxs-lookup"><span data-stu-id="38086-233">If **-S** is not specified, **ssbdiagnose** uses the value of the SQLCMDSERVER environment variable.</span></span> <span data-ttu-id="38086-234">Если переменная SQLCMDSERVER также не задана, то программа **ssbdiagnose** соединяется с экземпляром компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] по умолчанию на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="38086-234">If SQLCMDSERVER is not set either, **ssbdiagnose** connects to the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on the local computer.</span></span>  
  
 <span data-ttu-id="38086-235">**-d** *имя_базы_данных*</span><span class="sxs-lookup"><span data-stu-id="38086-235">**-d** *database_name*</span></span>  
 <span data-ttu-id="38086-236">Задает базу данных, где размещаются службы компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)] для анализа.</span><span class="sxs-lookup"><span data-stu-id="38086-236">Specifies the database that holds the [!INCLUDE[ssSB](../../includes/sssb-md.md)] services to be analyzed.</span></span> <span data-ttu-id="38086-237">Если такой базы данных не существует, то выдается ошибка.</span><span class="sxs-lookup"><span data-stu-id="38086-237">If the database does not exist, an error message is generated.</span></span> <span data-ttu-id="38086-238">Если параметр **-d** не задан, то по умолчанию используется база данных, указанная в свойстве default-database текущего имени входа.</span><span class="sxs-lookup"><span data-stu-id="38086-238">If **-d** is not specified, the default is the database specified in the default-database property for your login.</span></span>  
  
 <span data-ttu-id="38086-239">**-l** *время_ожидания_входа*</span><span class="sxs-lookup"><span data-stu-id="38086-239">**-l** *login_timeout*</span></span>  
 <span data-ttu-id="38086-240">Указывает время ожидания соединения с сервером (в секундах). Если параметр **-l** не задан, то программа **ssbdiagnose** использует значение из переменной среды SQLCMDLOGINTIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="38086-240">Specifies the number of seconds before an attempt to connect to a server times out. If **-l** is not specified, **ssbdiagnose** uses the value set for the SQLCMDLOGINTIMEOUT environment variable.</span></span> <span data-ttu-id="38086-241">Если переменная SQLCMDLOGINTIMEOUT также не задана, то время ожидания по умолчанию составляет тридцать секунд.</span><span class="sxs-lookup"><span data-stu-id="38086-241">If SQLCMDLOGINTIMEOUT is not set either, the default time-out is thirty seconds.</span></span> <span data-ttu-id="38086-242">Время ожидания входа должно быть числом в диапазоне от 0 до 65 534.</span><span class="sxs-lookup"><span data-stu-id="38086-242">The login time-out must be a number between 0 and 65534.</span></span> <span data-ttu-id="38086-243">Если указанное значение не является числом или выходит за пределы указанного диапазона, то программа **ssbdiagnose** выдаст сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="38086-243">If the value that is supplied is not numeric or does not fall into that range, **ssbdiagnose** generates an error message.</span></span> <span data-ttu-id="38086-244">Значение 0 задает неограниченное время ожидания.</span><span class="sxs-lookup"><span data-stu-id="38086-244">A value of 0 specifies time-out to be infinite.</span></span>  
  
 <span data-ttu-id="38086-245">**-?**</span><span class="sxs-lookup"><span data-stu-id="38086-245">**-?**</span></span>  
 <span data-ttu-id="38086-246">Отображает справку командной строки.</span><span class="sxs-lookup"><span data-stu-id="38086-246">Displays command line help.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38086-247">Remarks</span><span class="sxs-lookup"><span data-stu-id="38086-247">Remarks</span></span>  
 <span data-ttu-id="38086-248">Программа **ssbdiagnose** предназначена для выполнения следующих задач.</span><span class="sxs-lookup"><span data-stu-id="38086-248">Use **ssbdiagnose** to do the following:</span></span>  
  
-   <span data-ttu-id="38086-249">Проверка отсутствия ошибок конфигурации во вновь настроенном приложении компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38086-249">Confirm that there are no configuration errors in a newly configured [!INCLUDE[ssSB](../../includes/sssb-md.md)] application.</span></span>  
  
-   <span data-ttu-id="38086-250">Проверка отсутствия ошибок конфигурации после настройки существующего приложения компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38086-250">Confirm that there are no configuration errors after changing the configuration of an existing [!INCLUDE[ssSB](../../includes/sssb-md.md)] application.</span></span>  
  
-   <span data-ttu-id="38086-251">Проверка отсутствия ошибок конфигурации после отсоединения базы данных компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)] и дальнейшего присоединения к новому экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38086-251">Confirm that there are no configuration errors after a [!INCLUDE[ssSB](../../includes/sssb-md.md)] database is detached and then reattached to a new instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="38086-252">Выявление наличия ошибок конфигурации при возникновении неполадок при передаче сообщений между службами.</span><span class="sxs-lookup"><span data-stu-id="38086-252">Research whether there are configuration errors when messages are not successfully transmitted between services.</span></span>  
  
-   <span data-ttu-id="38086-253">Выдача сообщений об ошибках, возникающих в наборе элементов диалогов компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38086-253">Get a report of any errors that occur in a set of [!INCLUDE[ssSB](../../includes/sssb-md.md)] conversation elements.</span></span>  
  
## <a name="configuration-reporting"></a><span data-ttu-id="38086-254">Отчеты о конфигурации</span><span class="sxs-lookup"><span data-stu-id="38086-254">Configuration Reporting</span></span>  
 <span data-ttu-id="38086-255">Чтобы правильно проанализировать конфигурацию, используемую в диалоге, отчет о конфигурации в программе **ssbdiagnose** следует запускать с теми же параметрами, которые используются в диалоге.</span><span class="sxs-lookup"><span data-stu-id="38086-255">To correctly analyze the configuration used by a conversation, run a **ssbdiagnose** configuration report that uses the same options that are used by the conversation.</span></span> <span data-ttu-id="38086-256">Если в программе **ssbdiagnose** заданы параметры более низкого уровня, чем те, которые используются в диалоге, то программа **ssbdiagnose** может не зарегистрировать ошибки, которые могут возникнуть в диалоге.</span><span class="sxs-lookup"><span data-stu-id="38086-256">If you specify a lower level of options for **ssbdiagnose** than are used by the conversation, **ssbdiagnose** might not report conditions that are required by the conversation.</span></span> <span data-ttu-id="38086-257">Если же задать в программе **ssbdiagnose**параметры более высокого уровня, то она может обнаружить проблемы в ситуациях, которые никогда в диалоге не возникнут.</span><span class="sxs-lookup"><span data-stu-id="38086-257">If you specify a higher level of options for **ssbdiagnose**, it might report items that are not required by the conversation.</span></span> <span data-ttu-id="38086-258">Например, диалог между двумя службами, расположенными в одной базе данных, можно запустить с указанием параметра ENCRYPTION OFF.</span><span class="sxs-lookup"><span data-stu-id="38086-258">For example, a conversation between two services in the same database can be run with ENCPRYPTION OFF.</span></span> <span data-ttu-id="38086-259">Если запустить программу **ssbdiagnose** для проверки конфигурации диалога между этими двумя службами и указать значение по умолчанию ENCRYPTION ON, то программа **ssbdiagnose** сообщит об отсутствии главного ключа в базе данных,</span><span class="sxs-lookup"><span data-stu-id="38086-259">If you run **ssbdiagnose** to validate the configuration between the two services, but use the default ENCRYPTION ON setting, **ssbdiagnose** reports that the database is missing a master key.</span></span> <span data-ttu-id="38086-260">хотя для этого диалога главный ключ не нужен.</span><span class="sxs-lookup"><span data-stu-id="38086-260">A master key is not required for the conversation.</span></span>  
  
 <span data-ttu-id="38086-261">При каждом запуске программы **ssbdiagnose** для составления отчетов о конфигурации выполняется анализ либо одной службы, либо одной пары служб компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38086-261">The **ssbdiagnose** configuration report analyzes only one [!INCLUDE[ssSB](../../includes/sssb-md.md)] service or a single pair of services every time it is run.</span></span> <span data-ttu-id="38086-262">Чтобы создать отчет для нескольких пар служб компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)] , создайте командный CMD-файл, который будет вызывать программу **ssbdiagnose** несколько раз.</span><span class="sxs-lookup"><span data-stu-id="38086-262">To report on multiple pairs of [!INCLUDE[ssSB](../../includes/sssb-md.md)] services, build a .cmd command file that calls **ssbdiagnose** multiple times.</span></span>  
  
## <a name="runtime-reporting"></a><span data-ttu-id="38086-263">Отчеты времени выполнения</span><span class="sxs-lookup"><span data-stu-id="38086-263">Runtime Reporting</span></span>  
 <span data-ttu-id="38086-264">Если указан параметр -RUNTIME, программа **ssbdiagnose** выполняет поиск всех баз данных, указанных в **runtimeconnectionoptions** и **baseconnectionoptions** , для построения списка идентификаторов [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38086-264">When -RUNTIME is specified, **ssbdiagnose** searches all databases specified in **runtimeconnectionoptions** and **baseconnectionoptions** to build a list of [!INCLUDE[ssSB](../../includes/sssb-md.md)] IDs.</span></span> <span data-ttu-id="38086-265">Полное содержимое списка зависит от значений, заданных для параметров -NEW и -ID.</span><span class="sxs-lookup"><span data-stu-id="38086-265">The full list of IDs built depends on what is specified for -NEW and -ID:</span></span>  
  
-   <span data-ttu-id="38086-266">Если не указан ни параметр **-NEW** , ни параметр **-ID** , то в список будут включены все диалоги во всех базах данных, указанных в параметрах соединения.</span><span class="sxs-lookup"><span data-stu-id="38086-266">If neither **-NEW** or **-ID** are specified, the list includes all conversations for all databases specified in the connection options.</span></span>  
  
-   <span data-ttu-id="38086-267">Если указан параметр **-NEW** , то программа **ssbdiagnose** включает в список элементы для первого диалога, который начинается после запуска программы **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="38086-267">If **-NEW** is specified, **ssbdiagnose** includes the elements for the first conversation that starts after **ssbdiagnose** is run.</span></span> <span data-ttu-id="38086-268">К таким элементам относятся идентификатор диалога и дескрипторы диалога для вызывающей и целевой конечных точек диалога.</span><span class="sxs-lookup"><span data-stu-id="38086-268">This includes the conversation ID and the conversation handles for both the target and initiator conversation endpoints.</span></span>  
  
-   <span data-ttu-id="38086-269">Если параметр **-ID** указан с дескриптором диалога, то в список будет включен только этот дескриптор.</span><span class="sxs-lookup"><span data-stu-id="38086-269">If **-ID** is specified with a conversation handle, only that handle is included in the list.</span></span>  
  
-   <span data-ttu-id="38086-270">Если параметр **-ID** указан с идентификатором диалога, то в список будет добавлен этот идентификатор и дескрипторы для обеих конечных точек соответствующего диалога.</span><span class="sxs-lookup"><span data-stu-id="38086-270">If **-ID** is specified with a conversation ID, the conversation ID and the handles for both of its conversation endpoints are added to the list.</span></span>  
  
-   <span data-ttu-id="38086-271">Если параметр **-ID** указан с идентификатором группы диалогов, то в список будут добавлены все идентификаторы диалогов и все дескрипторы диалогов, входящих в эту группу.</span><span class="sxs-lookup"><span data-stu-id="38086-271">If **-ID** is specified with a conversation group ID, all the conversation IDs and conversation handles in that group are added to the list.</span></span>  
  
 <span data-ttu-id="38086-272">В список не включаются элементы, находящиеся в базах данных, которые не указаны в параметрах соединения.</span><span class="sxs-lookup"><span data-stu-id="38086-272">The list does not include elements from databases that are not covered by the connection options.</span></span> <span data-ttu-id="38086-273">Например, предположим, что в параметре **-ID** указан идентификатор диалога, а предложение **runtimeconnectionoptions** задано для базы данных инициатора и не задано для целевой базы данных.</span><span class="sxs-lookup"><span data-stu-id="38086-273">For example, assume that you use **-ID** to specify a conversation ID, but only provide a **runtimeconnectionoptions** clause for the initiator database and not the target database.</span></span> <span data-ttu-id="38086-274">Программа**ssbdiagnose** не включит дескриптор целевого диалога в свой список идентификаторов. В список будет включен только идентификатор диалога и дескриптор инициатора диалога.</span><span class="sxs-lookup"><span data-stu-id="38086-274">**ssbdiagnose** will not include the target conversation handle in its list of IDs, only the conversation ID and the initiator conversation handle.</span></span>  
  
 <span data-ttu-id="38086-275">Программа**ssbdiagnose** наблюдает за событиями [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] в базах данных, охватываемых **runtimeconnectionoptions** и **baseconnectionoptions**.</span><span class="sxs-lookup"><span data-stu-id="38086-275">**ssbdiagnose** monitors the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] events from the databases covered by **runtimeconnectionoptions** and **baseconnectionoptions**.</span></span> <span data-ttu-id="38086-276">Она выполняет поиск событий [!INCLUDE[ssSB](../../includes/sssb-md.md)] , указывающих на ошибку, обнаруженную одним или несколькими идентификаторами [!INCLUDE[ssSB](../../includes/sssb-md.md)] в списке времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="38086-276">It searches for [!INCLUDE[ssSB](../../includes/sssb-md.md)] events that indicate an error was encountered by one or more of the [!INCLUDE[ssSB](../../includes/sssb-md.md)] IDs in the runtime list.</span></span> <span data-ttu-id="38086-277">Программа **ssbdiagnose**, кроме того, выполняет поиск событий ошибок [!INCLUDE[ssSB](../../includes/sssb-md.md)] системного уровня, не связанных ни с одной из групп диалогов.</span><span class="sxs-lookup"><span data-stu-id="38086-277">**ssbdiagnose** also searches for system-level [!INCLUDE[ssSB](../../includes/sssb-md.md)] error events not specifically associated with any conversation group.</span></span>  
  
 <span data-ttu-id="38086-278">Если программа **ssbdiagnose** обнаружит ошибки диалога, то предпримет попытку выяснить их первопричину, запустив отчет о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="38086-278">If **ssbdiagnose** finds conversation errors, the utility will attempt to report on the root cause of the events by also running a configuration report.</span></span> <span data-ttu-id="38086-279">Программа**ssbdiagnose** на основе метаданных баз данных определяет, какие экземпляры, идентификаторы [!INCLUDE[ssSB](../../includes/sssb-md.md)] , базы данных, службы и контракты используются в диалоге.</span><span class="sxs-lookup"><span data-stu-id="38086-279">**ssbdiagnose** uses the metadata in the databases to try to determine the instances, [!INCLUDE[ssSB](../../includes/sssb-md.md)] IDs, databases, services, and contracts used by the conversation.</span></span> <span data-ttu-id="38086-280">Затем запускается отчет о конфигурации, учитывающий все доступные сведения.</span><span class="sxs-lookup"><span data-stu-id="38086-280">It then runs a configuration report using all available information.</span></span>  
  
 <span data-ttu-id="38086-281">По умолчанию программа **ssbdiagnose** не сообщает о событиях ошибок.</span><span class="sxs-lookup"><span data-stu-id="38086-281">By default, **ssbdiagnose** does not report error events.</span></span> <span data-ttu-id="38086-282">Она сообщает только об исходных проблемах, выявленных в процессе проверки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="38086-282">It only reports the underlying issues found during the configuration check.</span></span> <span data-ttu-id="38086-283">Это сокращает объем включаемых в отчет сведений и позволяет сосредоточить внимание на первопричинах возникновения проблем конфигурации.</span><span class="sxs-lookup"><span data-stu-id="38086-283">This minimizes the amount of information reported and helps you focus on the underlying configuration issues.</span></span> <span data-ttu-id="38086-284">Можно задать параметр **-SHOWEVENTS** , чтобы вывести обнаруженные программой **ssbdiagnose**события ошибок.</span><span class="sxs-lookup"><span data-stu-id="38086-284">You can specify **-SHOWEVENTS** to see the error events encountered by **ssbdiagnose**.</span></span>  
  
## <a name="issues-reported-by-ssbdiagnose"></a><span data-ttu-id="38086-285">Неполадки, о которых сообщает программа ssbdiagnose</span><span class="sxs-lookup"><span data-stu-id="38086-285">Issues Reported by ssbdiagnose</span></span>  
 <span data-ttu-id="38086-286">Программа**ssbdiagnose** включает в отчет неполадки трех типов.</span><span class="sxs-lookup"><span data-stu-id="38086-286">**ssbdiagnose** reports three classes of issues.</span></span> <span data-ttu-id="38086-287">Каждый класс неполадок включается в выходной XML-файл в виде отдельного элемента Issue.</span><span class="sxs-lookup"><span data-stu-id="38086-287">In the XML output file, each class of issue is reported as a separate type of the Issue element.</span></span> <span data-ttu-id="38086-288">Далее перечислены три типа неполадок, о которых сообщает программа **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="38086-288">The three types of issues reported by **ssbdiagnose** are as follows:</span></span>  
  
 <span data-ttu-id="38086-289">**Diagnosis**</span><span class="sxs-lookup"><span data-stu-id="38086-289">**Diagnosis**</span></span>  
 <span data-ttu-id="38086-290">Указывает на проблемы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="38086-290">Reports a configuration issue.</span></span> <span data-ttu-id="38086-291">К ним относятся проблемы, обнаруженные во время выполнения отчета **CONFIGURATION** или во время этапа конфигурации отчета **RUNTIME** .</span><span class="sxs-lookup"><span data-stu-id="38086-291">This includes issues found either a **CONFIGURATION** report is running, or during the configuration phase of a **RUNTIME** report.</span></span> <span data-ttu-id="38086-292">Программа**ssbdiagnose** сообщает о каждой проблеме конфигурации один раз.</span><span class="sxs-lookup"><span data-stu-id="38086-292">**ssbdiagnose** reports each configuration issue one time.</span></span>  
  
 <span data-ttu-id="38086-293">**Событие**</span><span class="sxs-lookup"><span data-stu-id="38086-293">**Event**</span></span>  
 <span data-ttu-id="38086-294">Сообщает о событии [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , сигнализирующем о проблеме, обнаруженной в диалоге, который отслеживается отчетом **RUNTIME** .</span><span class="sxs-lookup"><span data-stu-id="38086-294">Reports a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] event that indicates a problem was encountered by a conversation being monitored during a **RUNTIME** report.</span></span> <span data-ttu-id="38086-295">Программа**ssbdiagnose** сообщает о каждом случае создания таких событий.</span><span class="sxs-lookup"><span data-stu-id="38086-295">**ssbdiagnose** reports events every time they are generated.</span></span> <span data-ttu-id="38086-296">Если проблема обнаружена в нескольких диалогах, то событие может быть включено в отчет многократно.</span><span class="sxs-lookup"><span data-stu-id="38086-296">Events can be reported multiple times if several conversations encounter the problem.</span></span>  
  
 <span data-ttu-id="38086-297">**Проблема.**</span><span class="sxs-lookup"><span data-stu-id="38086-297">**Problem**</span></span>  
 <span data-ttu-id="38086-298">Сообщает о проблеме, из-за которой программа **ssbdiagnose** не имеет возможности выполнять анализ конфигурации или мониторинг диалогов.</span><span class="sxs-lookup"><span data-stu-id="38086-298">Reports an issue that is preventing **ssbdiagnose** from completing a configuration analysis or from monitoring conversations.</span></span>  
  
## <a name="sqlcmd-environment-variables"></a><span data-ttu-id="38086-299">Переменные среды sqlcmd</span><span class="sxs-lookup"><span data-stu-id="38086-299">sqlcmd Environment Variables</span></span>  
 <span data-ttu-id="38086-300">Программа **ssbdiagnose** поддерживает переменные среды SQLCMDSERVER, SQLCMDUSER, SQLCMDPASSWORD и SQLCMDLOGINTIMEOUT, которые также используются программой **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="38086-300">The **ssbdiagnose** utility supports the SQLCMDSERVER, SQLCMDUSER, SQLCMDPASSWORD, and SQLCMDLOGINTIMOUT environment variables that are also used by the **sqlcmd** utility.</span></span> <span data-ttu-id="38086-301">Они могут быть заданы при помощи команды командной строки SET или команды **setvar** в скриптах [!INCLUDE[tsql](../../includes/tsql-md.md)] , которые выполняются программой **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="38086-301">You can set the environment variables either by using the command prompt SET command, or by using the **setvar** command in [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts that you run by using **sqlcmd**.</span></span> <span data-ttu-id="38086-302">Дополнительные сведения об использовании **setvar** в **sqlcmd**см. в разделе [Использование программы sqlcmd с переменными скрипта](../../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md).</span><span class="sxs-lookup"><span data-stu-id="38086-302">For more information about how to use **setvar** in **sqlcmd**, see [Use sqlcmd with Scripting Variables](../../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="38086-303">Разрешения</span><span class="sxs-lookup"><span data-stu-id="38086-303">Permissions</span></span>  
 <span data-ttu-id="38086-304">В каждом предложении **connectionoptions** имя входа, указанное в параметре **-E** или **-U** , должно быть членом предопределенной роли сервера **sysadmin** для экземпляра, указанного в параметре **-S**.</span><span class="sxs-lookup"><span data-stu-id="38086-304">In each **connectionoptions** clause, the login specified with either **-E** or **-U** must be a member of the **sysadmin** fixed-server role in the instance specified in **-S**.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="38086-305">Примеры</span><span class="sxs-lookup"><span data-stu-id="38086-305">Examples</span></span>  
 <span data-ttu-id="38086-306">В этом разделе приведены примеры использования программы **ssbdiagnose** в командной строке.</span><span class="sxs-lookup"><span data-stu-id="38086-306">This section contains examples of using **ssbdiagnose** at a command prompt.</span></span>  
  
### <a name="a-checking-the-configuration-of-two-services-in-the-same-database"></a><span data-ttu-id="38086-307">A.</span><span class="sxs-lookup"><span data-stu-id="38086-307">A.</span></span> <span data-ttu-id="38086-308">Проверка конфигурации двух служб, расположенных в одной базе данных</span><span class="sxs-lookup"><span data-stu-id="38086-308">Checking the Configuration of Two Services in the Same Database</span></span>  
 <span data-ttu-id="38086-309">В этом примере показано, как запросить отчет о конфигурации, если выполняются следующие условия.</span><span class="sxs-lookup"><span data-stu-id="38086-309">The following example shows how to request a configuration report when the following are true;</span></span>  
  
-   <span data-ttu-id="38086-310">Вызывающая и целевая службы размещаются в одной базе данных.</span><span class="sxs-lookup"><span data-stu-id="38086-310">The initiator and target service are in the same database.</span></span>  
  
-   <span data-ttu-id="38086-311">База данных размещена в экземпляре компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)]по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="38086-311">The database is in the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="38086-312">Экземпляры расположены на том же компьютере, на котором работает программа **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="38086-312">The instances is on the same computer on which **ssbdiagnose** is run.</span></span>  
  
 <span data-ttu-id="38086-313">Программа **ssbdiagnose** строит отчет по конфигурации, использующей контракт DEFAULT, поскольку не указано предложение ON CONTRACT.</span><span class="sxs-lookup"><span data-stu-id="38086-313">The **ssbdiagnose** utility reports the configuration that uses the DEFAULT contract because ON CONTRACT is not specified.</span></span>  
  
```  
ssbdiagnose -E -d MyDatabase CONFIGURATION FROM SERVICE /test/initiator TO SERVICE /test/target  
```  
  
### <a name="b-checking-the-configuration-of-two-services-on-separate-computers-that-use-one-login"></a><span data-ttu-id="38086-314">Б.</span><span class="sxs-lookup"><span data-stu-id="38086-314">B.</span></span> <span data-ttu-id="38086-315">Проверка конфигурации двух служб, расположенных на разных компьютерах, использующих одно имя входа</span><span class="sxs-lookup"><span data-stu-id="38086-315">Checking the Configuration of Two Services on Separate Computers That Use One Login</span></span>  
 <span data-ttu-id="38086-316">В следующем примере показано, как запросить отчет о конфигурации в том случае, если вызывающая и целевая службы расположены на разных компьютерах, но к ним возможен доступ с помощью одного имени входа, проходящего проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="38086-316">The following example shows how to request a configuration report when the initiator and target service are on separate computers, but can be accessed by using the same Windows Authentication login.</span></span>  
  
```  
ssbdiagnose -E CONFIGURATION FROM SERVICE /text/initiator -S InitiatorComputer -d InitiatorDatabase TO SERVICE /test/target -S TargetComputer -d TargetDatabase ON CONTRACT TestContract  
```  
  
### <a name="c-checking-the-configuration-of-two-services-on-separate-computers-that-use-separate-logins"></a><span data-ttu-id="38086-317">В.</span><span class="sxs-lookup"><span data-stu-id="38086-317">C.</span></span> <span data-ttu-id="38086-318">Проверка конфигурации двух служб, расположенных на разных компьютерах, использующих различные имена входа</span><span class="sxs-lookup"><span data-stu-id="38086-318">Checking the Configuration of Two Services on Separate Computers That Use Separate Logins</span></span>  
 <span data-ttu-id="38086-319">В следующем примере показано, как запросить отчет о конфигурации в том случае, когда вызывающая и целевая службы расположены на разных компьютерах и каждому из экземпляров компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] необходимо собственное имя входа для проверки подлинности [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38086-319">The following example shows how to request a configuration report when the initiator and target service are on separate computers, and separate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication logins are required for each instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
```  
ssbdiagnose CONFIGURATION FROM SERVICE /text/initiator   
-S InitiatorComputer -U InitiatorLogin -p !wEx23Dvb   
-d InitiatorDatabase TO SERVICE /test/target -S TargetComputer   
-U TargetLogin -p ER!49jiy -d TargetDatabase ON CONTRACT TestContract  
```  
  
### <a name="d-checking-mirrored-service-configurations-on-separate-computers-with-anonymous-encryption"></a><span data-ttu-id="38086-320">Г.</span><span class="sxs-lookup"><span data-stu-id="38086-320">D.</span></span> <span data-ttu-id="38086-321">Проверка конфигурации для нескольких компьютеров, в которой участвует зеркальная служба и используется анонимное шифрование</span><span class="sxs-lookup"><span data-stu-id="38086-321">Checking Mirrored Service Configurations on Separate Computers With Anonymous Encryption</span></span>  
 <span data-ttu-id="38086-322">В следующем примере показано, как запросить отчет о конфигурации в том случае, когда вызывающая и целевая службы расположены на разных компьютерах, а для вызывающей службы существует зеркальная копия на именованном экземпляре.</span><span class="sxs-lookup"><span data-stu-id="38086-322">The following example shows how to request a configuration report when the initiator and target service are on separate computers and the initiator is mirrored to a named instance.</span></span> <span data-ttu-id="38086-323">В ходе отчета также проверяется, что службы настроены для использования анонимного шифрования.</span><span class="sxs-lookup"><span data-stu-id="38086-323">The report also verifies that the services are configured to use anonymous encryption.</span></span>  
  
```  
ssbdiagnose -E CONFIGURATION FROM SERVICE /text/initiator   
-S InitiatorComputer -d InitiatorDatabase MIRROR   
-S MirrorComputer/MirrorInstance TO SERVICE /test/target   
-S TargetComputer -d TargetDatabase ON CONTRACT TestContract ENCRYPTION ANONYMOUS  
```  
  
### <a name="e-checking-the-configuration-of-two-contracts"></a><span data-ttu-id="38086-324">Д.</span><span class="sxs-lookup"><span data-stu-id="38086-324">E.</span></span> <span data-ttu-id="38086-325">Проверка конфигурации двух контрактов</span><span class="sxs-lookup"><span data-stu-id="38086-325">Checking the Configuration of Two Contracts</span></span>  
 <span data-ttu-id="38086-326">В этом примере показано, как построить командный файл, запрашивающий отчет о конфигурации, если выполняются следующие условия.</span><span class="sxs-lookup"><span data-stu-id="38086-326">The following example shows how to build a command file that requests configuration reports when the following are true:</span></span>  
  
-   <span data-ttu-id="38086-327">Вызывающая и целевая службы размещаются в одной базе данных.</span><span class="sxs-lookup"><span data-stu-id="38086-327">The initiator and target service are in the same database.</span></span>  
  
-   <span data-ttu-id="38086-328">База данных размещена в экземпляре компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)]по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="38086-328">The database is in the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="38086-329">Экземпляр расположен на том же компьютере, на котором работает программа **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="38086-329">The instance is on the same computer on which **ssbdiagnose** is run.</span></span>  
  
 <span data-ttu-id="38086-330">При каждом запуске программы **ssbdiagnose** она формирует отчет по конфигурации отдельного контракта, действующего между одними и теми же службами.</span><span class="sxs-lookup"><span data-stu-id="38086-330">Each time **ssbdiagnose** is run it reports the configuration for a different contract between the same services.</span></span>  
  
```  
ssbdiagnose -E -d MyDatabase CONFIGURATION FROM SERVICE   
/test/initiator TO SERVICE /test/target ON CONTRACT PayRaiseContract  
ssbdiagnose -E -d MyDatabase CONFIGURATION FROM SERVICE /test/initiator   
TO SERVICE /test/target ON CONTRACT PromotionContract  
```  
  
### <a name="f-monitor-the-status-of-a-specific-conversation-on-the-local-computer-with-a-time-out"></a><span data-ttu-id="38086-331">Е.</span><span class="sxs-lookup"><span data-stu-id="38086-331">F.</span></span> <span data-ttu-id="38086-332">Наблюдение за состоянием отдельного диалога на локальном компьютере с ограниченным временем ожидания</span><span class="sxs-lookup"><span data-stu-id="38086-332">Monitor the status of a specific conversation on the local computer with a time out</span></span>  
 <span data-ttu-id="38086-333">В следующем примере показано, как запустить наблюдение за отдельным диалогом, где вызывающая и целевая службы расположены в одной базе данных на экземпляре по умолчанию, который работает на том же компьютере, где запускается программа **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="38086-333">The following example shows how to monitor a specific conversation where the initiator and target services are in the same database in the default instance of the same computer that is running **ssbdiagnose**.</span></span> <span data-ttu-id="38086-334">Время ожидания устанавливается в значение 20 секунд.</span><span class="sxs-lookup"><span data-stu-id="38086-334">The time-out interval is set to 20 seconds.</span></span>  
  
```  
ssbdiagnose -E -d TestDatabase RUNTIME -ID D68D77A9-B1CF-41BF-A5CE-279ABCAB140D -TIMEOUT 20  
```  
  
### <a name="g-monitor-the-status-of-a-conversation-that-spans-two-computers"></a><span data-ttu-id="38086-335">Ж.</span><span class="sxs-lookup"><span data-stu-id="38086-335">G.</span></span> <span data-ttu-id="38086-336">Наблюдение за состоянием диалога, в котором участвуют два компьютера</span><span class="sxs-lookup"><span data-stu-id="38086-336">Monitor the status of a conversation that spans two computers</span></span>  
 <span data-ttu-id="38086-337">В следующем примере показано, как запустить наблюдение за отдельным диалогом, где вызывающая и целевая службы расположены на разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="38086-337">The following example shows how to monitor a specific conversation where the initiator and target services are on separate computers.</span></span>  
  
```  
ssbdiagnose RUNTIME -ID D68D77A9-B1CF-41BF-A5CE-279ABCAB140D   
-TIMEOUT 10 CONNECT TO -E -S InitiatorComputer/InitiatorInstance   
-d InitiatorDatabase CONNECT TO -E -S TargetComputer/TargetInstance   
-d TargetDatabase  
```  
  
### <a name="h-monitor-the-status-of-a-conversation-in-two-databases-in-the-same-instance"></a><span data-ttu-id="38086-338">З.</span><span class="sxs-lookup"><span data-stu-id="38086-338">H.</span></span> <span data-ttu-id="38086-339">Наблюдение за состоянием диалога, в котором участвуют две базы данных, расположенные в одном экземпляре</span><span class="sxs-lookup"><span data-stu-id="38086-339">Monitor the status of a conversation in two databases in the same instance</span></span>  
 <span data-ttu-id="38086-340">В следующем примере показано, как запустить наблюдение за отдельным диалогом, где вызывающая и целевая службы находятся в разных базах данных, размещенных в одном экземпляре компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38086-340">The following example shows how to monitor a specific conversation where the initiator and target services are in separate databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="38086-341">В этом примере параметр **baseconnectionoptions** указывает сведения об экземпляре и данные входа, а два предложения CONNECT TO указывают базы данных.</span><span class="sxs-lookup"><span data-stu-id="38086-341">The example uses the **baseconnectionoptions** to specify the instance and login information, and two CONNECT TO clauses to specify the databases.</span></span> <span data-ttu-id="38086-342">Кроме того, указан параметр -SHOWEVENTS, согласно которому в отчет включаются все события времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="38086-342">-SHOWEVENTS is specified so that all runtime events are included in the report output.</span></span>  
  
```  
ssbdiagnose -E -S TestComputer/DevTestInstance RUNTIME -SHOWEVENTS   
-ID 5094d4a7-e38c-4c37-da37-1d58b1cb8455 -TIMEOUT 10 CONNECT TO   
-d InitiatorDatabase CONNECT TO -d TargetDatabase  
```  
  
### <a name="i-monitor-the-status-of-two-conversations-between-two-databases"></a><span data-ttu-id="38086-343">И.</span><span class="sxs-lookup"><span data-stu-id="38086-343">I.</span></span> <span data-ttu-id="38086-344">Наблюдение за состоянием двух диалогов между двумя базами данных</span><span class="sxs-lookup"><span data-stu-id="38086-344">Monitor the status of two conversations between two databases</span></span>  
 <span data-ttu-id="38086-345">В следующем примере показано, как запустить наблюдение за двумя диалогами, где вызывающая и целевая службы находятся в разных базах данных, размещенных в одном экземпляре компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38086-345">The following example shows how to monitor two conversations where the initiator and target services are in separate databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="38086-346">В этом примере параметр **baseconnectionoptions** указывает сведения об экземпляре и данные входа, а два предложения CONNECT TO указывают базы данных.</span><span class="sxs-lookup"><span data-stu-id="38086-346">The example uses the **baseconnectionoptions** to specify the instance and login information, and two CONNECT TO clauses to specify the databases.</span></span>  
  
```  
ssbdiagnose -E -S TestComputer/DevTestInstance RUNTIME   
-ID 5094d4a7-e38c-4c37-da37-1d58b1cb8455   
-ID 9b293be9-226b-4e22-e169-1d2c2c15be86 -TIMEOUT 10 CONNECT TO   
-d InitiatorDatabase CONNECT TO -d TargetDatabase  
```  
  
### <a name="j-monitor-the-status-of-all-conversations-between-two-databases"></a><span data-ttu-id="38086-347">К.</span><span class="sxs-lookup"><span data-stu-id="38086-347">J.</span></span> <span data-ttu-id="38086-348">Наблюдение за состоянием всех диалогов между двумя базами данных</span><span class="sxs-lookup"><span data-stu-id="38086-348">Monitor the status of all conversations between two databases</span></span>  
 <span data-ttu-id="38086-349">В следующем примере показано, как запустить наблюдение за всеми диалогами между двумя базами данных, расположенными в одном экземпляре компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38086-349">The following example shows how to monitor all the conversation between two databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="38086-350">В этом примере параметр **baseconnectionoptions** указывает сведения об экземпляре и данные входа, а два предложения CONNECT TO указывают базы данных.</span><span class="sxs-lookup"><span data-stu-id="38086-350">The example uses the **baseconnectionoptions** to specify the instance and login information, and two CONNECT TO clauses to specify the databases.</span></span>  
  
```  
ssbdiagnose -E -S TestComputer/DevTestInstance RUNTIME   
-TIMEOUT 10 CONNECT TO -d InitiatorDatabase CONNECT TO   
-d TargetDatabase  
```  
  
### <a name="k-ignore-specific-errors"></a><span data-ttu-id="38086-351">Л.</span><span class="sxs-lookup"><span data-stu-id="38086-351">K.</span></span> <span data-ttu-id="38086-352">Пропуск отдельных ошибок</span><span class="sxs-lookup"><span data-stu-id="38086-352">Ignore Specific Errors</span></span>  
 <span data-ttu-id="38086-353">В следующем примере показано, как пропустить обработку известных ошибок (303 и 304) в конфигурации активации, используемой в тестовой системе.</span><span class="sxs-lookup"><span data-stu-id="38086-353">The following example shows how to ignore known errors (303 and 304) in how activation is currently configured in a test system.</span></span>  
  
```  
ssbdiagnose -IGNORE 303 -IGNORE 304 -E -d TestDatabase   
CONFIGURATION FROM SERVICE /test/initiator TO SERVICE /test/target   
ON CONTRACT TextContract  
```  
  
### <a name="l-redirecting-ssbdiagnose-xml-output"></a><span data-ttu-id="38086-354">М.</span><span class="sxs-lookup"><span data-stu-id="38086-354">L.</span></span> <span data-ttu-id="38086-355">Перенаправление вывода XML программы ssbdiagnose</span><span class="sxs-lookup"><span data-stu-id="38086-355">Redirecting ssbdiagnose XML Output</span></span>  
 <span data-ttu-id="38086-356">В следующем примере показано, как запросить формирование программой **ssbdiagnose** выходного XML-файла, который перенаправляется в файл.</span><span class="sxs-lookup"><span data-stu-id="38086-356">The following example shows how to request that **ssbdiagnose** generate its output as an XML file that is redirected to a file.</span></span> <span data-ttu-id="38086-357">Далее файл TestDiag.xml можно открыть в приложении, предназначенном для анализа XML-файлов программы **ssbdiagnose** или создания по ним отчетов.</span><span class="sxs-lookup"><span data-stu-id="38086-357">The TestDiag.xml file can then be opened by an application to analyze or report **ssbdiagnose** XML files.</span></span> <span data-ttu-id="38086-358">Кроме того, этот файл можно просмотреть в редакторе XML общего назначения, например в XML-блокноте.</span><span class="sxs-lookup"><span data-stu-id="38086-358">Or, you can view it from a general XML editor such as XML Notepad.</span></span>  
  
```  
ssbdiagnose -XML -E -d MyDatabase CONFIGURATION FROM SERVICE   
/test/initiator TO SERVICE /test/target > c:\MyDiagnostics\TestDiag.xml  
```  
  
### <a name="m-using-an-environment-variable"></a><span data-ttu-id="38086-359">Н.</span><span class="sxs-lookup"><span data-stu-id="38086-359">M.</span></span> <span data-ttu-id="38086-360">Использование переменной среды</span><span class="sxs-lookup"><span data-stu-id="38086-360">Using an Environment Variable</span></span>  
 <span data-ttu-id="38086-361">В приведенном ниже примере сначала устанавливается переменная среды SQLCMDSERVER, в которой хранится имя сервера, а затем запускается программа **ssbdiagnose** без указания параметра **-S**.</span><span class="sxs-lookup"><span data-stu-id="38086-361">The following example first sets the SQLCMDSERVER environment variable to hold the server name, and then runs **ssbdiagnose** without specifying **-S**.</span></span>  
  
```  
SET SQLCMDSERVER=MyComputer  
ssbdiagnose -XML -E -d MyDatabase CONFIGURATION FROM SERVICE   
/test/initiator TO SERVICE /test/target  
```  
  
## <a name="see-also"></a><span data-ttu-id="38086-362">См. также:</span><span class="sxs-lookup"><span data-stu-id="38086-362">See Also</span></span>  
 <span data-ttu-id="38086-363">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span><span class="sxs-lookup"><span data-stu-id="38086-363">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span></span>  
 <span data-ttu-id="38086-364">[BEGIN DIALOG CONVERSATION (Transact-SQL)](/sql/t-sql/statements/begin-dialog-conversation-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="38086-364">[BEGIN DIALOG CONVERSATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/begin-dialog-conversation-transact-sql) </span></span>  
 <span data-ttu-id="38086-365">[CREATE BROKER PRIORITY (Transact-SQL)](/sql/t-sql/statements/create-broker-priority-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="38086-365">[CREATE BROKER PRIORITY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-broker-priority-transact-sql) </span></span>  
 <span data-ttu-id="38086-366">[CREATE CERTIFICATE (Transact-SQL)](/sql/t-sql/statements/create-certificate-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="38086-366">[CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql) </span></span>  
 <span data-ttu-id="38086-367">[CREATE CONTRACT (Transact-SQL)](/sql/t-sql/statements/create-contract-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="38086-367">[CREATE CONTRACT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-contract-transact-sql) </span></span>  
 <span data-ttu-id="38086-368">[CREATE ENDPOINT (Transact-SQL)](/sql/t-sql/statements/create-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="38086-368">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="38086-369">[CREATE MASTER KEY (Transact-SQL)](/sql/t-sql/statements/create-master-key-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="38086-369">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span></span>  
 <span data-ttu-id="38086-370">[CREATE MESSAGE TYPE (Transact-SQL)](/sql/t-sql/statements/create-message-type-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="38086-370">[CREATE MESSAGE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-message-type-transact-sql) </span></span>  
 <span data-ttu-id="38086-371">[CREATE QUEUE (Transact-SQL)](/sql/t-sql/statements/create-queue-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="38086-371">[CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) </span></span>  
 <span data-ttu-id="38086-372">[CREATE REMOTE SERVICE BINDING (Transact-SQL)](/sql/t-sql/statements/create-remote-service-binding-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="38086-372">[CREATE REMOTE SERVICE BINDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-remote-service-binding-transact-sql) </span></span>  
 <span data-ttu-id="38086-373">[CREATE ROUTE (Transact-SQL)](/sql/t-sql/statements/create-route-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="38086-373">[CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql) </span></span>  
 <span data-ttu-id="38086-374">[CREATE SERVICE (Transact-SQL)](/sql/t-sql/statements/create-service-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="38086-374">[CREATE SERVICE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-service-transact-sql) </span></span>  
 <span data-ttu-id="38086-375">[RECEIVE (Transact-SQL)](/sql/t-sql/statements/receive-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="38086-375">[RECEIVE &#40;Transact-SQL&#41;](/sql/t-sql/statements/receive-transact-sql) </span></span>  
 <span data-ttu-id="38086-376">[sys.transmission_queue (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-transmission-queue-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="38086-376">[sys.transmission_queue &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-transmission-queue-transact-sql) </span></span>  
 <span data-ttu-id="38086-377">[sys.conversation_endpoints (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-conversation-endpoints-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="38086-377">[sys.conversation_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-conversation-endpoints-transact-sql) </span></span>  
 [<span data-ttu-id="38086-378">sys.conversation_groups (Transact-SQ)</span><span class="sxs-lookup"><span data-stu-id="38086-378">sys.conversation_groups &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-conversation-groups-transact-sql)  
  
  
