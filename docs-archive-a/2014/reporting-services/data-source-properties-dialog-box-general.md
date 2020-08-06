---
title: Диалоговое окно "Свойства источника данных" — "Общие" | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.datasourceproperties.general.f1
- "10120"
ms.assetid: 44b5edd3-5c11-4d3d-91b8-5871aa0572ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c79ad70cdd4dcb10e1abce1102fa39eef4c67461
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654915"
---
# <a name="data-source-properties-dialog-box-general"></a><span data-ttu-id="feaba-102">Диалоговое окно «Свойства источника данных» — «Общие»</span><span class="sxs-lookup"><span data-stu-id="feaba-102">Data Source Properties Dialog Box, General</span></span>
  <span data-ttu-id="feaba-103">Вкладка **Общие** в диалоговом окне **Источник данных** позволяет просмотреть и изменить сведения о соединении источника данных с отчетом.</span><span class="sxs-lookup"><span data-stu-id="feaba-103">Select **General** on the **Data Source Properties** dialog box to display and modify connection information for a data source in the report.</span></span>  
  
## <a name="options"></a><span data-ttu-id="feaba-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="feaba-104">Options</span></span>  
 <span data-ttu-id="feaba-105">**имя**;</span><span class="sxs-lookup"><span data-stu-id="feaba-105">**Name**</span></span>  
 <span data-ttu-id="feaba-106">Введите имя источника данных.</span><span class="sxs-lookup"><span data-stu-id="feaba-106">Type the name of the data source.</span></span> <span data-ttu-id="feaba-107">Имя источника данных должно быть уникальным в пределах отчета.</span><span class="sxs-lookup"><span data-stu-id="feaba-107">The data source name must be unique within the report.</span></span> <span data-ttu-id="feaba-108">По умолчанию источнику данных присваивается стандартное имя, например ИсточникДанных1 или ИсточникДанных2.</span><span class="sxs-lookup"><span data-stu-id="feaba-108">By default, a general name, such as DataSource1 or DataSource2, is assigned to the data source.</span></span>  
  
 <span data-ttu-id="feaba-109">**Внедренное соединение**</span><span class="sxs-lookup"><span data-stu-id="feaba-109">**Embedded connection**</span></span>  
 <span data-ttu-id="feaba-110">Выберите этот параметр, если общий источник данных не нужен.</span><span class="sxs-lookup"><span data-stu-id="feaba-110">Select this option when you do not want to use a shared data source.</span></span>  
  
 <span data-ttu-id="feaba-111">**Тип**</span><span class="sxs-lookup"><span data-stu-id="feaba-111">**Type**</span></span>  
 <span data-ttu-id="feaba-112">Выберите модуль обработки данных.</span><span class="sxs-lookup"><span data-stu-id="feaba-112">Select a data processing extension.</span></span> <span data-ttu-id="feaba-113">В списке перечислены все зарегистрированные модули.</span><span class="sxs-lookup"><span data-stu-id="feaba-113">The list displays all registered extensions.</span></span>  
  
 <span data-ttu-id="feaba-114">**Строка подключения**</span><span class="sxs-lookup"><span data-stu-id="feaba-114">**Connection string**</span></span>  
 <span data-ttu-id="feaba-115">Введите строку соединения для источника данных.</span><span class="sxs-lookup"><span data-stu-id="feaba-115">Enter a connection string for the data source.</span></span> <span data-ttu-id="feaba-116">Чтобы построить строку соединения с помощью диалогового окна **Свойства соединения** , нажмите кнопку **Изменить** .</span><span class="sxs-lookup"><span data-stu-id="feaba-116">Click **Edit** to build the connection string using the **Connection Properties** dialog box.</span></span> <span data-ttu-id="feaba-117">Чтобы изменить выражение, нажмите кнопку **Выражение** (*fx*).</span><span class="sxs-lookup"><span data-stu-id="feaba-117">Click the **Expressions** (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="feaba-118">**Использовать ссылку на общий источник данных**</span><span class="sxs-lookup"><span data-stu-id="feaba-118">**Use shared data source reference**</span></span>  
 <span data-ttu-id="feaba-119">Выберите этот параметр, чтобы задать ссылку на общий источник данных.</span><span class="sxs-lookup"><span data-stu-id="feaba-119">Select this option to link to a shared data source.</span></span> <span data-ttu-id="feaba-120">Выберите общий источник данных из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="feaba-120">Select a shared data source from the drop-down list.</span></span> <span data-ttu-id="feaba-121">Чтобы изменить выбранный источник данных, нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="feaba-121">To edit the selected data source, click **Edit**.</span></span> <span data-ttu-id="feaba-122">Если установлен флажок **Использовать ссылку на общий источник данных** , флажки **Тип** и **Строка соединения** отключены.</span><span class="sxs-lookup"><span data-stu-id="feaba-122">If **Use shared data source reference** is selected, **Type** and **Connection string** are disabled.</span></span>  
  
 <span data-ttu-id="feaba-123">**Использовать одну транзакцию при обработке запросов**</span><span class="sxs-lookup"><span data-stu-id="feaba-123">**Use a single transaction when processing the queries**</span></span>  
 <span data-ttu-id="feaba-124">Выберите этот параметр, чтобы указать, что все наборы данных, использующие этот источник данных, запускаются в единой транзакции базы данных.</span><span class="sxs-lookup"><span data-stu-id="feaba-124">Select this option to indicate that datasets that use this data source are run in a single transaction against the database.</span></span> <span data-ttu-id="feaba-125">Чтобы транзакции вложенного отчета использовали тот же источник данных, задайте для этого вложенного отчета в панели **Свойства** в разделе **Прочее** для свойства **MergeTransactions** значение **True** .</span><span class="sxs-lookup"><span data-stu-id="feaba-125">To include transactions for subreports that use the same data source, set **MergeTransactions** to **True** in the subreport's **Other** properties section of the **Properties** pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feaba-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="feaba-126">See Also</span></span>  
 <span data-ttu-id="feaba-127">[Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="feaba-127">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="feaba-128">[Создание внедренного или общего источника данных &#40;SSRS&#41;](../../2014/reporting-services/create-an-embedded-or-shared-data-source-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="feaba-128">[Create an Embedded or Shared Data Source &#40;SSRS&#41;](../../2014/reporting-services/create-an-embedded-or-shared-data-source-ssrs.md) </span></span>  
 <span data-ttu-id="feaba-129">[Подключения к данным, источники данных и строки подключения в Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="feaba-129">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="feaba-130">Диалоговое окно "Свойства источника данных" — "Учетные данные"</span><span class="sxs-lookup"><span data-stu-id="feaba-130">Data Source Properties Dialog Box, Credentials</span></span>](../../2014/reporting-services/data-source-properties-dialog-box-credentials.md)  
  
  
