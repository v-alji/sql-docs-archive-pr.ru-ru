---
title: Публикация данных из Excel в MDS (надстройка MDS для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 89fce454-a816-4b33-a26a-d1b9741d269b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 597a954760816d8938628974998fe8f6daad1af5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667253"
---
# <a name="publish-data-from-excel-to-mds-mds-add-in-for-excel"></a><span data-ttu-id="f6e8e-102">Публикация данных из Excel в MDS (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="f6e8e-102">Publish Data from Excel to MDS (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="f6e8e-103">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]необходимо по окончании работы в Excel выполнить публикацию данных в репозитории MDS, чтобы другие пользователи могли получить к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], publish data to the MDS repository when you are finished working in Excel and want to save your changes so other users have access to them.</span></span>  
  
> [!NOTE]
>  -   <span data-ttu-id="f6e8e-104">Комментарии в ячейках, управляемых MDS, при публикации изменений удаляются.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-104">When you publish changes, comments on MDS-managed cells are deleted.</span></span>  
> -   <span data-ttu-id="f6e8e-105">Формула не поддерживается в ячейке, управляемой MDS.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-105">A formula is not supported in an MDS-managed cell.</span></span> <span data-ttu-id="f6e8e-106">Формула в управляемой MDS ячейке обрабатывается как текстовое значение.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-106">A formula in an MDS-managed cell is handled as a text value.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f6e8e-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f6e8e-107">Prerequisites</span></span>  
 <span data-ttu-id="f6e8e-108">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="f6e8e-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="f6e8e-109">Необходимо иметь разрешение на доступ к функциональной области **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="f6e8e-109">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="f6e8e-110">Активный лист должен содержать данные, управляемые MDS, и в эти данные должны быть внесены изменения или дополнения.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-110">The active worksheet must contain MDS-managed data and you must have made changes or additions to the MDS-managed data.</span></span>  
  
-   <span data-ttu-id="f6e8e-111">Если добавляются новые элементы, то для них не нужно указывать значение **Code** , если формирование кодов сущностей производится автоматически.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-111">If you are adding members, you do not have to specify a **Code** value if codes for the entity are being automatically generated.</span></span> <span data-ttu-id="f6e8e-112">Дополнительные сведения см. в разделе [Автоматическое создание кода &#40;Master Data Services&#41;](../automatic-code-creation-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f6e8e-112">For more information, see [Automatic Code Creation &#40;Master Data Services&#41;](../automatic-code-creation-master-data-services.md).</span></span>  
  
### <a name="to-publish-data-to-the-mds-repository"></a><span data-ttu-id="f6e8e-113">Публикация данных в репозитории MDS</span><span class="sxs-lookup"><span data-stu-id="f6e8e-113">To publish data to the MDS repository</span></span>  
  
1.  <span data-ttu-id="f6e8e-114">В группе **Публикация и проверка** нажмите **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-114">In the **Publish and Validate** group, click **Publish**.</span></span>  
  
2.  <span data-ttu-id="f6e8e-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-115">Optional.</span></span> <span data-ttu-id="f6e8e-116">Если открылось диалоговое окно **Публикация и заметки** , то выберите либо использование одной заметки (комментария) для всех обновлений, либо задание заметок отдельно для каждого изменения.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-116">If the **Publish and Annotate** dialog box is displayed, choose to share the same annotation (comment) for all updates, or to annotate each change individually.</span></span>  
  
3.  <span data-ttu-id="f6e8e-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-117">Optional.</span></span> <span data-ttu-id="f6e8e-118">Выберите флажок **Больше не показывать это диалоговое окно** .</span><span class="sxs-lookup"><span data-stu-id="f6e8e-118">Select the **Do not show this dialog box again** check box.</span></span> <span data-ttu-id="f6e8e-119">Его отображение можно будет в любой момент включить, выбрав **Настройки** и установив флажок **Показывать диалоговое окно «Публикация и заметки» при публикации** .</span><span class="sxs-lookup"><span data-stu-id="f6e8e-119">You can always show the dialog box in the future by choosing **Settings** and selecting the **Show Publish and Annotate dialog box when publishing** check box.</span></span>  
  
4.  <span data-ttu-id="f6e8e-120">Щелкните **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-120">Click **Publish**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f6e8e-121">Если при добавлении на лист новых элементов (строк) их не удалось успешно опубликовать в репозитории MDS, то, возможно, у вас нет разрешения **Обновление** для всех атрибутов листа.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-121">If you are adding new members (rows) to your worksheet and you cannot successfully publish them to the MDS repository, you may not have **Update** permission to all of the attributes in the worksheet.</span></span> <span data-ttu-id="f6e8e-122">На вкладке **Просмотр** в группе **Изменения** нажмите **Снять защиту листа** и повторите попытку публикации.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-122">On the **Review** tab, in the **Changes** group, click **Unprotect Sheet** and try to publish again.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f6e8e-123">Next Steps</span><span class="sxs-lookup"><span data-stu-id="f6e8e-123">Next Steps</span></span>  
 [<span data-ttu-id="f6e8e-124">Применение бизнес-правил (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="f6e8e-124">Apply Business Rules &#40;MDS Add-in for Excel&#41;</span></span>](apply-business-rules-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="f6e8e-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="f6e8e-125">See Also</span></span>  
 <span data-ttu-id="f6e8e-126">[Публикация &#40;данных надстройка MDS для Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="f6e8e-126">[Publishing Data &#40;MDS Add-in for Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="f6e8e-127">Проверка данных (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="f6e8e-127">Validating Data &#40;MDS Add-in for Excel&#41;</span></span>](validating-data-mds-add-in-for-excel.md)  
  
  
