---
title: Распространитель | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replicationutilities.selectdistributor.f1
ms.assetid: 787f0e9c-09dd-438a-bc04-5b8f99c127b8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c601a540088b5cd9d7a2033510a5cf9b83c3170e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655624"
---
# <a name="distributor"></a><span data-ttu-id="6e1b6-102">Распространитель</span><span class="sxs-lookup"><span data-stu-id="6e1b6-102">Distributor</span></span>
  <span data-ttu-id="6e1b6-103">Страница **Распространитель** доступна в мастере настройки распространения и в мастере создания публикаций.</span><span class="sxs-lookup"><span data-stu-id="6e1b6-103">The **Distributor** page appears in the Configure Distribution Wizard and in the New Publication Wizard.</span></span> <span data-ttu-id="6e1b6-104">Распространитель — это сервер, который содержит базу данных распространителя и хранит метаданные и данные журнала всех типов репликации.</span><span class="sxs-lookup"><span data-stu-id="6e1b6-104">The Distributor is a server that contains the distribution database and stores metadata and history data for all types of replication.</span></span> <span data-ttu-id="6e1b6-105">Распространитель также хранит транзакции для репликации транзакций.</span><span class="sxs-lookup"><span data-stu-id="6e1b6-105">The Distributor also stores transactions for transactional replication.</span></span> <span data-ttu-id="6e1b6-106">Распространителем может быть тот же сервер, который является издателем (локальный распространитель), либо отдельный сервер (удаленный распространитель).</span><span class="sxs-lookup"><span data-stu-id="6e1b6-106">The Distributor can be the same server as the Publisher (a local Distributor) or it can be a separate server from the Publisher (a remote Distributor).</span></span> <span data-ttu-id="6e1b6-107">Роль распространителя различна в зависимости от реализуемого типа репликации.</span><span class="sxs-lookup"><span data-stu-id="6e1b6-107">The role of the Distributor varies, depending on which type of replication you implement.</span></span> <span data-ttu-id="6e1b6-108">В целом, его роль существенно важнее для репликации транзакций, чем для репликации слиянием и репликации моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="6e1b6-108">In general, its role is much greater for transactional replication than it is for merge replication and snapshot replication.</span></span> <span data-ttu-id="6e1b6-109">Для репликации слиянием и репликации моментальных снимков, как правило, используется локальный распространитель, но для репликации транзакций на очень сильно загруженной системе может оказаться полезным удаленный распространитель.</span><span class="sxs-lookup"><span data-stu-id="6e1b6-109">Merge and snapshot replication typically use a local Distributor, but transactional replication on a very busy system can benefit from using a remote Distributor.</span></span>  
  
 <span data-ttu-id="6e1b6-110">Распространитель использует следующие дополнительные ресурсы на сервере, где он расположен.</span><span class="sxs-lookup"><span data-stu-id="6e1b6-110">The Distributor uses these additional resources on the server where it is located:</span></span>  
  
-   <span data-ttu-id="6e1b6-111">Дополнительное место на диске, если файлы моментальных снимков для публикации хранятся на нем (обычно так и происходит).</span><span class="sxs-lookup"><span data-stu-id="6e1b6-111">Additional disk space if the snapshot files for the publication are stored on it (which they typically are).</span></span>  
  
-   <span data-ttu-id="6e1b6-112">Дополнительное место на диске для хранения базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="6e1b6-112">Additional disk space to store the distribution database.</span></span>  
  
-   <span data-ttu-id="6e1b6-113">Дополнительное использование процессора агентами репликации для принудительных подписок на распространителе.</span><span class="sxs-lookup"><span data-stu-id="6e1b6-113">Additional processor usage by replication agents for push subscriptions running on the Distributor.</span></span>  
  
 <span data-ttu-id="6e1b6-114">Сервер, который был выбран в качестве распространителя, должен иметь достаточно места на диске и достаточно мощный процессор для поддержки репликации и других действий на данном сервере.</span><span class="sxs-lookup"><span data-stu-id="6e1b6-114">The server you select as the Distributor should have adequate disk space and processor power to support replication and any other activities on that server.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6e1b6-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="6e1b6-115">Options</span></span>  
 <span data-ttu-id="6e1b6-116">**'\<ServerName>' будет выступать в качестве своего собственного распространителя; SQL Server создаст базу данных распространителя и журнал**</span><span class="sxs-lookup"><span data-stu-id="6e1b6-116">**'\<ServerName>' will act as its own Distributor; SQL Server will create a distribution database and log**</span></span>  
 <span data-ttu-id="6e1b6-117">Выберите этот параметр, чтобы настроить сервер, с которым установлено соединение, для работы в качестве своего собственного распространителя.</span><span class="sxs-lookup"><span data-stu-id="6e1b6-117">Select this option to configure the server you are connected to as a Distributor.</span></span>  
  
 <span data-ttu-id="6e1b6-118">**Использовать следующий сервер в качестве распространителя. (Примечание. Выбранный сервер должен быть уже настроен в качестве распространителя.)**</span><span class="sxs-lookup"><span data-stu-id="6e1b6-118">**Use the following server as the Distributor (Note: the server you select must already be configured as a Distributor)**</span></span>  
 <span data-ttu-id="6e1b6-119">Выберите этот параметр, а затем щелкните имя сервера ниже, чтобы настроить другой сервер для работы в качестве распространителя.</span><span class="sxs-lookup"><span data-stu-id="6e1b6-119">Select this option and then click on the name of a server below to configure another server as the Distributor.</span></span>  
  
 <span data-ttu-id="6e1b6-120">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="6e1b6-120">**Add**</span></span>  
 <span data-ttu-id="6e1b6-121">Если сервер, который следует использовать в качестве распространителя, отсутствует в списке, нажмите кнопку **Добавить** , чтобы найти нужный сервер и добавить его в список.</span><span class="sxs-lookup"><span data-stu-id="6e1b6-121">If the server you want to use as a Distributor is not listed, click **Add** to identify the server and add it to the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6e1b6-122">Для использования удаленного сервера в качестве распространителя, этот удаленный сервер должен быть уже настроен как распространитель.</span><span class="sxs-lookup"><span data-stu-id="6e1b6-122">To use a remote server as the Distributor, the remote server must already be configured as a Distributor.</span></span> <span data-ttu-id="6e1b6-123">Сервер, на котором работает этот мастер, должен быть включен на этом распространителе в качестве издателя.</span><span class="sxs-lookup"><span data-stu-id="6e1b6-123">The server against which this wizard is running must be enabled as a Publisher on that Distributor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e1b6-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="6e1b6-124">See Also</span></span>  
 <span data-ttu-id="6e1b6-125">[Настройка распространения](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="6e1b6-125">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="6e1b6-126">Настройка публикации и распространения</span><span class="sxs-lookup"><span data-stu-id="6e1b6-126">Configure Publishing and Distribution</span></span>](configure-publishing-and-distribution.md)  
  
  
