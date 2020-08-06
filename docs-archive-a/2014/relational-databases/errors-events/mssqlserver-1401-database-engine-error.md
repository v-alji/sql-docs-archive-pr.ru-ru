---
title: MSSQLSERVER_1401 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1401 (Database Engine error)
ms.assetid: 02928770-aa63-4509-8713-406c73e4cedc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 720263939e2f1685649fc41896e8ea10907d92ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667181"
---
# <a name="mssqlserver_1401"></a><span data-ttu-id="67250-102">MSSQLSERVER_1401</span><span class="sxs-lookup"><span data-stu-id="67250-102">MSSQLSERVER_1401</span></span>
    
## <a name="details"></a><span data-ttu-id="67250-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="67250-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67250-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="67250-104">Product Name</span></span>|<span data-ttu-id="67250-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="67250-105">SQL Server</span></span>|  
|<span data-ttu-id="67250-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="67250-106">Event ID</span></span>|<span data-ttu-id="67250-107">1401</span><span class="sxs-lookup"><span data-stu-id="67250-107">1401</span></span>|  
|<span data-ttu-id="67250-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="67250-108">Event Source</span></span>|<span data-ttu-id="67250-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="67250-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="67250-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="67250-110">Component</span></span>|<span data-ttu-id="67250-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="67250-111">SQLEngine</span></span>|  
|<span data-ttu-id="67250-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="67250-112">Symbolic Name</span></span>|<span data-ttu-id="67250-113">DBM_MASTERSTARTUP</span><span class="sxs-lookup"><span data-stu-id="67250-113">DBM_MASTERSTARTUP</span></span>|  
|<span data-ttu-id="67250-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="67250-114">Message Text</span></span>|<span data-ttu-id="67250-115">Запуск подпрограммы основного потока зеркального отображения базы данных завершился неудачей по следующей причине: %ls.</span><span class="sxs-lookup"><span data-stu-id="67250-115">Startup of the database-mirroring master thread routine failed for the following reason: %ls.</span></span> <span data-ttu-id="67250-116">Устраните причину данной ошибки и перезапустите службу SQL Server.</span><span class="sxs-lookup"><span data-stu-id="67250-116">Correct the cause of this error, and restart the SQL Server service.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="67250-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="67250-117">Explanation</span></span>  
 <span data-ttu-id="67250-118">Запуск контрольного потока зеркального отображения завершился неудачно.</span><span class="sxs-lookup"><span data-stu-id="67250-118">Startup of the mirroring control thread failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67250-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="67250-119">User Action</span></span>  
 <span data-ttu-id="67250-120">В журнале событий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] найдите сведения об ошибке, предшествующей сообщению.</span><span class="sxs-lookup"><span data-stu-id="67250-120">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, look for the associated error that preceded this message.</span></span> <span data-ttu-id="67250-121">Устраните причину этой ошибки и перезапустите службу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="67250-121">Correct the cause of this error, and then restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service (MSSQLSERVER).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67250-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="67250-122">See Also</span></span>  
 [<span data-ttu-id="67250-123">Запуск, остановка, приостановка, возобновление и перезапуск компонента Database Engine, агента SQL и службы браузера SQL Server</span><span class="sxs-lookup"><span data-stu-id="67250-123">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
  
