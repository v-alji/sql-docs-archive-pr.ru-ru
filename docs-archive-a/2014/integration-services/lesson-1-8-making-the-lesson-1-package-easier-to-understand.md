---
title: Шаг 8. Облегчение чтения пакета, созданного на занятии 1 | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e3751e53-77c7-47d0-8fe8-73ed1a53413a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 67fb8e2adb9062b5b777acc14df0ddc5b45884ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664343"
---
# <a name="step-8-making-the-lesson-1-package-easier-to-understand"></a><span data-ttu-id="70429-102">Шаг 8. Облегчение чтения пакета, созданного на занятии 1</span><span class="sxs-lookup"><span data-stu-id="70429-102">Step 8: Making the Lesson 1 Package Easier to Understand</span></span>
  <span data-ttu-id="70429-103">После завершения настройки пакета, созданного на занятии 1, можно приступить к приведению его макета в порядок.</span><span class="sxs-lookup"><span data-stu-id="70429-103">Now that you have completed the configuration of the Lesson 1 package, it is a good idea to tidy up the package layout.</span></span> <span data-ttu-id="70429-104">Если фигуры в макетах элементов управления и потока данных имеют случайные размеры или если эти элементы не упорядочены или не сгруппированы, то функциональность пакета трудно понять.</span><span class="sxs-lookup"><span data-stu-id="70429-104">If the shapes in the control and data flow layouts are random sizes, or if the shapes are not aligned or grouped, the functionality of package can be more difficult to understand.</span></span>  
  
 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="70429-105">Data Tools предоставляет средства, которые облегчают и ускоряют форматирование макета пакета.</span><span class="sxs-lookup"><span data-stu-id="70429-105">Data Tools provides tools that make it easy and quick to format the package layout.</span></span> <span data-ttu-id="70429-106">К функциям форматирования относится возможность создавать элементы одного размера, выравнивать их, а также управлять горизонтальным и вертикальным пространством между элементами.</span><span class="sxs-lookup"><span data-stu-id="70429-106">The formatting features include the ability to make shapes the same size, align shapes, and manipulate the horizontal and vertical spacing between shapes.</span></span>  
  
 <span data-ttu-id="70429-107">Другим способом добиться лучшего понимания функциональности пакета является добавление заметок, описывающих функциональность пакета.</span><span class="sxs-lookup"><span data-stu-id="70429-107">Another way to improve the understanding of package functionality is to add annotations that describe package functionality.</span></span>  
  
 <span data-ttu-id="70429-108">В этой задаче будут использованы функции форматирования [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools, чтобы улучшить макет потока данных и добавить к нему заметку.</span><span class="sxs-lookup"><span data-stu-id="70429-108">In this task, you will use the formatting features in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools to improve the layout of the data flow and also add an annotation to the data flow.</span></span>  
  
### <a name="to-format-the-layout-of-the-data-flow"></a><span data-ttu-id="70429-109">Форматирование макета потока данных</span><span class="sxs-lookup"><span data-stu-id="70429-109">To format the layout of the data flow</span></span>  
  
1.  <span data-ttu-id="70429-110">Если пакет, созданный на занятии 1, еще не открыт, дважды щелкните Lesson 1.dtsx в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="70429-110">If the Lesson 1 package is not already open, double-click Lesson 1.dtsx in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="70429-111">Перейдите на вкладку **Поток данных** .</span><span class="sxs-lookup"><span data-stu-id="70429-111">Click the **Data Flow** tab.</span></span>  
  
3.  <span data-ttu-id="70429-112">Установите курсор на верхний правый угол преобразования «Извлечение валюты образца», щелкните и протащите курсор через все компоненты потока данных.</span><span class="sxs-lookup"><span data-stu-id="70429-112">Place the cursor to the top and to the right of the Extract Sample Currency transformation, click, and then drag the cursor across all the data flow components.</span></span>  
  
4.  <span data-ttu-id="70429-113">В меню **Формат** выберите команду **Установить тот же размер**и щелкните **Оба**.</span><span class="sxs-lookup"><span data-stu-id="70429-113">On the **Format** menu, point to **Make Same Size**, and then click **Both**.</span></span>  
  
5.  <span data-ttu-id="70429-114">При выделенных объектах потока данных в меню **Формат** выберите команду **Выравнивание**и щелкните **Слева**.</span><span class="sxs-lookup"><span data-stu-id="70429-114">With the data flow objects selected, on the **Format** menu, point to **Align**, and then click **Lefts**.</span></span>  
  
### <a name="to-add-an-annotation-to-the-data-flow"></a><span data-ttu-id="70429-115">Добавление заметки к потоку данных</span><span class="sxs-lookup"><span data-stu-id="70429-115">To add an annotation to the data flow</span></span>  
  
1.  <span data-ttu-id="70429-116">Щелкните правой кнопкой мыши в области конструктора потока данных и выберите команду **Добавить заметку**.</span><span class="sxs-lookup"><span data-stu-id="70429-116">Right-click anywhere in the background of the data flow design surface and then click **Add Annotation**.</span></span>  
  
2.  <span data-ttu-id="70429-117">В окне заметки введите или вставьте копированием следующий текст.</span><span class="sxs-lookup"><span data-stu-id="70429-117">Type or paste the following text in the annotation box.</span></span>  
  
     <span data-ttu-id="70429-118">**Поток данных извлекает данные из файла, находит значения в столбце CurrencyKey таблицы DimCurrency и в столбце DateKey таблицы DimDate, после чего записывает данные в таблицу NewFactCurrencyRate.**</span><span class="sxs-lookup"><span data-stu-id="70429-118">**The data flow extracts data from a file, looks up values in the CurrencyKey column in the DimCurrency table and the DateKey column in the DimDate table, and writes the data to the NewFactCurrencyRate table.**</span></span>  
  
     <span data-ttu-id="70429-119">Чтобы в окне заметки перенести текст на следующую строку, поместите курсор в то место, где должна начинаться новая строка, и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="70429-119">To wrap the text in the annotation box, place the cursor where you want to start a new line and press the Enter key.</span></span>  
  
     <span data-ttu-id="70429-120">Если в окне заметки не введен никакой текст, то окно закрывается при щелчке за его пределами.</span><span class="sxs-lookup"><span data-stu-id="70429-120">If you do not add text to the annotation box, it disappears when you click outside the box.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="70429-121">Next Steps</span><span class="sxs-lookup"><span data-stu-id="70429-121">Next Steps</span></span>  
 [<span data-ttu-id="70429-122">Шаг 9. Проверка учебного пакета, созданного на занятии 1</span><span class="sxs-lookup"><span data-stu-id="70429-122">Step 9: Testing the Lesson 1 Tutorial Package</span></span>](../integration-services/lesson-1-9-testing-the-lesson-1-tutorial-package.md)  
  
  
