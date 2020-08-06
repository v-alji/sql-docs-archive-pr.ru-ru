---
title: Занятие 3. Определение управляемой данными подписки | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 89197b9b-7502-4fe2-bea3-ed7943eebf3b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d1bbc25bdd08b369180e31378a6d25a595badbcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751799"
---
# <a name="lesson-3-defining-a-data-driven-subscription"></a><span data-ttu-id="57be4-102">Lesson 3: Defining a Data-Driven Subscription</span><span class="sxs-lookup"><span data-stu-id="57be4-102">Lesson 3: Defining a Data-Driven Subscription</span></span>
  <span data-ttu-id="57be4-103">На этом занятии будет использована управляемая данными подписка для подключения к источнику данных подписки, построен запрос, получающий данные для этой подписки, а также сопоставлен результирующий набор с отчетом и параметрами доставки.</span><span class="sxs-lookup"><span data-stu-id="57be4-103">In this lesson, you use the data-driven subscription pages to connect to a subscription data source, build a query that retrieves subscription data, and map the result set to report and delivery options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="57be4-104">Перед началом работы убедитесь, что служба агента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] запущена.</span><span class="sxs-lookup"><span data-stu-id="57be4-104">Before you start, verify that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service is running.</span></span> <span data-ttu-id="57be4-105">Если она не запущена, подписку сохранить не удастся.</span><span class="sxs-lookup"><span data-stu-id="57be4-105">If it is not running, you cannot save the subscription.</span></span>  
  
 <span data-ttu-id="57be4-106">В этом занятии предполагается, что занятия 1 и 2 пройдены и источник данных отчета использует сохраненные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="57be4-106">This lesson assumes you completed Lesson 1 and Lesson 2 and that the report data source uses stored credentials.</span></span>  <span data-ttu-id="57be4-107">Дополнительные сведения см. в разделе [Занятие 2. Изменение свойств источника данных отчета](../reporting-services/lesson-2-modifying-the-report-data-source-properties.md).</span><span class="sxs-lookup"><span data-stu-id="57be4-107">For more information, see [Lesson 2: Modifying the Report Data Source Properties](../reporting-services/lesson-2-modifying-the-report-data-source-properties.md)</span></span>  
  
 <span data-ttu-id="57be4-108">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="57be4-108">In this topic:</span></span>  
  
-   [<span data-ttu-id="57be4-109">Запуск мастера управляемой данными подписки</span><span class="sxs-lookup"><span data-stu-id="57be4-109">Start the Data-Driven Subscription Wizard</span></span>](#bkmk_startwizard)  
  
-   [<span data-ttu-id="57be4-110">Шаг 1. Задайте подписку</span><span class="sxs-lookup"><span data-stu-id="57be4-110">Step 1 - Define a description</span></span>](#bkmk_definesubscription)  
  
-   [<span data-ttu-id="57be4-111">Шаг 2. Задайте соединение с источником данных подписчика</span><span class="sxs-lookup"><span data-stu-id="57be4-111">Step 2 - Define a Connection to the Subscriber Data Source</span></span>](#bkmk_defineconnectiontosubscriber)  
  
-   [<span data-ttu-id="57be4-112">Шаг 3. Определите запрос для получения данных подписчика</span><span class="sxs-lookup"><span data-stu-id="57be4-112">Step 3 - Define a Query to Retrieve Subscriber data</span></span>](#bkmk_definequery)  
  
-   [<span data-ttu-id="57be4-113">Шаг 4. Задайте параметры доставки</span><span class="sxs-lookup"><span data-stu-id="57be4-113">Step 4 - Set Delivery Options</span></span>](#bkmk_set_deliveryoptions)  
  
-   [<span data-ttu-id="57be4-114">Шаг 5. Задайте значение параметра для изменения вывода отчета</span><span class="sxs-lookup"><span data-stu-id="57be4-114">Step 5 - Configure a Parameter Value to Very Report Output</span></span>](#bkmk_configure_parameter)  
  
-   [<span data-ttu-id="57be4-115">Шаг 6. Создайте расписание для подписки</span><span class="sxs-lookup"><span data-stu-id="57be4-115">Step 6 - To Schedule a Subscription</span></span>](#bkmk_schedule_subscription)  
  
##  <a name="start-the-data-driven-subscription-wizard"></a><a name="bkmk_startwizard"></a><span data-ttu-id="57be4-116">Запуск мастера управляемой данными подписки</span><span class="sxs-lookup"><span data-stu-id="57be4-116">Start the Data-Driven Subscription Wizard</span></span>  
  
1.  <span data-ttu-id="57be4-117">В диспетчере отчетов нажмите кнопку **Корневая папка**и перейдите к папке, содержащей отчет **Sales Orders** (сводка продаж по сотрудникам отдела продаж).</span><span class="sxs-lookup"><span data-stu-id="57be4-117">In Report Manager, click **Home**, and navigate to the folder containing the **Sales Orders** report.</span></span>  
  
2.  <span data-ttu-id="57be4-118">В контекстном меню отчета выберите пункт **Управление**, а затем перейдите на вкладку **Подписки** .</span><span class="sxs-lookup"><span data-stu-id="57be4-118">In the context menu of the report, click **Manage**, and then click the **Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="57be4-119">Щелкните **Создать управляемую данными подписку**.</span><span class="sxs-lookup"><span data-stu-id="57be4-119">Click **New Data-driven Subscription**.</span></span> <span data-ttu-id="57be4-120">Если указанная кнопка не видна, это означает отсутствие разрешений диспетчера содержимого.</span><span class="sxs-lookup"><span data-stu-id="57be4-120">If you do not see this button, you do not have Content Manager permissions.</span></span>  
  
##  <a name="step-1---define-a-description"></a><a name="bkmk_definesubscription"></a><span data-ttu-id="57be4-121">Шаг 1. Определение описания</span><span class="sxs-lookup"><span data-stu-id="57be4-121">Step 1 - Define a description</span></span>  
  
1.  <span data-ttu-id="57be4-122">В качестве описания введите **Sales Order delivery** (Доставка заказа на продажу).</span><span class="sxs-lookup"><span data-stu-id="57be4-122">Type **Sales Order delivery** in description.</span></span>  
  
2.  <span data-ttu-id="57be4-123">В раскрывающемся списке **Указать способ уведомления получателей** выберите **Общая папка Windows**.</span><span class="sxs-lookup"><span data-stu-id="57be4-123">Select **Windows FileShare** for **Specify how recipients are notified**.</span></span>  
  
3.  <span data-ttu-id="57be4-124">Выберите **Указать только для этой подписки**и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="57be4-124">Select **Specify for this subscription only**, and then click **Next**.</span></span>  
  
##  <a name="step-2---define-a-connection-to-the-subscriber-data-source"></a><a name="bkmk_defineconnectiontosubscriber"></a><span data-ttu-id="57be4-125">Шаг 2. Определение соединения с источником данных подписчика</span><span class="sxs-lookup"><span data-stu-id="57be4-125">Step 2 - Define a Connection to the Subscriber Data Source</span></span>  
  
1.  <span data-ttu-id="57be4-126">В качестве типа источника данных выберите **Microsoft SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="57be4-126">Select **Microsoft SQL Server** as the data source type.</span></span>  
  
2.  <span data-ttu-id="57be4-127">В поле «Строка подключения» введите следующую строку:</span><span class="sxs-lookup"><span data-stu-id="57be4-127">In Connection string, type the following connection string:</span></span>  
  
    ```  
    data source=localhost; initial catalog=Subscribers  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="57be4-128">Подписчики — это база данных, созданная во время занятия 1</span><span class="sxs-lookup"><span data-stu-id="57be4-128">Subscribers is the database you created in lesson 1.</span></span>  
  
3.  <span data-ttu-id="57be4-129">Щелкните **Учетные данные, которые безопасно хранятся на сервере отчетов**.</span><span class="sxs-lookup"><span data-stu-id="57be4-129">Click **Credentials stored securely in the report server**.</span></span>  
  
4.  <span data-ttu-id="57be4-130">В полях **Имя пользователя** и **Пароль**введите доменное имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="57be4-130">In **User Name** and **Password**, type your domain user name and password.</span></span> <span data-ttu-id="57be4-131">При указании значения **Имя пользователя**необходимо включать как домен, так и учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="57be4-131">Include both the domain and user account when specifying **User Name**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="57be4-132">Учетные данные, используемые для подключения к источникам данных подписчика, не передаются обратно в среду [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57be4-132">Credentials used to connect to a subscriber data source are not passed back to [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="57be4-133">При последующем изменении параметров подписки потребуется ввести пароль для подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="57be4-133">If you modify the subscription later, you must retype the password used to connect to the data source.</span></span>  
  
5.  <span data-ttu-id="57be4-134">Выберите **Использовать учетные данные Windows при подключении к источнику данных**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="57be4-134">Select **Use as windows credentials when connecting to the data source**, and then click **Next**.</span></span>  
  
##  <a name="step-3---define-a-query-to-retrieve-subscriber-data"></a><a name="bkmk_definequery"></a><span data-ttu-id="57be4-135">Шаг 3. Определение запроса для получения данных подписчика</span><span class="sxs-lookup"><span data-stu-id="57be4-135">Step 3 - Define a Query to Retrieve Subscriber data</span></span>  
  
1.  <span data-ttu-id="57be4-136">Введите следующий запрос в поле запроса:</span><span class="sxs-lookup"><span data-stu-id="57be4-136">In the query box, type the following query:</span></span>  
  
    ```  
    Select * from OrderInfo  
    ```  
  
2.  <span data-ttu-id="57be4-137">Задайте время ожидания 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="57be4-137">Specify a time-out of 30 seconds.</span></span>  
  
3.  <span data-ttu-id="57be4-138">Нажмите кнопку **Проверить**, а затем кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="57be4-138">Click **Validate**, and then click **Next**.</span></span>  
  
##  <a name="step-4---set-delivery-options"></a><a name="bkmk_set_deliveryoptions"></a><span data-ttu-id="57be4-139">Шаг 4. Настройка параметров доставки</span><span class="sxs-lookup"><span data-stu-id="57be4-139">Step 4 - Set Delivery Options</span></span>  
  
1.  <span data-ttu-id="57be4-140">Для параметра **Имя файла**выберите **Получить значение из базы данных**.</span><span class="sxs-lookup"><span data-stu-id="57be4-140">For **File name**, select **Get the value from the database**.</span></span> <span data-ttu-id="57be4-141">Выберите поле **Order**.</span><span class="sxs-lookup"><span data-stu-id="57be4-141">Select the field **Order**.</span></span>  
  
2.  <span data-ttu-id="57be4-142">Для параметра **Путь**выберите **Указать статическое значение**.</span><span class="sxs-lookup"><span data-stu-id="57be4-142">For **Path**, select **Specify a static value**.</span></span> <span data-ttu-id="57be4-143">В поле «Значение параметра» введите имя общей папки, для которой имеется разрешение на запись (например: `\\mycomputer\public\myreports`).</span><span class="sxs-lookup"><span data-stu-id="57be4-143">In Setting Value, type the name of a public file share for which you have write permissions (for example, `\\mycomputer\public\myreports`).</span></span>  
  
3.  <span data-ttu-id="57be4-144">Для параметра **Формат обработки**выберите **Получить значение из базы данных**.</span><span class="sxs-lookup"><span data-stu-id="57be4-144">For **Render Format**, select **Get the value from the database**.</span></span> <span data-ttu-id="57be4-145">Выберите **Формат**.</span><span class="sxs-lookup"><span data-stu-id="57be4-145">Select **Format**.</span></span>  
  
4.  <span data-ttu-id="57be4-146">Для параметра **Режим записи**выберите **Указать статическое значение** , а затем выберите **Автоувеличение**.</span><span class="sxs-lookup"><span data-stu-id="57be4-146">For **Write mode**, select **Specify a static value** and select **AutoIncrement**.</span></span>  
  
5.  <span data-ttu-id="57be4-147">Для параметра **Расширение файла**выберите **Указать статическое значение** , а затем ― **True**.</span><span class="sxs-lookup"><span data-stu-id="57be4-147">For **File Extension**, select **Specify a static value** and select **True**.</span></span>  
  
6.  <span data-ttu-id="57be4-148">Для параметра **Имя пользователя**выберите **Указать статическое значение**.</span><span class="sxs-lookup"><span data-stu-id="57be4-148">For **User name**, select **Specify a static value**.</span></span> <span data-ttu-id="57be4-149">Введите учетную запись пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="57be4-149">Type your domain user account.</span></span> <span data-ttu-id="57be4-150">Введите ее в указанном формате: `<domain>\<account>`.</span><span class="sxs-lookup"><span data-stu-id="57be4-150">Enter it in this format: `<domain>\<account>`.</span></span> <span data-ttu-id="57be4-151">Учетная запись пользователя должна обладать разрешениями на путь, заданный в предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="57be4-151">The user account needs to have permissions to the path you configured in the previous steps.</span></span>  
  
7.  <span data-ttu-id="57be4-152">Для параметра **Пароль**выберите **Указать статическое значение**.</span><span class="sxs-lookup"><span data-stu-id="57be4-152">For **Password**, select **Specify a static value**.</span></span> <span data-ttu-id="57be4-153">Введите пароль.</span><span class="sxs-lookup"><span data-stu-id="57be4-153">Type your password.</span></span> <span data-ttu-id="57be4-154">Вводите пароль внимательно.</span><span class="sxs-lookup"><span data-stu-id="57be4-154">Be sure that you type the password carefully.</span></span> <span data-ttu-id="57be4-155">Мастер не проводит проверку пароля.</span><span class="sxs-lookup"><span data-stu-id="57be4-155">The wizard does not validate the password.</span></span>  
  
8.  <span data-ttu-id="57be4-156">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="57be4-156">Click **Next.**</span></span>  
  
##  <a name="step-5---configure-a-parameter-value-to-very-report-output"></a><a name="bkmk_configure_parameter"></a><span data-ttu-id="57be4-157">Шаг 5. Настройка значения параметра для очень большого вывода отчета</span><span class="sxs-lookup"><span data-stu-id="57be4-157">Step 5 - Configure a Parameter Value to Very Report Output</span></span>  
  
1.  <span data-ttu-id="57be4-158">Для параметра **OrderNumber**выберите **Получить значение из базы данных**.</span><span class="sxs-lookup"><span data-stu-id="57be4-158">For **OrderNumber**, select **Get the value from the database**.</span></span> <span data-ttu-id="57be4-159">В поле «Значение параметра» выберите **Order**.</span><span class="sxs-lookup"><span data-stu-id="57be4-159">In Value, select **Order**.</span></span> <span data-ttu-id="57be4-160">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="57be4-160">Click **Next.**</span></span>  
  
##  <a name="step-6---to-schedule-a-subscription"></a><a name="bkmk_schedule_subscription"></a><span data-ttu-id="57be4-161">Шаг 6. Планирование подписки</span><span class="sxs-lookup"><span data-stu-id="57be4-161">Step 6 - To Schedule a Subscription</span></span>  
  
1.  <span data-ttu-id="57be4-162">Щелкните **По расписанию, созданному для этой подписки**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="57be4-162">Click **On a schedule created for this subscription**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="57be4-163">В окне **Подробности расписания**нажмите кнопку **Однократно**.</span><span class="sxs-lookup"><span data-stu-id="57be4-163">In **Schedule Details**, click **Once**.</span></span>  
  
3.  <span data-ttu-id="57be4-164">Укажите время начала через несколько минут после текущего момента.</span><span class="sxs-lookup"><span data-stu-id="57be4-164">Specify a start time that is a few minutes ahead of the current time.</span></span>  
  
4.  <span data-ttu-id="57be4-165">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="57be4-165">Click **Finish**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="57be4-166">Next Steps</span><span class="sxs-lookup"><span data-stu-id="57be4-166">Next Steps</span></span>  
 <span data-ttu-id="57be4-167">При выполнении подписки в указанную общую папку будут доставлены четыре файла отчетов, по одному для каждого заказа из источника данных *Подписчики* .</span><span class="sxs-lookup"><span data-stu-id="57be4-167">When the subscription runs, four report files will be delivered to the file share you specified, one for each order in the *Subscribers* data source.</span></span> <span data-ttu-id="57be4-168">Каждая доставка должна содержать уникальные данные (данные должны различаться в зависимости от заказа), иметь свой формат подготовки и формат файла.</span><span class="sxs-lookup"><span data-stu-id="57be4-168">Each delivery should be unique in terms of data (the data should be order-specific), rendering format, and file format.</span></span> <span data-ttu-id="57be4-169">Можно открыть любой отчет из общей папки, чтобы убедиться, что каждая версия настроена в соответствии с указанными параметрами подписки.</span><span class="sxs-lookup"><span data-stu-id="57be4-169">You can open each report from the shared folder to verify that each version is customized based on the subscription options you defined.</span></span>  
  
 <span data-ttu-id="57be4-170">![Список файлов, созданных подпиской](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-filelist.gif "Список файлов, созданных подпиской")</span><span class="sxs-lookup"><span data-stu-id="57be4-170">![List of files created by the subscription](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-filelist.gif "List of files created by the subscription")</span></span>  
  
 <span data-ttu-id="57be4-171">Страница подписки в диспетчере отчетов будет содержать **Дату последнего запуска** и **Состояние** для подписки.</span><span class="sxs-lookup"><span data-stu-id="57be4-171">The subscription page in Report Manager will contain the **Last Run** date and **Status** of the subscription.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="57be4-172">Для вывода обновленной информации необходимо обновить страницу после запуска подписок.</span><span class="sxs-lookup"><span data-stu-id="57be4-172">Refresh the page after the subscription runs to see the updated information.</span></span>  
  
 <span data-ttu-id="57be4-173">![Результаты подписки в диспетчере отчетов](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-status-reportmanager.gif "Результаты подписки в диспетчере отчетов")</span><span class="sxs-lookup"><span data-stu-id="57be4-173">![Subscription results in Report Manager](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-status-reportmanager.gif "Subscription results in Report Manager")</span></span>  
  
 <span data-ttu-id="57be4-174">Этот шаг завершает учебник «Определение управляемой данными подписки».</span><span class="sxs-lookup"><span data-stu-id="57be4-174">This step concludes the tutorial "Defining a Data-Driven Subscription".</span></span> <span data-ttu-id="57be4-175">Дополнительные сведения о других [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] руководствах см. в [руководствах по Reporting Services &#40;SSRS&#41;](../reporting-services/reporting-services-tutorials-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="57be4-175">To learn more about other [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] tutorials, see [Reporting Services Tutorials &#40;SSRS&#41;](../reporting-services/reporting-services-tutorials-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57be4-176">См. также:</span><span class="sxs-lookup"><span data-stu-id="57be4-176">See Also</span></span>  
 <span data-ttu-id="57be4-177">[Создание управляемой данными подписки (учебник по службам SSRS)](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="57be4-177">[Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) </span></span>  
 <span data-ttu-id="57be4-178">[Подписки и доставка (службы Reporting Services)](subscriptions/subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="57be4-178">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span></span>  
 <span data-ttu-id="57be4-179">[Data-Driven Subscriptions](subscriptions/data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="57be4-179">[Data-Driven Subscriptions](subscriptions/data-driven-subscriptions.md) </span></span>  
 <span data-ttu-id="57be4-180">[Создание, изменение и удаление управляемой данными подписки](subscriptions/create-modify-and-delete-data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="57be4-180">[Create, Modify, and Delete a Data-Driven Subscription](subscriptions/create-modify-and-delete-data-driven-subscriptions.md) </span></span>  
 [<span data-ttu-id="57be4-181">Использование внешнего источника данных подписчика (управляемая данными подписка)</span><span class="sxs-lookup"><span data-stu-id="57be4-181">Use an External Data Source for Subscriber Data &#40;Data-Driven Subscription&#41;</span></span>](subscriptions/use-an-external-data-source-for-subscriber-data-data-driven-subscription.md)  
  
  
