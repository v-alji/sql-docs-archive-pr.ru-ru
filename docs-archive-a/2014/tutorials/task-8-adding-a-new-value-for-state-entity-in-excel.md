---
title: Задача 8. Добавление нового значения для сущности State в Excel | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: a763d76b-06a3-4d51-9614-01fc9fb1c158
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cace99419997e48088420c331a823cdf3639a3ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734645"
---
# <a name="task-8-adding-a-new-value-for-state-entity-in-excel"></a><span data-ttu-id="ded62-102">Задача 8. Добавление нового значения для сущности штата в Excel</span><span class="sxs-lookup"><span data-stu-id="ded62-102">Task 8: Adding a New Value for State Entity in Excel</span></span>
  <span data-ttu-id="ded62-103">В этой задаче добавляется новое значение для сущности State в Excel и выполняется публикация изменений на сервере MDS.</span><span class="sxs-lookup"><span data-stu-id="ded62-103">In this task, you add a value for the State entity in Excel and publish the change to the MDS server.</span></span>  
  
1.  <span data-ttu-id="ded62-104">Добавьте **Рабочий лист** в Excel, щелкнув вкладку создать внизу.</span><span class="sxs-lookup"><span data-stu-id="ded62-104">Add a **work sheet** in Excel by clicking the new tab at the bottom.</span></span>  
  
     <span data-ttu-id="ded62-105">![Excel — вкладка нового листа](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-01.jpg "Excel — вкладка нового листа")</span><span class="sxs-lookup"><span data-stu-id="ded62-105">![Excel - New Worksheet Tab](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-01.jpg "Excel - New Worksheet Tab")</span></span>  
  
2.  <span data-ttu-id="ded62-106">В **Excel**откройте вкладку **основные данные** в меню и выберите пункт **Показывать обозреватель** на ленте.</span><span class="sxs-lookup"><span data-stu-id="ded62-106">In **Excel**, click the **Master Data** tab on the menu, and then click **Show Explorer** on the ribbon.</span></span>  
  
3.  <span data-ttu-id="ded62-107">В **главном обозреватель данных**выберите **поставщики** для **модели**.</span><span class="sxs-lookup"><span data-stu-id="ded62-107">In the **Master Data Explorer**, select **Suppliers** for **Model**.</span></span> <span data-ttu-id="ded62-108">В списке сущностей должны отобразиться две сущности: **поставщик** и **состояние** .</span><span class="sxs-lookup"><span data-stu-id="ded62-108">You should see two entities: **Supplier** and **State** in the entity list.</span></span>  
  
4.  <span data-ttu-id="ded62-109">Дважды щелкните **состояние** в списке.</span><span class="sxs-lookup"><span data-stu-id="ded62-109">Double-click **State** in the list.</span></span> <span data-ttu-id="ded62-110">Все члены сущности **State** из MDS должны отображаться на листе.</span><span class="sxs-lookup"><span data-stu-id="ded62-110">All the members of the **State** entity from MDS should be displayed in the worksheet.</span></span>  
  
5.  <span data-ttu-id="ded62-111">Теперь добавьте строку в конце со следующими значениями: **North Каролина** для **Name** и **NC** для **Code**.</span><span class="sxs-lookup"><span data-stu-id="ded62-111">Now, add a row at the end with the following values: **North Carolina** for **Name** and **NC** for **Code**.</span></span> <span data-ttu-id="ded62-112">Выделение цветом помогает отличать новые или обновленные записи от других записей.</span><span class="sxs-lookup"><span data-stu-id="ded62-112">The color coding differentiates any new/updated records from the other records.</span></span>  
  
     <span data-ttu-id="ded62-113">![Excel — добавить к штатам Северную Каролину](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-02.jpg "Excel — добавить к штатам Северную Каролину")</span><span class="sxs-lookup"><span data-stu-id="ded62-113">![Excel - Add North Carolina to States](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-02.jpg "Excel - Add North Carolina to States")</span></span>  
  
6.  <span data-ttu-id="ded62-114">Щелкните **опубликовать** на ленте, чтобы опубликовать изменения в MDS.</span><span class="sxs-lookup"><span data-stu-id="ded62-114">Click **Publish** on the ribbon to publish the change to MDS.</span></span>  
  
     <span data-ttu-id="ded62-115">![Excel — кнопка публикации на вкладке основных данных](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-03.jpg "Excel — кнопка публикации на вкладке основных данных")</span><span class="sxs-lookup"><span data-stu-id="ded62-115">![Excel - Publish Button on Master Data Tab](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-03.jpg "Excel - Publish Button on Master Data Tab")</span></span>  
  
7.  <span data-ttu-id="ded62-116">Обратите внимание, что в диалоговом окне **Публикация и заметки** выбран параметр **использовать ту же аннотацию для всех изменений** .</span><span class="sxs-lookup"><span data-stu-id="ded62-116">On the **Publish and Annotate** dialog box, notice that the **Use same annotation for all changes** is selected.</span></span> <span data-ttu-id="ded62-117">Здесь можно ввести одну заметку для всех изменений.</span><span class="sxs-lookup"><span data-stu-id="ded62-117">You can enter a single annotation for all the changes here.</span></span>  
  
8.  <span data-ttu-id="ded62-118">Выберите **проверить изменения и предоставить заметки по отдельности** , чтобы заметка для каждого изменения (в данном случае только один).</span><span class="sxs-lookup"><span data-stu-id="ded62-118">Select **Review changes and provide annotations individually** option to provide annotation for each change (in this case, only one).</span></span>  
  
     <span data-ttu-id="ded62-119">![Excel — диалоговое окно «Публикация и заметки»](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-04.jpg "Excel — диалоговое окно «Публикация и заметки»")</span><span class="sxs-lookup"><span data-stu-id="ded62-119">![Excel - Publish and Annotate Dialog Box](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-04.jpg "Excel - Publish and Annotate Dialog Box")</span></span>  
  
9. <span data-ttu-id="ded62-120">Нажмите кнопку **опубликовать** , чтобы опубликовать данные в MDS.</span><span class="sxs-lookup"><span data-stu-id="ded62-120">Click **Publish** to publish data to MDS.</span></span>  
  
10. <span data-ttu-id="ded62-121">Обратите внимание, что **Цветовая кодировка** для строки с **северным Каролина** в качестве **состояния** совпадает с другими записями прямо сейчас.</span><span class="sxs-lookup"><span data-stu-id="ded62-121">Notice that **color coding** for the row with **North Carolina** as the **State** is same as other records now.</span></span>  
  
11. <span data-ttu-id="ded62-122">**Необязательно:** Убедитесь, что новый элемент (NC) добавлен в сущность **State** с помощью **обозревателя** в **Диспетчер основных данных**.</span><span class="sxs-lookup"><span data-stu-id="ded62-122">**Optional:** Verify that the new member (NC) is added to the **State** entity by using the **Explorer** in **Master Data Manager**.</span></span>  
  
12. <span data-ttu-id="ded62-123">В Excel щелкните правой кнопкой мыши лист **штат** внизу и выберите **Удалить** , чтобы удалить лист.</span><span class="sxs-lookup"><span data-stu-id="ded62-123">In Excel, right-click the **State** worksheet at the bottom, and click **Delete** to delete the worksheet.</span></span> <span data-ttu-id="ded62-124">При удалении листа не выполняется удаление данных с сервера MDS.</span><span class="sxs-lookup"><span data-stu-id="ded62-124">Deleting the worksheet does not delete any data from the MDS server.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="ded62-125">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="ded62-125">Next Step</span></span>  
 [<span data-ttu-id="ded62-126">Задача 9. Создание производной иерархии с помощью диспетчера основных данных</span><span class="sxs-lookup"><span data-stu-id="ded62-126">Task 9: Creating a Derived Hierarchy using Master Data Manager</span></span>](../../2014/tutorials/task-9-creating-a-derived-hierarchy-using-master-data-manager.md)  
  
  
