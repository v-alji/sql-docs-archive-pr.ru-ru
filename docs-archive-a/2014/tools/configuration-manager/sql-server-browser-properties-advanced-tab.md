---
title: Свойства агента браузера SQL Server (вкладка "Дополнительно") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: ba79137a-cb72-4bf3-a650-e11d02cfce10
author: stevestein
ms.author: sstein
ms.openlocfilehash: 480cd93c3feca44dd455a1a9ce2fd12994ca6100
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667508"
---
# <a name="sql-server-browser-properties-advanced-tab"></a><span data-ttu-id="622fc-102">Свойства браузера SQL Server (вкладка «Дополнительно»)</span><span class="sxs-lookup"><span data-stu-id="622fc-102">SQL Server Browser Properties (Advanced Tab)</span></span>
  <span data-ttu-id="622fc-103">Программа браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] работает в качестве службы на сервере.</span><span class="sxs-lookup"><span data-stu-id="622fc-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser program runs as a service on the server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="622fc-104">прослушивает входящие запросы к ресурсам [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и предоставляет сведения об экземплярах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="622fc-104">Browser listens for incoming requests for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="622fc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="622fc-105">Options</span></span>  
 <span data-ttu-id="622fc-106">**Кластеризованный**</span><span class="sxs-lookup"><span data-stu-id="622fc-106">**Clustered**</span></span>  
 <span data-ttu-id="622fc-107">Указывает, установлена ли эта служба в качестве ресурса кластеризованного сервера.</span><span class="sxs-lookup"><span data-stu-id="622fc-107">Indicates if this service is installed as a resource of a clustered server.</span></span>  
  
 <span data-ttu-id="622fc-108">**Передача отзывов пользователей**</span><span class="sxs-lookup"><span data-stu-id="622fc-108">**Customer Feedback Reporting**</span></span>  
 <span data-ttu-id="622fc-109">Указывает, был ли запущен контроль качества обслуживания для этой службы.</span><span class="sxs-lookup"><span data-stu-id="622fc-109">Indicates whether Service Quality Monitoring has been enabled on this service.</span></span> <span data-ttu-id="622fc-110">Дополнительные сведения о передаче отзывов пользователей см. в разделе «Настройки параметров отчета об ошибках» электронной документации.</span><span class="sxs-lookup"><span data-stu-id="622fc-110">For more information on Customer Feedback Reporting, search Books Online for the topic, "Error and Usage Report Settings."</span></span>  
  
 <span data-ttu-id="622fc-111">**Каталог дампа**</span><span class="sxs-lookup"><span data-stu-id="622fc-111">**Dump Directory**</span></span>  
 <span data-ttu-id="622fc-112">Каталог, куда в случае возникновения ошибки помещаются дампы памяти.</span><span class="sxs-lookup"><span data-stu-id="622fc-112">The location where memory dumps are placed in case of an error.</span></span>  
  
 <span data-ttu-id="622fc-113">**Отчет об ошибках**</span><span class="sxs-lookup"><span data-stu-id="622fc-113">**Error Reporting**</span></span>  
 <span data-ttu-id="622fc-114">Если установлено значение **Да**, то в случае возникновения серьезного сбоя программа "Доктор Ватсон» направит сведения либо в [!INCLUDE[msCoName](../../includes/msconame-md.md)] , либо на сервер ошибок.</span><span class="sxs-lookup"><span data-stu-id="622fc-114">When set to **Yes**, the Dr. Watson program forwards information to either [!INCLUDE[msCoName](../../includes/msconame-md.md)] or your error server if a serious failure occurs.</span></span> <span data-ttu-id="622fc-115">Дополнительные сведения по отчетам об ошибках см. в разделе «Настройки параметров отчета об ошибках» электронной документации.</span><span class="sxs-lookup"><span data-stu-id="622fc-115">For more information on Error Reporting, search Books Online for the topic, "Error and Usage Report Settings."</span></span>  
  
 <span data-ttu-id="622fc-116">**Идентификатор экземпляра**</span><span class="sxs-lookup"><span data-stu-id="622fc-116">**Instance ID**</span></span>  
 <span data-ttu-id="622fc-117">Указывает экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который использует этот экземпляр агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="622fc-117">Indicates the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that used this [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent instance.</span></span> <span data-ttu-id="622fc-118">Экземпляр по умолчанию: **MSSQL10_50.MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="622fc-118">The default instance is **MSSQL10_50.MSSQLSERVER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="622fc-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="622fc-119">See Also</span></span>  
 [<span data-ttu-id="622fc-120">Служба обозревателя SQL Server</span><span class="sxs-lookup"><span data-stu-id="622fc-120">SQL Server Browser Service</span></span>](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
