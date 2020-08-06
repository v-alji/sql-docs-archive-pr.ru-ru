---
title: Свойства агента SQL Server (страница "Система заданий") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.job.f1
ms.assetid: e171d13e-1302-4f0e-88be-67d656aec8d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 743a8d558e97e9ad83cfc66e9ef1adf2e1bc0c2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667523"
---
# <a name="sql-server-agent-properties-job-system-page"></a><span data-ttu-id="41615-102">Свойства агента SQL Server (страница «Система заданий»)</span><span class="sxs-lookup"><span data-stu-id="41615-102">SQL Server Agent Properties (Job System Page)</span></span>
  <span data-ttu-id="41615-103">Эта страница используется для просмотра и изменения того, как [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Служба агента управляет заданиями.</span><span class="sxs-lookup"><span data-stu-id="41615-103">Use this page to view and modify how the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Service manages jobs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="41615-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="41615-104">Options</span></span>  
 <span data-ttu-id="41615-105">**Время ожидания при завершении работы (в секундах)**</span><span class="sxs-lookup"><span data-stu-id="41615-105">**Shutdown time-out interval (in seconds)**</span></span>  
 <span data-ttu-id="41615-106">Указывает число секунд, в течение которых агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ожидает завершения заданий при окончании работы.</span><span class="sxs-lookup"><span data-stu-id="41615-106">Specifies the number of seconds that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent waits for jobs to complete before shutting down.</span></span> <span data-ttu-id="41615-107">Если отведенное время истекло, а задание так и не завершилось, агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] принудительно его останавливает.</span><span class="sxs-lookup"><span data-stu-id="41615-107">If the job is still running after the interval specified, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent forcefully stops the job.</span></span>  
  
 <span data-ttu-id="41615-108">**Использовать неадминистративную учетную запись-посредник**</span><span class="sxs-lookup"><span data-stu-id="41615-108">**Use a non-administrator proxy account**</span></span>  
 <span data-ttu-id="41615-109">Задает неадминистративную учетную запись-посредник для агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="41615-109">Sets a non-administrator proxy account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="41615-110">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]и более поздние версии поддерживают несколько учетных записей-посредников, поэтому этот параметр применим только при управлении [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Версии агента до [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="41615-110">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions support multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="41615-111">**User name**</span><span class="sxs-lookup"><span data-stu-id="41615-111">**User name**</span></span>  
 <span data-ttu-id="41615-112">Введите имя пользователя для неадминистративной учетной записи-посредника.</span><span class="sxs-lookup"><span data-stu-id="41615-112">Type the name of the user for the non-administrator proxy account.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="41615-113">поддерживает несколько учетных записей-посредников, и поэтому этот параметр применим только в случае работы с версиями агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ранее [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41615-113">supports multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="41615-114">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="41615-114">**Password**</span></span>  
 <span data-ttu-id="41615-115">Введите пароль пользователя для неадминистративной учетной записи-посредника.</span><span class="sxs-lookup"><span data-stu-id="41615-115">Type the password of the user for the non-administrator proxy account.</span></span> [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="41615-116">и более поздние версии поддерживают несколько учетных записей-посредников, и поэтому этот параметр применим только в случае работы с версиями агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ранее [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41615-116">and later versions support multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="41615-117">**Домен**</span><span class="sxs-lookup"><span data-stu-id="41615-117">**Domain**</span></span>  
 <span data-ttu-id="41615-118">Введите домен пользователя для неадминистративной учетной записи-посредника.</span><span class="sxs-lookup"><span data-stu-id="41615-118">Type the domain of the user for the non-administrative proxy account.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="41615-119">поддерживает несколько учетных записей-посредников, и поэтому этот параметр применим только в случае работы с версиями агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ранее [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41615-119">supports multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41615-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="41615-120">See Also</span></span>  
 [<span data-ttu-id="41615-121">Реализация заданий</span><span class="sxs-lookup"><span data-stu-id="41615-121">Implement Jobs</span></span>](implement-jobs.md)  
  
  
