---
title: Задача 9. Добавление преобразования UNION ALL для объединения правильных и исправленных записей | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 24ba466d-a7d3-49e7-9111-b348399c9e58
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 83afb5ea9367660048fe36d00ab59d808da17b81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751580"
---
# <a name="task-9-adding-union-all-transform-to-combine-correct-and-corrected-records"></a><span data-ttu-id="dd38d-102">Задача 9. Добавление преобразования "Объединить все" для объединения верных и исправленных записей</span><span class="sxs-lookup"><span data-stu-id="dd38d-102">Task 9: Adding Union All Transform to Combine Correct and Corrected Records</span></span>
  <span data-ttu-id="dd38d-103">В этой задаче в поток данных добавляется преобразование «Объединить все».</span><span class="sxs-lookup"><span data-stu-id="dd38d-103">In this task, you add the Union All Transform to the data flow.</span></span> <span data-ttu-id="dd38d-104">Преобразование «Объединить все» объединяет несколько входов в один выход.</span><span class="sxs-lookup"><span data-stu-id="dd38d-104">The Union All transformation combines multiple inputs into one output.</span></span> <span data-ttu-id="dd38d-105">В вашем сценарии это преобразование позволяет объединить верные и исправленные записи в одном потоке.</span><span class="sxs-lookup"><span data-stu-id="dd38d-105">In your scenario, it combine both Correct and Corrected records into one stream.</span></span>  
  
1.  <span data-ttu-id="dd38d-106">Перетащите элемент **объединить все** преобразование из **общего** раздела **панели элементов служб SSIS** на вкладку **поток данных** и поместите его в разделе **Выберите правильные и исправленные записи**.</span><span class="sxs-lookup"><span data-stu-id="dd38d-106">Drag-drop **Union All** Transform from **Common** section of the **SSIS Toolbox** to the **Data Flow** tab and place it under **Pick Correct and Corrected Records**.</span></span>  
  
2.  <span data-ttu-id="dd38d-107">Щелкните правой кнопкой мыши элемент преобразование **объединить все** на вкладке **поток данных** и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="dd38d-107">Right-click **Union All** Transform in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="dd38d-108">Введите **сочетание правильных и исправленных записей**и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="dd38d-108">Type **Combine Correct and Corrected Records**, and press **ENTER**.</span></span>  
  
     <span data-ttu-id="dd38d-109">![Объединение правильных и исправленных записей](../../2014/tutorials/media/et-addinguattocombinecacrecords-01.jpg "Объединение правильных и исправленных записей")</span><span class="sxs-lookup"><span data-stu-id="dd38d-109">![Combine Correct and Corrected Reocrds](../../2014/tutorials/media/et-addinguattocombinecacrecords-01.jpg "Combine Correct and Corrected Reocrds")</span></span>  
  
3.  <span data-ttu-id="dd38d-110">Connect **Выберите правильные и исправленные записи** , чтобы **объединить правильные и исправленные записи** на вкладке **поток данных** с помощью синего соединителя.</span><span class="sxs-lookup"><span data-stu-id="dd38d-110">Connect **Pick Correct and Corrected Records** to **Combine Correct and Corrected Records** in the **Data Flow** tab by using the blue connector.</span></span> <span data-ttu-id="dd38d-111">Вы должны увидеть диалоговое окно **Выбор входных данных** .</span><span class="sxs-lookup"><span data-stu-id="dd38d-111">You should see the **Input Output Selection** dialog box.</span></span>  
  
4.  <span data-ttu-id="dd38d-112">В диалоговом окне **входные данные** выберите **исправить** для **выходных данных** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dd38d-112">In the **Input Output** dialog box, select **Correct** for **Output** and click **OK**.</span></span>  
  
     <span data-ttu-id="dd38d-113">![Диалоговое окно «Выбор входов и выходов»](../../2014/tutorials/media/et-addinguattocombinecacrecords-02.jpg "Диалоговое окно «Выбор входов и выходов»")</span><span class="sxs-lookup"><span data-stu-id="dd38d-113">![Input Output Selection Dialog Box](../../2014/tutorials/media/et-addinguattocombinecacrecords-02.jpg "Input Output Selection Dialog Box")</span></span>  
  
5.  <span data-ttu-id="dd38d-114">Переместите соединитель с названием **правильный** слева, перетащив точку в конце соединительной линии влево.</span><span class="sxs-lookup"><span data-stu-id="dd38d-114">Move the connector titled **Correct** to the left by dragging and dropping the dot at the end of the connector to left.</span></span>  
  
     <span data-ttu-id="dd38d-115">![Соединение с правильными для объединения правильных и исправленных записей](../../2014/tutorials/media/et-addinguattocombinecacrecords-03.jpg "Соединение с правильными для объединения правильных и исправленных записей")</span><span class="sxs-lookup"><span data-stu-id="dd38d-115">![Connect Correct to Combine Correct and Corrected](../../2014/tutorials/media/et-addinguattocombinecacrecords-03.jpg "Connect Correct to Combine Correct and Corrected")</span></span>  
  
6.  <span data-ttu-id="dd38d-116">Если выбрать вариант **выбрать правильное и исправленное преобразование записей** , появится еще один синий соединитель.</span><span class="sxs-lookup"><span data-stu-id="dd38d-116">If you select **Pick Correct and Corrected Records** transform, you should see another blue connector.</span></span> <span data-ttu-id="dd38d-117">Перетащите этот синий соединитель, чтобы **объединить правильные и исправленные записи**.</span><span class="sxs-lookup"><span data-stu-id="dd38d-117">Drag that blue connector to **Combine Correct and Corrected Records**.</span></span>  
  
     <span data-ttu-id="dd38d-118">![Соединение с исправленными для объединения правильных и исправленных записей](../../2014/tutorials/media/et-addinguattocombinecacrecords-04.jpg "Соединение с исправленными для объединения правильных и исправленных записей")</span><span class="sxs-lookup"><span data-stu-id="dd38d-118">![Connect Corrected to Combine Correct and Corrected](../../2014/tutorials/media/et-addinguattocombinecacrecords-04.jpg "Connect Corrected to Combine Correct and Corrected")</span></span>  
  
7.  <span data-ttu-id="dd38d-119">Этот **соединитель** должен иметь название **Исправлено**.</span><span class="sxs-lookup"><span data-stu-id="dd38d-119">This **connector** should be titled **Corrected**.</span></span> <span data-ttu-id="dd38d-120">Так как у вас есть только два условия, которые **верны** и **исправлены**, и одно условие уже использовалось, диалоговое окно **выбора входных данных** не отображается на этот раз.</span><span class="sxs-lookup"><span data-stu-id="dd38d-120">Since you have only two conditions **Correct** and **Corrected**, and one condition was already used, the **Input Output Selection** dialog box is not displayed this time.</span></span> <span data-ttu-id="dd38d-121">Если соединители пересекаются, переместите один влево, а другой вправо с помощью перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="dd38d-121">If the connectors overlap, move one to left and the other one to right by dragging the connector to left or right.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="dd38d-122">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="dd38d-122">Next Step</span></span>  
 [<span data-ttu-id="dd38d-123">Задача 10. Добавление преобразования "Нечеткое группирование" для выявления повторов</span><span class="sxs-lookup"><span data-stu-id="dd38d-123">Task 10: Adding Fuzzy Group Transform to Identify Duplicates</span></span>](../../2014/tutorials/task-10-adding-fuzzy-group-transform-to-identify-duplicates.md)  
  
  
