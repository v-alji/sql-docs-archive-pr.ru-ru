---
title: Использование связей значений в составном домене | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dm.cdvaluerelations.f1
ms.assetid: 5ee468f0-8538-4620-90e8-63f466c9000e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 135934ec99fed612609e5e1b962f08bb93b98ede
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751484"
---
# <a name="use-value-relations-in-a-composite-domain"></a><span data-ttu-id="05417-102">Использование связей значений в составном домене</span><span class="sxs-lookup"><span data-stu-id="05417-102">Use Value Relations in a Composite Domain</span></span>
  <span data-ttu-id="05417-103">В этом разделе описываются способы просмотра сочетаний значений, обнаруженных для составного домена в процессе обнаружения знаний в службах [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="05417-103">This topic describes how to view value combinations found for the composite domain during the knowledge discovery process in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="05417-104">Эта страница показывает количество повторений сочетаний значений.</span><span class="sxs-lookup"><span data-stu-id="05417-104">This page shows the number of occurrences of the value combinations.</span></span> <span data-ttu-id="05417-105">Управление значениями не поддерживается для составных доменов, поэтому операции с этими значениями выполнить не удастся.</span><span class="sxs-lookup"><span data-stu-id="05417-105">Value management is not supported for composite domains, so you cannot perform any operations on these values.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="05417-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="05417-106">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="05417-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="05417-107">Prerequisites</span></span>  
 <span data-ttu-id="05417-108">Чтобы просмотреть связи значений, необходимо создать и открыть составной домен.</span><span class="sxs-lookup"><span data-stu-id="05417-108">To view value relations, you must have created and opened a composite domain.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="05417-109">безопасность</span><span class="sxs-lookup"><span data-stu-id="05417-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="05417-110">Permissions</span><span class="sxs-lookup"><span data-stu-id="05417-110">Permissions</span></span>  
 <span data-ttu-id="05417-111">Для просмотра связей значений в составном домене необходимо иметь роль dqs_kb_editor или dqs_administrator в базе данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="05417-111">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to view value relations in a composite domain.</span></span>  
  
##  <a name="view-value-relations"></a><a name="Use"></a><span data-ttu-id="05417-112">Просмотр связей значений</span><span class="sxs-lookup"><span data-stu-id="05417-112">View Value Relations</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="05417-113">[Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="05417-113">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="05417-114">На главном экране клиента [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] откройте или создайте базу знаний.</span><span class="sxs-lookup"><span data-stu-id="05417-114">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open or create a knowledge base.</span></span> <span data-ttu-id="05417-115">Выберите операцию **Управление доменами** , а затем нажмите кнопку **Открыть** или **Создать**.</span><span class="sxs-lookup"><span data-stu-id="05417-115">Select **Domain Management** as the activity, and then click **Open** or **Create**.</span></span> <span data-ttu-id="05417-116">Дополнительные сведения см. в разделе [Создание базы знаний](../../2014/data-quality-services/create-a-knowledge-base.md) или [Открытие базы знаний](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="05417-116">For more information, see [Create a Knowledge Base](../../2014/data-quality-services/create-a-knowledge-base.md) or [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
3.  <span data-ttu-id="05417-117">Из **Списка доменов** на странице **Управление доменами** выберите составной домен, для которого надо создать доменное правило, или просто создайте новый составной домен.</span><span class="sxs-lookup"><span data-stu-id="05417-117">From the **Domain list** on the **Domain Management** page, select the composite domain that you want to create a domain rule for, or create a new composite domain.</span></span> <span data-ttu-id="05417-118">Если нужно создать новый домен, см. раздел [Create a Composite Domain](../../2014/data-quality-services/create-a-composite-domain.md).</span><span class="sxs-lookup"><span data-stu-id="05417-118">If you have to create a new domain, see [Create a Composite Domain](../../2014/data-quality-services/create-a-composite-domain.md).</span></span>  
  
4.  <span data-ttu-id="05417-119">Перейдите на вкладку **Связи значений** .</span><span class="sxs-lookup"><span data-stu-id="05417-119">Click the **Value Relations** tab.</span></span>  
  
5.  <span data-ttu-id="05417-120">Просмотрите частоту повторения каждого сочетания значений.</span><span class="sxs-lookup"><span data-stu-id="05417-120">View the frequencies displayed for each value combination.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="05417-121">В таблице **Значение** показаны все сочетания значений, существующие в составном домене.</span><span class="sxs-lookup"><span data-stu-id="05417-121">The **Value** table shows each combination of values that exists in the composite domain.</span></span> <span data-ttu-id="05417-122">Каждое значение отображается в отдельном домене, к которому оно относится.</span><span class="sxs-lookup"><span data-stu-id="05417-122">Each value is shown in the single domain that it applies to.</span></span> <span data-ttu-id="05417-123">По умолчанию связи значений в таблице сортируются по частоте, но вы можете щелкнуть другой столбец, чтобы сортировать по этому столбцу.</span><span class="sxs-lookup"><span data-stu-id="05417-123">The default sorting of the value relations table is by frequency, but you can click on another column to sort by that column.</span></span> <span data-ttu-id="05417-124">Отображаются только значения с частотой, большей или равной 20.</span><span class="sxs-lookup"><span data-stu-id="05417-124">Only those values with a frequency greater than or equal to 20 are displayed.</span></span>  
  
6.  <span data-ttu-id="05417-125">Изменить какие-либо значения в этой таблице нельзя.</span><span class="sxs-lookup"><span data-stu-id="05417-125">You cannot change any of the values in the table.</span></span> <span data-ttu-id="05417-126">Если вы выполнили другие операции, нажмите кнопку **Готово** для завершения действия по управлению доменами.</span><span class="sxs-lookup"><span data-stu-id="05417-126">If you have performed other operations, click **Finish** to complete the domain management activity.</span></span> <span data-ttu-id="05417-127">В противном случае нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="05417-127">Otherwise, click **Cancel**.</span></span>  
  
##  <a name="follow-up-after-viewing-value-relations"></a><a name="FollowUp"></a><span data-ttu-id="05417-128">Дальнейшие действия. После просмотра связей значений</span><span class="sxs-lookup"><span data-stu-id="05417-128">Follow Up: After Viewing Value Relations</span></span>  
 <span data-ttu-id="05417-129">После просмотра связей значений в домене можно выполнить другие задачи по управлению доменами, произвести обнаружение знаний для добавления набора знаний в домен или добавить в домен политику сопоставления.</span><span class="sxs-lookup"><span data-stu-id="05417-129">After you view value relations, you can perform other domain management tasks on the domain, you can perform knowledge discovery to add knowledge to the domain, or you can add a matching policy to the domain.</span></span> <span data-ttu-id="05417-130">Дополнительные сведения см. в разделах [Обнаружение набора знаний](../../2014/data-quality-services/perform-knowledge-discovery.md), [Управление доменом](../../2014/data-quality-services/managing-a-domain.md) и [Создание политики сопоставления](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="05417-130">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
  
