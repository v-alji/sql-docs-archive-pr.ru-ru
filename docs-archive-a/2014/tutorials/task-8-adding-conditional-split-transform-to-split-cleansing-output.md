---
title: Задача 8. Добавление преобразования "Условное разбиение" для разбиения выходных данных очистки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: d4ebe420-a4a9-4076-89d3-41abe726fc5c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9be7ea6f5330382ad0417df99e18bcba5b59a4e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654644"
---
# <a name="task-8-adding-conditional-split-transform-to-split-cleansing-output"></a><span data-ttu-id="b881a-102">Задача 8. Добавление преобразования "Условное разбиение" для выходных данных очистки</span><span class="sxs-lookup"><span data-stu-id="b881a-102">Task 8: Adding Conditional Split Transform to Split Cleansing Output</span></span>
  <span data-ttu-id="b881a-103">В этом преобразовании в поток данных добавляется преобразование «Условное разбиение».</span><span class="sxs-lookup"><span data-stu-id="b881a-103">In this transform, you add a Conditional Split Transform to the data flow.</span></span> <span data-ttu-id="b881a-104">Преобразование «Условное разбиение» может направлять строки данных в различные выходы в зависимости от содержимого данных.</span><span class="sxs-lookup"><span data-stu-id="b881a-104">The Conditional Split transformation can route rows to different outputs based on the content of the data.</span></span> <span data-ttu-id="b881a-105">В этом руководстве используется столбец выходные данные **состояния записи** из преобразования «Очистка DQS».</span><span class="sxs-lookup"><span data-stu-id="b881a-105">For this tutorial, you use the **Record Status** output column from the DQS Cleansing transform.</span></span> <span data-ttu-id="b881a-106">В этом учебнике вы передаете на сервер MDS только верные или исправленные записи.</span><span class="sxs-lookup"><span data-stu-id="b881a-106">You will upload only correct or corrected records to MDS server in this tutorial.</span></span> <span data-ttu-id="b881a-107">Поэтому проверяется **правильность** или **исправление** **состояния записи** , а также объединение записей перед отправкой записей в MDS.</span><span class="sxs-lookup"><span data-stu-id="b881a-107">Therefore you check if the **Record Status** is **Correct** or **Corrected**, and combine the records before uploading the records to MDS.</span></span>  
  
1.  <span data-ttu-id="b881a-108">Перетащите **Преобразование Условное разбиение** из раздела **Общие** в **области элементов служб SSIS** на вкладку **поток данных** в разделе **Очистка данных поставщика**.</span><span class="sxs-lookup"><span data-stu-id="b881a-108">Drag-drop **Conditional Split Transform** from **Common** section in the **SSIS Toolbox** to the **Data Flow** tab under **Cleanse Supplier Data**.</span></span>  
  
2.  <span data-ttu-id="b881a-109">Щелкните правой кнопкой мыши **Условное разбиение**и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="b881a-109">Right-click **Conditional Split**, and click **Rename**.</span></span> <span data-ttu-id="b881a-110">Введите **Выберите правильные и исправленные записи** и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="b881a-110">Type **Pick Correct and Corrected Records** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="b881a-111">Подключите **данные поставщика очистки** и **Выберите правильные и исправленные записи** с помощью синего соединителя.</span><span class="sxs-lookup"><span data-stu-id="b881a-111">Connect **Cleanse Supplier Data** and **Pick Correct and Corrected Records** using the blue connector.</span></span>  
  
     <span data-ttu-id="b881a-112">![Очистка данных поставщика. > выбрать правильный & исправлено](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-01.jpg "Очистка данных поставщика —> выбор параметров «Правильно» и «Исправлено»")</span><span class="sxs-lookup"><span data-stu-id="b881a-112">![Cleanse Supplier Data -> Pick Correct & Corrected](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-01.jpg "Cleanse Supplier Data -> Pick Correct & Corrected")</span></span>  
  
4.  <span data-ttu-id="b881a-113">Дважды щелкните **выбрать правильные и исправленные записи** на вкладке **поток данных** .</span><span class="sxs-lookup"><span data-stu-id="b881a-113">Double-click **Pick Correct and Corrected Records** in the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="b881a-114">Измените **имя выхода по умолчанию** в нижней части экрана, чтобы **исправить**его.</span><span class="sxs-lookup"><span data-stu-id="b881a-114">Change the **Default Output Name** at the bottom of the screen to **Correct**.</span></span>  
  
6.  <span data-ttu-id="b881a-115">Разверните **столбцы** в **левой верхней области**.</span><span class="sxs-lookup"><span data-stu-id="b881a-115">Expand **Columns** in the **top-left pane**.</span></span>  
  
     <span data-ttu-id="b881a-116">![редактор преобразования «Условное разбиение»](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-02.jpg "редактор преобразования «Условное разбиение»")</span><span class="sxs-lookup"><span data-stu-id="b881a-116">![Conditional Split Transformation Editor](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-02.jpg "Conditional Split Transformation Editor")</span></span>  
  
7.  <span data-ttu-id="b881a-117">Перетащите элемент **состояние записи** в столбец **условие** .</span><span class="sxs-lookup"><span data-stu-id="b881a-117">Drag-drop **Record Status** to the **Condition** column.</span></span>  
  
8.  <span data-ttu-id="b881a-118">Введите **= = "Исправлено"** рядом с полем **[состояние записи]** для столбца **условие** .</span><span class="sxs-lookup"><span data-stu-id="b881a-118">Type **=="Corrected"** next to **[Record Status]** for the **Condition** column.</span></span>  
  
9. <span data-ttu-id="b881a-119">Щелкните **вариант 1** в **столбце Имя выхода**и измените имя на **Исправлено**.</span><span class="sxs-lookup"><span data-stu-id="b881a-119">Click **Case 1** in the **Output Name Column**, and change the name to **Corrected**.</span></span>  
  
10. <span data-ttu-id="b881a-120">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Редактор преобразования «Условное разбиение** ».</span><span class="sxs-lookup"><span data-stu-id="b881a-120">Click **OK** to close the **Conditional Split Transformation Editor** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="b881a-121">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="b881a-121">Next Step</span></span>  
 [<span data-ttu-id="b881a-122">Задача 9. Добавление преобразования "Объединить все" для объединения верных и исправленных записей</span><span class="sxs-lookup"><span data-stu-id="b881a-122">Task 9: Adding Union All Transform to Combine Correct and Corrected Records</span></span>](../../2014/tutorials/task-9-adding-union-all-transform-to-combine-correct-and-corrected-records.md)  
  
  
