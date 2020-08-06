---
title: Добавление вложенного отчета и параметров (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10093"
- sql12.rtp.rptdesigner.subreportproperties.general.f1
ms.assetid: 94f960f8-a629-4f1e-8277-c3b8f0680d98
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3aeede343763ea5fc8fbdfde179208f98fa1a2ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654804"
---
# <a name="add-a-subreport-and-parameters-report-builder-and-ssrs"></a><span data-ttu-id="47982-102">Добавление вложенного отчета и параметров (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="47982-102">Add a Subreport and Parameters (Report Builder and SSRS)</span></span>
  <span data-ttu-id="47982-103">Вложенные отчеты следует использовать в том случае, если необходимо создать основной отчет, являющийся контейнером для нескольких связанных отчетов.</span><span class="sxs-lookup"><span data-stu-id="47982-103">Add subreports to a report when you want to create a main report that is a container for multiple related reports.</span></span> <span data-ttu-id="47982-104">Вложенный отчет — это ссылка на другой отчет.</span><span class="sxs-lookup"><span data-stu-id="47982-104">A subreport is a reference to another report.</span></span> <span data-ttu-id="47982-105">Чтобы связать отчеты посредством значений данных (например, для отображения данных из нескольких отчетов одному клиенту), необходимо разработать параметризованный отчет (например отчет, показывающий сведения об определенном клиенте), который будет служить в качестве вложенного отчета.</span><span class="sxs-lookup"><span data-stu-id="47982-105">To relate the reports through data values (for example, to have multiple reports show data for the same customer), you must design a parameterized report (for example, a report that shows the details for a specific customer) as the subreport.</span></span> <span data-ttu-id="47982-106">При добавлении вложенного отчета в основной отчет можно указать параметры, которые будут переданы вложенному отчету.</span><span class="sxs-lookup"><span data-stu-id="47982-106">When you add a subreport to the main report, you can specify parameters to pass to the subreport.</span></span>  
  
 <span data-ttu-id="47982-107">Вложенные отчеты также можно добавить к динамическим строкам или столбцам в таблице или матрице.</span><span class="sxs-lookup"><span data-stu-id="47982-107">You can also add subreports to dynamic rows or columns in a table or matrix.</span></span> <span data-ttu-id="47982-108">При обработке основного отчета будет выполнена обработка вложенного отчета для каждой строки.</span><span class="sxs-lookup"><span data-stu-id="47982-108">When the main report is processed, the subreport is processed for each row.</span></span> <span data-ttu-id="47982-109">В данном случае следует оценить, можно ли получить необходимый результат с помощью областей данных или вложенных областей данных.</span><span class="sxs-lookup"><span data-stu-id="47982-109">In this case, consider whether you can achieve the desired effect by using data regions or nested data regions.</span></span>  
  
 <span data-ttu-id="47982-110">Чтобы добавить вложенный отчет к отчету, сначала необходимо создать отчет, который будет использоваться в качестве вложенного.</span><span class="sxs-lookup"><span data-stu-id="47982-110">To add a subreport to a report, you must first create the report that will act as the subreport.</span></span> <span data-ttu-id="47982-111">Дополнительные сведения о создании вложенного отчета см. в разделе [Вложенные отчеты (построитель отчетов и службы SSRS)](subreports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="47982-111">For more information on creating the subreport, see [Subreports &#40;Report Builder and SSRS&#41;](subreports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-subreport"></a><span data-ttu-id="47982-112">Добавление вложенного отчета</span><span class="sxs-lookup"><span data-stu-id="47982-112">To add a subreport</span></span>  
  
1.  <span data-ttu-id="47982-113">На вкладке **Вставка** щелкните **Вложенный отчет**.</span><span class="sxs-lookup"><span data-stu-id="47982-113">On the **Insert** tab, click **Subreport**.</span></span>  
  
2.  <span data-ttu-id="47982-114">В области конструктора щелкните поверхность отчета и перетащите его поле до желаемого размера вложенного отчета.</span><span class="sxs-lookup"><span data-stu-id="47982-114">On the design surface, click a location on the report and then drag a box to the desired size of the subreport.</span></span> <span data-ttu-id="47982-115">Либо щелкните область конструктора, чтобы создать вложенный отчет с размером по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="47982-115">Alternatively, click the design surface to create a subreport of default size.</span></span>  
  
3.  <span data-ttu-id="47982-116">Щелкните правой кнопкой мыши вложенный отчет, а затем выберите пункт **Свойства вложенного отчета**.</span><span class="sxs-lookup"><span data-stu-id="47982-116">Right-click the subreport, and then click **Subreport Properties**.</span></span>  
  
4.  <span data-ttu-id="47982-117">В диалоговом окне **Свойства вложенного отчета** введите имя в текстовое поле **Имя** или примите имя по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="47982-117">In the **Subreport Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span> <span data-ttu-id="47982-118">В пределах отчета имя должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="47982-118">The name must be unique within the report.</span></span> <span data-ttu-id="47982-119">По умолчанию присваивается стандартное имя, такое как Subreport1 или Subreport2.</span><span class="sxs-lookup"><span data-stu-id="47982-119">By default, a general name such as Subreport1 or Subreport2 is assigned.</span></span>  
  
5.  <span data-ttu-id="47982-120">В списке **Использовать этот отчет в качестве вложенного отчета** нажмите кнопку **Обзор**или введите имя отчета.</span><span class="sxs-lookup"><span data-stu-id="47982-120">In the **Use this report as a subreport** box, click **Browse**, or type the name of the report.</span></span> <span data-ttu-id="47982-121">Рекомендуется нажать кнопку **Обзор** , поскольку путь к вложенному отчету будет указан автоматически.</span><span class="sxs-lookup"><span data-stu-id="47982-121">Clicking **Browse** is preferred because the path to the subreport will be specified automatically.</span></span> <span data-ttu-id="47982-122">Указать отчет можно несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="47982-122">You can specify the report in the several ways.</span></span> <span data-ttu-id="47982-123">Дополнительные сведения см. в разделе [Указание путей к внешним элементам (построитель отчетов и службы SSRS)](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="47982-123">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="47982-124">Щелкните **Да** в области **Пропустить границу на разрыве страницы** , чтобы предотвратить вывод границы в середине вложенного отчета, если он занимает более одной страницы (необязательно).</span><span class="sxs-lookup"><span data-stu-id="47982-124">(Optional) Click **Yes** for **Omit border on page break** to prevent a border from being rendered in the middle of the subreport if the subreport spans more than one page.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-specify-parameters-to-pass-to-a-subreport"></a><span data-ttu-id="47982-125">Указание параметров, передаваемых вложенному отчету</span><span class="sxs-lookup"><span data-stu-id="47982-125">To specify parameters to pass to a subreport</span></span>  
  
1.  <span data-ttu-id="47982-126">В режиме конструктора щелкните правой кнопкой мыши вложенный отчет и выберите **Свойства вложенного отчета**.</span><span class="sxs-lookup"><span data-stu-id="47982-126">In Design view, right-click the subreport and then click **Subreport Properties**.</span></span>  
  
2.  <span data-ttu-id="47982-127">В диалоговом окне **Свойства вложенного отчета** щелкните **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="47982-127">In the **Subreport Properties** dialog box, click **Parameters**.</span></span>  
  
3.  <span data-ttu-id="47982-128">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="47982-128">Click **Add**.</span></span> <span data-ttu-id="47982-129">В сетку параметров добавится новая строка.</span><span class="sxs-lookup"><span data-stu-id="47982-129">A new row is added to the parameter grid.</span></span>  
  
4.  <span data-ttu-id="47982-130">Введите имя параметра во вложенном отчете в текстовое поле **Имя** или выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="47982-130">In the **Name** text box, type the name of a parameter in the subreport or choose it from the list box.</span></span> <span data-ttu-id="47982-131">Это имя должно совпадать с именем параметра вложенного отчета, а не с именем параметра запроса.</span><span class="sxs-lookup"><span data-stu-id="47982-131">This name must match a report parameter, not a query parameter, in the subreport.</span></span>  
  
5.  <span data-ttu-id="47982-132">В списке **Значение** введите или выберите значение для передачи вложенному отчету.</span><span class="sxs-lookup"><span data-stu-id="47982-132">In the **Value** list box, type or select a value to pass to the subreport.</span></span> <span data-ttu-id="47982-133">Это значение может быть статическим текстом или выражением, ссылающимся на какое-либо поле или иной объект в основном отчете.</span><span class="sxs-lookup"><span data-stu-id="47982-133">This value can be static text or an expression that references a field or other object in the main report.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="47982-134">Если в списке **Параметры** построителя отчетов пропущен параметр, а вложенный отчет имеет определенное значение по умолчанию, вложенный отчет будет обработан правильно.</span><span class="sxs-lookup"><span data-stu-id="47982-134">In Report Builder, if a parameter is missing from the **Parameters** list and the subreport has a default value defined, the subreport will be processed correctly.</span></span>  
    >   
    >  <span data-ttu-id="47982-135">В конструкторе отчетов все параметры, которые требуются вложенному отчету, должны быть включены в список **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="47982-135">In Report Designer, all parameters that are required by the subreport must be included in the **Parameters** list.</span></span> <span data-ttu-id="47982-136">Если не хватает какого-либо требуемого параметра, вложенный отчет не будет правильно отображен в основном отчете.</span><span class="sxs-lookup"><span data-stu-id="47982-136">If a required parameter is missing, the subreport is not displayed correctly in the main report.</span></span>  
  
6.  <span data-ttu-id="47982-137">Повторите шаги с 3 по 5, чтобы указать имена и значения для всех параметров вложенного отчета.</span><span class="sxs-lookup"><span data-stu-id="47982-137">Repeat steps 3-5 to specify a name and value for each subreport parameter.</span></span>  
  
7.  <span data-ttu-id="47982-138">Для удаления параметра вложенного отчета щелкните этот параметр в сетке параметров и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="47982-138">To delete a subreport parameter, click the parameter in the parameter grid, and then click **Delete**.</span></span>  
  
8.  <span data-ttu-id="47982-139">Чтобы изменить порядок параметров вложенного отчета, щелкните параметр и нажмите кнопку со стрелкой вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="47982-139">To change the order of a subreport parameter, click the parameter, and then click the up button or the down button.</span></span>  
  
     <span data-ttu-id="47982-140">Изменение порядка параметров вложенного отчета не скажется на обработке вложенного отчета.</span><span class="sxs-lookup"><span data-stu-id="47982-140">Changing the order of a subreport parameter does not affect the processing of the subreport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47982-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="47982-141">See Also</span></span>  
 <span data-ttu-id="47982-142">[Вложенные отчеты (построитель отчетов и службы SSRS)](subreports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="47982-142">[Subreports &#40;Report Builder and SSRS&#41;](subreports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="47982-143">Поведение при подготовке к просмотру (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="47982-143">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](rendering-behaviors-report-builder-and-ssrs.md)  
  
  
