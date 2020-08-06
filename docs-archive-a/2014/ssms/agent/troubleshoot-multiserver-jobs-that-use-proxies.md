---
title: Устранение неполадок, связанных с многосерверными заданиями, использующими учетные записи-посредники | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], multiserver jobs
- jobs [SQL Server Agent], multiserver jobs using proxies
ms.assetid: fc579bd3-010c-4f72-8b5c-d0cc18a1f280
author: stevestein
ms.author: sstein
ms.openlocfilehash: 19de975ef5e1f22c93cec72a5014a01da5b03dd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731306"
---
# <a name="troubleshoot-multiserver-jobs-that-use-proxies"></a><span data-ttu-id="2c345-102">Устранение неполадок, связанных с многосерверными заданиями, использующими учетные записи-посредники</span><span class="sxs-lookup"><span data-stu-id="2c345-102">Troubleshoot Multiserver Jobs That Use Proxies</span></span>
  <span data-ttu-id="2c345-103">Распределенные задания, шаги выполнения которых связаны с учетной записью-посредником, выполняются в контексте учетной записи-посредника на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="2c345-103">Distributed jobs whose steps are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="2c345-104">При неудачной загрузке с главного сервера на целевой сервер шагов задания, использующего учетную запись-посредник, проверьте в столбце **error_message** таблицы **sysdownloadlist** базы данных **msdb** наличие следующих сообщений об ошибках:</span><span class="sxs-lookup"><span data-stu-id="2c345-104">If job steps that use proxy accounts fail when downloaded from the master server, check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="2c345-105">«Для этого шага задания необходима учетная запись-посредник, однако проверка совпадения учетной записи-посредника на целевом сервере отключена.»</span><span class="sxs-lookup"><span data-stu-id="2c345-105">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span>  
  
     <span data-ttu-id="2c345-106">Чтобы устранить эту ошибку, задайте для параметра **\ HKEY_LOCAL_MACHINE \СОФТВАРЕ\МИКРОСОФТ\МИКРОСОФТ SQL Server\MSSQL.** \<n_>В подразделе реестра _**\sqlserveragent\allowdownloadedjobstomatchproxyname значение** значение **1 (true)**.</span><span class="sxs-lookup"><span data-stu-id="2c345-106">To resolve this error, set the **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\MSSQL.**_\<n_>**\SQLServerAgent\AllowDownloadedJobsToMatchProxyName** registry subkey to **1 (true)**.</span></span> <span data-ttu-id="2c345-107">По умолчанию этот подраздел имеет значение **0** ( `false` ).</span><span class="sxs-lookup"><span data-stu-id="2c345-107">By default, this subkey is set to **0** (`false`).</span></span> <span data-ttu-id="2c345-108">Значение **MSSQL.**\<*n*></span><span class="sxs-lookup"><span data-stu-id="2c345-108">The value of **MSSQL.**\<*n*></span></span> <span data-ttu-id="2c345-109">имя экземпляра; Например, **MSSQL. 1** или **MSSQL. 3**.</span><span class="sxs-lookup"><span data-stu-id="2c345-109">is the instance name; for example, **MSSQL.1** or **MSSQL.3**.</span></span>  
  
-   <span data-ttu-id="2c345-110">«Учетная запись-посредник не найдена.»</span><span class="sxs-lookup"><span data-stu-id="2c345-110">"Proxy not found."</span></span>  
  
     <span data-ttu-id="2c345-111">Чтобы устранить эту ошибку, убедитесь, что на целевом сервере существует учетная запись-посредник, имя которой совпадает с именем учетной записи-посредника на главном сервере, под которой выполняется шаг задания.</span><span class="sxs-lookup"><span data-stu-id="2c345-111">To resolve this error, make sure a proxy account exists on the target server with the same name as the master server proxy account under which the job step runs.</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2c345-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="2c345-112">See Also</span></span>  
 [<span data-ttu-id="2c345-113">Создание многосерверной среды</span><span class="sxs-lookup"><span data-stu-id="2c345-113">Create a Multiserver Environment</span></span>](create-a-multiserver-environment.md)  
  
  
