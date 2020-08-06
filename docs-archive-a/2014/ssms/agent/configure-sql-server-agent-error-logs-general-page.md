---
title: Журналы ошибок конфигурации агента SQL Server (страница "Общие") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.errorlog.configure.f1
ms.assetid: e08de622-6f87-470c-aee0-b2d6cb6cca88
author: stevestein
ms.author: sstein
ms.openlocfilehash: bd4c083ea7e7d220d5da20594079b7679c0bb724
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665762"
---
# <a name="configure-sql-server-agent-error-logs-general-page"></a><span data-ttu-id="a0cf8-102">Журналы ошибок конфигурации агента SQL Server (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="a0cf8-102">Configure SQL Server Agent Error Logs (General Page)</span></span>
  <span data-ttu-id="a0cf8-103">Эта страница используется для просмотра и изменения параметров журнала ошибок агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a0cf8-103">Use this screen to view and update settings for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error logging.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a0cf8-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="a0cf8-104">Options</span></span>  
 <span data-ttu-id="a0cf8-105">**Файл журнала ошибок**</span><span class="sxs-lookup"><span data-stu-id="a0cf8-105">**Error log file**</span></span>  
 <span data-ttu-id="a0cf8-106">Указывает файл, в который агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] производит запись журнала ошибок.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-106">Specifies the file to which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent writes error logs.</span></span>  
  
 <span data-ttu-id="a0cf8-107">**...**</span><span class="sxs-lookup"><span data-stu-id="a0cf8-107">**...**</span></span>  
 <span data-ttu-id="a0cf8-108">Перейдите к файлу журнала ошибок.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-108">Browse to the error log file.</span></span>  
  
 <span data-ttu-id="a0cf8-109">**Запись журнала ошибок в OEM**</span><span class="sxs-lookup"><span data-stu-id="a0cf8-109">**Write OEM error log**</span></span>  
 <span data-ttu-id="a0cf8-110">Запись файла журнала ошибок производится не в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-110">Writes the error log file as a non-Unicode file.</span></span> <span data-ttu-id="a0cf8-111">Это позволяет уменьшить место на диске, необходимое для файла журнала.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-111">This reduces the amount of disk space consumed by the log file.</span></span> <span data-ttu-id="a0cf8-112">Однако при включении этого параметра могут возникнуть трудности с чтением сообщений, содержащих данные в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-112">However, messages that include Unicode data may be more difficult to read when this option is enabled.</span></span>  
  
 <span data-ttu-id="a0cf8-113">**ошибки**</span><span class="sxs-lookup"><span data-stu-id="a0cf8-113">**Errors**</span></span>  
 <span data-ttu-id="a0cf8-114">В файл журнала ошибок производится только запись ошибок и информационных сообщений.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-114">Writes only errors and informational messages to the log file.</span></span>  
  
 <span data-ttu-id="a0cf8-115">**Предупреждения**</span><span class="sxs-lookup"><span data-stu-id="a0cf8-115">**Warnings**</span></span>  
 <span data-ttu-id="a0cf8-116">В файл журнала ошибок производится только запись предупреждений и информационных сообщений.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-116">Writes only warnings and informational messages to the log file.</span></span>  
  
 <span data-ttu-id="a0cf8-117">**Информация**</span><span class="sxs-lookup"><span data-stu-id="a0cf8-117">**Information**</span></span>  
 <span data-ttu-id="a0cf8-118">В файл журнала ошибок производится только запись информационных сообщений.</span><span class="sxs-lookup"><span data-stu-id="a0cf8-118">Writes only informational messages to the log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0cf8-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="a0cf8-119">See Also</span></span>  
 [<span data-ttu-id="a0cf8-120">Журнал ошибок агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="a0cf8-120">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
