---
title: Анализ табличной модели в Excel (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.chooseperspect.f1
ms.assetid: 47fa45fc-60ab-41a1-bde3-5781c8462889
author: minewiskan
ms.author: owend
ms.openlocfilehash: fae542ffb5b470d23d9cf27fcc11367f571e7cec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666746"
---
# <a name="analyze-a-tabular-model-in-excel-ssas-tabular"></a><span data-ttu-id="5cb4c-102">Анализ табличной модели в Excel (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="5cb4c-102">Analyze a Tabular Model in Excel (SSAS Tabular)</span></span>
  <span data-ttu-id="5cb4c-103">Функция анализа в Excel в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] открывает Microsoft Excel, создает соединение с источником данных, в качестве которого выступает база данных рабочей области модели, а затем добавляет сводную таблицу на рабочий лист.</span><span class="sxs-lookup"><span data-stu-id="5cb4c-103">The Analyze in Excel feature in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] opens Microsoft Excel, creates a data source connection to the model workspace database, and adds a PivotTable to the worksheet.</span></span> <span data-ttu-id="5cb4c-104">Объекты модели (таблицы, столбцы, меры, иерархии и ключевые показатели эффективности) включаются в качестве полей в список полей сводной таблицы.</span><span class="sxs-lookup"><span data-stu-id="5cb4c-104">Model objects (tables, columns, measures, hierarchies, and KPIs) are included as fields in the PivotTable field list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5cb4c-105">Для использования функции анализа в Excel необходимо на тот же компьютер, где находится среда [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], установить Microsoft Office 2003 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="5cb4c-105">To use the Analyze in Excel feature, you must have Microsoft Office 2003 or later installed on the same computer as [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="5cb4c-106">Если Microsoft Office не установлен на том же компьютере, то можно с помощью Excel на другом компьютере подключиться к базе данных рабочей области модели в качестве источника данных.</span><span class="sxs-lookup"><span data-stu-id="5cb4c-106">If Office is not installed on the same computer, you can use Excel on another computer and connect to the model workspace database as a data source.</span></span> <span data-ttu-id="5cb4c-107">Затем можно вручную добавить сводную таблицу на лист.</span><span class="sxs-lookup"><span data-stu-id="5cb4c-107">You can then manually add a PivotTable to the worksheet.</span></span> <span data-ttu-id="5cb4c-108">Объекты модели (таблицы, столбцы, меры и ключевые показатели эффективности) включаются в качестве полей в список полей сводной таблицы.</span><span class="sxs-lookup"><span data-stu-id="5cb4c-108">Model objects (tables, columns, measures, and KPIs) are included as fields in the PivotTable field list.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="5cb4c-109">Задания</span><span class="sxs-lookup"><span data-stu-id="5cb4c-109">Tasks</span></span>  
  
#### <a name="to-analyze-a-tabular-model-project-by-using-the-analyze-in-excel-feature"></a><span data-ttu-id="5cb4c-110">Анализ проекта табличной модели с помощью функции анализа в Excel</span><span class="sxs-lookup"><span data-stu-id="5cb4c-110">To analyze a tabular model project by using the Analyze in Excel feature</span></span>  
  
1.  <span data-ttu-id="5cb4c-111">В среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]щелкните меню **Модель** и выберите пункт **Анализ в Excel**.</span><span class="sxs-lookup"><span data-stu-id="5cb4c-111">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Analyze in Excel**.</span></span>  
  
2.  <span data-ttu-id="5cb4c-112">В диалоговом окне **Выбор учетных данных и перспективы** выберите один из приведенных ниже вариантов учетных данных для подключения к источнику данных рабочей области модели:</span><span class="sxs-lookup"><span data-stu-id="5cb4c-112">In the **Choose Credential and Perspective** dialog box, select one of the following credential options to connect to the model workspace data source:</span></span>  
  
    -   <span data-ttu-id="5cb4c-113">Для использования текущей учетной записи пользователя выберите **Текущий пользователь Windows**.</span><span class="sxs-lookup"><span data-stu-id="5cb4c-113">To use the current user account, select **Current Windows User**.</span></span>  
  
    -   <span data-ttu-id="5cb4c-114">Чтобы воспользоваться другой учетной записью, выберите **Другой пользователь Windows**.</span><span class="sxs-lookup"><span data-stu-id="5cb4c-114">To use a different user account, select **Other Windows User**.</span></span>  
  
         <span data-ttu-id="5cb4c-115">Обычно эта учетная запись будет членом той или иной роли.</span><span class="sxs-lookup"><span data-stu-id="5cb4c-115">Typically, this user account will be a member of a role.</span></span> <span data-ttu-id="5cb4c-116">Пароль не требуется.</span><span class="sxs-lookup"><span data-stu-id="5cb4c-116">No password is required.</span></span> <span data-ttu-id="5cb4c-117">Эта учетная запись может использоваться только в контексте подключения Excel к базе данных рабочей области.</span><span class="sxs-lookup"><span data-stu-id="5cb4c-117">The account can only be used in the context of an Excel connection to the workspace database.</span></span>  
  
    -   <span data-ttu-id="5cb4c-118">Чтобы воспользоваться ролью безопасности, выберите **Роль**, а затем в поле со списком выберите одну или несколько ролей.</span><span class="sxs-lookup"><span data-stu-id="5cb4c-118">To use a security role, select **Role**, and then in the listbox, select one or more roles.</span></span>  
  
         <span data-ttu-id="5cb4c-119">Роли безопасности должны определяться с помощью диспетчера ролей.</span><span class="sxs-lookup"><span data-stu-id="5cb4c-119">Security roles must be defined using the Role Manager.</span></span> <span data-ttu-id="5cb4c-120">Дополнительные сведения см. в разделе [Создание ролей и управление ими (табличные службы SSAS)](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="5cb4c-120">For more information, see [Create and Manage Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
3.  <span data-ttu-id="5cb4c-121">Чтобы воспользоваться перспективой, выберите нужную в поле со списком **Перспектива** .</span><span class="sxs-lookup"><span data-stu-id="5cb4c-121">To use a perspective, in the **Perspective** listbox, select a perspective.</span></span>  
  
     <span data-ttu-id="5cb4c-122">Перспективы (за исключением заданных по умолчанию) должны определяться в диалоговом окне «Перспективы».</span><span class="sxs-lookup"><span data-stu-id="5cb4c-122">Perspectives (other than default) must be defined using the Perspectives dialog box.</span></span> <span data-ttu-id="5cb4c-123">Дополнительные сведения см. в статье [Создание и управление перспективами &#40;табличных&#41;SSAS ](perspectives-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="5cb4c-123">For more information, see [Create and Manage Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5cb4c-124">Список полей сводной таблицы в Excel не обновляется автоматически при внесении изменений в проект модели в конструкторе моделей.</span><span class="sxs-lookup"><span data-stu-id="5cb4c-124">The PivotTable Field List in Excel does not refresh automatically as you make changes to the model project in the model designer.</span></span> <span data-ttu-id="5cb4c-125">Чтобы обновить список полей сводной таблицы в Excel, нажмите кнопку **Обновить** на ленте **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="5cb4c-125">To refresh the PivotTable Field List, in Excel, on the **Options** ribbon, click **Refresh**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cb4c-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="5cb4c-126">See Also</span></span>  
 [<span data-ttu-id="5cb4c-127">Анализ в Excel (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="5cb4c-127">Analyze in Excel &#40;SSAS Tabular&#41;</span></span>](analyze-in-excel-ssas-tabular.md)  
  
  
