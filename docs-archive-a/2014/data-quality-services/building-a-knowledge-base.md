---
title: Построение базы знаний | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 51eff161-6ecd-4ee4-8187-1dd8ef4814bd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 03c9fc6c3a9168a66e8293c61db21a87fadc260f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655984"
---
# <a name="building-a-knowledge-base"></a><span data-ttu-id="64cab-102">Построение базы знаний</span><span class="sxs-lookup"><span data-stu-id="64cab-102">Building a Knowledge Base</span></span>
  <span data-ttu-id="64cab-103">База знаний в службах [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) является репозиторием знаний о данных, помогающим понимать данные и поддерживать их целостность.</span><span class="sxs-lookup"><span data-stu-id="64cab-103">A knowledge base in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) is a repository of knowledge about your data that enables you to understand your data and maintain its integrity.</span></span> <span data-ttu-id="64cab-104">База знаний состоит из доменов, каждый из которых представляет данные в поле данных.</span><span class="sxs-lookup"><span data-stu-id="64cab-104">A knowledge base consists of domains, each of which represents the data in a data field.</span></span> <span data-ttu-id="64cab-105">База знаний используется службами DQS для выполнения очистки данных и исключения из базы данных повторяющихся значений.</span><span class="sxs-lookup"><span data-stu-id="64cab-105">The knowledge base is used by DQS to perform data cleansing and deduplication on a database.</span></span> <span data-ttu-id="64cab-106">Для подготовки базы знаний к очистке данных вы можете запустить на экземпляре данных компьютерный анализ и интерактивно управлять значениями в доменах.</span><span class="sxs-lookup"><span data-stu-id="64cab-106">To prepare the knowledge base for data cleansing, you can run a computer-assisted analysis of a data sample, and interactively manage values in the domains.</span></span> <span data-ttu-id="64cab-107">Службы DQS позволяют импортировать знания, создавать правила и связи, напрямую изменять значения данных и использовать базу данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="64cab-107">DQS enables you to import knowledge, create rules and relationships, change data values directly, and leverage a default database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="64cab-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="64cab-108">In This Section</span></span>  
 <span data-ttu-id="64cab-109">Над базой знаний вы можете выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="64cab-109">You can perform the following operations on a knowledge base:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="64cab-110">Создать новую базу знаний с нуля или на основе существующей базы знаний или файла данных DQS.</span><span class="sxs-lookup"><span data-stu-id="64cab-110">Create a new knowledge base from scratch, from an existing knowledge base, or from a .dqs data file.</span></span>|[<span data-ttu-id="64cab-111">Создание базы знаний</span><span class="sxs-lookup"><span data-stu-id="64cab-111">Create a Knowledge Base</span></span>](../../2014/data-quality-services/create-a-knowledge-base.md)|  
|<span data-ttu-id="64cab-112">Открыть существующую базу знаний для обнаружения знаний, управления доменами или добавления политики сопоставления.</span><span class="sxs-lookup"><span data-stu-id="64cab-112">Open an existing knowledge base to perform knowledge discovery, domain management, or add a matching policy.</span></span>|[<span data-ttu-id="64cab-113">Открытие базы знаний</span><span class="sxs-lookup"><span data-stu-id="64cab-113">Open a Knowledge Base</span></span>](../../2014/data-quality-services/open-a-knowledge-base.md)|  
|<span data-ttu-id="64cab-114">Выполнять действия по управлению базой знаний, включая ее открытие, разблокировку, отмену работы, переименование, удаление и просмотр ее свойств.</span><span class="sxs-lookup"><span data-stu-id="64cab-114">Perform management actions on a knowledge base, including opening it, unlocking it, discarding your work on it, renaming it, deleting it, or viewing its properties.</span></span>|[<span data-ttu-id="64cab-115">Управление базой знаний</span><span class="sxs-lookup"><span data-stu-id="64cab-115">Manage a Knowledge Base</span></span>](../../2014/data-quality-services/manage-a-knowledge-base.md)|  
|<span data-ttu-id="64cab-116">Добавлять набор знаний в базу знаний с помощью обнаружения знаний; управления значениями в домене; добавления соответствующей политики; импорта набора знаний, доменов или значений; или с помощью базы знаний по умолчанию, DQS Data.</span><span class="sxs-lookup"><span data-stu-id="64cab-116">Add knowledge to a knowledge base through knowledge discovery; domain value management; adding a matching policy; importing a knowledge, domain, or values; or using the default knowledge base, DQS Data.</span></span>|[<span data-ttu-id="64cab-117">Добавление знаний в базу знаний</span><span class="sxs-lookup"><span data-stu-id="64cab-117">Adding Knowledge to a Knowledge Base</span></span>](../../2014/data-quality-services/adding-knowledge-to-a-knowledge-base.md)|  
|<span data-ttu-id="64cab-118">Анализировать образец данные по критериям качества данных.</span><span class="sxs-lookup"><span data-stu-id="64cab-118">Analyze a data sample for data quality criteria.</span></span>|[<span data-ttu-id="64cab-119">Обнаружение набора знаний</span><span class="sxs-lookup"><span data-stu-id="64cab-119">Perform Knowledge Discovery</span></span>](../../2014/data-quality-services/perform-knowledge-discovery.md)|  
  
## <a name="related-tasks"></a><span data-ttu-id="64cab-120">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="64cab-120">Related Tasks</span></span>  
  
|<span data-ttu-id="64cab-121">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="64cab-121">Task Description</span></span>|<span data-ttu-id="64cab-122">Раздел</span><span class="sxs-lookup"><span data-stu-id="64cab-122">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="64cab-123">Импорт знаний в базу знаний или экспорт из нее.</span><span class="sxs-lookup"><span data-stu-id="64cab-123">Importing knowledge into, or exporting it from, a knowledge base.</span></span>|[<span data-ttu-id="64cab-124">Импорт и экспорт набора знаний</span><span class="sxs-lookup"><span data-stu-id="64cab-124">Importing and Exporting Knowledge</span></span>](../../2014/data-quality-services/importing-and-exporting-knowledge.md)|  
|<span data-ttu-id="64cab-125">Создание отдельного домена и добавление набора знаний в этот домен.</span><span class="sxs-lookup"><span data-stu-id="64cab-125">Creating a single domain, and adding knowledge to the domain.</span></span>|[<span data-ttu-id="64cab-126">Управление доменом</span><span class="sxs-lookup"><span data-stu-id="64cab-126">Managing a Domain</span></span>](../../2014/data-quality-services/managing-a-domain.md)|  
|<span data-ttu-id="64cab-127">Создание составного домена и добавление набора знаний в этот домен.</span><span class="sxs-lookup"><span data-stu-id="64cab-127">Creating a composite domain, and adding knowledge to the domain.</span></span>|[<span data-ttu-id="64cab-128">Управление составным доменом</span><span class="sxs-lookup"><span data-stu-id="64cab-128">Managing a Composite Domain</span></span>](../../2014/data-quality-services/managing-a-composite-domain.md)|  
  
  
