---
title: Создание измерения с помощью мастера измерений | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], creating
ms.assetid: d84f66ae-7551-49bf-99d0-88368ca2dd0e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9ec38dc7170b915dce0cedea60c93385560e11f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737055"
---
# <a name="create-a-dimension-using-the-dimension-wizard"></a><span data-ttu-id="ea331-102">Создание измерения с помощью мастера измерений</span><span class="sxs-lookup"><span data-stu-id="ea331-102">Create a Dimension Using the Dimension Wizard</span></span>
  <span data-ttu-id="ea331-103">Можно создать новое измерение с помощью мастера измерений в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea331-103">You can create a new dimension by using the Dimension Wizard in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="to-create-a-new-dimension"></a><span data-ttu-id="ea331-104">Создание нового измерения</span><span class="sxs-lookup"><span data-stu-id="ea331-104">To create a new dimension</span></span>  
  
1.  <span data-ttu-id="ea331-105">В **обозревателе решений**щелкните правой кнопкой мыши узел **Измерения**и выберите команду **Создать измерение**.</span><span class="sxs-lookup"><span data-stu-id="ea331-105">In **Solution Explorer**, right-click **Dimensions**, and then click **New Dimension**.</span></span>  
  
2.  <span data-ttu-id="ea331-106">На странице **Выбор метода создания** мастера измерений выберите **Использовать существующую таблицу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ea331-106">On the **Select Creation Method** page of the Dimension Wizard, select **Use an existing table**, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ea331-107">Иногда приходится создавать измерение, не используя существующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="ea331-107">You might occasionally have to create a dimension without using an existing table.</span></span> <span data-ttu-id="ea331-108">Дополнительные сведения см. в разделах [Создание измерения путем формирования в источнике данных таблицы, отличной от таблицы времени](create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md) и [Создание измерения времени посредством формирования таблицы времени](create-a-time-dimension-by-generating-a-time-table.md).</span><span class="sxs-lookup"><span data-stu-id="ea331-108">For more information, see [Create a Dimension by Generating a Non-Time Table in the Data Source](create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md) and [Create a Time Dimension by Generating a Time Table](create-a-time-dimension-by-generating-a-time-table.md).</span></span>  
  
3.  <span data-ttu-id="ea331-109">На странице **Определение исходных сведений** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ea331-109">On the **Specify Source Information** page, do the following procedures:</span></span>  
  
    1.  <span data-ttu-id="ea331-110">В списке **Представление источника данных** выберите представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="ea331-110">In the **Data source view** list, select a data source view.</span></span>  
  
    2.  <span data-ttu-id="ea331-111">В списке **Основная таблица** выберите основную таблицу измерения.</span><span class="sxs-lookup"><span data-stu-id="ea331-111">In the **Main table** list, select the main dimension table.</span></span>  
  
    3.  <span data-ttu-id="ea331-112">В списке **Ключевые столбцы** просмотрите список ключевых столбцов, автоматически выбранных мастером на основе первичного ключа, заданного в основной таблице измерений.</span><span class="sxs-lookup"><span data-stu-id="ea331-112">In the **Key columns** list, review the key columns that the wizard has automatically selected based on the primary key that is defined in the main dimension table.</span></span> <span data-ttu-id="ea331-113">Для изменения настроек по умолчанию задайте ключевые столбцы, связывающие таблицу измерения с таблицей фактов.</span><span class="sxs-lookup"><span data-stu-id="ea331-113">To change this default setting, specify the key columns that link the dimension table to the fact table.</span></span>  
  
    4.  <span data-ttu-id="ea331-114">В раскрывающемся списке **Столбец имени** проверьте столбец имен, автоматически выбранный мастером.</span><span class="sxs-lookup"><span data-stu-id="ea331-114">In the **Name column** drop-down list, review the name column that the wizard has automatically selected.</span></span>  
  
         <span data-ttu-id="ea331-115">Имя, используемое по умолчанию, подходит, если столбец содержит описательные сведения.</span><span class="sxs-lookup"><span data-stu-id="ea331-115">This default name is appropriate when the column contains descriptive information.</span></span> <span data-ttu-id="ea331-116">Однако при желании можно задать имя, более значимое для конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="ea331-116">However, you might want to specify a name that contains values that are more meaningful for the end user.</span></span> <span data-ttu-id="ea331-117">Например, если атрибут категории продуктов в измерении «Продукты» использует столбец **ProductCategoryKey** в качестве ключевого столбца, то можно в качестве его столбца имени указать столбец **ProductCategoryName** .</span><span class="sxs-lookup"><span data-stu-id="ea331-117">For example, if a product category attribute in a Products dimension uses the **ProductCategoryKey** column as its key column, you can specify the **ProductCategoryName** column as its name column.</span></span>  
  
         <span data-ttu-id="ea331-118">Если список **Ключевые столбцы** содержит несколько ключевых столбцов, следует задать столбец имени, из которого будут взяты значения элементов для ключевого атрибута.</span><span class="sxs-lookup"><span data-stu-id="ea331-118">If the **Key columns** list contains multiple key columns, you must specify a name column that provides the member values for the key attribute.</span></span> <span data-ttu-id="ea331-119">Для этого создайте именованное вычисление в представлении источника данных и используйте его как столбец имени.</span><span class="sxs-lookup"><span data-stu-id="ea331-119">To do this, you can create a named calculation in the data source view and use that as the name column.</span></span>  
  
    5.  <span data-ttu-id="ea331-120">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ea331-120">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="ea331-121">На странице **Выбор связанных таблиц** выберите связанные таблицы, которые нужно включить в измерение, и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ea331-121">On the **Select Related Tables** page, select the related tables that you want to include in your dimension, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ea331-122"> Страница **Выбор связанных таблиц** появляется, если заданная основная таблица измерения связана с другими таблицами.</span><span class="sxs-lookup"><span data-stu-id="ea331-122">The **Select Related Tables** page appears if the main dimension table that you specified has relationships to other dimension tables.</span></span>  
  
5.  <span data-ttu-id="ea331-123">На странице **Выбор атрибутов измерения** выберите атрибуты, которые нужно включить в измерение, а затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ea331-123">On the **Select Dimension Attributes** page, select the attributes that you want to include in the dimension, and then click **Next**.</span></span>  
  
     <span data-ttu-id="ea331-124">При необходимости можно поменять имена атрибутов, разрешить или запретить просмотр и задать тип атрибута.</span><span class="sxs-lookup"><span data-stu-id="ea331-124">Optionally, you can change the attribute names, enable or disable browsing, and specify the attribute type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ea331-125"> Чтобы поля **Разрешить обзор** и **Тип атрибута** были активны, необходимо выбрать атрибут для включения в измерение.</span><span class="sxs-lookup"><span data-stu-id="ea331-125">To make the **Enable Browsing** and **Attribute Type** fields of an attribute active, the attribute must be selected for inclusion in the dimension.</span></span>  
  
6.  <span data-ttu-id="ea331-126">На странице **Определение логики операций со счетами** в столбце **Встроенные типы счетов** выберите тип счета, а затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ea331-126">On the **Define Account Intelligence** page, in the **Built-In Account Types** column, select the account type, and then click **Next**.</span></span>  
  
     <span data-ttu-id="ea331-127">Тип счета должен соответствовать типу счета исходной таблицы, указанному в столбце **Типы счетов исходной таблицы** .</span><span class="sxs-lookup"><span data-stu-id="ea331-127">The account type must correspond to the account type of the source table that is listed in the **Source Table Account Types** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ea331-128"> Страница **Определение логики операций со счетами** появляется, если вы определили атрибут измерения **Тип счета** на странице **Выбор атрибутов измерения** мастера.</span><span class="sxs-lookup"><span data-stu-id="ea331-128">The **Define Account Intelligence** page appears if you defined an **Account Type** dimension attribute on the **Select Dimension Attributes** page of the wizard.</span></span>  
  
7.  <span data-ttu-id="ea331-129">На странице **Завершение работы мастера** введите имя для этого нового измерения и просмотрите структуру измерения.</span><span class="sxs-lookup"><span data-stu-id="ea331-129">On the **Completing the Wizard** page, enter a name for the new dimension and review the dimension structure.</span></span> <span data-ttu-id="ea331-130">Если надо что-либо изменить, нажмите кнопку **Назад**, если нет, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ea331-130">If you want to make changes, click **Back**; otherwise, click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ea331-131">После добавления, удаления и настройки атрибутов и иерархий в измерении с помощью мастера измерений можно использовать конструктор измерений.</span><span class="sxs-lookup"><span data-stu-id="ea331-131">You can use Dimension Designer after you complete the Dimension Wizard to add, remove, and configure attributes and hierarchies in the dimension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea331-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="ea331-132">See Also</span></span>  
 [<span data-ttu-id="ea331-133">Создание измерения с помощью существующей таблицы</span><span class="sxs-lookup"><span data-stu-id="ea331-133">Create a Dimension by Using an Existing Table</span></span>](create-a-dimension-by-using-an-existing-table.md)  
  
  
