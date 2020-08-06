---
title: Извлечение данных с помощью источника ODBC | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 10f25703-49a2-4d45-abab-6b4da2a57ba5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c05efe2b0479047280fc093ee555e037c77d82e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751331"
---
# <a name="extract-data-by-using-the-odbc-source"></a><span data-ttu-id="1e1a0-102">Извлечение данных с помощью источника ODBC</span><span class="sxs-lookup"><span data-stu-id="1e1a0-102">Extract Data by Using the ODBC Source</span></span>
  <span data-ttu-id="1e1a0-103">Эта процедура описывает, как извлечь данные с использованием источника ODBC.</span><span class="sxs-lookup"><span data-stu-id="1e1a0-103">This procedure describes how to extract data by using an ODBC source.</span></span> <span data-ttu-id="1e1a0-104">Чтобы добавить и настроить источник ODBC, пакет должен уже содержать не менее одной задачи потока данных.</span><span class="sxs-lookup"><span data-stu-id="1e1a0-104">To add and configure an ODBC source, the package must already include at least one Data Flow task.</span></span>  
  
### <a name="to-extract-data-using-an-odbc-source"></a><span data-ttu-id="1e1a0-105">Извлечение данных с использованием ODBC-источника</span><span class="sxs-lookup"><span data-stu-id="1e1a0-105">To extract data using an ODBC source</span></span>  
  
1.  <span data-ttu-id="1e1a0-106">В среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]откройте необходимый пакет служб [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e1a0-106">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] package you want.</span></span>  
  
2.  <span data-ttu-id="1e1a0-107">Щелкните вкладку **Поток данных** , а затем с панели **Панель элементов**перетащите источник ODBC в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="1e1a0-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the ODBC source to the design surface.</span></span>  
  
3.  <span data-ttu-id="1e1a0-108">Дважды щелкните источник ODBC.</span><span class="sxs-lookup"><span data-stu-id="1e1a0-108">Double-click the ODBC source.</span></span>  
  
4.  <span data-ttu-id="1e1a0-109">В диалоговом окне **Редактор источников ODBC** , на странице **Диспетчер соединений** выберите существующий диспетчер соединений ODBC или щелкните **Создать** , чтобы создать новый диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="1e1a0-109">In the **ODBC Source Editor** dialog box, on the **Connection Manager** page, select an existing ODBC connection manager or click **New** to create a new connection manager.</span></span>  
  
5.  <span data-ttu-id="1e1a0-110">Выберите метод доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="1e1a0-110">Select the data access method.</span></span>  
  
    -   <span data-ttu-id="1e1a0-111">**Имя таблицы**. Выберите таблицу или представление в базе данных или введите регулярное выражение для обозначения таблицы, к которой подключается диспетчер подключений ODBC.</span><span class="sxs-lookup"><span data-stu-id="1e1a0-111">**Table Name**: Select a table or view in the database or type a regular expression to identify the table to which the ODBC connection manager connects.</span></span>  
  
         <span data-ttu-id="1e1a0-112">Этот список содержит только первые 1000 таблиц.</span><span class="sxs-lookup"><span data-stu-id="1e1a0-112">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="1e1a0-113">Если база данных содержит больше 1000 таблиц, можно ввести начальную часть имени таблицы или воспользоваться символом-шаблоном (\*), чтобы ввести любую часть имени для вывода нужных таблиц.</span><span class="sxs-lookup"><span data-stu-id="1e1a0-113">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>  
  
    -   <span data-ttu-id="1e1a0-114">**Команда SQL**. Введите команду SQL или нажмите кнопку **Обзор** , чтобы загрузить SQL-запрос из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="1e1a0-114">**SQL Command**: Type an SQL Command or click **Browse** to load the SQL query from a text file.</span></span>  
  
6.  <span data-ttu-id="1e1a0-115">Можно щелкнуть **Предварительный просмотр** , чтобы рассмотреть до 200 строк данных, извлеченных источником ODBC.</span><span class="sxs-lookup"><span data-stu-id="1e1a0-115">You can click **Preview** to view up to 200 rows of the data extracted by the ODBC source.</span></span>  
  
7.  <span data-ttu-id="1e1a0-116">Чтобы обновить сопоставление между внешними и выходными столбцами, щелкните **Столбцы** и выберите другие столбцы в списке **Внешний столбец** .</span><span class="sxs-lookup"><span data-stu-id="1e1a0-116">To update the mapping between external and output columns, click **Columns** and select different columns in the **External Column** list.</span></span>  
  
8.  <span data-ttu-id="1e1a0-117">В случае необходимости обновите имена выходных столбцов, изменив значения в списке **Выходной столбец** .</span><span class="sxs-lookup"><span data-stu-id="1e1a0-117">If necessary, update the names of output columns by editing values in the **Output Column** list.</span></span>  
  
9. <span data-ttu-id="1e1a0-118">Чтобы настроить выход ошибок, щелкните **Вывод ошибок**.</span><span class="sxs-lookup"><span data-stu-id="1e1a0-118">To configure the error output, click **Error Output**.</span></span>  
  
10. <span data-ttu-id="1e1a0-119">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1e1a0-119">Click **OK**.</span></span>  
  
11. <span data-ttu-id="1e1a0-120">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="1e1a0-120">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e1a0-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="1e1a0-121">See Also</span></span>  
 <span data-ttu-id="1e1a0-122">[Редактор источника ODBC (страница "Диспетчер соединений")](../odbc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="1e1a0-122">[ODBC Source Editor &#40;Connection Manager Page&#41;](../odbc-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="1e1a0-123">[Редактор источника ODBC (страница "Столбцы")](../odbc-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="1e1a0-123">[ODBC Source Editor &#40;Columns Page&#41;](../odbc-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="1e1a0-124">Редактор источника ODBC (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="1e1a0-124">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
  
