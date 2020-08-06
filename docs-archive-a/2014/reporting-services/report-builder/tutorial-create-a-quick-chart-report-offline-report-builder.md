---
title: Руководство по Создание стандартного отчета с диаграммой в автономном режиме (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports, creating
- tutorials, getting started
- creating reports
ms.assetid: 6b1db67a-cf75-494c-b70c-09f1e6a8d414
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 51a9e648550a0108f47e3d93d75267ab0c1c24f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657535"
---
# <a name="tutorial-create-a-quick-chart-report-offline-report-builder"></a><span data-ttu-id="36ac9-102">Учебник. Создание стандартного отчета с диаграммой в режиме "вне сети" (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="36ac9-102">Tutorial: Create a Quick Chart Report Offline (Report Builder)</span></span>
  <span data-ttu-id="36ac9-103">В этом учебнике будет создана круговая диаграмма с помощью мастера, а затем она будет немного изменена, чтобы получить общее представление о том, что можно сделать.</span><span class="sxs-lookup"><span data-stu-id="36ac9-103">In this tutorial, you'll create a pie chart by using a wizard, and then you'll modify it a little, just to get an idea of what's possible.</span></span> <span data-ttu-id="36ac9-104">Задания этого учебника вы можете выполнить двумя различными способами.</span><span class="sxs-lookup"><span data-stu-id="36ac9-104">You can do this tutorial two different ways.</span></span> <span data-ttu-id="36ac9-105">Оба метода имеют одинаковый результат — круговую диаграмму, подобную показанной на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="36ac9-105">Both methods have the same outcome-a pie chart like the one in the following illustration:</span></span>

 <span data-ttu-id="36ac9-106">![«Моя первая круговая диаграмма» в режиме выполнения](../media/rs-my1stpierunview.gif "Моя первая круговая диаграмма в представлении "Запуск"")</span><span class="sxs-lookup"><span data-stu-id="36ac9-106">!["My First Pie Chart" in Run view](../media/rs-my1stpierunview.gif "My First Pie Chart in Run view")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="36ac9-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="36ac9-107">Prerequisites</span></span>
 <span data-ttu-id="36ac9-108">Независимо от используемого метода (XML-данные или запрос [!INCLUDE[tsql](../../../includes/tsql-md.md)]), требуется доступ к построителю отчетов [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36ac9-108">Whether you use XML data or a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query, you need to have access to [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] Report Builder.</span></span> <span data-ttu-id="36ac9-109">Можно запустить изолированную версию построителя отчетов или версию ClickOnce, которая доступна из диспетчера отчетов или с сайта SharePoint.</span><span class="sxs-lookup"><span data-stu-id="36ac9-109">You can run the stand-alone version or the ClickOnce version available from Report Manager or a SharePoint site.</span></span> <span data-ttu-id="36ac9-110">Для версии ClickOnce отличается только первый шаг — открытие построителя отчетов.</span><span class="sxs-lookup"><span data-stu-id="36ac9-110">Only the first step, how to open Report Builder, is different for ClickOnce versions.</span></span> <span data-ttu-id="36ac9-111">Дополнительные сведения см. в разделе [Установка, удаление и поддержка построитель отчетов](../install-uninstall-and-report-builder-support.md).</span><span class="sxs-lookup"><span data-stu-id="36ac9-111">For more information, see [Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md).</span></span>

##  <a name="two-ways-to-do-this-tutorial"></a><a name="TwoWays"></a><span data-ttu-id="36ac9-112">Два способа работы с этим руководством</span><span class="sxs-lookup"><span data-stu-id="36ac9-112">Two Ways To Do This Tutorial</span></span>

-   [<span data-ttu-id="36ac9-113">Создание круговой диаграммы с использованием XML-данных</span><span class="sxs-lookup"><span data-stu-id="36ac9-113">Create the pie chart with XML data</span></span>](#CreatePieChartXML)

-   [<span data-ttu-id="36ac9-114">Создание круговой диаграммы с помощью запроса Transact-SQL, содержащего данные</span><span class="sxs-lookup"><span data-stu-id="36ac9-114">Create the pie chart with a Transact-SQL query that contains data</span></span>](#CreatePieQueryData)

### <a name="using-xml-data-for-this-tutorial"></a><span data-ttu-id="36ac9-115">Использование XML-данных при работе с этим учебником</span><span class="sxs-lookup"><span data-stu-id="36ac9-115">Using XML data for this tutorial</span></span>
 <span data-ttu-id="36ac9-116">Можно использовать XML-данные, скопированные из этого раздела и вставленные в мастер.</span><span class="sxs-lookup"><span data-stu-id="36ac9-116">You can use XML data that you copy from this topic and paste into the wizard.</span></span> <span data-ttu-id="36ac9-117">При этом не требуется соединение с сервером отчетов или сервером отчетов в режиме интеграции с SharePoint и не нужен доступ к экземпляру [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36ac9-117">You don't need to be connected to a report server or a report server in SharePoint integrated mode, and you don't need access to an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>

 [<span data-ttu-id="36ac9-118">Создание круговой диаграммы с использованием XML-данных</span><span class="sxs-lookup"><span data-stu-id="36ac9-118">Create the pie chart with XML data</span></span>](#CreatePieChartXML)

### <a name="using-a-transact-sql-query-that-contains-data-for-this-tutorial"></a><span data-ttu-id="36ac9-119">Использование запроса Transact-SQL, содержащего данные, при работе с этим учебником</span><span class="sxs-lookup"><span data-stu-id="36ac9-119">Using a Transact-SQL query that contains data for this tutorial</span></span>
 <span data-ttu-id="36ac9-120">Можно скопировать запрос с данными, которые содержатся в нем, из этого раздела и вставить в мастер.</span><span class="sxs-lookup"><span data-stu-id="36ac9-120">You can copy a query with data included in it from this topic and paste it into the wizard.</span></span> <span data-ttu-id="36ac9-121">При этом потребуется имя экземпляра [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] и учетные данные, необходимые для доступа к базе данных только для чтения.</span><span class="sxs-lookup"><span data-stu-id="36ac9-121">You will need the name of an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] and credentials sufficient for read-only access to any database.</span></span> <span data-ttu-id="36ac9-122">В запросе набора данных в этом учебнике используются данные литералов, но запрос должен обрабатываться экземпляром [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] для возвращения метаданных, необходимых для набора данных отчета.</span><span class="sxs-lookup"><span data-stu-id="36ac9-122">The dataset query in the tutorial uses literal data, but the query must be processed by an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] to return the metadata that is required for a report dataset.</span></span>

 <span data-ttu-id="36ac9-123">Преимущество использования запроса [!INCLUDE[tsql](../../../includes/tsql-md.md)] заключается в том, что во всех учебниках построителя отчетов используется один и тот же метод, поэтому при выполнении других учебников этот метод будет уже знаком.</span><span class="sxs-lookup"><span data-stu-id="36ac9-123">The advantage of using the [!INCLUDE[tsql](../../../includes/tsql-md.md)] query is that all the other Report Builder tutorials use the same method, so when you do the other tutorials, you will already know what to do.</span></span>

 <span data-ttu-id="36ac9-124">Для выполнения запроса [!INCLUDE[tsql](../../../includes/tsql-md.md)] существует несколько других предварительных условий.</span><span class="sxs-lookup"><span data-stu-id="36ac9-124">The [!INCLUDE[tsql](../../../includes/tsql-md.md)] query does require a few other prerequisites.</span></span> <span data-ttu-id="36ac9-125">Дополнительные сведения см. в разделе [Предварительные условия для использования учебников (построитель отчетов)](../report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="36ac9-125">For more information, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md).</span></span>

 [<span data-ttu-id="36ac9-126">Создание круговой диаграммы с помощью запроса Transact-SQL, содержащего данные</span><span class="sxs-lookup"><span data-stu-id="36ac9-126">Create the pie chart with a Transact-SQL query that contains data</span></span>](#CreatePieQueryData)

## <a name="also-in-this-article"></a><span data-ttu-id="36ac9-127">Также в этой статье</span><span class="sxs-lookup"><span data-stu-id="36ac9-127">Also in This Article</span></span>
 [<span data-ttu-id="36ac9-128">После завершения работы мастера</span><span class="sxs-lookup"><span data-stu-id="36ac9-128">After You Run the Wizard</span></span>](#AfterWizard)

 [<span data-ttu-id="36ac9-129">Что дальше</span><span class="sxs-lookup"><span data-stu-id="36ac9-129">What's Next</span></span>](#WhatsNext)

##  <a name="creating-the-pie-chart-with-xml-data"></a><a name="CreatePieChartXML"></a><span data-ttu-id="36ac9-130">Создание круговой диаграммы с XML-данными</span><span class="sxs-lookup"><span data-stu-id="36ac9-130">Creating the pie chart with XML data</span></span>

#### <a name="to-create-the-pie-chart-with-xml-data"></a><span data-ttu-id="36ac9-131">Создание круговой диаграммы с использованием XML-данных</span><span class="sxs-lookup"><span data-stu-id="36ac9-131">To create the pie chart with XML data</span></span>

1.  <span data-ttu-id="36ac9-132">Нажмите кнопку **Пуск**, наведите курсор на пункты **Все программы**, **Построитель отчетов Microsoft SQL Server 2012**и выберите пункт **Построитель отчетов**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-132">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>

     <span data-ttu-id="36ac9-133">Откроется диалоговое окно **Начало работы** .</span><span class="sxs-lookup"><span data-stu-id="36ac9-133">The **Getting Started** dialog box appears.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="36ac9-134">Если диалоговое окно **Начало работы** не отображается, на кнопке **Построитель отчетов** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-134">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>

2.  <span data-ttu-id="36ac9-135">Убедитесь, что на панели слева выбран пункт **Отчет** .</span><span class="sxs-lookup"><span data-stu-id="36ac9-135">In the left pane, verify that **Report** is selected.</span></span>

3.  <span data-ttu-id="36ac9-136">На правой панели нажмите **Мастер диаграмм**, а затем щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-136">In the right pane, click **Chart Wizard**, and then click **Create**.</span></span>

4.  <span data-ttu-id="36ac9-137">На странице **Выбор набора данных** нажмите кнопку **Создать набор данных**, а затем **Далее**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-137">In the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>

5.  <span data-ttu-id="36ac9-138">На странице **Выбор соединения с источником данных** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-138">In the **Choose a connection to a data source** page, click **New**.</span></span>

     <span data-ttu-id="36ac9-139">Откроется диалоговое окно **Свойства источника данных** .</span><span class="sxs-lookup"><span data-stu-id="36ac9-139">The **Data Source Properties** dialog box opens.</span></span>

6.  <span data-ttu-id="36ac9-140">Источник данных можно назвать произвольным образом.</span><span class="sxs-lookup"><span data-stu-id="36ac9-140">You can name a data source anything you want.</span></span> <span data-ttu-id="36ac9-141">В поле **Имя** введите **MyPieChart**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-141">In the **Name** box, type **MyPieChart**.</span></span>

7.  <span data-ttu-id="36ac9-142">В поле **Выбор типа подключения** щелкните **XML.**</span><span class="sxs-lookup"><span data-stu-id="36ac9-142">In the **Select connection type** box, click **XML.**</span></span>

8.  <span data-ttu-id="36ac9-143">Перейдите на вкладку **учетные данные** и выберите параметр **использовать текущего пользователя Windows. Может потребоваться делегирование Kerberos**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-143">Click the **Credentials** tab, select **Use current Windows user. Kerberos delegation may be required**, and then click **OK**.</span></span>

9. <span data-ttu-id="36ac9-144">На странице **Выбор соединения с источником данных** выберите **Моя круговая диаграмма**, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-144">In the **Choose a connection to a data source** page, click **MyPieChart**, and then click **Next**.</span></span>

10. <span data-ttu-id="36ac9-145">Скопируйте приведенный ниже текст и вставьте его в большое поле в центре страницы **Конструирование запроса** .</span><span class="sxs-lookup"><span data-stu-id="36ac9-145">Copy the following text and paste it in the large box in the center of the **Design a query** page.</span></span>

    ```
    <Query>
    <ElementPath>Root /S  {@Sales (Integer)} /C {@FullName} </ElementPath>
    <XmlData>
    <Root>
    <S Sales="150">
      <C FullName="Jae Pak" />
    </S>
    <S Sales="350">
      <C FullName="Jillian  Carson" />
    </S>
    <S Sales="250">
      <C FullName="Linda C Mitchell" />
    </S>
    <S Sales="500">
      <C FullName="Michael Blythe" />
    </S>
    <S Sales="450">
      <C FullName="Ranjit Varkey" />
    </S>
    </Root>
    </XmlData>
    </Query>
    ```

11. <span data-ttu-id="36ac9-146">Нажмите кнопку Выполнить (**!**), чтобы просмотреть данные, на основе которых будет создана диаграмма (необязательно).</span><span class="sxs-lookup"><span data-stu-id="36ac9-146">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>

12. <span data-ttu-id="36ac9-147">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-147">Click **Next**.</span></span>

13. <span data-ttu-id="36ac9-148">На странице **Выбор типа диаграммы** выберите **Круговая диаграмма**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-148">In the **Choose a chart type** page, click **Pie**, and then click **Next**.</span></span>

14. <span data-ttu-id="36ac9-149">На странице **Расположение полей диаграммы** дважды щелкните поле **Sales (продажи** ) в поле **Доступные поля** .</span><span class="sxs-lookup"><span data-stu-id="36ac9-149">In the **Arrange chart fields** page, double-click the **Sales** field in the **Available fields** box.</span></span>

     <span data-ttu-id="36ac9-150">Обратите внимание на то, что оно автоматически перемещается в поле **Значения** , так как это числовое значение.</span><span class="sxs-lookup"><span data-stu-id="36ac9-150">Note that it automatically moves to the **Values** box, because it is a numerical value.</span></span>

15. <span data-ttu-id="36ac9-151">Перетащите поле **FullName** из поля **Доступные поля** в поле **категории** (или дважды щелкните его; оно перейдет в поле **категории** ), а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-151">Drag the **FullName** field from the **Available fields** box to the **Categories** box (or double-click it; it will go to the **Categories** box), and then click **Next**.</span></span>

16. <span data-ttu-id="36ac9-152">На странице **Выбор стиля** по умолчанию выбрано значение **океан** .</span><span class="sxs-lookup"><span data-stu-id="36ac9-152">In the **Choose a style** page, **Ocean** is selected by default.</span></span> <span data-ttu-id="36ac9-153">Щелкните другие стили, чтобы просмотреть, как они выглядят.</span><span class="sxs-lookup"><span data-stu-id="36ac9-153">Click the other styles to see what they look like.</span></span>

17. <span data-ttu-id="36ac9-154">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-154">Click **Finish**.</span></span>

     <span data-ttu-id="36ac9-155">Теперь в области конструктора отображается новый отчет с круговой диаграммой.</span><span class="sxs-lookup"><span data-stu-id="36ac9-155">You're now looking at your new pie chart report on the design surface.</span></span> <span data-ttu-id="36ac9-156">Это стандартное представление.</span><span class="sxs-lookup"><span data-stu-id="36ac9-156">What you see is representational.</span></span> <span data-ttu-id="36ac9-157">В условных обозначениях указываются «Полное имя 1», «Полное имя 2» и т. д., а не имена менеджеров по продажам. Кроме того, размер секторов круговой диаграммы неточен.</span><span class="sxs-lookup"><span data-stu-id="36ac9-157">The legend reads Full Name 1, Full Name 2, etc., rather than the salespeople's names, and the size of the slices of pie are not accurate.</span></span> <span data-ttu-id="36ac9-158">Это изображение дает лишь общее представление о том, как будет выглядеть отчет.</span><span class="sxs-lookup"><span data-stu-id="36ac9-158">This is just to give you an idea of what your report will look like.</span></span>

18. <span data-ttu-id="36ac9-159">Чтобы просмотреть настоящую круговую диаграмму, нажмите кнопку **Выполнить** на вкладке **Главная** ленты.</span><span class="sxs-lookup"><span data-stu-id="36ac9-159">To see your actual pie chart, click **Run** on the **Home** tab of the Ribbon.</span></span>

 <span data-ttu-id="36ac9-160">![Значок стрелки, используемый для ссылки возврата в](../../2014-toc/media/uparrow16x16.gif "Значок стрелки, используемый со ссылкой В начало") [Начало](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="36ac9-160">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

##  <a name="creating-the-pie-chart-with-a-tsql-query"></a><a name="CreatePieQueryData"></a> <span data-ttu-id="36ac9-161">Создание круговой диаграммы с помощью запроса [!INCLUDE[tsql](../../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36ac9-161">Creating the pie chart with a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query</span></span>

#### <a name="to-create-the-pie-chart-with-a-tsql-query-that-contains-data"></a><span data-ttu-id="36ac9-162">Создание круговой диаграммы с помощью запроса [!INCLUDE[tsql](../../../includes/tsql-md.md)], содержащего данные</span><span class="sxs-lookup"><span data-stu-id="36ac9-162">To create the pie chart with a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query that contains data</span></span>

1.  <span data-ttu-id="36ac9-163">Нажмите кнопку **Пуск**, наведите курсор на пункты **Все программы**, **Построитель отчетов Microsoft SQL Server 2012**и выберите пункт **Построитель отчетов**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-163">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>

2.  <span data-ttu-id="36ac9-164">В диалоговом окне **Новый отчет или набор данных** убедитесь, что на левой панели выбран **отчет** .</span><span class="sxs-lookup"><span data-stu-id="36ac9-164">In the **New report or dataset** dialog box, verify that **Report** is selected in the left pane.</span></span>

3.  <span data-ttu-id="36ac9-165">На правой панели нажмите **Мастер диаграмм**, а затем щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-165">In the right pane, click **Chart Wizard**, and then click **Create**.</span></span>

4.  <span data-ttu-id="36ac9-166">На странице **Выбор набора данных** нажмите кнопку **Создать набор данных**, а затем **Далее**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-166">In the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>

5.  <span data-ttu-id="36ac9-167">На странице **Выбор соединения с источником данных** выберите существующий источник данных или перейдите к серверу отчетов и выберите источник данных, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-167">In the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="36ac9-168">Может потребоваться указать имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="36ac9-168">You may need to enter a user name and password.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="36ac9-169">При наличии необходимых разрешений выбор источника данных не имеет существенного значения.</span><span class="sxs-lookup"><span data-stu-id="36ac9-169">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="36ac9-170">Этот источник данных не будет использоваться для получения данных.</span><span class="sxs-lookup"><span data-stu-id="36ac9-170">You will not be getting data from the data source.</span></span> <span data-ttu-id="36ac9-171">Дополнительные сведения см. в разделе [Предварительные условия для использования учебников (построитель отчетов)](../report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="36ac9-171">For more information, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md).</span></span>

6.  <span data-ttu-id="36ac9-172">На странице **Конструирование запроса** нажмите кнопку **изменить как текст**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-172">On the **Design a Query** page, click **Edit as Text**.</span></span>

7.  <span data-ttu-id="36ac9-173">На панель запроса вставьте следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="36ac9-173">Paste the following query into the query pane:</span></span>

    ```
    SELECT 150 AS Sales, 'Jae Pak' AS FullName 
    UNION SELECT 350 AS Sales, 'Jillian Carson' AS FullName 
    UNION SELECT 250 AS Sales, 'Linda C Mitchell' AS FullName 
    UNION SELECT 500 AS Sales, 'Michael Blythe' AS FullName 
    UNION SELECT 450 AS Sales, 'Ranjit Varkey' AS FullName 
    ```

8.  <span data-ttu-id="36ac9-174">Нажмите кнопку Выполнить (**!**), чтобы просмотреть данные, на основе которых будет создана диаграмма (необязательно).</span><span class="sxs-lookup"><span data-stu-id="36ac9-174">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>

9. <span data-ttu-id="36ac9-175">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-175">Click **Next**.</span></span>

10. <span data-ttu-id="36ac9-176">На странице **Выбор типа диаграммы** выберите **Круговая диаграмма**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-176">In the **Choose a chart type** page, click **Pie**, and then click **Next**.</span></span>

11. <span data-ttu-id="36ac9-177">На странице **Расположение полей диаграммы** дважды щелкните поле **Sales (продажи** ) в поле **Доступные поля** .</span><span class="sxs-lookup"><span data-stu-id="36ac9-177">In the **Arrange chart fields** page, double-click the **Sales** field in the **Available fields** box.</span></span>

     <span data-ttu-id="36ac9-178">Обратите внимание на то, что оно автоматически перемещается в поле **Значение** , так как это числовое значение.</span><span class="sxs-lookup"><span data-stu-id="36ac9-178">Note that it automatically moves to the **Values** box, because it's a numerical value.</span></span>

12. <span data-ttu-id="36ac9-179">Перетащите поле **FullName** из поля **Доступные поля** в поле **категории** (или дважды щелкните его; оно перейдет в поле **категории** ), а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-179">Drag the **FullName** field from the **Available fields** box to the **Categories** box (or double-click it; it will go to the **Categories** box), and then click **Next**.</span></span>

13. <span data-ttu-id="36ac9-180">На странице **Выбор стиля** по умолчанию выбран стиль «Аквамарин».</span><span class="sxs-lookup"><span data-stu-id="36ac9-180">In the **Choose a style** page, Ocean is selected by default.</span></span> <span data-ttu-id="36ac9-181">Щелкните другие стили, чтобы просмотреть, как они выглядят.</span><span class="sxs-lookup"><span data-stu-id="36ac9-181">Click the other styles to see what they look like.</span></span>

14. <span data-ttu-id="36ac9-182">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-182">Click **Finish**.</span></span>

     <span data-ttu-id="36ac9-183">Теперь в области конструктора отображается новый отчет с круговой диаграммой.</span><span class="sxs-lookup"><span data-stu-id="36ac9-183">You're now looking at your new pie chart report on the design surface.</span></span> <span data-ttu-id="36ac9-184">Это стандартное представление.</span><span class="sxs-lookup"><span data-stu-id="36ac9-184">What you see is representational.</span></span> <span data-ttu-id="36ac9-185">В условных обозначениях указываются «Полное имя 1», «Полное имя 2» и т. д., а не имена менеджеров по продажам. Кроме того, размер секторов круговой диаграммы неточен.</span><span class="sxs-lookup"><span data-stu-id="36ac9-185">The legend reads Full Name 1, Full Name 2, etc., rather than the salespeople's names, and the size of the slices of pie are not accurate.</span></span> <span data-ttu-id="36ac9-186">Это изображение дает лишь общее представление о том, как будет выглядеть отчет.</span><span class="sxs-lookup"><span data-stu-id="36ac9-186">This is just to give you an idea of what your report will look like.</span></span>

15. <span data-ttu-id="36ac9-187">Чтобы просмотреть настоящую круговую диаграмму, нажмите кнопку **Выполнить** на вкладке **Главная** ленты.</span><span class="sxs-lookup"><span data-stu-id="36ac9-187">To see your actual pie chart, click **Run** on the **Home** tab of the Ribbon.</span></span>

 <span data-ttu-id="36ac9-188">![Значок стрелки, используемый для ссылки возврата в](../../2014-toc/media/uparrow16x16.gif "Значок стрелки, используемый со ссылкой В начало") [Начало](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="36ac9-188">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

##  <a name="after-you-run-the-wizard"></a><a name="AfterWizard"></a><span data-ttu-id="36ac9-189">После запуска мастера</span><span class="sxs-lookup"><span data-stu-id="36ac9-189">After You Run the Wizard</span></span>
 <span data-ttu-id="36ac9-190">После получения отчета с круговой диаграммой его можно изменить.</span><span class="sxs-lookup"><span data-stu-id="36ac9-190">Now that you have your pie chart report, you can play with it.</span></span> <span data-ttu-id="36ac9-191">На вкладке **Выполнение** ленты выберите **Проектирование**, чтобы продолжить изменение отчета.</span><span class="sxs-lookup"><span data-stu-id="36ac9-191">On the **Run** tab of the Ribbon, click **Design**, so you can continue modifying it.</span></span>

### <a name="make-the-chart-bigger"></a><span data-ttu-id="36ac9-192">Увеличение диаграммы</span><span class="sxs-lookup"><span data-stu-id="36ac9-192">Make the chart bigger</span></span>
 <span data-ttu-id="36ac9-193">Может возникнуть необходимость в увеличении размера круговой диаграммы.</span><span class="sxs-lookup"><span data-stu-id="36ac9-193">You may want the pie chart to be bigger.</span></span> <span data-ttu-id="36ac9-194">Для увеличения диаграммы щелкните диаграмму вне области какого-либо элемента диаграммы, чтобы выделить ее и перетащить нижний правый угол.</span><span class="sxs-lookup"><span data-stu-id="36ac9-194">Click the chart, but not on any element in the chart, to select it and drag the lower-right corner to resize it.</span></span>

### <a name="add-a-report-title"></a><span data-ttu-id="36ac9-195">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="36ac9-195">Add a report title</span></span>
 <span data-ttu-id="36ac9-196">В верхней части диаграммы выберите слова **Заголовок диаграммы** , а затем введите заголовок, например, **Круговая диаграмма продаж**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-196">Select the words **Chart title** at the top of the chart, and then type a title, such as **Sales Pie Chart**.</span></span>

### <a name="add-percentages"></a><span data-ttu-id="36ac9-197">Добавление процентных показателей</span><span class="sxs-lookup"><span data-stu-id="36ac9-197">Add percentages</span></span>

##### <a name="to-display-percentage-values-as-labels-on-a-pie-chart"></a><span data-ttu-id="36ac9-198">Отображение на круговой диаграмме значений в процентах в качестве меток</span><span class="sxs-lookup"><span data-stu-id="36ac9-198">To display percentage values as labels on a pie chart</span></span>

1.  <span data-ttu-id="36ac9-199">Щелкните правой кнопкой мыши круговую диаграмму и выберите команду **отобразить метки данных**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-199">Right-click on the pie chart and select **Show Data Labels**.</span></span> <span data-ttu-id="36ac9-200">Метки данных должны появиться в каждом срезе круговой диаграммы.</span><span class="sxs-lookup"><span data-stu-id="36ac9-200">The data labels should appear within each slice on the pie chart.</span></span>

2.  <span data-ttu-id="36ac9-201">Щелкните правой кнопкой мыши метки и выберите пункт **Свойства метки ряда**.</span><span class="sxs-lookup"><span data-stu-id="36ac9-201">Right-click on the labels and select **Series Label Properties**.</span></span> <span data-ttu-id="36ac9-202">Появится диалоговое окно **Свойства метки ряда** .</span><span class="sxs-lookup"><span data-stu-id="36ac9-202">The **Series Label Properties** dialog box appears.</span></span>

3.  <span data-ttu-id="36ac9-203">Введите `#PERCENT{P0}` для параметра **данных метки** .</span><span class="sxs-lookup"><span data-stu-id="36ac9-203">Type `#PERCENT{P0}` for the **Label data** option.</span></span>

     <span data-ttu-id="36ac9-204">Значение `{P0}` дает процент без десятичных разрядов.</span><span class="sxs-lookup"><span data-stu-id="36ac9-204">The `{P0}` gives you the percentage without decimal places.</span></span> <span data-ttu-id="36ac9-205">Если просто ввести `#PERCENT`, числа будут иметь два десятичных разряда.</span><span class="sxs-lookup"><span data-stu-id="36ac9-205">If you type just `#PERCENT`, your numbers will have two decimal places.</span></span> <span data-ttu-id="36ac9-206">`#PERCENT` является ключевым словом, с помощью которого выполняются вычисления; имеются и многие другие ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="36ac9-206">`#PERCENT` is a keyword that performs a calculation or function for you; there are many others.</span></span>

 <span data-ttu-id="36ac9-207">Дополнительные сведения о настройке меток диаграммы и условные обозначения см. в разделе [Отображение процентных значений на круговой диаграмме (построитель отчетов и службы SSRS)](../report-design/display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) и [Изменение текста элемента условных обозначений (построитель отчетов и службы SSRS)](../report-design/chart-legend-change-item-text-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="36ac9-207">For more information about customizing chart labels and legends, see [Display Percentage Values on a Pie Chart &#40;Report Builder and SSRS&#41;](../report-design/display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) and [Change the Text of a Legend Item &#40;Report Builder and SSRS&#41;](../report-design/chart-legend-change-item-text-report-builder.md).</span></span>

 <span data-ttu-id="36ac9-208">![Значок стрелки, используемый для ссылки возврата в](../../2014-toc/media/uparrow16x16.gif "Значок стрелки, используемый со ссылкой В начало") [Начало](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="36ac9-208">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

##  <a name="whats-next"></a><a name="WhatsNext"></a><span data-ttu-id="36ac9-209">Что дальше?</span><span class="sxs-lookup"><span data-stu-id="36ac9-209">What's Next?</span></span>
 <span data-ttu-id="36ac9-210">Теперь после создания первого отчета в построителе отчетов можно ознакомиться с другими учебниками и начать создавать отчеты на основе собственных данных.</span><span class="sxs-lookup"><span data-stu-id="36ac9-210">Now that you have created your first report in Report Builder, you are ready to try the other tutorials and to start creating reports from your own data.</span></span> <span data-ttu-id="36ac9-211">Для запуска построитель отчетов необходимо разрешение на доступ к источникам данных, таким как базы данных, со *строкой подключения*, которая фактически подключается к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="36ac9-211">To run Report Builder, you need permission to access your data sources, such as databases, with a *connection string*, which actually connects you to the data source.</span></span> <span data-ttu-id="36ac9-212">У системного администратора имеются эти данные, и он может установить соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="36ac9-212">Your system administrator will have this information and can set you up.</span></span>

 <span data-ttu-id="36ac9-213">Для выполнения других учебников необходимо имя экземпляра [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] и учетные данные, необходимые для доступа к базе данных только для чтения.</span><span class="sxs-lookup"><span data-stu-id="36ac9-213">To work through the other tutorials, you need the name of an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] and credentials sufficient for read-only access to any database.</span></span> <span data-ttu-id="36ac9-214">Системный администратор также может предоставить такой доступ.</span><span class="sxs-lookup"><span data-stu-id="36ac9-214">Your system administrator can also set that up for you.</span></span>

 <span data-ttu-id="36ac9-215">Наконец, чтобы сохранять отчеты в сервере отчетов или на сайте SharePoint, интегрированном с сервером отчетов, необходимы URL-адрес и разрешения.</span><span class="sxs-lookup"><span data-stu-id="36ac9-215">Finally, to save your reports to a report server or a SharePoint site that is integrated with a report server, you need the URL and permissions.</span></span> <span data-ttu-id="36ac9-216">Можно выполнять любой отчет, создаваемый непосредственно на компьютере, но если отчеты запускаются с сервера отчетов или из сайта SharePoint, они обладают более широкими функциональными возможностями.</span><span class="sxs-lookup"><span data-stu-id="36ac9-216">You can run any report you create directly from your computer, but reports have more functionality when run from the report server or SharePoint site.</span></span> <span data-ttu-id="36ac9-217">Для запуска опубликованных отчетов с сервера отчетов или из сайта SharePoint необходимы разрешения.</span><span class="sxs-lookup"><span data-stu-id="36ac9-217">You need permissions to run your reports or others from the report server or SharePoint site where they are published.</span></span> <span data-ttu-id="36ac9-218">Для получения соответствующих прав доступа можно также обратиться к системному администратору.</span><span class="sxs-lookup"><span data-stu-id="36ac9-218">Talk to your system administrator to obtain access.</span></span>

 <span data-ttu-id="36ac9-219">Перед началом работы он может помочь в ознакомлении с некоторыми основными понятиями и терминами.</span><span class="sxs-lookup"><span data-stu-id="36ac9-219">It may help to read about some of the concepts and terms before you get started.</span></span> <span data-ttu-id="36ac9-220">Дополнительные сведения см. в разделе [Основные понятия разработки отчетов &#40;построитель отчетов и службы SSRS&#41;](../report-design/report-authoring-concepts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="36ac9-220">For more information, see [Report Authoring Concepts &#40;Report Builder and SSRS&#41;](../report-design/report-authoring-concepts-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="36ac9-221">Кроме того, перед созданием первого отчета необходимо затратить некоторое время на планирование.</span><span class="sxs-lookup"><span data-stu-id="36ac9-221">Also, spend some time planning, before you create your first report.</span></span> <span data-ttu-id="36ac9-222">Это время не будет затрачено впустую.</span><span class="sxs-lookup"><span data-stu-id="36ac9-222">It will be time well spent.</span></span> <span data-ttu-id="36ac9-223">Дополнительные сведения см. в разделе [Planning a Report &#40;построитель отчетов&#41;](../report-design/planning-a-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="36ac9-223">For more information, see [Planning a Report &#40;Report Builder&#41;](../report-design/planning-a-report-report-builder.md).</span></span>

 <span data-ttu-id="36ac9-224">![Значок стрелки, используемый для ссылки возврата в](../../2014-toc/media/uparrow16x16.gif "Значок стрелки, используемый со ссылкой В начало") [Начало](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="36ac9-224">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

## <a name="see-also"></a><span data-ttu-id="36ac9-225">См. также:</span><span class="sxs-lookup"><span data-stu-id="36ac9-225">See Also</span></span>
 <span data-ttu-id="36ac9-226">[Учебники &#40;построитель отчетов&#41;](../report-builder-tutorials.md) [построитель отчетов в SQL Server 2014](report-builder-in-sql-server-2016.md)</span><span class="sxs-lookup"><span data-stu-id="36ac9-226">[Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md) [Report Builder in SQL Server 2014](report-builder-in-sql-server-2016.md)</span></span>


