---
title: Изменение существующего соединения с источником данных (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.selexistconn.f1
ms.assetid: 97e63f18-a01d-4c91-a411-e7e6d40a0647
author: minewiskan
ms.author: owend
ms.openlocfilehash: 675a0d1119e25a92231d3e74a79739cb2e96b6d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667461"
---
# <a name="edit-an-existing-data-source-connection-ssas-tabular"></a><span data-ttu-id="07957-102">Изменение существующего соединения с источником данных (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="07957-102">Edit an Existing Data Source Connection (SSAS Tabular)</span></span>
  <span data-ttu-id="07957-103">В этом разделе описано изменение свойств существующего соединения с источником данных в табличной модели.</span><span class="sxs-lookup"><span data-stu-id="07957-103">This topic describes how to edit the properties of an existing data source connection in a tabular model.</span></span>  
  
 <span data-ttu-id="07957-104">После создания соединения с внешним источником данных это соединение можно изменить несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="07957-104">After you have created a connection to an external data source, you can later modify that connection in these ways:</span></span>  
  
-   <span data-ttu-id="07957-105">Можно изменить сведения о соединении (включая файл, канал или базу данных, которая используется как источник), его свойства или другие параметры, зависящие от поставщика.</span><span class="sxs-lookup"><span data-stu-id="07957-105">You can change the connection information, including the file, feed, or database used as a source, its properties, or other provider-specific connection options.</span></span>  
  
-   <span data-ttu-id="07957-106">Можно изменять сопоставления таблиц и столбцов, а также удалять ссылки на столбцы, которые более не используются.</span><span class="sxs-lookup"><span data-stu-id="07957-106">You can change table and column mappings, and remove references to columns that are no longer used.</span></span>  
  
-   <span data-ttu-id="07957-107">Можно изменить таблицы, представления или столбцы, которые получаются из внешнего источника данных.</span><span class="sxs-lookup"><span data-stu-id="07957-107">You can change the tables, views, or columns that you get from the external data source.</span></span>  
  
## <a name="modify-a-connection"></a><span data-ttu-id="07957-108">Изменение соединения</span><span class="sxs-lookup"><span data-stu-id="07957-108">Modify a Connection</span></span>  
 <span data-ttu-id="07957-109">Эта процедура описывает, как изменить соединение с источником данных базы данных.</span><span class="sxs-lookup"><span data-stu-id="07957-109">This procedure describes how to modify a database data source connection.</span></span> <span data-ttu-id="07957-110">Некоторые параметры для работы с источниками данных зависят от типа источника данных, однако можно легко определить эти различия.</span><span class="sxs-lookup"><span data-stu-id="07957-110">Some options for working with data sources differ depending on the data source type; however, you should be able to easily identify those differences.</span></span>  
  
#### <a name="to-change-the-external-data-source-used-by-a-current-connection"></a><span data-ttu-id="07957-111">Изменение внешнего источника данных, который используется текущим соединением</span><span class="sxs-lookup"><span data-stu-id="07957-111">To change the external data source used by a current connection</span></span>  
  
1.  <span data-ttu-id="07957-112">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]в меню **Модель** выберите пункт **Существующие соединения**.</span><span class="sxs-lookup"><span data-stu-id="07957-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Existing Connections**.</span></span>  
  
2.  <span data-ttu-id="07957-113">Выберите соединение с источником данных, которое необходимо изменить, и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="07957-113">Select the data source connection you want to modify, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="07957-114">В диалоговом окне **Изменить соединение** нажмите кнопку **Обзор** , чтобы выбрать другую базу данных того же типа с другим именем или в другом расположении.</span><span class="sxs-lookup"><span data-stu-id="07957-114">In the **Edit Connection** dialog box, click **Browse** to locate another database of the same type but with a different name or location.</span></span>  
  
     <span data-ttu-id="07957-115">Как только происходит изменение файла базы данных, появляется сообщение о том, что необходимо сохранить и обновить таблицы для просмотра новых данных.</span><span class="sxs-lookup"><span data-stu-id="07957-115">As soon as you change the database file, a message appears indicating that you need to save and refresh the tables in order to see the new data.</span></span>  
  
4.  <span data-ttu-id="07957-116">Нажмите кнопку **Сохранить**, а затем кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="07957-116">Click **Save**, and then click **Close**.</span></span>  
  
5.  <span data-ttu-id="07957-117">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите в меню **Модель**пункт **Обработать**, а затем **Обработать все**.</span><span class="sxs-lookup"><span data-stu-id="07957-117">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Model**, click **Process**, and then click **Process All**.</span></span>  
  
     <span data-ttu-id="07957-118">Таблицы будут повторно обработаны с использованием нового источника данных, но с первоначальным выбором данных.</span><span class="sxs-lookup"><span data-stu-id="07957-118">The tables are re-processed using the new data source, but with the original data selections.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="07957-119">Если новый источник данных содержит дополнительные таблицы, которых не было в первоначальном источнике данных, то необходимо повторно открыть измененное соединение и добавить эти таблицы.</span><span class="sxs-lookup"><span data-stu-id="07957-119">If the new data source contains any additional tables that were not present in the original data source, you must re-open the changed connection and add the tables.</span></span>  
  
## <a name="edit-table-and-column-mappings-bindings"></a><span data-ttu-id="07957-120">Изменение сопоставлений таблиц и столбцов (привязки)</span><span class="sxs-lookup"><span data-stu-id="07957-120">Edit Table and Column Mappings (Bindings)</span></span>  
 <span data-ttu-id="07957-121">Эта процедура описывает порядок изменения сопоставлений после изменения источника данных.</span><span class="sxs-lookup"><span data-stu-id="07957-121">This procedure describes how to edit the mappings after you change a data source.</span></span>  
  
#### <a name="to-edit-column-mappings-when-a-data-source-changes"></a><span data-ttu-id="07957-122">Изменение сопоставлений столбцов после изменения источника данных</span><span class="sxs-lookup"><span data-stu-id="07957-122">To edit column mappings when a data source changes</span></span>  
  
1.  <span data-ttu-id="07957-123">В конструкторе моделей выберите таблицу.</span><span class="sxs-lookup"><span data-stu-id="07957-123">In the model designer, select a table.</span></span>  
  
2.  <span data-ttu-id="07957-124">Выберите в меню **Таблица** пункт **Свойства таблицы**.</span><span class="sxs-lookup"><span data-stu-id="07957-124">Click on the **Table** menu, and then click **Table Properties**.</span></span>  
  
     <span data-ttu-id="07957-125">Имя выбранной таблицы отображается в поле **Имя таблицы** .</span><span class="sxs-lookup"><span data-stu-id="07957-125">The name of the selected table is displayed in the **Table Name** box.</span></span> <span data-ttu-id="07957-126">Поле **Имя источника** содержит имя таблицы во внешнем источнике данных.</span><span class="sxs-lookup"><span data-stu-id="07957-126">The **Source Name** box contains the name of the table in the external data source.</span></span> <span data-ttu-id="07957-127">Если столбцы названы по-разному в источнике и модели, можно выбрать между двумя наборами имен столбцов с помощью выбора одного из вариантов **Источник** или **Модель**.</span><span class="sxs-lookup"><span data-stu-id="07957-127">If columns are named differently in the source and in the model, you can toggle between the two sets of column names by selecting the options **Source** or **Model**.</span></span>  
  
3.  <span data-ttu-id="07957-128">Для изменения таблицы, которая используется в качестве источника данных в поле **Имя источника**, выберите другую таблицу, отличную от текущей.</span><span class="sxs-lookup"><span data-stu-id="07957-128">To change the table that is used as a data source, for **Source Name**, select a different table than the current one.</span></span>  
  
4.  <span data-ttu-id="07957-129">При необходимости измените сопоставления столбцов.</span><span class="sxs-lookup"><span data-stu-id="07957-129">Change column mappings if needed:</span></span>  
  
    1.  <span data-ttu-id="07957-130">Чтобы добавить столбцы, которые есть в источнике, но отсутствуют в модели, установите флажок рядом с именем столбца.</span><span class="sxs-lookup"><span data-stu-id="07957-130">To add columns that are present in the source but not in the model, select the checkbox beside the column name.</span></span>  
  
         <span data-ttu-id="07957-131">Фактические данные будут загружены в модель при следующем обновлении.</span><span class="sxs-lookup"><span data-stu-id="07957-131">The actual data will be loaded into the model the next time you refresh.</span></span>  
  
    2.  <span data-ttu-id="07957-132">Если некоторые столбцы в модели больше недоступны в текущем источнике данных, в области уведомлений появляется сообщение, в котором перечисляются недопустимые столбцы.</span><span class="sxs-lookup"><span data-stu-id="07957-132">If some columns in the model are no longer available in the current data source, a message appears in the notification area that lists the invalid columns.</span></span> <span data-ttu-id="07957-133">Другие действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="07957-133">You do not need to do anything else.</span></span>  
  
5.  <span data-ttu-id="07957-134">Чтобы применить изменения к модели, нажмите кнопку **Сохранить** .</span><span class="sxs-lookup"><span data-stu-id="07957-134">Click **Save** to apply the changes to your model.</span></span>  
  
     <span data-ttu-id="07957-135">При сохранении текущего набора свойств таблицы может появиться сообщение, указывающее на необходимость обработки таблиц.</span><span class="sxs-lookup"><span data-stu-id="07957-135">When you save the current set of table properties, a message may appear indicating that you need to process the tables.</span></span> <span data-ttu-id="07957-136">Чтобы загрузить обновленные данные в модель, нажмите кнопку **Обработать** .</span><span class="sxs-lookup"><span data-stu-id="07957-136">Click **Process** to load updated data into your model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07957-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="07957-137">See Also</span></span>  
 <span data-ttu-id="07957-138">[Обработка данных &#40;табличные&#41;SSAS](process-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="07957-138">[Process Data &#40;SSAS Tabular&#41;](process-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="07957-139">Поддерживаемые источники данных (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="07957-139">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  
