---
title: Импорт из реляционного источника данных (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 043201cc-fbef-4ed0-bde8-dc5e3a3e8bea
author: minewiskan
ms.author: owend
ms.openlocfilehash: 93bb9ba9ba8d40262e4e90e840dcd15ac6826df3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667941"
---
# <a name="import-from-a-relational-data-source-ssas-tabular"></a><span data-ttu-id="8fb16-102">Импорт из реляционного источника данных (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="8fb16-102">Import from a Relational Data Source (SSAS Tabular)</span></span>
  <span data-ttu-id="8fb16-103">С помощью мастера импорта таблиц можно импортировать данные из разных реляционных баз данных:</span><span class="sxs-lookup"><span data-stu-id="8fb16-103">You can import data from a variety of relational databases by using the Table Import Wizard.</span></span> <span data-ttu-id="8fb16-104">Этот мастер доступен в меню [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]Модель \*\*\*\* .</span><span class="sxs-lookup"><span data-stu-id="8fb16-104">The wizard is available in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Model** menu.</span></span> <span data-ttu-id="8fb16-105">Для соединения с источником данных на компьютере должен быть установлен соответствующий поставщик.</span><span class="sxs-lookup"><span data-stu-id="8fb16-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span> <span data-ttu-id="8fb16-106">Дополнительные сведения о поддерживаемых источниках данных и поставщиках см. в разделе [Поддерживаемые источники данных (табличные службы SSAS)](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="8fb16-106">For more information about supported data sources and providers, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="8fb16-107">Мастер импорта таблиц поддерживает импорт данных из следующих источников данных:</span><span class="sxs-lookup"><span data-stu-id="8fb16-107">The Table Import Wizard supports importing data from the following data sources:</span></span>  
  
 <span data-ttu-id="8fb16-108">**Реляционные базы данных**</span><span class="sxs-lookup"><span data-stu-id="8fb16-108">**Relational Databases**</span></span>  
  
-   <span data-ttu-id="8fb16-109">База данных Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="8fb16-109">Microsoft SQL Server database</span></span>  
  
-   <span data-ttu-id="8fb16-110">Microsoft SQL Azure</span><span class="sxs-lookup"><span data-stu-id="8fb16-110">Microsoft SQL Azure</span></span>  
  
-   <span data-ttu-id="8fb16-111">База данных Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="8fb16-111">Microsoft Access database</span></span>  
  
-   <span data-ttu-id="8fb16-112">Параллельные хранилища данных Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="8fb16-112">Microsoft SQL Server Parallel Data Warehouse</span></span>  
  
-   <span data-ttu-id="8fb16-113">Oracle;</span><span class="sxs-lookup"><span data-stu-id="8fb16-113">Oracle</span></span>  
  
-   <span data-ttu-id="8fb16-114">Teradata</span><span class="sxs-lookup"><span data-stu-id="8fb16-114">Teradata</span></span>  
  
-   <span data-ttu-id="8fb16-115">Sybase</span><span class="sxs-lookup"><span data-stu-id="8fb16-115">Sybase</span></span>  
  
-   <span data-ttu-id="8fb16-116">Informix</span><span class="sxs-lookup"><span data-stu-id="8fb16-116">Informix</span></span>  
  
-   <span data-ttu-id="8fb16-117">IBM DB2</span><span class="sxs-lookup"><span data-stu-id="8fb16-117">IBM DB2</span></span>  
  
-   <span data-ttu-id="8fb16-118">OLE DB/ODBC</span><span class="sxs-lookup"><span data-stu-id="8fb16-118">OLE DB/ODBC</span></span>  
  
 <span data-ttu-id="8fb16-119">**Многомерные источники**</span><span class="sxs-lookup"><span data-stu-id="8fb16-119">**Multidimensional Sources**</span></span>  
  
-   <span data-ttu-id="8fb16-120">Куб служб Microsoft SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="8fb16-120">Microsoft SQL Server Analysis Services cube</span></span>  
  
 <span data-ttu-id="8fb16-121">Мастер импорта таблиц не поддерживает импорт данных из книги [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] в качестве источника данных.</span><span class="sxs-lookup"><span data-stu-id="8fb16-121">The Table Import Wizard does not support importing data from a [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] Workbook as a data source.</span></span>  
  
### <a name="to-import-data-from-a-database"></a><span data-ttu-id="8fb16-122">Импорт данных из базы данных</span><span class="sxs-lookup"><span data-stu-id="8fb16-122">To import data from a database</span></span>  
  
1.  <span data-ttu-id="8fb16-123">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="8fb16-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Import from Data Source**.</span></span>  
  
2.  <span data-ttu-id="8fb16-124">На странице **Подключение к источнику данных** выберите тип базы данных для подключения и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8fb16-124">On the **Connect to a Data Source** page, select the type of database to connect to, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="8fb16-125">Выполните шаги мастера импорта таблиц.</span><span class="sxs-lookup"><span data-stu-id="8fb16-125">Follow the steps in the Table Import Wizard.</span></span> <span data-ttu-id="8fb16-126">На последующих страницах можно будет выбрать отдельные таблицы и представления или применить фильтры на странице **Выбор таблиц и представлений** или с помощью создания SQL-запроса на странице **Указание SQL-запроса** .</span><span class="sxs-lookup"><span data-stu-id="8fb16-126">On subsequent pages, you will be able to select specific tables and views or apply filters by using the **Select Tables and Views** page or by creating a SQL query on **Specify a SQL Query** page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fb16-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="8fb16-127">See Also</span></span>  
 <span data-ttu-id="8fb16-128">[Импорт данных &#40;табличные&#41;SSAS](import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="8fb16-128">[Import Data &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="8fb16-129">Поддерживаемые источники данных (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="8fb16-129">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  
