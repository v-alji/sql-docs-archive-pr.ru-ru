---
title: Параметр конфигурации сервера "c2 audit mode" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- audits [SQL Server], C2 Audit Mode option
- C2 auditing
- C2 Audit Mode option
- recording attempts
ms.assetid: 5a8d73a6-c4f6-4967-ba11-ecbcfc90b9cc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3407a2a94a43adb2d3d3b52994093d6ed0c2e684
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740436"
---
# <a name="c2-audit-mode-server-configuration-option"></a><span data-ttu-id="efbd7-102">Параметр конфигурации сервера «c2 audit mode»</span><span class="sxs-lookup"><span data-stu-id="efbd7-102">c2 audit mode Server Configuration Option</span></span>
  <span data-ttu-id="efbd7-103">Режим аудита C2 можно настроить с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или параметра **c2 audit mode** в **sp_configure**.</span><span class="sxs-lookup"><span data-stu-id="efbd7-103">C2 audit mode can be configured through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or with the **c2 audit mode** option in **sp_configure**.</span></span> <span data-ttu-id="efbd7-104">Включение этого параметра заставляет сервер регистрировать как успешные, так и неуспешные попытки получения доступа к инструкциям и объектам.</span><span class="sxs-lookup"><span data-stu-id="efbd7-104">Selecting this option will configure the server to record both failed and successful attempts to access statements and objects.</span></span> <span data-ttu-id="efbd7-105">Эти сведения позволяют профилировать работу системы и отслеживать возможные нарушения политики безопасности.</span><span class="sxs-lookup"><span data-stu-id="efbd7-105">This information can help you profile system activity and track possible security policy violations.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="efbd7-106">Стандарт безопасности С2 был заменен стандартом Common Criteria Certification.</span><span class="sxs-lookup"><span data-stu-id="efbd7-106">The C2 security standard has been superseded by Common Criteria Certification.</span></span> <span data-ttu-id="efbd7-107">См. [Параметр конфигурации сервера common criteria compliance enabled](common-criteria-compliance-enabled-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="efbd7-107">See the [common criteria compliance enabled Server Configuration Option](common-criteria-compliance-enabled-server-configuration-option.md).</span></span>  
  
## <a name="audit-log-file"></a><span data-ttu-id="efbd7-108">Файл журнала аудита</span><span class="sxs-lookup"><span data-stu-id="efbd7-108">Audit Log File</span></span>  
 <span data-ttu-id="efbd7-109">Файл данных режима аудита С2 сохраняется в каталоге данных по умолчанию для экземпляра.</span><span class="sxs-lookup"><span data-stu-id="efbd7-109">C2 audit mode data is saved in a file in the default data directory of the instance.</span></span> <span data-ttu-id="efbd7-110">Если размер файла журнала аудита превышает максимально допустимый предел в 200 мегабайт, в версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] он закрывается, создается новый файл, и все новые записи аудита записываются в новый файл.</span><span class="sxs-lookup"><span data-stu-id="efbd7-110">If the audit log file reaches its size limit of 200 megabytes (MB), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will create a new file, close the old file, and write all new audit records to the new file.</span></span> <span data-ttu-id="efbd7-111">Этот процесс продолжается до тех пор, пока не заполнится каталог данных аудита или аудит не будет отключен.</span><span class="sxs-lookup"><span data-stu-id="efbd7-111">This process will continue until the audit data directory fills up or auditing is turned off.</span></span> <span data-ttu-id="efbd7-112">Чтобы определить состояние трассировки C2, выполните запрос к представлению каталога sys.traces.</span><span class="sxs-lookup"><span data-stu-id="efbd7-112">To determine the status of a C2 trace, query the sys.traces catalog view.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="efbd7-113">В режиме аудита С2 в файле журнала сохраняется большой объем данных о событиях, что приводит к его быстрому росту.</span><span class="sxs-lookup"><span data-stu-id="efbd7-113">C2 audit mode saves a large amount of event information to the log file, which can grow quickly.</span></span> <span data-ttu-id="efbd7-114">Если в каталоге данных, в котором хранятся журналы, заканчивается свободное место, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] завершает свою работу.</span><span class="sxs-lookup"><span data-stu-id="efbd7-114">If the data directory in which logs are being saved runs out of space, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will shut itself down.</span></span> <span data-ttu-id="efbd7-115">Если настроен автоматический запуск аудита, нужно либо перезапустить экземпляр с флагом **-f** (без аудита), либо освободить место на диске для записи журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="efbd7-115">If auditing is set to start automatically, you must either restart the instance with the **-f** flag (which bypasses auditing), or free up additional disk space for the audit log.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="efbd7-116">Разрешения</span><span class="sxs-lookup"><span data-stu-id="efbd7-116">Permissions</span></span>  
 <span data-ttu-id="efbd7-117">Необходимо членство в предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="efbd7-117">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efbd7-118">Пример</span><span class="sxs-lookup"><span data-stu-id="efbd7-118">Example</span></span>  
 <span data-ttu-id="efbd7-119">В следующем примере включается режим аудита С2.</span><span class="sxs-lookup"><span data-stu-id="efbd7-119">The following example turns on C2 audit mode.</span></span>  
  
```  
sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
sp_configure 'c2 audit mode', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="efbd7-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="efbd7-120">See Also</span></span>  
 <span data-ttu-id="efbd7-121">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="efbd7-121">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="efbd7-122">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="efbd7-122">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="efbd7-123">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="efbd7-123">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
