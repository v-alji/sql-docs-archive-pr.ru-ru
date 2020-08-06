---
title: Справочник по ошибкам и событиям (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- errors [SQL Server Database Engine]
- Database Engine [SQL Server], errors
- events [SQL Server Database Engine]
ms.assetid: ea928535-6fd1-4738-a8ed-ffb602f3825e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e991accfd0e6fdd4fa25746499308455eff85ce3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735293"
---
# <a name="errors-and-events-reference-database-engine"></a><span data-ttu-id="d4d7d-102">Справочник по ошибкам и событиям (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="d4d7d-102">Errors and Events Reference (Database Engine)</span></span>

<span data-ttu-id="d4d7d-103">Этот раздел содержит выбранные ядро СУБД сообщения об ошибках, для которых требуется дополнительное объяснение.</span><span class="sxs-lookup"><span data-stu-id="d4d7d-103">This section contains selected Database Engine error messages that need further explanation.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="d4d7d-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="d4d7d-104">In This Section</span></span>  
 <span data-ttu-id="d4d7d-105">[События и ошибки ядро СУБД](database-engine-events-and-errors.md) Описывает формат [!INCLUDE[ssDE](../../includes/ssde-md.md)] сообщений об ошибках и объясняет, как просматривать сообщения об ошибках и возвращать сообщения об ошибках в приложения.</span><span class="sxs-lookup"><span data-stu-id="d4d7d-105">[Database Engine Events and Errors](database-engine-events-and-errors.md) Describes the format of [!INCLUDE[ssDE](../../includes/ssde-md.md)] error messages and explains how to view error messages and return error messages to applications.</span></span>  
  
 <span data-ttu-id="d4d7d-106">Содержит объяснение сообщений об ошибках компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , возможные причины и действия по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="d4d7d-106">Provides an explanation of [!INCLUDE[ssDE](../../includes/ssde-md.md)] error messages, possible causes, and any actions you can take to correct the problem.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="d4d7d-107">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="d4d7d-107">External Resources</span></span>  
 <span data-ttu-id="d4d7d-108">Если в документации по продуктам или на веб-сайте отсутствуют необходимые сведения, можно подать запрос в сообщество [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или запросить помощь в службе поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d4d7d-108">If you have not found the information you are looking for in the product documentation or on the Web, you can either ask a question in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] community or request help from [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="d4d7d-109">В следующей таблице указаны ссылки на эти источники, а также приведено их описание.</span><span class="sxs-lookup"><span data-stu-id="d4d7d-109">The following table links to and describes these resources.</span></span>  
  
|<span data-ttu-id="d4d7d-110">Ресурс</span><span class="sxs-lookup"><span data-stu-id="d4d7d-110">Resource</span></span>|<span data-ttu-id="d4d7d-111">Описание</span><span class="sxs-lookup"><span data-stu-id="d4d7d-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="d4d7d-112">Сообщество SQL Server</span><span class="sxs-lookup"><span data-stu-id="d4d7d-112">SQL Server Community</span></span>](https://go.microsoft.com/fwlink/?LinkId=42455)|<span data-ttu-id="d4d7d-113">Этот сайт содержит ссылки на группы новостей и форумы, контролируемые сообществом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d4d7d-113">This site has links to newsgroups and forums monitored by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] community.</span></span> <span data-ttu-id="d4d7d-114">Кроме того, здесь перечислены источники данных сообщества, такие как блоги и сайты.</span><span class="sxs-lookup"><span data-stu-id="d4d7d-114">It also lists community information sources, such as blogs and Web sites.</span></span> <span data-ttu-id="d4d7d-115">Сообщество [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] оказывает значительную помощь, отвечая на вопросы, однако ответ не может быть гарантирован.</span><span class="sxs-lookup"><span data-stu-id="d4d7d-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] community is very helpful in answering questions, although an answer cannot be guaranteed.</span></span>|  
|[<span data-ttu-id="d4d7d-116">Сообщество центра разработчиков SQL Server</span><span class="sxs-lookup"><span data-stu-id="d4d7d-116">SQL Server Developer Center Community</span></span>](https://go.microsoft.com/fwlink/?LinkId=42456)|<span data-ttu-id="d4d7d-117">На этом сайте находятся группы новостей, форумы и другие источники сообщества, которые полезны для разработчиков [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d4d7d-117">This site focuses on the newsgroups, forums, and other community resources that are useful to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] developers.</span></span>|  
|[<span data-ttu-id="d4d7d-118">Справка и поддержка Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d4d7d-118">Microsoft Help and Support</span></span>](https://go.microsoft.com/fwlink/?linkid=16419)|<span data-ttu-id="d4d7d-119">Этот сайт можно использовать для обращения к специалисту службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d4d7d-119">You can use this Web site to open a case with a [!INCLUDE[msCoName](../../includes/msconame-md.md)] support professional.</span></span>|  
  
  
