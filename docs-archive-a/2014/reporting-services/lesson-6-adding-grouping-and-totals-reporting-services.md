---
title: 'Занятие 6: Добавление группирования и итогов (службы Reporting Services) | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e3d61228-2aa4-42cc-955e-602dbf3406a7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b98798005a984edf00aff469d4c1b09aa2e34d98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668090"
---
# <a name="lesson-6-adding-grouping-and-totals-reporting-services"></a><span data-ttu-id="731c2-102">Занятие 6: Добавление группирования и итогов (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="731c2-102">Lesson 6: Adding Grouping and Totals (Reporting Services)</span></span>
  <span data-ttu-id="731c2-103">Добавление группирования и итогов к отчету предназначено для организации и суммирования данных.</span><span class="sxs-lookup"><span data-stu-id="731c2-103">Add grouping and totals to your report to organize and summarize your data.</span></span>  
  
 <span data-ttu-id="731c2-104">Дополнительные сведения о добавлении итоговых значений в отчеты см. [в разделе Добавление итогов к отчетам Reporting Services (SSRS)](https://www.tutorialgateway.org/add-total-and-subtotal-to-ssrs-report/).</span><span class="sxs-lookup"><span data-stu-id="731c2-104">For information about adding running totals to reports, see: [Adding totals to Reporting Services (SSRS) reports](https://www.tutorialgateway.org/add-total-and-subtotal-to-ssrs-report/).</span></span>  
  
 <span data-ttu-id="731c2-105">**В этом разделе:**</span><span class="sxs-lookup"><span data-stu-id="731c2-105">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="731c2-106">Группирование данных в отчете</span><span class="sxs-lookup"><span data-stu-id="731c2-106">To group data in a report</span></span>](#bkmk_groupdata)  
  
-   [<span data-ttu-id="731c2-107">Добавление итогов в отчет</span><span class="sxs-lookup"><span data-stu-id="731c2-107">To add totals to a report</span></span>](#bkmk_addtotals)  
  
-   [<span data-ttu-id="731c2-108">Добавление ежедневного итога к отчету</span><span class="sxs-lookup"><span data-stu-id="731c2-108">To add a daily total to a report</span></span>](#bkmk_adddailytotal)  
  
-   [<span data-ttu-id="731c2-109">Добавление в отчет общего итога</span><span class="sxs-lookup"><span data-stu-id="731c2-109">To add a grand total to a report</span></span>](#bkmk_addgrandtotal)  
  
-   [<span data-ttu-id="731c2-110">Публикация отчета на сервере отчетов (необязательно)</span><span class="sxs-lookup"><span data-stu-id="731c2-110">To Publish the Report to the Report Server (Optional)</span></span>](#bkmk_publishreport)  
  
##  <a name="to-group-data-in-a-report"></a><a name="bkmk_groupdata"></a><span data-ttu-id="731c2-111">Группирование данных в отчете</span><span class="sxs-lookup"><span data-stu-id="731c2-111">To group data in a report</span></span>  
  
1.  <span data-ttu-id="731c2-112">Перейдите на вкладку **Макет** .</span><span class="sxs-lookup"><span data-stu-id="731c2-112">Click the **Design** tab.</span></span>  
  
2.  <span data-ttu-id="731c2-113">Если панель « **группы строк** » не видна, щелкните правой кнопкой мыши область конструктора и выберите пункт меню **вид** , а затем пункт **группирование**.</span><span class="sxs-lookup"><span data-stu-id="731c2-113">If you do not see the **Row Groups** pane , right-click the design surface and click **view** and then click **Grouping**.</span></span>  
  
3.  <span data-ttu-id="731c2-114">Из области **Данные отчета** перетащите поле `Date` на панель **Группы строк**.</span><span class="sxs-lookup"><span data-stu-id="731c2-114">From the **Report Data** pane, drag the `Date` field to the **Row Groups** pane.</span></span> <span data-ttu-id="731c2-115">Поместите это поле над строкой **(Сведения)**.</span><span class="sxs-lookup"><span data-stu-id="731c2-115">Place it above the row called **(Details)**.</span></span>  
  
     <span data-ttu-id="731c2-116">Обратите внимание на то, что теперь на маркере строк отображается квадратная скобка, указывающая на наличие группы.</span><span class="sxs-lookup"><span data-stu-id="731c2-116">Note that the row handle now has a bracket in it, to show a group.</span></span> <span data-ttu-id="731c2-117">Теперь в таблице имеются два столбца «Дата», по одному с двух сторон от вертикальной пунктирной линии.</span><span class="sxs-lookup"><span data-stu-id="731c2-117">The table now also has two Date columns -- one on either side of a vertical dotted line.</span></span>  
  
     ![](../../2014/tutorials/media/rs-basictablegroups1design.gif "rs_BasicTableGroups1Design")  
  
4.  <span data-ttu-id="731c2-118">Из области **Данные отчета** перетащите поле `Order` на панель **Группы строк**.</span><span class="sxs-lookup"><span data-stu-id="731c2-118">From the **Report Data** pane, drag the `Order` field to the **Row Groups** pane.</span></span> <span data-ttu-id="731c2-119">Поместите это поле под обозначением "Дата" и над обозначением **(Сведения)**.</span><span class="sxs-lookup"><span data-stu-id="731c2-119">Place it below Date and above **(Details)**.</span></span>  
  
     <span data-ttu-id="731c2-120">Обратите внимание на то, что теперь на маркере строки отображаются две квадратные скобки, указывая на наличие двух групп.</span><span class="sxs-lookup"><span data-stu-id="731c2-120">Note that the row handle now has two brackets in it, to show two groups.</span></span> <span data-ttu-id="731c2-121">Теперь таблица имеет два `Order` столбца.</span><span class="sxs-lookup"><span data-stu-id="731c2-121">The table now has two `Order` columns, too.</span></span>  
  
5.  <span data-ttu-id="731c2-122">Удалите исходные столбцы Дата и Заказ**справа** от двойной линии.</span><span class="sxs-lookup"><span data-stu-id="731c2-122">Delete the original Date and Order columns to the **right** of the double line.</span></span> <span data-ttu-id="731c2-123">Это приведет к удалению соответствующих отдельных значений записи, чтобы отображалось только значение группы.</span><span class="sxs-lookup"><span data-stu-id="731c2-123">This removes this individual record values so that only the group value is displayed.</span></span> <span data-ttu-id="731c2-124">Выберите маркеры двух столбцов, щелкните правой кнопкой мыши и выберите пункт **Удалить столбцы**.</span><span class="sxs-lookup"><span data-stu-id="731c2-124">Select the column handles for the two columns, right-click and click **Delete Columns**.</span></span>  
  
     <span data-ttu-id="731c2-125">![Выбор столбцов для удаления](../../2014/tutorials/media/rs-basictablegroupsdeletecols.gif "Выбор столбцов для удаления")</span><span class="sxs-lookup"><span data-stu-id="731c2-125">![Select columns to delete](../../2014/tutorials/media/rs-basictablegroupsdeletecols.gif "Select columns to delete")</span></span>  
  
     <span data-ttu-id="731c2-126">После этого можно снова форматировать заголовки столбцов и дату.</span><span class="sxs-lookup"><span data-stu-id="731c2-126">You can format the column headers and date again.</span></span>  
  
6.  <span data-ttu-id="731c2-127">Откройте вкладку **Просмотр** для просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="731c2-127">Switch to the **Preview** tab to preview the report.</span></span> <span data-ttu-id="731c2-128">Он должен выглядеть примерно так, как на следующей иллюстрации:</span><span class="sxs-lookup"><span data-stu-id="731c2-128">It should look similar to the following illustration:</span></span>  
  
     <span data-ttu-id="731c2-129">![Таблица сгруппирована по дате и заказу](../../2014/tutorials/media/rs-basictablegroupspreview.gif "Таблица сгруппирована по дате и заказу")</span><span class="sxs-lookup"><span data-stu-id="731c2-129">![Table grouped by date and then order](../../2014/tutorials/media/rs-basictablegroupspreview.gif "Table grouped by date and then order")</span></span>  
  
##  <a name="to-add-totals-to-a-report"></a><a name="bkmk_addtotals"></a><span data-ttu-id="731c2-130">Добавление итогов в отчет</span><span class="sxs-lookup"><span data-stu-id="731c2-130">To add totals to a report</span></span>  
  
1.  <span data-ttu-id="731c2-131">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="731c2-131">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="731c2-132">Щелкните правой кнопкой мыши ячейку области данных, которая содержит поле `[LineTotal]`, и выберите пункт **Добавить итог**.</span><span class="sxs-lookup"><span data-stu-id="731c2-132">Right-click the data region cell that contains the field `[LineTotal]`, and click **Add Total**.</span></span>  
  
     <span data-ttu-id="731c2-133">Это приведет к добавлению строки с суммарной стоимостью в долларах для каждого заказа.</span><span class="sxs-lookup"><span data-stu-id="731c2-133">This adds a row with a sum of the dollar amount for each order.</span></span>  
  
3.  <span data-ttu-id="731c2-134">Щелкните правой кнопкой мыши ячейку, которая содержит поле `[Qty]`, и выберите пункт **Добавить итог**.</span><span class="sxs-lookup"><span data-stu-id="731c2-134">Right-click the cell that contains the field `[Qty]`, and click **Add Total**.</span></span>  
  
     <span data-ttu-id="731c2-135">Это приведет к добавлению суммы количеств по каждому заказу в строку итогов.</span><span class="sxs-lookup"><span data-stu-id="731c2-135">This adds a sum of the quantity for each order to the totals row.</span></span>  
  
4.  <span data-ttu-id="731c2-136">В пустой ячейке слева от поля `Sum[Qty]`введите метку**Итог заказа**.</span><span class="sxs-lookup"><span data-stu-id="731c2-136">In the empty cell to the left of `Sum[Qty]`, type the label "**Order Total"**.</span></span>  
  
5.  <span data-ttu-id="731c2-137">К строке итогов можно добавить цвет фона.</span><span class="sxs-lookup"><span data-stu-id="731c2-137">You can add a background color to the totals row.</span></span> <span data-ttu-id="731c2-138">Выберите две ячейки суммы и ячейку метки.</span><span class="sxs-lookup"><span data-stu-id="731c2-138">Select the two sum cells and the label cell.</span></span>  
  
6.  <span data-ttu-id="731c2-139">В меню **Формат** щелкните элемент **Цвет фона**, а затем щелкните элемент **Светло-серый**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="731c2-139">On the **Format** menu, click **Background Color**, click **Light Gray**, and click **OK**.</span></span>  
  
     <span data-ttu-id="731c2-140">![Представление конструирования: базовая таблица с итогом заказа](../../2014/tutorials/media/rs-basictablesumlinetotaldesign.gif "Представление конструирования: базовая таблица с итогом заказа")</span><span class="sxs-lookup"><span data-stu-id="731c2-140">![Design view: Basic table with order total](../../2014/tutorials/media/rs-basictablesumlinetotaldesign.gif "Design view: Basic table with order total")</span></span>  
  
##  <a name="to-add-a-daily-total-to-a-report"></a><a name="bkmk_adddailytotal"></a><span data-ttu-id="731c2-141">Добавление ежедневного итога в отчет</span><span class="sxs-lookup"><span data-stu-id="731c2-141">To add a daily total to a report</span></span>  
  
1.  <span data-ttu-id="731c2-142">Щелкните правой кнопкой мыши ячейку Заказ , наведите указатель на пункт **Добавить итог**и выберите пункт **После**.</span><span class="sxs-lookup"><span data-stu-id="731c2-142">Right-click the Order cell, point to **Add Total**, and click **After**.</span></span>  
  
     <span data-ttu-id="731c2-143">При этом добавляется новая строка, содержащая суммы количества и суммы в долларах для каждого дня, а также метка "**итог**" в столбце "порядок".</span><span class="sxs-lookup"><span data-stu-id="731c2-143">This adds a new row containing sums of the quantity and dollar amount for each day, and the label "**Total**" in the Order column.</span></span>  
  
2.  <span data-ttu-id="731c2-144">Введите слово **Ежедневный** перед словом **Итог** в той же ячейке, чтобы в ней находилась надпись **Ежедневный итог**.</span><span class="sxs-lookup"><span data-stu-id="731c2-144">Type the word **Daily** before the word **Total** in the same cell, so it reads **Daily Total**.</span></span>  
  
3.  <span data-ttu-id="731c2-145">Выберите ячейку **Ежедневный итог** , две ячейки **Сумма** и пустую ячейку между ними.</span><span class="sxs-lookup"><span data-stu-id="731c2-145">Select the **Daily Total** cell, the two **Sum** cells and the empty cell between them.</span></span>  
  
4.  <span data-ttu-id="731c2-146">В меню **Формат** щелкните элемент **Цвет фона**, а затем щелкните элемент **Оранжевый**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="731c2-146">On the **Format** menu, click **Background Color**, click **Orange**, and click **OK**.</span></span>  
  
     ![](../../2014/tutorials/media/rs-basictablesumdaytotaldesign.gif "rs_BasicTableSumDayTotalDesign")  
  
##  <a name="to-add-a-grand-total-to-a-report"></a><a name="bkmk_addgrandtotal"></a><span data-ttu-id="731c2-147">Добавление в отчет общего итога</span><span class="sxs-lookup"><span data-stu-id="731c2-147">To add a grand total to a report</span></span>  
  
1.  <span data-ttu-id="731c2-148">Щелкните правой кнопкой мыши ячейку "Дата", наведите указатель на пункт **Добавить итог**и выберите пункт **После**.</span><span class="sxs-lookup"><span data-stu-id="731c2-148">Right-click the Date cell, point to **Add Total**, and click **After**.</span></span>  
  
     <span data-ttu-id="731c2-149">При этом добавляется новая строка, содержащая суммы количества и суммы в долларах для всего отчета, а также **Общая** метка в `Date` столбце.</span><span class="sxs-lookup"><span data-stu-id="731c2-149">This adds a new row containing sums of the quantity and dollar amount for the entire report, and the **Total** label in the `Date` column.</span></span>  
  
2.  <span data-ttu-id="731c2-150">Введите слово **Общий** перед словом **Итог** в той же ячейке, чтобы в ней появилась надпись **Общий итог**.</span><span class="sxs-lookup"><span data-stu-id="731c2-150">Type the word **Grand** before the word **Total** in the same cell, so it reads **Grand Total**.</span></span>  
  
3.  <span data-ttu-id="731c2-151">Выберите ячейку **Общий итог** , две ячейки **Сумма** и пустые ячейки между ними.</span><span class="sxs-lookup"><span data-stu-id="731c2-151">Select the **Grand Total** cell, the two **Sum** cells and the empty cells between them.</span></span>  
  
4.  <span data-ttu-id="731c2-152">В меню **Формат** щелкните элемент **Цвет фона**, а затем щелкните элемент **Светло-синий**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="731c2-152">On the **Format** menu, click **Background Color**, click **Light Blue**, and click **OK**.</span></span>  
  
     <span data-ttu-id="731c2-153">![Представление конструирования: общий итог в базовой таблице](../../2014/tutorials/media/rs-basictablesumgrandtotaldesign.gif "Представление конструирования: общий итог в базовой таблице")</span><span class="sxs-lookup"><span data-stu-id="731c2-153">![Design view: Grand total in basic table](../../2014/tutorials/media/rs-basictablesumgrandtotaldesign.gif "Design view: Grand total in basic table")</span></span>  
  
5.  <span data-ttu-id="731c2-154">Нажмите кнопку «Предварительный просмотр».</span><span class="sxs-lookup"><span data-stu-id="731c2-154">Click Preview.</span></span>  
  
     <span data-ttu-id="731c2-155">Последняя страница должна выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="731c2-155">The last page should look something like this:</span></span>  
  
     <span data-ttu-id="731c2-156">![Предварительный просмотр: базовая таблица с общим итогом](../../2014/tutorials/media/rs-basictablesumgrandtotalpreview.gif "Предварительный просмотр: базовая таблица с общим итогом")</span><span class="sxs-lookup"><span data-stu-id="731c2-156">![Preview: Basic table with grand total](../../2014/tutorials/media/rs-basictablesumgrandtotalpreview.gif "Preview: Basic table with grand total")</span></span>  
  
##  <a name="to-publish-the-report-to-the-report-server-optional"></a><a name="bkmk_publishreport"></a><span data-ttu-id="731c2-157">Публикация отчета на сервере отчетов (необязательно)</span><span class="sxs-lookup"><span data-stu-id="731c2-157">To Publish the Report to the Report Server (Optional)</span></span>  
  
1.  <span data-ttu-id="731c2-158">Необязательным шагом является публикация готового отчета на сервере отчетов, работающем в собственном режиме, с тем чтобы его можно было просматривать из диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="731c2-158">An optional step is to publish the completed report to the native mode report server so you can view the report from Report Manager.</span></span>  
  
2.  <span data-ttu-id="731c2-159">На панели инструментов щелкните **Проект** и выберите **Свойства учебника...**</span><span class="sxs-lookup"><span data-stu-id="731c2-159">On the toolbar click **Project** and then click **tutorial Properties...**</span></span>  
  
3.  <span data-ttu-id="731c2-160">**Введите имя** сервера отчетов в тип файла, например **http:// \<servername> /ReportServer**</span><span class="sxs-lookup"><span data-stu-id="731c2-160">In the **TargetServerURL** type the name of the name of your report server, for example **http://\<servername>/reportserver**</span></span>  
  
4.  <span data-ttu-id="731c2-161">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="731c2-161">Click **OK**</span></span>  
  
5.  <span data-ttu-id="731c2-162">На панели инструментов щелкните **Построить** , а затем ― **Развернуть учебник**.</span><span class="sxs-lookup"><span data-stu-id="731c2-162">On the toolbar click **Build** and then click **Deploy tutorial**.</span></span>  
  
     <span data-ttu-id="731c2-163">Если в окне вывода появится сообщение примерно следующего содержания, это означает, что развертывание прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="731c2-163">If you see a message similar to the following in the output window, it indicates a successful deployment.</span></span>  
  
    > <span data-ttu-id="731c2-164">------ Build started: Project: tutorial, Configuration: Debug ------Skipping 'Sales Orders.rdl'.</span><span class="sxs-lookup"><span data-stu-id="731c2-164">------ Build started: Project: tutorial, Configuration: Debug ------Skipping 'Sales Orders.rdl'.</span></span> <span data-ttu-id="731c2-165">Элемент находится в актуальном состоянии. Сборка завершена--0 ошибок, 0 предупреждений------развертывание начато: проект: учебник, конфигурация: Отладка------развертывание в http:// \<server name> /репортсервердеплойинг отчет "/туториал/Салес Orders". Развертывание завершено--0 ошибок, 0 предупреждений = = = = = = = = = = сборка: 1 выполнено или Обновлено, 0 — сбой, 0 пропущено = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = =</span><span class="sxs-lookup"><span data-stu-id="731c2-165">Item is up to date.Build complete -- 0 errors, 0 warnings------ Deploy started: Project: tutorial, Configuration: Debug ------Deploying to http://\<server name>/reportserverDeploying report '/tutorial/Sales Orders'.Deploy complete -- 0 errors, 0 warnings========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==================== Deploy: 1 succeeded, 0 failed, 0 skipped ==========</span></span>  
  
     <span data-ttu-id="731c2-166">Если же откроется сообщение об ошибке примерно следующего содержания, удостоверьтесь в наличии разрешений на сервер отчетов, а также запустите среду [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="731c2-166">If you see an error message similar to the following, verify you have permissions on the report server and you have started [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] with administrator privileges.</span></span>  
  
    > <span data-ttu-id="731c2-167">"Разрешения, предоставленные пользователю XXXXXXXX \\<имени пользователя \> ", недостаточны для выполнения этой операции "</span><span class="sxs-lookup"><span data-stu-id="731c2-167">"The permissions granted to user 'XXXXXXXX\\<your user name\>' are insufficient for performing this operation"</span></span>  
  
6.  <span data-ttu-id="731c2-168">Запустите диспетчер отчетов с правами администратора, например щелкните правой кнопкой мыши значок Internet Explorer и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="731c2-168">Start Report Manager with administrator privileges, for example, right-click the icon for Internet Explorer and click **Run as administrator**.</span></span>  
  
     <span data-ttu-id="731c2-169">Перейдите по URL-адресу диспетчера отчетов, например: `http://<server name>/reports`.</span><span class="sxs-lookup"><span data-stu-id="731c2-169">Browse to the Report Manager URL, for example: `http://<server name>/reports`.</span></span>  
  
7.  <span data-ttu-id="731c2-170">Перейдите в папку с отчетом и щелкните имя отчета `Sales Orders`, чтобы отобразить этот отчет в браузере.</span><span class="sxs-lookup"><span data-stu-id="731c2-170">Browse to the folder that contains the report and click the name of the report `Sales Orders` to view the rendered report in the browser.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="731c2-171">Next Steps</span><span class="sxs-lookup"><span data-stu-id="731c2-171">Next Steps</span></span>  
 <span data-ttu-id="731c2-172">Учебник по созданию базового табличного отчета успешно освоен.</span><span class="sxs-lookup"><span data-stu-id="731c2-172">You have successfully completed the Creating a Basic Table Report tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="731c2-173">См. также:</span><span class="sxs-lookup"><span data-stu-id="731c2-173">See Also</span></span>  
 [<span data-ttu-id="731c2-174">Фильтрация, группирование и сортировка данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="731c2-174">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](report-design/filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
