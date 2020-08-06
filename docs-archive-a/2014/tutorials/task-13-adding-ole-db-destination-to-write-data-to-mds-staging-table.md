---
title: Задача 13. Добавление OLE DB назначения для записи данных в промежуточную таблицу MDS | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: e6c67fa9-bb52-44a9-82f6-d86551cf12b2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 77799782518a3be2441b4c461467e3132781298d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731190"
---
# <a name="task-13-adding-ole-db-destination-to-write-data-to-mds-staging-table"></a><span data-ttu-id="81d8c-102">Задача 13. Добавление назначения OLE DB для записи данных в промежуточную таблицу MDS</span><span class="sxs-lookup"><span data-stu-id="81d8c-102">Task 13: Adding OLE DB Destination to Write Data to MDS Staging Table</span></span>
  <span data-ttu-id="81d8c-103">Теперь, когда вы добавили значения **ImportType** и **BatchTag** во все записи, вы можете отправить их в MDS для промежуточного хранения.</span><span class="sxs-lookup"><span data-stu-id="81d8c-103">Now that you have added **ImportType** and **BatchTag** values to all records, you are ready to send them over to MDS for staging.</span></span> <span data-ttu-id="81d8c-104">В этой задаче используется назначение OLE DB для записи данных в промежуточную таблицу **STG. supplier_Leaf** .</span><span class="sxs-lookup"><span data-stu-id="81d8c-104">In this task, you use the OLE DB Destination to write the data into **stg.supplier_Leaf** staging table.</span></span>  
  
1.  <span data-ttu-id="81d8c-105">Перетащите **OLE DB назначение** из раздела **другие назначения** в **области элементов служб SSIS** на вкладку **поток данных** и поместите его в разделе **Добавление столбцов, необходимых для MDS**.</span><span class="sxs-lookup"><span data-stu-id="81d8c-105">Drag **OLE DB Destination** from **Other Destinations** section in the **SSIS Toolbox** to the **Data Flow** tab and drop it under **Add Columns Required by MDS**.</span></span>  
  
2.  <span data-ttu-id="81d8c-106">Щелкните правой кнопкой мыши **OLE DB назначение** на вкладке **поток данных** и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="81d8c-106">Right-click **OLE DB Destination** in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="81d8c-107">Введите **запись данных поставщика в промежуточную таблицу MDS** и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="81d8c-107">Type **Write Supplier Data to MDS Staging Table** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="81d8c-108">Подключите **Добавление столбцов, необходимых MDS** , для **записи данных поставщика в промежуточную таблицу MDS** с помощью синего соединителя.</span><span class="sxs-lookup"><span data-stu-id="81d8c-108">Connect the **Add Columns Required by MDS** to **Write Supplier Data to MDS Staging Table** using the blue connector.</span></span>  
  
4.  <span data-ttu-id="81d8c-109">Дважды щелкните **запись данных поставщика в промежуточную таблицу MDS** на вкладке **поток данных** .</span><span class="sxs-lookup"><span data-stu-id="81d8c-109">Double-click **Write Supplier Data to MDS Staging Table** in the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="81d8c-110">В диалоговом окне **Редактор назначения OLE DB** убедитесь, что **(local). MDS** (или **localhost). MDS**) выбрано для поля **диспетчера соединений OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="81d8c-110">In the **OLE DB Destination Editor** Dialog box, make sure that **(local).MDS** (or **localhost.MDS**) is selected for the **OLE DB Connection Manager** field.</span></span>  
  
6.  <span data-ttu-id="81d8c-111">Выберите **STG. Supplier_Leaf** таблицу из списка **имен таблицы или представления**.</span><span class="sxs-lookup"><span data-stu-id="81d8c-111">Select **stg.Supplier_Leaf** table from the list of **Name of the table or the view**.</span></span>  
  
     <span data-ttu-id="81d8c-112">![Редактор назначения OLEDB](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-01.jpg "Редактор назначения OLEDB")</span><span class="sxs-lookup"><span data-stu-id="81d8c-112">![OLEDB Destination Editor](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-01.jpg "OLEDB Destination Editor")</span></span>  
  
7.  <span data-ttu-id="81d8c-113">Перейдите на страницу **сопоставления** , щелкнув элемент **сопоставление** в меню слева.</span><span class="sxs-lookup"><span data-stu-id="81d8c-113">Switch to the **Mappings** page by clicking **Mapping** on the menu on left.</span></span>  
  
8.  <span data-ttu-id="81d8c-114">Сопоставьте **входные** и **целевые** столбцы, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="81d8c-114">Map **input** and **destination** columns as shown in the following table.</span></span>  
  
     <span data-ttu-id="81d8c-115">![Редактор назначения OLEDB — сопоставления](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-02.jpg "Редактор назначения OLEDB — сопоставления")</span><span class="sxs-lookup"><span data-stu-id="81d8c-115">![OLEDB Destination Editor - Mappings](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-02.jpg "OLEDB Destination Editor - Mappings")</span></span>  
  
9. <span data-ttu-id="81d8c-116">Убедитесь, что используются **_Output** столбцы для входных столбцов, а не **_Status** или **_Source** столбцов.</span><span class="sxs-lookup"><span data-stu-id="81d8c-116">Confirm that you are using **_Output** columns for Input Columns, not the **_Status** or **_Source** columns.</span></span> <span data-ttu-id="81d8c-117">**_Output** столбцы содержат выходные значения из очистки DQS.</span><span class="sxs-lookup"><span data-stu-id="81d8c-117">**_Output** columns contain the output values from DQS Cleansing.</span></span>  
  
10. <span data-ttu-id="81d8c-118">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Редактор назначения OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="81d8c-118">Click **OK** to close the **OLE DB Destination Editor** dialog box.</span></span>  
  
11. <span data-ttu-id="81d8c-119">Поток данных должен выглядеть примерно следующим образом.</span><span class="sxs-lookup"><span data-stu-id="81d8c-119">The data flow should like the following image.</span></span>  
  
     <span data-ttu-id="81d8c-120">![Завершенный поток данных](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-03.jpg "Завершенный поток данных")</span><span class="sxs-lookup"><span data-stu-id="81d8c-120">![Completed Data Flow](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-03.jpg "Completed Data Flow")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="81d8c-121">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="81d8c-121">Next Step</span></span>  
 [<span data-ttu-id="81d8c-122">Задача 14. Добавление в поток управления задачи "Выполнение SQL" для запуска хранимой процедуры для MDS</span><span class="sxs-lookup"><span data-stu-id="81d8c-122">Task 14: Adding Execute SQL Task to Control Flow to Run the Stored Procedure for MDS</span></span>](../../2014/tutorials/task-14-add-execute-to-control-flow-run-mds-stored-procedure.md)  
  
  
