---
title: Задание ориентации текстового поля (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 64bd53f4-2f31-4732-8c2e-64c7b54b6972
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d509f1df29203fa5def79b61b74ae9db8f40d204
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654794"
---
# <a name="set-text-box-orientation-report-builder-and-ssrs"></a><span data-ttu-id="915ec-102">Задание ориентации текстового поля (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="915ec-102">Set Text Box Orientation (Report Builder and SSRS)</span></span>
  <span data-ttu-id="915ec-103">Направление ориентации текстового поля может быть различным: горизонтальным, вертикальным (текст читается сверху вниз) или повернутым на 270 градусов (текст читается снизу вверх).</span><span class="sxs-lookup"><span data-stu-id="915ec-103">A text box can be oriented in different directions: horizontally, vertically (text reading from top to bottom), or rotated by 270 degrees (text reading from bottom to top).</span></span> <span data-ttu-id="915ec-104">Поскольку ориентация задается для текстового поля, а не для текста, ориентация применяется ко всему тексту в поле.</span><span class="sxs-lookup"><span data-stu-id="915ec-104">Because orientation is set on the text box not the text, the orientation applies to all the text in the text box.</span></span> <span data-ttu-id="915ec-105">Для различных областей текста нельзя указать различную ориентацию.</span><span class="sxs-lookup"><span data-stu-id="915ec-105">You cannot specify different orientations for parts of the text.</span></span> <span data-ttu-id="915ec-106">Чтобы разместить разворачиваемый текст, задайте значения ширины столбца и высоты строки вручную.</span><span class="sxs-lookup"><span data-stu-id="915ec-106">Size the column width and the row height manually to accommodate the rotated text.</span></span>  
  
 <span data-ttu-id="915ec-107">Свойство WritingMode, используемое для указания ориентации текста, недоступно в диалоговом окне **Свойства текстового поля** .</span><span class="sxs-lookup"><span data-stu-id="915ec-107">The WritingMode property, which you use to specify text orientation, is not available in the **Text Box Properties** dialog box.</span></span> <span data-ttu-id="915ec-108">Необходимо открыть панель свойств и задать свойства в ней.</span><span class="sxs-lookup"><span data-stu-id="915ec-108">You need to open the Properties pane and set the property there.</span></span> <span data-ttu-id="915ec-109">Доступными значениями для свойства WritingMode являются **горизонтальные** (текст читается слева направо), **вертикальный** (чтение текста сверху вниз), **Rotate270** (текст читается снизу вверх).</span><span class="sxs-lookup"><span data-stu-id="915ec-109">The available values for the WritingMode property are **Horizontal** (text reading left to right), **Vertical** (text reading top to bottom), **Rotate270** (text reading bottom to top).</span></span> <span data-ttu-id="915ec-110">Чтобы разместить текст, необходимо вручную указать значения ширины столбца и высоты строки.</span><span class="sxs-lookup"><span data-stu-id="915ec-110">You must manually size the column width and the row height to accommodate the text.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-text-orientation"></a><span data-ttu-id="915ec-111">Задание ориентации текста</span><span class="sxs-lookup"><span data-stu-id="915ec-111">To set text orientation</span></span>  
  
1.  <span data-ttu-id="915ec-112">Создайте новый отчет или откройте существующий отчет.</span><span class="sxs-lookup"><span data-stu-id="915ec-112">Create a new report or open an existing report.</span></span>  
  
2.  <span data-ttu-id="915ec-113">Если панель свойств не открыта, перейдите на вкладку **Вид** и установите флажок **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="915ec-113">If the Properties pane is not open, click the **View** tab and select the **Properties** check box.</span></span>  
  
3.  <span data-ttu-id="915ec-114">Щелкните текстовое поле, для которого необходимо изменить ориентацию текста.</span><span class="sxs-lookup"><span data-stu-id="915ec-114">Click the text box for which you want to change text orientation.</span></span>  
  
4.  <span data-ttu-id="915ec-115">На панели свойств перейдите к свойству WritingMode и в раскрывающемся списке выберите ориентацию текста для применения к текстовому полю.</span><span class="sxs-lookup"><span data-stu-id="915ec-115">Locate the WritingMode property in the Properties pane and in the drop-down list select the text orientation to apply to the text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="915ec-116">Если свойства на панели свойств упорядочены по категориям, свойство WritingMode относится к категории **Локализация** .</span><span class="sxs-lookup"><span data-stu-id="915ec-116">When the properties in the Properties pane are organized into categories, WritingMode is in the **Localization** category.</span></span>  
  
5.  <span data-ttu-id="915ec-117">В списке выберите **Горизонтально**, **Вертикально**или **Поворот на 270 градусов**.</span><span class="sxs-lookup"><span data-stu-id="915ec-117">In the list box, select **Horizontal**, **Vertical**, or **Rotate270**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="915ec-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="915ec-118">See Also</span></span>  
 <span data-ttu-id="915ec-119">[Текстовые поля &#40;построитель отчетов и службы SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="915ec-119">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="915ec-120">Учебник. Форматирование текста (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="915ec-120">Tutorial: Format Text &#40;Report Builder&#41;</span></span>](../tutorial-format-text-report-builder.md)  
  
  
