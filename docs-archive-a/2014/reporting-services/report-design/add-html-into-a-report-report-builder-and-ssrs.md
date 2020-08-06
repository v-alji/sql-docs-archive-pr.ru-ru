---
title: Добавление HTML в отчет (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 30bd631a-f774-48e7-a13a-b6c2eb54d9bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 605c84843d62fb664a8a665a3fc3b024f8f87186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737958"
---
# <a name="add-html-into-a-report-report-builder-and-ssrs"></a><span data-ttu-id="a7500-102">Добавление HTML в отчет (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="a7500-102">Add HTML into a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a7500-103">С помощью заполнителя можно импортировать HTML из поля в наборе данных, чтобы использовать в отчете.</span><span class="sxs-lookup"><span data-stu-id="a7500-103">Using a placeholder, you can import HTML from a field in your dataset for use in the report.</span></span> <span data-ttu-id="a7500-104">По умолчанию заполнитель представляет простой текст, поэтому нужно изменить тип разметки заполнителя на HTML.</span><span class="sxs-lookup"><span data-stu-id="a7500-104">By default, a placeholder represents plain text, so you will need to change the placeholder mark-up type to HTML.</span></span> <span data-ttu-id="a7500-105">Дополнительные сведения см. в разделе [Импорт HTML в отчет (построитель отчетов и службы SSRS)](importing-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a7500-105">For more information, see [Importing HTML into a Report &#40;Report Builder and SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-html-from-a-field-in-your-dataset-into-a-text-box"></a><span data-ttu-id="a7500-106">Добавление HTML из поля набора данных в текстовое поле</span><span class="sxs-lookup"><span data-stu-id="a7500-106">To add HTML from a field in your dataset into a text box</span></span>  
  
1.  <span data-ttu-id="a7500-107">На вкладке **Вставка** щелкните **Список**.</span><span class="sxs-lookup"><span data-stu-id="a7500-107">On the **Insert** tab, click **List**.</span></span> <span data-ttu-id="a7500-108">Щелкните в области конструктора и перетащите указатель мыши, чтобы создать поле нужного размера.</span><span class="sxs-lookup"><span data-stu-id="a7500-108">Click the design surface, and then drag to create a box that is the size you want.</span></span>  
  
     <span data-ttu-id="a7500-109">Откроется диалоговое окно **Свойства набора данных** .</span><span class="sxs-lookup"><span data-stu-id="a7500-109">The **Dataset Properties** dialog box opens.</span></span> <span data-ttu-id="a7500-110">Можно использовать общий набор данных или набор данных, внедренный в отчет.</span><span class="sxs-lookup"><span data-stu-id="a7500-110">You can use a shared dataset or a dataset embedded in your report.</span></span> <span data-ttu-id="a7500-111">Чтобы получить дополнительные сведения, щелкните [Диалоговое окно "Свойства набора данных" — "Запрос" (построитель отчетов)](../report-data/dataset-properties-dialog-box-query-report-builder.md) или [Диалоговое окно "Свойства набора данных" — "Запрос"](../dataset-properties-dialog-box-query.md).</span><span class="sxs-lookup"><span data-stu-id="a7500-111">For more information, click [Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) or [Dataset Properties Dialog Box, Query](../dataset-properties-dialog-box-query.md).</span></span>  
  
2.  <span data-ttu-id="a7500-112">На вкладке **Вставка** щелкните **Текстовое поле**.</span><span class="sxs-lookup"><span data-stu-id="a7500-112">On the **Insert** tab, click **Text Box**.</span></span> <span data-ttu-id="a7500-113">Щелкните в списке и перетащите указатель мыши, чтобы создать поле нужного размера.</span><span class="sxs-lookup"><span data-stu-id="a7500-113">Click in the list, and then drag to create a box that is the size you want.</span></span>  
  
3.  <span data-ttu-id="a7500-114">Перетащите в текстовое поле HTML-поле из набора данных.</span><span class="sxs-lookup"><span data-stu-id="a7500-114">Drag an HTML field from your dataset into the text box.</span></span> <span data-ttu-id="a7500-115">Для поля создается заполнитель.</span><span class="sxs-lookup"><span data-stu-id="a7500-115">A placeholder is created for your field.</span></span>  
  
4.  <span data-ttu-id="a7500-116">Щелкните правой кнопкой мыши заполнитель и выберите пункт **Свойства местозаполнителя**.</span><span class="sxs-lookup"><span data-stu-id="a7500-116">Right-click the placeholder, and then click **Placeholder Properties**.</span></span>  
  
5.  <span data-ttu-id="a7500-117">На вкладке **Общие** убедитесь, что поле **Значение** содержит выражение, которое оценивается как поле, перемещенное на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="a7500-117">On the **General** tab, verify that the **Value** box contains an expression that evaluates to the field you dropped in step 3.</span></span>  
  
6.  <span data-ttu-id="a7500-118">Установите флажок **HTML — интерпретировать теги HTML как стили**.</span><span class="sxs-lookup"><span data-stu-id="a7500-118">Click **HTML - Interpret HTML tags as styles**.</span></span> <span data-ttu-id="a7500-119">Тем самым поля будут вычисляться как HTML.</span><span class="sxs-lookup"><span data-stu-id="a7500-119">This causes the field to be evaluated as HTML.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a7500-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7500-120">See Also</span></span>  
 <span data-ttu-id="a7500-121">[Форматирование чисел и дат (построитель отчетов и службы SSRS)](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a7500-121">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a7500-122">[Форматирование линий, цветов и изображений (построитель отчетов и службы SSRS)](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a7500-122">[Formatting Lines, Colors, and Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a7500-123">Диалоговое окно "Свойства заполнителя" — "Общие" (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="a7500-123">Placeholder Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../placeholder-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
