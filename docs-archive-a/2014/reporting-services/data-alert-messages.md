---
title: Предупреждающие сообщения | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6819720c-d848-4b90-9b51-89501b4f4645
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d50c3dd24c0057f695a9318c5eef7ad9e7540a45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665868"
---
# <a name="data-alert-messages"></a><span data-ttu-id="2e1dc-102">Предупреждающие сообщения</span><span class="sxs-lookup"><span data-stu-id="2e1dc-102">Data Alert Messages</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="2e1dc-103">доступны два типа предупреждающих сообщений, отправляемых по электронной почте: сообщения с результатами предупреждения об изменении данных и сообщения с описаниями ошибок.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-103">data alerts deliver two types of data alert messages by email: Messages with data alert results and messages with error descriptions.</span></span> <span data-ttu-id="2e1dc-104">Сообщения с результатами информируют всех получателей об изменениях в данных отчетов, представляющих для них интерес и важных для принятия бизнес-решений.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-104">Messages with results keep all recipients informed about changes in report data that is of common interest and important to business decisions.</span></span> <span data-ttu-id="2e1dc-105">Если по какой-то причине произошла ошибка и результаты оказались недоступны, вместо сообщения с результатами будет отправлено сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-105">If for some reason an error occurs and the results are not available, the error message is sent instead.</span></span>

 <span data-ttu-id="2e1dc-106">Владельцы определений предупреждений об изменении данных также могут просматривать сведения об экземплярах предупреждений об изменении данных в диспетчере предупреждения об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-106">The owner of the data alert definition also can view information about the data alert instance in Data Alert Manager.</span></span> <span data-ttu-id="2e1dc-107">Дополнительные сведения см. в статье [Data Alert Manager for SharePoint Users](../../2014/reporting-services/data-alert-manager-for-sharepoint-users.md).</span><span class="sxs-lookup"><span data-stu-id="2e1dc-107">For more information, see [Data Alert Manager for SharePoint Users](../../2014/reporting-services/data-alert-manager-for-sharepoint-users.md).</span></span>

##  <a name="data-alert-messages"></a><a name="DataAlertMessages"></a><span data-ttu-id="2e1dc-108">Сообщения предупреждений об изменении данных</span><span class="sxs-lookup"><span data-stu-id="2e1dc-108">Data Alert Messages</span></span>
 <span data-ttu-id="2e1dc-109">На изображениях ниже показаны предупреждающее сообщение с результатами и предупреждающее сообщение с описанием ошибки.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-109">The following pictures show a data alert message with results and an alert message with an error description.</span></span>

 <span data-ttu-id="2e1dc-110">**Сообщение с результатами**</span><span class="sxs-lookup"><span data-stu-id="2e1dc-110">**Results message**</span></span>

 <span data-ttu-id="2e1dc-111">![Предупреждение, отправленное по электронной почте, о данных с результатами](media/rs-alertmessageresults.gif "Предупреждение, отправленное по электронной почте, о данных с результатами")</span><span class="sxs-lookup"><span data-stu-id="2e1dc-111">![Data alert e-mail message with results](media/rs-alertmessageresults.gif "Data alert e-mail message with results")</span></span>

 <span data-ttu-id="2e1dc-112">**Сообщение об ошибке**</span><span class="sxs-lookup"><span data-stu-id="2e1dc-112">**Error message**</span></span>

 <span data-ttu-id="2e1dc-113">![Предупреждение о данных с сообщением об ошибке](media/rs-alertmessageerrror.gif "Предупреждение о данных с сообщением об ошибке")</span><span class="sxs-lookup"><span data-stu-id="2e1dc-113">![Data alert message with error message](media/rs-alertmessageerrror.gif "Data alert message with error message")</span></span>

 <span data-ttu-id="2e1dc-114">Эти сообщения включают в себя те же типы информации.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-114">The messages include the same types of information.</span></span>

1.  <span data-ttu-id="2e1dc-115">Поле**От имени** содержит имя пользователя, создавшего определение предупреждения об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-115">**On behalf of** contains the name of the person who created the data alert definition.</span></span>

2.  <span data-ttu-id="2e1dc-116">Если в определении предупреждения включено описание, оно будет отображено ниже в поле **От имени**.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-116">If you provided a description in the alert definition, it displays below **On behalf of**.</span></span>

3.  <span data-ttu-id="2e1dc-117">Поле**Результаты предупреждения** отображает строки в веб-канале данных, удовлетворяющие определению предупреждения, в табличном формате или отображает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-117">**Alert Results** display the rows in the report data feed that satisfy the rules specified in the alert definition in a tabular format or display an error description.</span></span> <span data-ttu-id="2e1dc-118">Ограничения на количество отображаемых строк не существует.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-118">There is no limit on the number of rows that displays.</span></span>

4.  <span data-ttu-id="2e1dc-119">**Перейти к отчету** — это ссылка на отчет, на основе которого построено определение предупреждения.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-119">**Go to report** is a link to the report that the alert definition is built upon.</span></span> <span data-ttu-id="2e1dc-120">Если ссылка недействительна из-за того, что отчет был перемещен или удален, будет отображено сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-120">If the link is not valid because the report was moved or deleted, an error message displays.</span></span>

5.  <span data-ttu-id="2e1dc-121">В поле**Правила** перечисляются правила и предложения из определения предупреждения.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-121">**Rule(s)** lists the rules and clauses in the alert definition.</span></span> <span data-ttu-id="2e1dc-122">Эти сведения помогают проверить и понять результаты предупреждения и определить правила определения предупреждения об изменении данных, которые можно изменить для расширения или сужения объема возвращаемых результатов.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-122">This information helps you verify and understand the alert results and identify rules in the data alert definition that you might want to change to narrow or broaden results.</span></span>

6.  <span data-ttu-id="2e1dc-123">В поле**Параметры отчета** перечисляются параметры и значения параметров, используемые при запуске отчета.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-123">**Report parameters** list the parameters and parameter values that were used when the report was run.</span></span> <span data-ttu-id="2e1dc-124">Параметры и значения параметров помогают понять результаты предупреждения.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-124">Parameters and parameter values help you understand the alert results.</span></span>

7.  <span data-ttu-id="2e1dc-125">В поле**Контекстуальные значения** перечисляются имена и значения элементов отчета, которые находятся вне областей данных отчета.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-125">**Contextual values** list the names and values of report items that are outside of the report data regions.</span></span> <span data-ttu-id="2e1dc-126">Обычно элементами являются текстовые поля.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-126">The items are typically text boxes.</span></span> <span data-ttu-id="2e1dc-127">Например, текстовое поле с постоянным значением — тема или описание отчета.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-127">For example, a text box with a constant value such as the subject or description of a report.</span></span>

 <span data-ttu-id="2e1dc-128">Единственным различием между двумя типами сообщений является элемент 5, **Результаты предупреждения**.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-128">The only difference between the two message types is item 5, **Alert Results**.</span></span> <span data-ttu-id="2e1dc-129">Если при создании экземпляра предупреждения об изменении данных или предупреждающего сообщения происходит ошибка, в поле **Результаты предупреждения** отображается сообщение об ошибке, описывающее проблему.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-129">If an error occurs when a data alert instance or data alert message is created, **Alert Results** displays an error message that describes the problem.</span></span> <span data-ttu-id="2e1dc-130">Сообщение об ошибке, отправленное всем получателям, позволяет им узнать, что ожидаемые результаты предупреждений, которые могли быть необходимы для принятия бизнес-решений, недоступны.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-130">The error message, sent to all recipients, let them know that the alert results that they are expecting and might rely on to make business decisions are not available.</span></span>

 

##  <a name="related-tasks"></a><a name="HowTo"></a> <span data-ttu-id="2e1dc-131">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="2e1dc-131">Related Tasks</span></span>
 <span data-ttu-id="2e1dc-132">В этом разделе перечисляются процедуры, показывающие, как можно создавать и редактировать определения предупреждений об изменении данных, предоставляющие большинство сведений, доступных в предупреждающих сообщениях.</span><span class="sxs-lookup"><span data-stu-id="2e1dc-132">This section lists procedures that show you how to create and edit the data alert definitions that provide much of the information that you see in data alert messages.</span></span>

-   [<span data-ttu-id="2e1dc-133">Создание предупреждения данных в конструкторе предупреждений</span><span class="sxs-lookup"><span data-stu-id="2e1dc-133">Create a Data Alert in Data Alert Designer</span></span>](create-a-data-alert-in-data-alert-designer.md)

-   [<span data-ttu-id="2e1dc-134">Изменение предупреждения в конструкторе предупреждений</span><span class="sxs-lookup"><span data-stu-id="2e1dc-134">Edit a Data Alert in Alert Designer</span></span>](edit-a-data-alert-in-alert-designer.md)



## <a name="see-also"></a><span data-ttu-id="2e1dc-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="2e1dc-135">See Also</span></span>
 <span data-ttu-id="2e1dc-136">[Конструктор предупреждений об изменении данных](../../2014/reporting-services/data-alert-designer.md) [Reporting Services предупреждения](../ssms/agent/alerts.md) об изменении данных</span><span class="sxs-lookup"><span data-stu-id="2e1dc-136">[Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>


