---
title: Шаг 7. Добавление и настройка назначения OLE DB | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 442c841d-d528-4bf0-8724-7156f909ee50
author: chugugrace
ms.author: chugu
ms.openlocfilehash: da917ccc4ca756c2442e70477976b5a71f7eb56e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664344"
---
# <a name="step-7-adding-and-configuring-the-ole-db-destination"></a><span data-ttu-id="7c628-102">Шаг 7. Добавление и настройка назначения OLE DB</span><span class="sxs-lookup"><span data-stu-id="7c628-102">Step 7: Adding and Configuring the OLE DB Destination</span></span>
  <span data-ttu-id="7c628-103">Созданный пакет теперь может извлекать данные из источника «Неструктурированный файл» и преобразовывать эти данные в формат, совместимый с форматом назначения.</span><span class="sxs-lookup"><span data-stu-id="7c628-103">Your package now can extract data from the flat file source and transform that data into a format that is compatible with the destination.</span></span> <span data-ttu-id="7c628-104">Далее требуется загрузить преобразованные данные в указанное назначение.</span><span class="sxs-lookup"><span data-stu-id="7c628-104">The next task is to actually load the transformed data into the destination.</span></span> <span data-ttu-id="7c628-105">Чтобы загрузить данные, необходимо добавить назначение OLE DB в поток данных.</span><span class="sxs-lookup"><span data-stu-id="7c628-105">To load the data, you must add an OLE DB destination to the data flow.</span></span> <span data-ttu-id="7c628-106">Назначение OLE DB может использовать таблицу, представление или SQL-команду базы данных, чтобы загрузить данные в различные OLE DB-совместимые базы данных.</span><span class="sxs-lookup"><span data-stu-id="7c628-106">The OLE DB destination can use a database table, view, or an SQL command to load data into a variety of OLE DB-compliant databases.</span></span>  
  
 <span data-ttu-id="7c628-107">В этой процедуре добавляется и настраивается назначение OLE DB, что позволит использовать диспетчер соединений OLE DB, созданный ранее.</span><span class="sxs-lookup"><span data-stu-id="7c628-107">In this procedure, you add and configure an OLE DB destination to use the OLE DB connection manager that you previously created.</span></span>  
  
### <a name="to-add-and-configure-the-sample-ole-db-destination"></a><span data-ttu-id="7c628-108">Добавление и настройка образца назначения OLE DB</span><span class="sxs-lookup"><span data-stu-id="7c628-108">To add and configure the sample OLE DB destination</span></span>  
  
1.  <span data-ttu-id="7c628-109">В **области элементов служб SSIS**разверните **узел другие назначения**и перетащите **OLE DB назначение** в область конструктора на вкладке **поток данных** . Поместите OLE DB назначение непосредственно под преобразованием « **Уточняющий запрос ключа даты** ».</span><span class="sxs-lookup"><span data-stu-id="7c628-109">In the **SSIS Toolbox**, expand **Other Destinations**, and drag **OLE DB Destination** onto the design surface of the **Data Flow** tab. Place the OLE DB destination directly below the **Lookup Date Key** transformation.</span></span>  
  
2.  <span data-ttu-id="7c628-110">Щелкните преобразование **Уточняющий запрос ключа даты** и перетащите зеленую стрелку к недавно добавленному элементу **Назначение OLE DB** , чтобы соединить эти два компонента.</span><span class="sxs-lookup"><span data-stu-id="7c628-110">Click the **Lookup Date Key** transformation and drag the green arrow over to the newly added **OLE DB Destination** to connect the two components together.</span></span>  
  
3.  <span data-ttu-id="7c628-111">В диалоговом окне **Выбор входов и выходов** щелкните **Вывод совпадений преобразования "Уточняющий запрос"** в списке **Вывод**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7c628-111">In the **Input Output Selection** dialog box, in the **Output** list box, click **Lookup Match Output**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="7c628-112">В области конструктора **Поток данных** щелкните элемент **Назначение OLE DB** в только что добавленном преобразовании **Назначение OLE DB** и измените имя на **Образец назначения OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="7c628-112">On the **Data Flow** design surface, click **OLE DB Destination** in the newly added **OLE DB Destination** component, and change the name to **Sample OLE DB Destination**.</span></span>  
  
5.  <span data-ttu-id="7c628-113">Дважды щелкните элемент **Образец назначения OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="7c628-113">Double-click **Sample OLE DB Destination**.</span></span>  
  
6.  <span data-ttu-id="7c628-114">Убедитесь в том, что в диалоговом окне **Редактор назначения OLE DB** в поле **Диспетчер соединений OLE DB** выбрано значение **localhost.AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="7c628-114">In the **OLE DB Destination Editor** dialog box, ensure that **localhost.AdventureWorksDW2012** is selected in the **OLE DB Connection manager** box.</span></span>  
  
7.  <span data-ttu-id="7c628-115">В поле **Имя таблицы или представления** введите или выберите значение **[dbo].[FactCurrencyRate]**.</span><span class="sxs-lookup"><span data-stu-id="7c628-115">In the **Name of the table or the view** box, type or select **[dbo].[FactCurrencyRate]**.</span></span>  
  
8.  <span data-ttu-id="7c628-116">Чтобы создать таблицу, нажмите кнопку **Создать** .</span><span class="sxs-lookup"><span data-stu-id="7c628-116">Click the **New** button to create a new table.</span></span>  <span data-ttu-id="7c628-117">Измените имя таблицы в скрипте на **NewFactCurrencyRate**.</span><span class="sxs-lookup"><span data-stu-id="7c628-117">Change the name of the table in the script to read **NewFactCurrencyRate**.</span></span>  <span data-ttu-id="7c628-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7c628-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="7c628-119">После нажатия кнопки **ОК**диалоговое окно закроется, а значение **Имя таблицы или представления** автоматически изменится на **NewFactCurrencyRate**.</span><span class="sxs-lookup"><span data-stu-id="7c628-119">Upon clicking **OK**, the dialog will close and the **Name of the table or the view** will automatically change to **NewFactCurrencyRate**.</span></span>  
  
10. <span data-ttu-id="7c628-120">Нажмите кнопку **Сопоставления**.</span><span class="sxs-lookup"><span data-stu-id="7c628-120">Click **Mappings**.</span></span>  
  
11. <span data-ttu-id="7c628-121">Убедитесь в том, что входные столбцы **AverageRate**, **CurrencyKey**, **EndOfDayRate**и **DateKey** правильно сопоставлены с целевыми столбцами.</span><span class="sxs-lookup"><span data-stu-id="7c628-121">Verify that the **AverageRate**, **CurrencyKey**, **EndOfDayRate**, and **DateKey** input columns are mapped correctly to the destination columns.</span></span> <span data-ttu-id="7c628-122">Если друг с другом сопоставлены столбцы с одинаковыми именами, то сопоставление правильное.</span><span class="sxs-lookup"><span data-stu-id="7c628-122">If same-named columns are mapped, the mapping is correct.</span></span>  
  
12. <span data-ttu-id="7c628-123">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7c628-123">Click **OK**.</span></span>  
  
13. <span data-ttu-id="7c628-124">Щелкните правой кнопкой мыши назначение **Образец назначения OLE DB** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7c628-124">Right-click the **Sample OLE DB Destination** destination and click **Properties**.</span></span>  
  
14. <span data-ttu-id="7c628-125">В окно свойств убедитесь, что `LocaleID` свойство имеет значение **английский (США)** , а `DefaultCodePage` свойство имеет значение **1252**.</span><span class="sxs-lookup"><span data-stu-id="7c628-125">In the Properties window, verify that the `LocaleID` property is set to **English (United States)** and the`DefaultCodePage` property is set to **1252**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7c628-126">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="7c628-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7c628-127">Шаг 8. Облегчение чтения пакета, созданного на занятии 1</span><span class="sxs-lookup"><span data-stu-id="7c628-127">Step 8: Making the Lesson 1 Package Easier to Understand</span></span>](lesson-1-8-making-the-lesson-1-package-easier-to-understand.md)  
  
## <a name="see-also"></a><span data-ttu-id="7c628-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="7c628-128">See Also</span></span>  
 [<span data-ttu-id="7c628-129">Назначение OLE DB</span><span class="sxs-lookup"><span data-stu-id="7c628-129">OLE DB Destination</span></span>](data-flow/ole-db-destination.md)  
  
  
