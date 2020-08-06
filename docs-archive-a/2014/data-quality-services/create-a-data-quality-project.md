---
title: Создание проекта служб DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dqproject.newdqproject.f1
helpviewer_keywords:
- create,data quality project
- data quality project,create
ms.assetid: 19c52d2b-d28e-4449-ab59-5fe0dc326cd9
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3bab14b34123464450bcf0de7540364fc642343e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728706"
---
# <a name="create-a-data-quality-project"></a><span data-ttu-id="1f0dc-102">Создание проекта служб DQS</span><span class="sxs-lookup"><span data-stu-id="1f0dc-102">Create a Data Quality Project</span></span>
  <span data-ttu-id="1f0dc-103">В этом разделе описывается создание проекта служб DQS с помощью программы [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f0dc-103">This topic describes how to create a data quality project by using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span> <span data-ttu-id="1f0dc-104">Проект качества данных используется для выполнения очистки или сопоставления данных в службах [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="1f0dc-104">A data quality project is used to run the cleansing or matching activity in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1f0dc-105">Перед началом</span><span class="sxs-lookup"><span data-stu-id="1f0dc-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="1f0dc-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1f0dc-106">Prerequisites</span></span>  
 <span data-ttu-id="1f0dc-107">Необходимо иметь соответствующие базы знаний для использования в проекте качества данных для выполнения очистки или сопоставления данных.</span><span class="sxs-lookup"><span data-stu-id="1f0dc-107">You must have a relevant knowledge base to use in the data quality project for the cleansing or matching activity.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1f0dc-108">безопасность</span><span class="sxs-lookup"><span data-stu-id="1f0dc-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1f0dc-109">Permissions</span><span class="sxs-lookup"><span data-stu-id="1f0dc-109">Permissions</span></span>  
 <span data-ttu-id="1f0dc-110">Для создания проекта служб DQS необходимо иметь роль dqs_kb_editor или dqs_kb_operator в базе данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="1f0dc-110">You must have the dqs_kb_editor or dqs_kb_operator role on the DQS_MAIN database to create a data quality project.</span></span>  
  
##  <a name="create-a-data-quality-project"></a><a name="Create"></a><span data-ttu-id="1f0dc-111">Создание проекта качества данных</span><span class="sxs-lookup"><span data-stu-id="1f0dc-111">Create a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="1f0dc-112">[Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="1f0dc-112">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="1f0dc-113">На главном экране [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] щелкните **Создать проект служб DQS**.</span><span class="sxs-lookup"><span data-stu-id="1f0dc-113">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **New data quality project**.</span></span>  
  
3.  <span data-ttu-id="1f0dc-114">На экране **Новый проект служб DQS**</span><span class="sxs-lookup"><span data-stu-id="1f0dc-114">In the **New Data Quality Project** screen:</span></span>  
  
    1.  <span data-ttu-id="1f0dc-115">в поле **Имя** введите имя нового проекта служб DQS.</span><span class="sxs-lookup"><span data-stu-id="1f0dc-115">In the **Name** box, type a name for the new data quality project.</span></span>  
  
    2.  <span data-ttu-id="1f0dc-116">В текстовом поле **Описание** введите описание нового проекта служб DQS (необязательно).</span><span class="sxs-lookup"><span data-stu-id="1f0dc-116">(Optional) In the **Description** box, type a description for the new data quality project.</span></span>  
  
    3.  <span data-ttu-id="1f0dc-117">В списке **Использовать базу знаний** выберите базу знаний для использования в проекте служб DQS.</span><span class="sxs-lookup"><span data-stu-id="1f0dc-117">In the **Use Knowledge base** list, click to select a knowledge base to be used for the data quality project.</span></span> <span data-ttu-id="1f0dc-118">Область **Сведения о базе знаний: <имя_базы_знаний>** в правой части содержит доступные в выбранной базе знаний доменные имена.</span><span class="sxs-lookup"><span data-stu-id="1f0dc-118">The **Knowledge base details: <Knowledge_Base_Name>** area on the right side displays the domain names available in the selected knowledge base.</span></span>  
  
    4.  <span data-ttu-id="1f0dc-119">В области **Выбор действия** выберите действие, которое требуется выполнить с помощью этого проекта служб DQS:</span><span class="sxs-lookup"><span data-stu-id="1f0dc-119">In the **Select Activity** area, click on an activity that you want to perform using this data quality project:</span></span>  
  
        -   <span data-ttu-id="1f0dc-120">**Очистка**. Выберите это действие для очистки источника данных.</span><span class="sxs-lookup"><span data-stu-id="1f0dc-120">**Cleansing**: Select this activity to cleanse the source data.</span></span>  
  
        -   <span data-ttu-id="1f0dc-121">**Сопоставление**. Выберите это действие, чтобы выполнить сопоставление.</span><span class="sxs-lookup"><span data-stu-id="1f0dc-121">**Matching**: Select this activity to perform matching.</span></span> <span data-ttu-id="1f0dc-122">Это действие доступно только в том случае, если база знаний, выбранная для проекта служб DQS, содержит политику сопоставления.</span><span class="sxs-lookup"><span data-stu-id="1f0dc-122">This activity is available only if the knowledge base selected for the data quality project contains a matching policy.</span></span>  
  
4.  <span data-ttu-id="1f0dc-123">Нажмите **Создать** , чтобы создать проект служб DQS.</span><span class="sxs-lookup"><span data-stu-id="1f0dc-123">Click **Create** to create a data quality project.</span></span>  
  
##  <a name="follow-up-after-creating-a-data-quality-project"></a><a name="FollowUp"></a><span data-ttu-id="1f0dc-124">Дальнейшие действия. После создания проекта качества данных</span><span class="sxs-lookup"><span data-stu-id="1f0dc-124">Follow Up: After Creating a Data Quality Project</span></span>  
 <span data-ttu-id="1f0dc-125">После того как проект качества данных создан, откроется мастер для выполнения выбранного действия: очистки или сопоставления.</span><span class="sxs-lookup"><span data-stu-id="1f0dc-125">After you create a data quality project, you are presented with a wizard that you use to perform the selected activity: cleansing or matching.</span></span> <span data-ttu-id="1f0dc-126">Дополнительные сведения о действиях по очистке и сопоставлению см. в разделах [Очистка данных](../../2014/data-quality-services/data-cleansing.md) и [Сопоставление данных](../../2014/data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="1f0dc-126">For more information about the cleansing and matching activities, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md) and [Data Matching](../../2014/data-quality-services/data-matching.md).</span></span>  
  
  
