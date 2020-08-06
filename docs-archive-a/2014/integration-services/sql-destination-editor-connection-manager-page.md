---
title: Редактор назначения «SQL» (страница «Диспетчер соединений») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdestadapter.connection.f1
helpviewer_keywords:
- SQL Server Destination Editor
ms.assetid: 423e1654-54af-47c6-ab6f-98670534557d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f3a552968cb297de337e1f0c406b444d95dc5a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658308"
---
# <a name="sql-destination-editor-connection-manager-page"></a><span data-ttu-id="d1ebf-102">Редактор назначения «SQL» (страница «Диспетчер соединений»)</span><span class="sxs-lookup"><span data-stu-id="d1ebf-102">SQL Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="d1ebf-103">Страница **Диспетчер соединений** диалогового окна **Редактор назначения «SQL»** используется для задания сведений об источнике данных и для предварительного просмотра результатов.</span><span class="sxs-lookup"><span data-stu-id="d1ebf-103">Use the **Connection Manager** page of the **SQL Destination Editor** dialog box to specify data source information, and to preview the results.</span></span> <span data-ttu-id="d1ebf-104">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]Назначение загружает данные в таблицы или представления в [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] базе данных.</span><span class="sxs-lookup"><span data-stu-id="d1ebf-104">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] destination loads data into tables or views in a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="d1ebf-105">Дополнительные сведения о назначении «SQL Server» см. в разделе [SQL Server Destination](data-flow/sql-server-destination.md).</span><span class="sxs-lookup"><span data-stu-id="d1ebf-105">To learn more about the SQL Server destination, see [SQL Server Destination](data-flow/sql-server-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d1ebf-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d1ebf-106">Options</span></span>  
 <span data-ttu-id="d1ebf-107">**Диспетчер соединений OLE DB**</span><span class="sxs-lookup"><span data-stu-id="d1ebf-107">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="d1ebf-108">Выберите существующий диспетчер подключений из списка или создайте новое соединение, выбрав пункт **Создать**.</span><span class="sxs-lookup"><span data-stu-id="d1ebf-108">Select an existing connection from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="d1ebf-109">**Создать**</span><span class="sxs-lookup"><span data-stu-id="d1ebf-109">**New**</span></span>  
 <span data-ttu-id="d1ebf-110">Создайте новое соединение с помощью диалогового окна **Настройка диспетчера соединений OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="d1ebf-110">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="d1ebf-111">**Использовать таблицу или представление**</span><span class="sxs-lookup"><span data-stu-id="d1ebf-111">**Use a table or view**</span></span>  
 <span data-ttu-id="d1ebf-112">Выберите существующую таблицу или представление из списка или создайте новое соединение, нажав кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="d1ebf-112">Select an existing table or view from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="d1ebf-113">**Создать**</span><span class="sxs-lookup"><span data-stu-id="d1ebf-113">**New**</span></span>  
 <span data-ttu-id="d1ebf-114">Создайте новую таблицу с помощью диалогового окна **Создание таблицы** .</span><span class="sxs-lookup"><span data-stu-id="d1ebf-114">Create a new table by using the **Create Table** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d1ebf-115">При нажатии кнопки **Создать**службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] по умолчанию формируют инструкцию CREATE TABLE на основе подключенного источника данных.</span><span class="sxs-lookup"><span data-stu-id="d1ebf-115">When you click **New**, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] generates a default CREATE TABLE statement based on the connected data source.</span></span> <span data-ttu-id="d1ebf-116">Эта инструкция CREATE TABLE не включает атрибут FILESTREAM, даже если исходная таблица содержит столбец, для которого объявлен атрибут FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="d1ebf-116">This default CREATE TABLE statement will not include the FILESTREAM attribute even if the source table includes a column with the FILESTREAM attribute declared.</span></span> <span data-ttu-id="d1ebf-117">Чтобы запустить компонент служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] с атрибутом FILESTREAM, сначала следует создать хранилище FILESTREAM в целевой базе данных.</span><span class="sxs-lookup"><span data-stu-id="d1ebf-117">To run an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] component with the FILESTREAM attribute, first implement FILESTREAM storage on the destination database.</span></span> <span data-ttu-id="d1ebf-118">Затем добавьте атрибут FILESTREAM к инструкции CREATE TABLE в диалоговом окне **Создание таблицы** .</span><span class="sxs-lookup"><span data-stu-id="d1ebf-118">Then, add the FILESTREAM attribute to the CREATE TABLE statement in the **Create Table** dialog box.</span></span> <span data-ttu-id="d1ebf-119">Дополнительные сведения см. в разделе [Данные большого двоичного объекта (SQL Server)](../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d1ebf-119">For more information, see [Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;](../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="d1ebf-120">**Предварительный просмотр**</span><span class="sxs-lookup"><span data-stu-id="d1ebf-120">**Preview**</span></span>  
 <span data-ttu-id="d1ebf-121">Просмотрите предварительные результаты, используя диалоговое окно **Предварительный просмотр результатов запроса** .</span><span class="sxs-lookup"><span data-stu-id="d1ebf-121">Preview results by using the **Preview Query Results** dialog box.</span></span> <span data-ttu-id="d1ebf-122">В окне «Предварительный просмотр» может отображаться до 200 строк.</span><span class="sxs-lookup"><span data-stu-id="d1ebf-122">Preview can display up to 200 rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1ebf-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="d1ebf-123">See Also</span></span>  
 <span data-ttu-id="d1ebf-124">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d1ebf-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d1ebf-125">[Редактор назначения "SQL &#40;страниц сопоставления"&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="d1ebf-125">[SQL Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="d1ebf-126">[Редактор назначения "SQL" &#40;страница "Дополнительно"&#41;](../../2014/integration-services/sql-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="d1ebf-126">[SQL Destination Editor &#40;Advanced Page&#41;](../../2014/integration-services/sql-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="d1ebf-127">Выполнение массовой загрузки данных с помощью назначения «SQL Server»</span><span class="sxs-lookup"><span data-stu-id="d1ebf-127">Bulk Load Data by Using the SQL Server Destination</span></span>](data-flow/bulk-load-data-by-using-the-sql-server-destination.md)  
  
  
