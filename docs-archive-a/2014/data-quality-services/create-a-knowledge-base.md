---
title: Создание базы знаний | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.selectkb.f1
- sql12.dqs.kb.newkb.f1
ms.assetid: 2733a284-975f-4650-abcc-cc2aad074cab
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 281fa663362cc4462cd4e32839c1eaf6908394e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655980"
---
# <a name="create-a-knowledge-base"></a><span data-ttu-id="0c2d9-102">Создание базы знаний</span><span class="sxs-lookup"><span data-stu-id="0c2d9-102">Create a Knowledge Base</span></span>
  <span data-ttu-id="0c2d9-103">В этом разделе описано, как создать базу знаний в службах [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) и подготовить ее для управления доменами, обнаружения знаний или добавления политики сопоставления.</span><span class="sxs-lookup"><span data-stu-id="0c2d9-103">This topic describes how to create a knowledge base in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS), and prepare it for domain management, knowledge discovery, or adding a matching policy.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0c2d9-104">Перед началом</span><span class="sxs-lookup"><span data-stu-id="0c2d9-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="0c2d9-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="0c2d9-105">Prerequisites</span></span>  
 <span data-ttu-id="0c2d9-106">Для создания базы знаний необходимо установить [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] и [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c2d9-106">To create a knowledge base, you must have installed [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] and [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0c2d9-107">безопасность</span><span class="sxs-lookup"><span data-stu-id="0c2d9-107">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0c2d9-108">Permissions</span><span class="sxs-lookup"><span data-stu-id="0c2d9-108">Permissions</span></span>  
 <span data-ttu-id="0c2d9-109">Для создания базы знаний необходимо иметь роль dqs_administrator или dqs_kb_editor в базе данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="0c2d9-109">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to create a knowledge base.</span></span>  
  
##  <a name="create-a-knowledge-base"></a><a name="Createaknowledgebase"></a><span data-ttu-id="0c2d9-110">Создание базы знаний</span><span class="sxs-lookup"><span data-stu-id="0c2d9-110">Create a knowledge base</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="0c2d9-111">[Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="0c2d9-111">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="0c2d9-112">На главном экране [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] нажмите кнопку **Создать базу знаний**.</span><span class="sxs-lookup"><span data-stu-id="0c2d9-112">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **New knowledge base**.</span></span>  
  
3.  <span data-ttu-id="0c2d9-113">Введите имя и описание новой базы знаний.</span><span class="sxs-lookup"><span data-stu-id="0c2d9-113">Enter a name and description for the new knowledge base.</span></span>  
  
4.  <span data-ttu-id="0c2d9-114">В поле **Создать базу знаний из**выберите основу для базы знаний:</span><span class="sxs-lookup"><span data-stu-id="0c2d9-114">In **Create knowledge base from**, select what to base the knowledge base on:</span></span>  
  
    -   <span data-ttu-id="0c2d9-115">Выберите **Нет** , если новая база знаний не должна основываться на существующей базе знаний или файле данных.</span><span class="sxs-lookup"><span data-stu-id="0c2d9-115">Select **None** if you do not want to base the new knowledge base on an existing knowledge base or data file.</span></span>  
  
    -   <span data-ttu-id="0c2d9-116">Выберите **Существующая база знаний** , чтобы создать новую базу знаний на основе базе знаний, которая уже была создана на сервере [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], или на базе знаний по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0c2d9-116">Select **Existing Knowledge Base** to base the new knowledge base on a knowledge base that has already been created on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], or on the default knowledge base.</span></span> <span data-ttu-id="0c2d9-117">Выберите базу знаний из раскрывающегося списка **Выбор базы знаний** или нажмите кнопку **Обзор** , чтобы отобразить диалоговое окно **Выбор базы знаний** , выберите существующую базу знаний, на которой основывается существующая база знаний, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0c2d9-117">Select the knowledge base from the **Select Knowledge Base** drop-down list, or click **Browse** to display the **Select a Knowledge Base** dialog box, select an existing knowledge base to base the new knowledge base on, and then click **OK**.</span></span> <span data-ttu-id="0c2d9-118">При выборе базы знаний из таблицы домены и правила сопоставления в базе знаний будут отображаться в правой части диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="0c2d9-118">When you select a knowledge base from the tablet, the domains and matching rules in the knowledge base will be displayed in the right-hand pane of the dialog box.</span></span> <span data-ttu-id="0c2d9-119">Вы можете также выбрать базу знаний **Данные служб DQS** , которая является базой знаний по умолчанию, содержащей типовые готовые домены и наборы знаний, относящиеся к американской организации, адрес и данные стороны.</span><span class="sxs-lookup"><span data-stu-id="0c2d9-119">You can also select the **DQS Data** knowledge base, which is the default knowledge base that contains common out-of-the-box domains and knowledge related to U.S. company, address, and party data.</span></span>  
  
    -   <span data-ttu-id="0c2d9-120">Выберите **Импортировать из файла DQS** , чтобы создать базу знаний на основе DQS-файла, расположенного на сервере [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c2d9-120">Select **Import from DQS File** to base the new knowledge base on a DQS file on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span> <span data-ttu-id="0c2d9-121">Нажмите кнопку **Обзор**, выберите файл данных DQS с расширением DQS и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0c2d9-121">Click **Browse**, select a DQS data file with an extension of .dqs, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="0c2d9-122">В поле **Выбор действия**выберите действие, которое нужно выполнить с новой базой знаний:</span><span class="sxs-lookup"><span data-stu-id="0c2d9-122">In **Select Activity**, select the activity that you want to perform on the new knowledge base:</span></span>  
  
    -   <span data-ttu-id="0c2d9-123">Нажмите кнопку **Управление доменами** , чтобы создать базу знаний и перейти на экраны, на которых можно изменить домены в базе знаний.</span><span class="sxs-lookup"><span data-stu-id="0c2d9-123">Select **Domain Management** to create the knowledge base and enter the screens that you use to modify the domains in the knowledge base.</span></span>  
  
    -   <span data-ttu-id="0c2d9-124">Нажмите кнопку **Обнаружение знаний** , чтобы создать базу знаний и запустить мастер, который позволяет проанализировать образец данных и заполнить домены базы знаний результатами анализа.</span><span class="sxs-lookup"><span data-stu-id="0c2d9-124">Select **Knowledge Discovery** to create the knowledge base and enter the wizard that you use to analyze a data sample and populate the domains of the knowledge base with the results.</span></span>  
  
    -   <span data-ttu-id="0c2d9-125">Выберите вариант **Политика сопоставления** , чтобы создать политику сопоставления и добавить ее в базу знаний.</span><span class="sxs-lookup"><span data-stu-id="0c2d9-125">Select **Matching Policy** to create a matching policy and add it to the knowledge base.</span></span>  
  
6.  <span data-ttu-id="0c2d9-126">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="0c2d9-126">Click **Create**.</span></span>  
  
##  <a name="follow-up-after-creating-a-knowledge-base"></a><a name="FollowUp"></a> <span data-ttu-id="0c2d9-127">Дальнейшие действия. После создания базы знаний</span><span class="sxs-lookup"><span data-stu-id="0c2d9-127">Follow Up: After Creating a Knowledge Base</span></span>  
 <span data-ttu-id="0c2d9-128">После создания базы знаний откроется мастер, с помощью которого можно выполнить обнаружение знаний, мастер для создания политики сопоставления или страницы для управления доменами.</span><span class="sxs-lookup"><span data-stu-id="0c2d9-128">After you create a knowledge base, you are presented with a wizard that you can use to perform knowledge discovery, a wizard to create a matching policy, or pages to perform domain management.</span></span> <span data-ttu-id="0c2d9-129">Дополнительные сведения об обнаружении знаний, управлении доменами и политике сопоставления см. в разделах [Обнаружение знаний](../../2014/data-quality-services/perform-knowledge-discovery.md), [Управление доменом](../../2014/data-quality-services/managing-a-domain.md) и [Создание политики сопоставления](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="0c2d9-129">For more information about the knowledge discovery, domain management, or matching policy, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
  
