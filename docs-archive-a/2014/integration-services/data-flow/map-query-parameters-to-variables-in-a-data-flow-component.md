---
title: Сопоставления параметров запросов с переменными в компонентах потока данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- queries [Integration Services], parameter mapping
- parameters [Integration Services]
- mapping query parameters to variables [Integration Services]
- variables [Integration Services], mapping parameters to
ms.assetid: 5e26977c-758c-46d6-acf1-4fd9238f0950
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b38940313397c7be7a8bcdbd2bf7f5233583096e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750047"
---
# <a name="map-query-parameters-to-variables-in-a-data-flow-component"></a><span data-ttu-id="bb56b-102">Сопоставления параметров запросов с переменными в компонентах потока данных</span><span class="sxs-lookup"><span data-stu-id="bb56b-102">Map Query Parameters to Variables in a Data Flow Component</span></span>
  <span data-ttu-id="bb56b-103">При настройке конфигурации источника OLE DB для использования параметризованных запросов можно сопоставить параметры с переменными.</span><span class="sxs-lookup"><span data-stu-id="bb56b-103">When you configure the OLE DB source to use parameterized queries, you can map the parameters to variables.</span></span>  
  
 <span data-ttu-id="bb56b-104">В источнике OLE DB параметризованные запросы используются для фильтрации данных при подключении источника к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="bb56b-104">The OLE DB source uses parameterized queries to filter data when the source connects to a data source.</span></span>  
  
### <a name="to-map-a-query-parameter-to-a-variable"></a><span data-ttu-id="bb56b-105">Сопоставление параметра запроса с переменной</span><span class="sxs-lookup"><span data-stu-id="bb56b-105">To map a query parameter to a variable</span></span>  
  
1.  <span data-ttu-id="bb56b-106">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="bb56b-106">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="bb56b-107">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="bb56b-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="bb56b-108">Щелкните вкладку **Поток данных** и перетащите источник OLE DB из **области элементов**в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="bb56b-108">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB source to the design surface.</span></span>  
  
4.  <span data-ttu-id="bb56b-109">Щелкните правой кнопкой источник OLE DB и выберите пункт **Правка**.</span><span class="sxs-lookup"><span data-stu-id="bb56b-109">Right-click the OLE DB source, and then click **Edit**.</span></span>  
  
5.  <span data-ttu-id="bb56b-110">В окне **Редактор источника OLE DB**выберите диспетчер соединений OLE DB, предназначенный для подключения к источнику данных, или нажмите кнопку **Создать** , чтобы создать новый диспетчер соединений OLE DB.</span><span class="sxs-lookup"><span data-stu-id="bb56b-110">In the **OLE DB Source Editor**, select an OLE DB connection manager to use to connect to the data source, or click **New** to create a new OLE DB connection manager.</span></span>  
  
6.  <span data-ttu-id="bb56b-111">Выберите параметр **Команда SQL** для режима доступа к данным, а затем введите параметризированный запрос панели **Текст команды SQL** .</span><span class="sxs-lookup"><span data-stu-id="bb56b-111">Select the **SQL command** option for data access mode, and then type a parameterized query in the **SQL command text** pane.</span></span>  
  
7.  <span data-ttu-id="bb56b-112">Нажмите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="bb56b-112">Click **Parameters**.</span></span>  
  
8.  <span data-ttu-id="bb56b-113">В диалоговом окне **Установка параметров запроса** сопоставьте каждый параметр в списке **Параметры** с переменной в списке **Переменные** или создайте переменную, щелкнув **\<New variable>** .</span><span class="sxs-lookup"><span data-stu-id="bb56b-113">In the **Set Query Parameters** dialog box, map each parameter in the **Parameters** list to a variable in the **Variables** list, or create a new variable by clicking **\<New variable>**.</span></span> <span data-ttu-id="bb56b-114">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bb56b-114">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bb56b-115">Для сопоставления доступны только системные и пользовательские переменные, находящиеся в области видимости данного пакета, родительского контейнера, такого как «цикл по каждому элементу», или задачи потока данных, содержащей компоненты потока данных, доступные для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="bb56b-115">Only system variables and user-defined variables that are in the scope of the package, a parent container such as a Foreach Loop, or the Data Flow task that contains the data flow component are available for mapping.</span></span> <span data-ttu-id="bb56b-116">Переменная должна иметь тип данных, совместимый со столбцом в предложении WHERE, которому назначен параметр.</span><span class="sxs-lookup"><span data-stu-id="bb56b-116">The variable must have a data type that is compatible with the column in the WHERE clause to which the parameter is assigned.</span></span>  
  
9. <span data-ttu-id="bb56b-117">Чтобы просмотреть до 200 строк данных, возвращаемых запросом, нажмите кнопку **Предварительный просмотр** .</span><span class="sxs-lookup"><span data-stu-id="bb56b-117">You can click **Preview** to view up to 200 rows of the data that the query returns.</span></span>  
  
10. <span data-ttu-id="bb56b-118">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="bb56b-118">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb56b-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb56b-119">See Also</span></span>  
 <span data-ttu-id="bb56b-120">[Источник OLE DB](ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="bb56b-120">[OLE DB Source](ole-db-source.md) </span></span>  
 [<span data-ttu-id="bb56b-121">Преобразование "Уточняющий запрос"</span><span class="sxs-lookup"><span data-stu-id="bb56b-121">Lookup Transformation</span></span>](transformations/lookup-transformation.md)  
  
  
