---
title: Учебник. Подготовка сервера к репликации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: ce30a095-2975-4387-9377-94a461ac78ee
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1f036ff2a111ee6b5f97655b9bebaf34391a436
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668750"
---
# <a name="tutorial-preparing-the-server-for-replication"></a><span data-ttu-id="2a62d-102">Учебник. Подготовка сервера к репликации</span><span class="sxs-lookup"><span data-stu-id="2a62d-102">Tutorial: Preparing the Server for Replication</span></span>
  <span data-ttu-id="2a62d-103">Перед тем, как настраивать топологию репликации, важно предусмотреть средства безопасности.</span><span class="sxs-lookup"><span data-stu-id="2a62d-103">It is important to plan for security before you configure your replication topology.</span></span> <span data-ttu-id="2a62d-104">В этом учебнике описывается, как лучше обезопасить топологию репликации и как настроить распространение, которое является первым шагом в репликации данных.</span><span class="sxs-lookup"><span data-stu-id="2a62d-104">This tutorial shows you how to better secure a replication topology as well as how to configure distribution, which is the first step in replicating data.</span></span> <span data-ttu-id="2a62d-105">В первую очередь необходимо пройти именно этот учебник.</span><span class="sxs-lookup"><span data-stu-id="2a62d-105">You must complete this tutorial before any of the others.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2a62d-106">Чтобы безопасно выполнять репликацию данных между серверами, следует выполнять все рекомендации, приведенные в разделе [Рекомендации по защите репликации](security/replication-security-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="2a62d-106">To replicate data securely between servers, you should implement all of the recommendations in [Replication Security Best Practices](security/replication-security-best-practices.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="2a62d-107">Обзор учебника</span><span class="sxs-lookup"><span data-stu-id="2a62d-107">What You Will Learn</span></span>  
 <span data-ttu-id="2a62d-108">В этом учебнике описывается, как подготовить сервер для безопасного выполнения репликации с минимальным числом привилегий.</span><span class="sxs-lookup"><span data-stu-id="2a62d-108">In this tutorial you will learn how to prepare a server so that replication can run securely with least privileges.</span></span> <span data-ttu-id="2a62d-109">На первом занятии создаются учетные записи службы Windows, используемые для запуска агентов репликации.</span><span class="sxs-lookup"><span data-stu-id="2a62d-109">The first lesson shows how to create the Windows service accounts used to run replication agents.</span></span> <span data-ttu-id="2a62d-110">На втором занятии демонстрируется настройка папки, используемой для формирования и хранения моментальных снимков публикации.</span><span class="sxs-lookup"><span data-stu-id="2a62d-110">The second lesson shows how to configure the folder used to generate and store publication snapshots.</span></span> <span data-ttu-id="2a62d-111">На третьем занятии выполняется настройка распространения и установка разрешений.</span><span class="sxs-lookup"><span data-stu-id="2a62d-111">The third lesson shows how to configure distribution and set permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a62d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="2a62d-112">Requirements</span></span>  
 <span data-ttu-id="2a62d-113">Этот учебник предназначен для пользователей, знакомых с основными операциями с базами данных, но имеющих ограниченный опыт работы с репликацией.</span><span class="sxs-lookup"><span data-stu-id="2a62d-113">This tutorial is intended for users familiar with fundamental database operations, but who have limited exposure to replication.</span></span>  
  
 <span data-ttu-id="2a62d-114">Для работы с этим учебником в системе должны быть установлены следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="2a62d-114">To use this tutorial, your system must have the following components installed:</span></span>  
  
-   [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] <span data-ttu-id="2a62d-115">с базой данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2a62d-115">with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="2a62d-116">В целях повышения безопасности образцы баз данных по умолчанию не устанавливаются.</span><span class="sxs-lookup"><span data-stu-id="2a62d-116">To enhance security, the sample databases are not installed by default.</span></span>  
  
 <span data-ttu-id="2a62d-117">**Предполагаемое время выполнения этого учебника: 30 минут.**</span><span class="sxs-lookup"><span data-stu-id="2a62d-117">**Estimated time to complete this tutorial: 30 minutes.**</span></span>  
  
## <a name="lessons-in-this-tutorial"></a><span data-ttu-id="2a62d-118">Занятия этого учебника</span><span class="sxs-lookup"><span data-stu-id="2a62d-118">Lessons in This Tutorial</span></span>  
  
-   [<span data-ttu-id="2a62d-119">Занятие 1. Создание учетных записей Windows для репликации</span><span class="sxs-lookup"><span data-stu-id="2a62d-119">Lesson 1: Creating Windows Accounts for Replication</span></span>](lesson-1-creating-windows-accounts-for-replication.md)  
  
-   [<span data-ttu-id="2a62d-120">Занятие 2. Подготовка папки моментальных снимков</span><span class="sxs-lookup"><span data-stu-id="2a62d-120">Lesson 2: Preparing the Snapshot Folder</span></span>](lesson-2-preparing-the-snapshot-folder.md)  
  
-   [<span data-ttu-id="2a62d-121">Урок 3. Настройка распространения</span><span class="sxs-lookup"><span data-stu-id="2a62d-121">Lesson 3: Configuring Distribution</span></span>](lesson-3-configuring-distribution.md)  
  
 [<span data-ttu-id="2a62d-122">Запуск учебника</span><span class="sxs-lookup"><span data-stu-id="2a62d-122">Start the Tutorial</span></span>](lesson-1-creating-windows-accounts-for-replication.md)  
  
## <a name="see-also"></a><span data-ttu-id="2a62d-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="2a62d-123">See Also</span></span>  
 <span data-ttu-id="2a62d-124">[Настройка распространения](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="2a62d-124">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="2a62d-125">Безопасность Репликация SQL Server</span><span class="sxs-lookup"><span data-stu-id="2a62d-125">SQL Server Replication Security</span></span>](security/view-and-modify-replication-security-settings.md)  
  
  
