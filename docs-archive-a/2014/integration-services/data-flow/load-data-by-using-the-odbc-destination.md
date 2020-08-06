---
title: Загрузка данных с помощью назначения "ODBС" | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 339ec0a8-922e-48c0-97b3-fc5ee34f95e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e8bf0b30619c2886df6ddb28858cf98bad858421
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731938"
---
# <a name="load-data-by-using-the-odbc-destination"></a><span data-ttu-id="be685-102">Загрузка данных с помощью назначения ODBС</span><span class="sxs-lookup"><span data-stu-id="be685-102">Load Data by Using the ODBC Destination</span></span>
  <span data-ttu-id="be685-103">Эта процедура показывает, как загрузить данные с использованием назначения ODBC.</span><span class="sxs-lookup"><span data-stu-id="be685-103">This procedure shows how to load data by using the ODBC destination.</span></span> <span data-ttu-id="be685-104">Чтобы можно было добавить и настроить назначение ODBC, пакет уже должен включать по крайней мере одну задачу «Поток данных» и источник.</span><span class="sxs-lookup"><span data-stu-id="be685-104">To add and configure an ODBC destination, the package must already include at least one Data Flow task and source.</span></span>  
  
### <a name="to-load-data-using-an-odbc-destination"></a><span data-ttu-id="be685-105">Загрузка данных с использованием назначения ODBC</span><span class="sxs-lookup"><span data-stu-id="be685-105">To load data using an ODBC destination</span></span>  
  
1.  <span data-ttu-id="be685-106">В среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]откройте необходимый пакет служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="be685-106">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package you want.</span></span>  
  
2.  <span data-ttu-id="be685-107">Щелкните вкладку **Поток данных** , а затем **Панель элементов**перетащите назначение ODBC в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="be685-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the ODBC destination to the design surface.</span></span>  
  
3.  <span data-ttu-id="be685-108">Перетащите доступный вывод компонента потока данных к вводу назначения ODBC.</span><span class="sxs-lookup"><span data-stu-id="be685-108">Drag an available output of a data flow component to the input of the ODBC destination.</span></span>  
  
4.  <span data-ttu-id="be685-109">Дважды щелкните назначение ODBC.</span><span class="sxs-lookup"><span data-stu-id="be685-109">Double-click the ODBC destination.</span></span>  
  
5.  <span data-ttu-id="be685-110">В диалоговом окне **Редактор назначения ODBC** , на странице **Диспетчер соединений** выберите существующий диспетчер соединений ODBC или щелкните **Создать** , чтобы создать новый диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="be685-110">In the **ODBC Destination Editor** dialog box, on the **Connection Manager** page, select an existing ODBC connection manager or click **New** to create a new connection manager.</span></span>  
  
6.  <span data-ttu-id="be685-111">Выберите метод доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="be685-111">Select the data access method.</span></span>  
  
    -   <span data-ttu-id="be685-112">**Имя таблицы — пакетом**: выберите этот параметр, чтобы настроить назначение ODBC для работы в пакетном режиме.</span><span class="sxs-lookup"><span data-stu-id="be685-112">**Table Name - Batch**: Select this option to configure the ODBC destination to work in batch mode.</span></span> <span data-ttu-id="be685-113">Если выбран этот параметр, можно задать значение **Размер пакета**.</span><span class="sxs-lookup"><span data-stu-id="be685-113">When you select this option, you can set the **Batch size**.</span></span>  
  
    -   <span data-ttu-id="be685-114">**Имя таблицы — построчно**: выберите этот параметр, чтобы настроить назначение ODBC для вставки каждой строки в целевую таблицу по отдельности.</span><span class="sxs-lookup"><span data-stu-id="be685-114">**Table Name - Row by Row**: Select this option to configure the ODBC destination to insert each of the rows into the destination table one at a time.</span></span> <span data-ttu-id="be685-115">Если выбран этот параметр, данные загружаются в таблицу построчно.</span><span class="sxs-lookup"><span data-stu-id="be685-115">When you select this option, the data is loaded into the table one row at a time.</span></span>  
  
7.  <span data-ttu-id="be685-116">В поле **Имя таблицы или представления** выберите доступную таблицу или представление базы данных из списка или введите регулярное выражение для обозначения таблицы. Этот список содержит только первую 1000 таблиц.</span><span class="sxs-lookup"><span data-stu-id="be685-116">In the **Name of the table or the view** field, select an available table or view from the database from the list or type in a regular expression to identify the table.This list contains the first 1000 tables only.</span></span> <span data-ttu-id="be685-117">Если база данных содержит больше 1000 таблиц, можно ввести начальную часть имени таблицы или воспользоваться символом-шаблоном (\*), чтобы ввести любую часть имени для вывода нужных таблиц.</span><span class="sxs-lookup"><span data-stu-id="be685-117">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>  
  
8.  <span data-ttu-id="be685-118">Можно щелкнуть **Предварительный просмотр** , чтобы рассмотреть до 200 строк данных таблицы, выбранной в назначении ODBC.</span><span class="sxs-lookup"><span data-stu-id="be685-118">You can click **Preview** to view up to 200 rows of the data from the table selected in the ODBC destination.</span></span>  
  
9. <span data-ttu-id="be685-119">Щелкните **Сопоставления** и сопоставьте столбцы из списка **Доступные входные столбцы** со столбцами из списка **Доступные целевые столбцы** , перетаскивая столбцы из одного списка в другой.</span><span class="sxs-lookup"><span data-stu-id="be685-119">Click **Mappings** and then map columns from the **Available Input Columns** list to columns in the **Available Destination Columns** list by dragging columns from one list to another.</span></span>  
  
10. <span data-ttu-id="be685-120">Чтобы настроить выход ошибок, щелкните **Вывод ошибок**.</span><span class="sxs-lookup"><span data-stu-id="be685-120">To configure the error output, click **Error Output**.</span></span>  
  
11. <span data-ttu-id="be685-121">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="be685-121">Click **OK**.</span></span>  
  
12. <span data-ttu-id="be685-122">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="be685-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be685-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="be685-123">See Also</span></span>  
 <span data-ttu-id="be685-124">[Редактор назначения ODBC (страница "Диспетчер соединений")](../odbc-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="be685-124">[ODBC Destination Editor &#40;Connection Manager Page&#41;](../odbc-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="be685-125">[Редактор назначения ODBC (страница "Сопоставления")](../odbc-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="be685-125">[ODBC Destination Editor &#40;Mappings Page&#41;](../odbc-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="be685-126">Редактор источника ODBC (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="be685-126">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
  
