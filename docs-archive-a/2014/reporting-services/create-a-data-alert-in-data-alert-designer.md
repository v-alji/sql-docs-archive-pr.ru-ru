---
title: Создание предупреждения данных в конструкторе предупреждений | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8464ab9d-afe1-4490-955f-9f3319bcbf8d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 19c3001d4663848c009a353baa068f237d4a0b5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735122"
---
# <a name="create-a-data-alert-in-data-alert-designer"></a><span data-ttu-id="8593d-102">Создание предупреждения данных в конструкторе предупреждений данных</span><span class="sxs-lookup"><span data-stu-id="8593d-102">Create a Data Alert in Data Alert Designer</span></span>
  <span data-ttu-id="8593d-103">Создание определений предупреждений об изменении данных осуществляется в конструкторе предупреждений об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="8593d-103">You create data alert definitions in Data Alert Designer.</span></span> <span data-ttu-id="8593d-104">После сохранения их можно открыть, изменить, а затем снова сохранить в конструкторе предупреждений об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="8593d-104">After you save the alert definitions, you can reopen, edit, and then resave them in Data Alert Designer.</span></span> <span data-ttu-id="8593d-105">Дополнительные сведения об изменении определений предупреждений см. в разделах [Управление предупреждениями данных в диспетчере предупреждений данных](manage-my-data-alerts-in-data-alert-manager.md) и [Изменение предупреждения данных в конструкторе предупреждений](edit-a-data-alert-in-alert-designer.md).</span><span class="sxs-lookup"><span data-stu-id="8593d-105">For information about editing alert definitions, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md) and [Edit a Data Alert in Alert Designer](edit-a-data-alert-in-alert-designer.md).</span></span>

### <a name="to-create-a-data-alert-definition"></a><span data-ttu-id="8593d-106">Создание определения предупреждения об изменении данных</span><span class="sxs-lookup"><span data-stu-id="8593d-106">To create a data alert definition</span></span>

1.  <span data-ttu-id="8593d-107">Найдите библиотеку SharePoint, содержащую отчет, для которого требуется создать определение предупреждения об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="8593d-107">Locate the SharePoint library that contains the report that you want to create a data alert definition for.</span></span>

2.  <span data-ttu-id="8593d-108">Щелкните отчет.</span><span class="sxs-lookup"><span data-stu-id="8593d-108">Click the report.</span></span>

     <span data-ttu-id="8593d-109">Начнется выполнение отчета.</span><span class="sxs-lookup"><span data-stu-id="8593d-109">The report runs.</span></span> <span data-ttu-id="8593d-110">Если отчет является параметризованным, убедитесь, что в отчете отображаются данные, для которых должны вы хотите получать предупреждающие сообщения.</span><span class="sxs-lookup"><span data-stu-id="8593d-110">If the report is parameterized, verify that the report shows the data that you want to receive alert messages about.</span></span> <span data-ttu-id="8593d-111">Если нужные столбцы или значения не отображаются, может потребоваться повторно выполнить отчет, используя другие значения параметров.</span><span class="sxs-lookup"><span data-stu-id="8593d-111">If you do not see the columns or values you are interested in, you might want to rerun the report, using different parameter values.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="8593d-112">Значения параметров, выбранные для запуска отчета, сохраняются в определении предупреждения и будут использоваться при повторном запуске отчета в ходе обработки определения предупреждения.</span><span class="sxs-lookup"><span data-stu-id="8593d-112">The parameter values you chose to run the report are saved in the alert definition and will be used when report is rerun as a step in processing the alert definition.</span></span> <span data-ttu-id="8593d-113">Для использования других значений параметров, следует создать новое определение предупреждения.</span><span class="sxs-lookup"><span data-stu-id="8593d-113">To use different parameter values, you must create a new alert definition.</span></span>

3.  <span data-ttu-id="8593d-114">В меню **Действия** выберите **Создать предупреждение об изменении данных**.</span><span class="sxs-lookup"><span data-stu-id="8593d-114">On the **Actions** menu, click **New Data Alert**.</span></span>

     <span data-ttu-id="8593d-115">Меню **Действия** показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="8593d-115">The following picture shows the **Actions** menu.</span></span>

     <span data-ttu-id="8593d-116">![Открытие конструктора предупреждений из библиотеки SharePoint](media/rs-openalertdesigneriw.gif "Открытие конструктора предупреждений из библиотеки SharePoint")</span><span class="sxs-lookup"><span data-stu-id="8593d-116">![Open Alert Designer from SharePoint library](media/rs-openalertdesigneriw.gif "Open Alert Designer from SharePoint library")</span></span>

     <span data-ttu-id="8593d-117">Откроется конструктор предупреждений об изменении данных и отобразит первые 100 строк первого потока данных, создаваемого отчетом в таблице.</span><span class="sxs-lookup"><span data-stu-id="8593d-117">The Data Alert Designer opens, showing the first 100 rows of the first data feed that the report generates in a table.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="8593d-118">Если команда **Создать предупреждение об изменении данных** не видна, это означает, что служба предупреждений не настроена на сайте SharePoint или что в выпуск [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] не включены предупреждения об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="8593d-118">If you do not see the **New Data Alert** option, the alerting service is not configured on the SharePoint site or the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] edition does not include data alerts.</span></span> <span data-ttu-id="8593d-119">Дополнительные сведения см. в разделе [Служба SharePoint и приложения служб Reporting Services](../../2014/reporting-services/reporting-services-sharepoint-service-and-service-applications.md).</span><span class="sxs-lookup"><span data-stu-id="8593d-119">For more information, see [Reporting Services SharePoint Service and Service Applications](../../2014/reporting-services/reporting-services-sharepoint-service-and-service-applications.md).</span></span>
    > 
    >  <span data-ttu-id="8593d-120">Если команда **Создать предупреждение об изменении данных** затенена, это означает, что источник данных отчета настроен на использование учетных данных встроенной безопасности или приглашений к вводу учетных данных.</span><span class="sxs-lookup"><span data-stu-id="8593d-120">If the **New Data Alert** option is grayed, the report data source is configured to use integrated security credentials or prompt for credentials.</span></span> <span data-ttu-id="8593d-121">Чтобы сделать команду **Создать предупреждение об изменении данных** доступной, необходимо обновить источник данных для использования сохраненных учетных данных или на работу без учетных данных.</span><span class="sxs-lookup"><span data-stu-id="8593d-121">To make the **New Data Alert** option available, you must update the data source to use stored credentials or no credentials.</span></span>

     <span data-ttu-id="8593d-122">Имя веб-канала данных будет отображено в раскрывающемся списке **Имя данных отчета** .</span><span class="sxs-lookup"><span data-stu-id="8593d-122">The name of the data feed appears in **Report data name** drop-down list.</span></span>

4.  <span data-ttu-id="8593d-123">При необходимости выберите другой веб-канал данных в раскрывающемся списке **Имя данных отчета** .</span><span class="sxs-lookup"><span data-stu-id="8593d-123">Optionally, select a different data feed in the **Report data name** drop-down list.</span></span>

     <span data-ttu-id="8593d-124">Если при выполнении отчета веб-канал данных не создается, создать определение предупреждения для отчета невозможно.</span><span class="sxs-lookup"><span data-stu-id="8593d-124">If no data feed is generated from the report, you cannot create an alert definition for the report.</span></span> <span data-ttu-id="8593d-125">Макет отчета определяет содержимое каждого веб-канала данных.</span><span class="sxs-lookup"><span data-stu-id="8593d-125">The layout of the report determines the content of each data feed.</span></span> <span data-ttu-id="8593d-126">Дополнительные сведения см. в статьях [Создание веб-каналов данных из отчетов &#40;построитель отчетов и службы SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8593d-126">For more information see, [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>

5.  <span data-ttu-id="8593d-127">При необходимости измените имя по умолчанию в текстовом поле **Имя предупреждения** , чтобы сделать его более значимым.</span><span class="sxs-lookup"><span data-stu-id="8593d-127">Optionally, in the **Alert name** text box, update the default name to be more meaningful.</span></span>

     <span data-ttu-id="8593d-128">По умолчанию этому определению предупреждения присваивается имя отчета.</span><span class="sxs-lookup"><span data-stu-id="8593d-128">The default name of the alert definition is the name of the report.</span></span> <span data-ttu-id="8593d-129">Имена определений предупреждений не обязательно должны быть уникальными, поэтому может оказаться, что при последующем просмотре списка предупреждений в диспетчере предупреждений об изменении данных их трудно отличить друг от друга.</span><span class="sxs-lookup"><span data-stu-id="8593d-129">Alert definition names do not have to be unique, which can make it difficult to tell them apart when you later view the list of your alerts in Data Alert Manager.</span></span> <span data-ttu-id="8593d-130">Рекомендуется использовать продуманные и уникальные имена для определений предупреждений.</span><span class="sxs-lookup"><span data-stu-id="8593d-130">It is recommended that you use meaningful and unique names for your alert definitions.</span></span>

6.  <span data-ttu-id="8593d-131">При необходимости замените параметр работы с данными **все данные, имеющиеся в потоке данных**, применяемый по умолчанию, параметром **без каких-либо данных, имеющихся в веб-канале данных**.</span><span class="sxs-lookup"><span data-stu-id="8593d-131">Optionally, change the default data option from **any data in the data feed has** to **no data in the data feed has**.</span></span>

7.  <span data-ttu-id="8593d-132">Нажмите кнопку **Добавить правило**.</span><span class="sxs-lookup"><span data-stu-id="8593d-132">Click **Add rule**.</span></span>

     <span data-ttu-id="8593d-133">Будет отображен список столбцов в веб-канале данных.</span><span class="sxs-lookup"><span data-stu-id="8593d-133">A list of the columns in the data feed appears.</span></span>

8.  <span data-ttu-id="8593d-134">В списке выберите столбец, который требуется использовать в правиле, затем выберите оператор сравнения и введите пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="8593d-134">In the list, select the column that you want to use in the rule, and then select a comparison operator and enter the threshold value.</span></span>

     <span data-ttu-id="8593d-135">В зависимости от типа данных выбранного столбца отображаются различные операторы сравнения.</span><span class="sxs-lookup"><span data-stu-id="8593d-135">Depending on the data type of the selected column, different comparison operators are listed.</span></span> <span data-ttu-id="8593d-136">Если столбец имеет тип данных date, рядом с пороговым значением для данного правила отображается значок календаря.</span><span class="sxs-lookup"><span data-stu-id="8593d-136">If the column has a date data type, a calendar icon displays next to threshold value for the rule.</span></span> <span data-ttu-id="8593d-137">Можно задать дату путем выбора ее в календаре или ввода значения даты.</span><span class="sxs-lookup"><span data-stu-id="8593d-137">You can enter a data by clicking a date in the calendar or typing the date.</span></span>

     <span data-ttu-id="8593d-138">В конструкторе предупреждений об изменении данных доступны два режима сравнения: **режим ввода значений** и **режим выбора поля**.</span><span class="sxs-lookup"><span data-stu-id="8593d-138">Data Alert Designer provides two comparison modes: **Value Entry Mode** and **Field Selection Mode**.</span></span> <span data-ttu-id="8593d-139">По умолчанию используется **режим ввода значений**.</span><span class="sxs-lookup"><span data-stu-id="8593d-139">The default mode is **Value Entry Mode**.</span></span> <span data-ttu-id="8593d-140">Предложения OR можно добавлять только в **режиме ввода значений** при использовании сравнения **is** .</span><span class="sxs-lookup"><span data-stu-id="8593d-140">You can add OR clauses only when you are in **Value Entry Mode** and are using the **is** comparison.</span></span>

9. <span data-ttu-id="8593d-141">Чтобы добавить предложение OR, щелкните стрелку вниз и выберите **режим ввода значений**.</span><span class="sxs-lookup"><span data-stu-id="8593d-141">To add an OR clause, click the down-arrow, and then click **Value Entry Mode**.</span></span>

10. <span data-ttu-id="8593d-142">Введите значение для сравнения.</span><span class="sxs-lookup"><span data-stu-id="8593d-142">Type the comparison value.</span></span>

11. <span data-ttu-id="8593d-143">При необходимости нажмите кнопку с многоточием **(...)** еще раз.</span><span class="sxs-lookup"><span data-stu-id="8593d-143">Optionally, click the ellipsis **(...)** again.</span></span>

     <span data-ttu-id="8593d-144">Многоточие **(...)** отображается в строке, содержащей первое предложение.</span><span class="sxs-lookup"><span data-stu-id="8593d-144">The ellipsis **(...)** appears on the line that contains the first clause.</span></span>

     <span data-ttu-id="8593d-145">Предложение OR добавляется ниже и в рамках правила AND.</span><span class="sxs-lookup"><span data-stu-id="8593d-145">An OR clause is added below and within the AND rule.</span></span>

12. <span data-ttu-id="8593d-146">Дополнительно можно щелкнуть стрелку вниз, выбрать **режим выбора поля**, а затем столбец из списка.</span><span class="sxs-lookup"><span data-stu-id="8593d-146">Optionally, click the down-arrow, select **Field Selection Mode**, and then select a column in the list.</span></span>

     <span data-ttu-id="8593d-147">Вы увидите, что многоточие **(...)** , которую вы щелкнули для добавления предложений OR, исчезло.</span><span class="sxs-lookup"><span data-stu-id="8593d-147">You will notice that the ellipsis **(...)** that you click to add OR clauses has disappeared.</span></span>

13. <span data-ttu-id="8593d-148">При необходимости нажмите кнопку **Добавить правило** еще раз, чтобы добавить дополнительные правила.</span><span class="sxs-lookup"><span data-stu-id="8593d-148">Optionally, click **Add rule** again to add additional rules.</span></span>

     <span data-ttu-id="8593d-149">Несколько правил объединяются с помощью логического оператора AND.</span><span class="sxs-lookup"><span data-stu-id="8593d-149">The rules are combined by using the AND logical operator.</span></span>

14. <span data-ttu-id="8593d-150">Выберите параметр в списке вхождений.</span><span class="sxs-lookup"><span data-stu-id="8593d-150">Select an option in the recurrence list.</span></span> <span data-ttu-id="8593d-151">Введите интервал с учетом типа вхождения.</span><span class="sxs-lookup"><span data-stu-id="8593d-151">Depending on the type of recurrence, enter an interval.</span></span>

15. <span data-ttu-id="8593d-152">При необходимости выберите **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="8593d-152">Optionally, click **Advanced**.</span></span>

16. <span data-ttu-id="8593d-153">При необходимости измените дату, с которой начинается использование предупреждающего сообщения, введя другую дату или открыв календарь и выбрав дату в календаре.</span><span class="sxs-lookup"><span data-stu-id="8593d-153">Optionally, change the date that the alert message starts on by typing a different date or opening the calendar, and then clicking a date in the calendar.</span></span>

     <span data-ttu-id="8593d-154">По умолчанию датой начала является текущая дата.</span><span class="sxs-lookup"><span data-stu-id="8593d-154">The default start date is the current date.</span></span>

17. <span data-ttu-id="8593d-155">При необходимости установите флажок, находящийся рядом с полем **Остановить предупреждение в**, а затем выберите дату окончания использования предупреждающего сообщения.</span><span class="sxs-lookup"><span data-stu-id="8593d-155">Optionally, select the checkbox located next to **Stop alert on**, and then choose a date to stop the alert message.</span></span>

     <span data-ttu-id="8593d-156">По умолчанию предупреждающее сообщение не имеет дату окончания использования.</span><span class="sxs-lookup"><span data-stu-id="8593d-156">By default, an alert message has no stop date.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="8593d-157">При остановке предупреждающего сообщения не происходит удаления определения предупреждения.</span><span class="sxs-lookup"><span data-stu-id="8593d-157">Stopping an alert message does not delete the alert definition.</span></span> <span data-ttu-id="8593d-158">После остановки предупреждающего сообщения его можно запустить повторно, обновив даты запуска и остановки.</span><span class="sxs-lookup"><span data-stu-id="8593d-158">After you stop an alert message, you can restart it by updating the start and stop dates.</span></span> <span data-ttu-id="8593d-159">Дополнительные сведения об удалении определений предупреждений см. в разделах [Управление предупреждениями данных в диспетчере предупреждений данных](manage-my-data-alerts-in-data-alert-manager.md).</span><span class="sxs-lookup"><span data-stu-id="8593d-159">For information about deleting alert definitions, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md).</span></span>

18. <span data-ttu-id="8593d-160">При необходимости снимите флажок **Отправлять сообщение только при изменении результатов** .</span><span class="sxs-lookup"><span data-stu-id="8593d-160">Optionally, clear the **Send message only if results change** checkbox.</span></span>

     <span data-ttu-id="8593d-161">Если предупреждающие сообщения отправляются часто, это может привести к появлению излишних данных. Этот флажок снимать не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="8593d-161">If you send alert messages frequently, redundant information might not be welcome and you should not clear this checkbox.</span></span>

19. <span data-ttu-id="8593d-162">Введите электронные адреса получателей сообщения с предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="8593d-162">Enter the email addresses of alert message recipients.</span></span> <span data-ttu-id="8593d-163">Разделите адреса точками с запятой.</span><span class="sxs-lookup"><span data-stu-id="8593d-163">Separate addresses with semicolons.</span></span>

     <span data-ttu-id="8593d-164">Если доступен адрес электронной почты пользователя, создавшего определение предупреждения, он добавляется в поле **Получатели** .</span><span class="sxs-lookup"><span data-stu-id="8593d-164">If the email address of the person who created the alert definition is available, it is added to the **Recipient(s)** box.</span></span>

20. <span data-ttu-id="8593d-165">Дополнительно в текстовом поле **Тема** можно обновить строку «Тема» предупреждающего сообщения.</span><span class="sxs-lookup"><span data-stu-id="8593d-165">Optionally, in the **Subject** text box, update the Subject line of the alert message.</span></span>

     <span data-ttu-id="8593d-166">Тема по умолчанию — \*\*предупреждение данных \<data alert name> для \*\*.</span><span class="sxs-lookup"><span data-stu-id="8593d-166">The default Subject is **Data alert for \<data alert name>**.</span></span>

21. <span data-ttu-id="8593d-167">При необходимости в текстовом поле **Описание** введите описание предупреждающего сообщения.</span><span class="sxs-lookup"><span data-stu-id="8593d-167">Optionally, in the **Description** text box, type a description of the alert message.</span></span>

22. <span data-ttu-id="8593d-168">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8593d-168">Click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="8593d-169">См. также:</span><span class="sxs-lookup"><span data-stu-id="8593d-169">See Also</span></span>
 <span data-ttu-id="8593d-170">Диспетчер предупреждений [данных](../../2014/reporting-services/data-alert-designer.md) Data [Manager для оповещения администраторов](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services предупреждения](../ssms/agent/alerts.md) об изменении данных</span><span class="sxs-lookup"><span data-stu-id="8593d-170">[Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) [Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>


