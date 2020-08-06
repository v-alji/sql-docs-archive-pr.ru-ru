---
title: Импорт базы знаний из файла DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 9b9786fe-9e80-429a-afcb-dc3b3dd6f0b0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 522c5f6d8f962cef77e215c21133927e8da4d04f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733202"
---
# <a name="import-a-knowledge-base-from-a-dqs-file"></a><span data-ttu-id="389f9-102">Импорт базы знаний из файла .dqs</span><span class="sxs-lookup"><span data-stu-id="389f9-102">Import a Knowledge Base from a .dqs File</span></span>
  <span data-ttu-id="389f9-103">В этом разделе описывается, как импортировать всю базу знаний из файла данных DQS в службах [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="389f9-103">This topic describes how to import an entire knowledge base from a .dqs data file in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="389f9-104">Этот файл данных создан путем экспорта существующей базы знаний из приложения [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] (см. раздел [Экспорт базы знаний в файл .dqs](../../2014/data-quality-services/export-a-knowledge-base-to-a-dqs-file.md)).</span><span class="sxs-lookup"><span data-stu-id="389f9-104">You create the data file by exporting an existing knowledge base from within the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] application (see [Export a Knowledge Base to a .dqs File](../../2014/data-quality-services/export-a-knowledge-base-to-a-dqs-file.md)).</span></span>  
  
 <span data-ttu-id="389f9-105">Использование файла DQS для экспорта содержания базы знаний и последующего импорта содержимого в другую базу знаний на том же [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] или на другом [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] упрощает процесс создания набора знаний, экономя время и усилия.</span><span class="sxs-lookup"><span data-stu-id="389f9-105">Using a .dqs data file to export the contents of a knowledge base and then import the contents into another knowledge base on the same [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] or a different [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] simplifies the knowledge generation process, saving time and effort.</span></span> <span data-ttu-id="389f9-106">Это позволяет совместно использовать базу знаний и ее знания, экономя время.</span><span class="sxs-lookup"><span data-stu-id="389f9-106">It enables you to share a knowledge base and its knowledge with others, saving them time.</span></span> <span data-ttu-id="389f9-107">Файл DQS будет содержать все сведения базы знаний, включая домены и политику сопоставления, кроме присоединенных ссылочных данных.</span><span class="sxs-lookup"><span data-stu-id="389f9-107">The .dqs file will contain all knowledge base information, including domains and the matching policy, except for the attached reference data information.</span></span> <span data-ttu-id="389f9-108">Будут импортированы опубликованные и неопубликованные данные.</span><span class="sxs-lookup"><span data-stu-id="389f9-108">Published and unpublished data will be imported.</span></span>  
  
 <span data-ttu-id="389f9-109">Файл данных .dqs зашифрован, поэтому его нельзя просмотреть.</span><span class="sxs-lookup"><span data-stu-id="389f9-109">A .dqs data file is encrypted, so cannot be viewed.</span></span>  
  
 <span data-ttu-id="389f9-110">При импорте базы знаний вы можете использовать то же самое имя, если только это имя базы знаний уже не существует в клиентском приложении; в этом случае базу знаний следует переименовать.</span><span class="sxs-lookup"><span data-stu-id="389f9-110">When you import a knowledge base, you can use the same name, unless the knowledge base name already exists in the client application, in which case you must rename it.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="389f9-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="389f9-111">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="389f9-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="389f9-112">Prerequisites</span></span>  
 <span data-ttu-id="389f9-113">Чтобы импортировать базу знаний из файла данных DQS, необходимо предварительно экспортировать базу знаний в файл DQS.</span><span class="sxs-lookup"><span data-stu-id="389f9-113">To import a knowledge base from a .dqs file, you must have already exported the knowledge base into the .dqs file.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="389f9-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="389f9-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="389f9-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="389f9-115">Permissions</span></span>  
 <span data-ttu-id="389f9-116">Для импорта базы знаний из файла DQS необходимо иметь роль dqs_kb_editor или dqs_administrator в базе данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="389f9-116">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to import a knowledge base from a .dqs data file.</span></span>  
  
##  <a name="import-a-knowledge-base-from-a-dqs-file"></a><a name="Import"></a><span data-ttu-id="389f9-117">Импорт базы знаний из файла DQS</span><span class="sxs-lookup"><span data-stu-id="389f9-117">Import a knowledge base from a .dqs file</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="389f9-118">[Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="389f9-118">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="389f9-119">На главном экране [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] нажмите кнопку **Создать базу знаний**.</span><span class="sxs-lookup"><span data-stu-id="389f9-119">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **New knowledge base**.</span></span>  
  
3.  <span data-ttu-id="389f9-120">Введите имя для базы знаний.</span><span class="sxs-lookup"><span data-stu-id="389f9-120">Enter a name for the knowledge base.</span></span>  
  
4.  <span data-ttu-id="389f9-121">Нажмите стрелку вниз **Создать базу знаний из**и выберите **Импорт из файла DQS**.</span><span class="sxs-lookup"><span data-stu-id="389f9-121">Click the down arrow for **Create knowledge base from**, and then select **Import from DQS file**.</span></span>  
  
5.  <span data-ttu-id="389f9-122">Чтобы **Выбрать файл данных**, нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="389f9-122">For **Select data file**, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="389f9-123">В диалоговом окне **Импорт из файла данных** перейдите к папке, содержащей файл DQS, который надо импортировать, и щелкните имя этого файла.</span><span class="sxs-lookup"><span data-stu-id="389f9-123">In the **Import from Data File** dialog box, move to the folder that contains the .dqs file that you want to import, and then click the name of the file.</span></span> <span data-ttu-id="389f9-124">Нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="389f9-124">Click **Open**.</span></span>  
  
7.  <span data-ttu-id="389f9-125">Убедитесь, что база знаний и домены правильно отображаются в списке **Домен** .</span><span class="sxs-lookup"><span data-stu-id="389f9-125">Verify that the correct knowledge base and domains are displayed in the **Domain** list.</span></span>  
  
8.  <span data-ttu-id="389f9-126">Выберите действия, которые требуется выполнить, и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="389f9-126">Select the activity that you want to perform, and then click **Create**.</span></span>  
  
9. <span data-ttu-id="389f9-127">В диалоговом окне **Импорт базы знаний** убедитесь, что строка состояния указывает, что импорт завершен.</span><span class="sxs-lookup"><span data-stu-id="389f9-127">In the **Import Knowledge Base** dialog box, verify that the status line indicates that the import completed.</span></span> <span data-ttu-id="389f9-128">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="389f9-128">Click **OK**.</span></span>  
  
10. <span data-ttu-id="389f9-129">Завершите задачи обнаружения знаний, управления доменами или политики сопоставления, которые необходимо выполнить, и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="389f9-129">Complete the knowledge discovery, domain management, or matching policy tasks that you need to perform, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="389f9-130">Нажмите кнопку **Опубликовать** , чтобы опубликовать знания в базе знаний, или кнопку **Нет** , чтобы не публиковать.</span><span class="sxs-lookup"><span data-stu-id="389f9-130">Click **Publish** to publish the knowledge in the knowledge base, or **No** not to.</span></span>  
  
12. <span data-ttu-id="389f9-131">Если вы опубликовали базу знаний, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="389f9-131">If you published the knowledge base, click **OK**.</span></span>  
  
13. <span data-ttu-id="389f9-132">На домашней странице служб Data Quality Services убедитесь, что база знаний содержится в списке **Недавние базы знаний**.</span><span class="sxs-lookup"><span data-stu-id="389f9-132">In the Data Quality Services home page, verify that the knowledge base is listed under **Recent knowledge bases**.</span></span>  
  
##  <a name="follow-up-after-importing-a-knowledge-base-from-a-dqs-file"></a><a name="FollowUp"></a> <span data-ttu-id="389f9-133">Дальнейшие действия. После импорта базы знаний из файла DQS</span><span class="sxs-lookup"><span data-stu-id="389f9-133">Follow Up: After Importing a Knowledge Base from a .dqs File</span></span>  
 <span data-ttu-id="389f9-134">После импорта базы знаний из файла DQS можно добавить набор знаний в базу знаний или использовать базу знаний в проекте очистки или сопоставления данных в зависимости от содержимого базы знаний.</span><span class="sxs-lookup"><span data-stu-id="389f9-134">After you import a knowledge base from a .dqs file, you can add knowledge to the knowledge base or use the knowledge base in a cleansing or matching project, depending on the contents of the knowledge base.</span></span> <span data-ttu-id="389f9-135">Дополнительные сведения см. в разделах [Обнаружение знаний](../../2014/data-quality-services/perform-knowledge-discovery.md), [Управление доменом](../../2014/data-quality-services/managing-a-domain.md), [Управление составным доменом](../../2014/data-quality-services/managing-a-composite-domain.md), [Создание политики сопоставления](../../2014/data-quality-services/create-a-matching-policy.md), [Очистка данных](../../2014/data-quality-services/data-cleansing.md) и [Сопоставление данных](../../2014/data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="389f9-135">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), [Managing a Composite Domain](../../2014/data-quality-services/managing-a-composite-domain.md), [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md), [Data Cleansing](../../2014/data-quality-services/data-cleansing.md), or [Data Matching](../../2014/data-quality-services/data-matching.md).</span></span>  
  
  
