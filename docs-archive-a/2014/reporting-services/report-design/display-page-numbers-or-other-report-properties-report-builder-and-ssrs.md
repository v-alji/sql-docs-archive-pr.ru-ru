---
title: Отображение номеров страниц или других свойств отчета (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c7d95245-4709-4d04-acb4-59bf71e60d97
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: efc3d5d5de11af1fcdfefc52ed12d5057ee12668
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663955"
---
# <a name="display-page-numbers-or-other-report-properties-report-builder-and-ssrs"></a><span data-ttu-id="48bf2-102">Отображение номеров страниц или других свойств отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="48bf2-102">Display Page Numbers or Other Report Properties (Report Builder and SSRS)</span></span>
  <span data-ttu-id="48bf2-103">К верхним или нижним колонтитулам страниц в отчете легко добавить номера страниц, заголовок отчета, имя файла и другие свойства отчета.</span><span class="sxs-lookup"><span data-stu-id="48bf2-103">It's easy to add page numbers, a report title, file name, and other report properties to the page headers or footers of your report.</span></span> <span data-ttu-id="48bf2-104">Эти свойства хранятся в виде полей в папке «Встроенные поля» в области данных отчета.</span><span class="sxs-lookup"><span data-stu-id="48bf2-104">These properties are stored as fields in the Built-in Fields folder in the Report Data pane:</span></span>  
  
-   <span data-ttu-id="48bf2-105">Время выполнения;</span><span class="sxs-lookup"><span data-stu-id="48bf2-105">Execution time</span></span>  
  
-   <span data-ttu-id="48bf2-106">Номер страницы</span><span class="sxs-lookup"><span data-stu-id="48bf2-106">Page number</span></span>  
  
-   <span data-ttu-id="48bf2-107">Папка отчета;</span><span class="sxs-lookup"><span data-stu-id="48bf2-107">Report folder</span></span>  
  
-   <span data-ttu-id="48bf2-108">Имя отчета</span><span class="sxs-lookup"><span data-stu-id="48bf2-108">Report name</span></span>  
  
-   <span data-ttu-id="48bf2-109">URL-адрес сервера отчетов;</span><span class="sxs-lookup"><span data-stu-id="48bf2-109">Report server URL</span></span>  
  
-   <span data-ttu-id="48bf2-110">Всего страниц</span><span class="sxs-lookup"><span data-stu-id="48bf2-110">Total pages</span></span>  
  
-   <span data-ttu-id="48bf2-111">Идентификатор пользователя.</span><span class="sxs-lookup"><span data-stu-id="48bf2-111">User ID</span></span>  
  
-   <span data-ttu-id="48bf2-112">Язык</span><span class="sxs-lookup"><span data-stu-id="48bf2-112">Language</span></span>  
  
 <span data-ttu-id="48bf2-113">При задании номера страницы может понадобиться добавить слово «Страница» перед номером.</span><span class="sxs-lookup"><span data-stu-id="48bf2-113">For a page number, you may want to add the word "Page" before the number.</span></span> <span data-ttu-id="48bf2-114">Также можно отобразить общее число страниц.</span><span class="sxs-lookup"><span data-stu-id="48bf2-114">You may also want to show the total number of pages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48bf2-115">Добавление общего числа страниц в нижний колонтитул может снизить производительность во время выполнения или предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="48bf2-115">Adding the total number of pages to the footer may slow performance when you run or preview your report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-number-or-other-report-properties"></a><span data-ttu-id="48bf2-116">Добавление номера страницы или других свойств отчета</span><span class="sxs-lookup"><span data-stu-id="48bf2-116">To add a page number or other report properties</span></span>  
  
1.  <span data-ttu-id="48bf2-117">В области данных отчета разверните папку «Встроенные поля».</span><span class="sxs-lookup"><span data-stu-id="48bf2-117">In the Report Data pane, expand the Built-in Fields folder.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="48bf2-118">Если область данных отчета не видна, на вкладке "Вид" установите флажок **Данные отчета**.</span><span class="sxs-lookup"><span data-stu-id="48bf2-118">If you don't see the Report Data pane, on the View tab, check **Report Data**.</span></span>  
  
2.  <span data-ttu-id="48bf2-119">Перетащите поле **Номер страницы** из области данных отчета в верхний или нижний колонтитул отчета.</span><span class="sxs-lookup"><span data-stu-id="48bf2-119">Drag the **Page Number** field from the Report Data pane to the report header or footer.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="48bf2-120">Нижний колонтитул страницы добавляется в отчет автоматически.</span><span class="sxs-lookup"><span data-stu-id="48bf2-120">The page footer is added to the report automatically.</span></span> <span data-ttu-id="48bf2-121">Чтобы добавить верхний колонтитул страницы, на вкладке **Вставка** выберите **Верхний колонтитул**, а затем **Добавить верхний колонтитул**.</span><span class="sxs-lookup"><span data-stu-id="48bf2-121">To add a page header, on the **Insert** tab, click **Header**, and then click **Add Header**.</span></span>  
    >   
    >  <span data-ttu-id="48bf2-122">Добавится текстовое поле, содержащее простое выражение [&PageNumber].</span><span class="sxs-lookup"><span data-stu-id="48bf2-122">A text box that contains the simple expression [&PageNumber] is added.</span></span>  
  
### <a name="to-add-the-word-page-before-the-page-number"></a><span data-ttu-id="48bf2-123">Добавление слова «Страница» перед номером страницы</span><span class="sxs-lookup"><span data-stu-id="48bf2-123">To add the word "Page" before the page number</span></span>  
  
1.  <span data-ttu-id="48bf2-124">Щелкните правой кнопкой мыши текстовое поле, содержащее выражение [&PageNumber], и выберите пункт **Выражения**.</span><span class="sxs-lookup"><span data-stu-id="48bf2-124">Right-click the text box that contains [&PageNumber] and click **Expressions**.</span></span>  
  
     <span data-ttu-id="48bf2-125">Текстовое поле **Задать выражение для: значение** содержит выражение =Globals!PageNumber.</span><span class="sxs-lookup"><span data-stu-id="48bf2-125">The **Set Expression for: Value** text box contains the expression =Globals!PageNumber.</span></span>  
  
2.  <span data-ttu-id="48bf2-126">Установите курсор после знака = и введите текст `"Page " &`.</span><span class="sxs-lookup"><span data-stu-id="48bf2-126">Place the cursor after the = sign and type `"Page " &`.</span></span>  
  
     <span data-ttu-id="48bf2-127">Теперь выражение будет иметь вид ="Стр. "&Globals!PageNumber</span><span class="sxs-lookup"><span data-stu-id="48bf2-127">The expression is now  ="Page "&Globals!PageNumber</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-add-total-number-of-pages-after-the-page-number"></a><span data-ttu-id="48bf2-128">Добавление общего числа страниц после номера страницы</span><span class="sxs-lookup"><span data-stu-id="48bf2-128">To add total number of pages after the page number</span></span>  
  
1.  <span data-ttu-id="48bf2-129">Щелкните правой кнопкой мыши текстовое поле с выражением и выберите пункт **Выражения**.</span><span class="sxs-lookup"><span data-stu-id="48bf2-129">Right click the text box with the expression and click **Expressions**.</span></span>  
  
2.  <span data-ttu-id="48bf2-130">Введите текст **&" из "&** в конце выражения.</span><span class="sxs-lookup"><span data-stu-id="48bf2-130">Type **&" of "&** at the end of the expression.</span></span>  
  
3.  <span data-ttu-id="48bf2-131">На панели категорий разверните узел **Встроенные поля** и дважды щелкните поле **TotalPages**.</span><span class="sxs-lookup"><span data-stu-id="48bf2-131">In the Category pane, expand **Built-in Fields** and double-click **TotalPages**.</span></span>  
  
     <span data-ttu-id="48bf2-132">Выражение будет иметь вид ="Стр. "&Globals!PageNumber &" из "&Globals!TotalPages</span><span class="sxs-lookup"><span data-stu-id="48bf2-132">The expression is now ="Page "&Globals!PageNumber &" of "&Globals!TotalPages</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="48bf2-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="48bf2-133">See Also</span></span>  
 <span data-ttu-id="48bf2-134">[Верхние и нижние колонтитулы страницы (построитель отчетов и службы SSRS)](page-headers-and-footers-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="48bf2-134">[Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="48bf2-135">Форматирование текста в текстовом поле (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="48bf2-135">Format Text in a Text Box &#40;Report Builder and SSRS&#41;</span></span>](format-text-in-a-text-box-report-builder-and-ssrs.md)  
  
  
