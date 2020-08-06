---
title: Подключение к файлу Microsoft Excel (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connexcelfile.f1
ms.assetid: 126f7d6b-d270-40e7-b23e-8d114f87065b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 79bb3d57470be8acbbb990dde71cf21b62b3cb2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656734"
---
# <a name="connect-to-a-microsoft-excel-file-ssas"></a><span data-ttu-id="73326-102">Соединение с файлом Microsoft Excel (SSAS)</span><span class="sxs-lookup"><span data-stu-id="73326-102">Connect to a Microsoft Excel File (SSAS)</span></span>
  <span data-ttu-id="73326-103">Эта страница **мастера импорта таблиц** используется для соединения с файлом Microsoft Excel, который хранится на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="73326-103">This page of the **Table Import Wizard** enables you to connect to a Microsoft Excel file stored on the local machine.</span></span> <span data-ttu-id="73326-104">Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="73326-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="73326-105">Для соединения с файлом Microsoft Excel необходимо, чтобы на компьютере был установлен поставщик ACE.</span><span class="sxs-lookup"><span data-stu-id="73326-105">To connect to a Microsoft Excel file, you must have the appropriate ACE provider installed on your computer.</span></span> <span data-ttu-id="73326-106">Дополнительные сведения см. в разделе [Поддерживаемые источники данных (табличные службы SSAS)](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="73326-106">For more information, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73326-107">При выборе файла на этой странице используются учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="73326-107">The credentials of the current user are used when selecting a file in this page.</span></span> <span data-ttu-id="73326-108">Тем не менее импорт не будет успешным, если пользователь, указанный на странице сведений об олицетворении, не имеет достаточных прав для чтения из выбранного файла.</span><span class="sxs-lookup"><span data-stu-id="73326-108">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected file.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="73326-109">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="73326-109">UI element list</span></span>  
 <span data-ttu-id="73326-110">**Понятное имя соединения**</span><span class="sxs-lookup"><span data-stu-id="73326-110">**Friendly connection name**</span></span>  
 <span data-ttu-id="73326-111">Введите уникальное имя для соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="73326-111">Type a unique name for this data source connection.</span></span> <span data-ttu-id="73326-112">Это поле является обязательным.</span><span class="sxs-lookup"><span data-stu-id="73326-112">This is a required field.</span></span>  
  
 <span data-ttu-id="73326-113">**Путь к файлу Excel**</span><span class="sxs-lookup"><span data-stu-id="73326-113">**Excel File Path**</span></span>  
 <span data-ttu-id="73326-114">Укажите полный путь к файлу Excel.</span><span class="sxs-lookup"><span data-stu-id="73326-114">Specify a full path for the Excel file.</span></span>  
  
 <span data-ttu-id="73326-115">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="73326-115">**Browse**</span></span>  
 <span data-ttu-id="73326-116">Перейдите в папку, в которой находится файл Excel.</span><span class="sxs-lookup"><span data-stu-id="73326-116">Navigate to a location where an Excel file is available.</span></span>  
  
 <span data-ttu-id="73326-117">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="73326-117">**Advanced**</span></span>  
 <span data-ttu-id="73326-118">Задание дополнительных свойств соединения с помощью диалогового окна « **Задание дополнительных свойств** ».</span><span class="sxs-lookup"><span data-stu-id="73326-118">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="73326-119">**Использовать первую строку для заголовков столбцов**</span><span class="sxs-lookup"><span data-stu-id="73326-119">**Use first row as column headers**</span></span>  
 <span data-ttu-id="73326-120">Укажите, следует ли использовать первую строку данных в качестве заголовков столбцов целевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="73326-120">Specify whether to use the first data row as the column headers of the destination table.</span></span>  
  
 <span data-ttu-id="73326-121">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="73326-121">**Test Connection**</span></span>  
 <span data-ttu-id="73326-122">Установите соединение с источником данных с использованием текущих параметров.</span><span class="sxs-lookup"><span data-stu-id="73326-122">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="73326-123">Появится сообщение об успешном или неуспешном соединении.</span><span class="sxs-lookup"><span data-stu-id="73326-123">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
