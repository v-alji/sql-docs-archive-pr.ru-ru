---
title: Удаление связей (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d40e3f05-54e8-4c4b-807a-0b06f446079b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c63324918eb6919ce0abd65b5ee0765f9d7243b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728845"
---
# <a name="delete-relationships-ssas-tabular"></a><span data-ttu-id="ac2c7-102">Удаление связей (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="ac2c7-102">Delete Relationships (SSAS Tabular)</span></span>
  <span data-ttu-id="ac2c7-103">Удалять существующие связи можно с помощью конструктора моделей в представлении диаграмм или диалогового окна «Управление связями».</span><span class="sxs-lookup"><span data-stu-id="ac2c7-103">You can delete existing relationships by using the model designer in Diagram View or by using the Manage Relationships dialog box.</span></span> <span data-ttu-id="ac2c7-104">Сведения об использовании связей в табличных моделях см. в разделе [Связи (табличные службы SSAS)](relationships-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="ac2c7-104">For information about how relationships are used in tabular models, see [Relationships &#40;SSAS Tabular&#41;](relationships-ssas-tabular.md).</span></span>  
  
## <a name="considerations-for-deleting-relationships"></a><span data-ttu-id="ac2c7-105">Замечания об удалении связей</span><span class="sxs-lookup"><span data-stu-id="ac2c7-105">Considerations for Deleting Relationships</span></span>  
 <span data-ttu-id="ac2c7-106">Принимая решение об удалении связи, необходимо учитывать следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="ac2c7-106">Keep the following issues in mind when deciding whether to delete a relationship:</span></span>  
  
-   <span data-ttu-id="ac2c7-107">Отменить удаление связи невозможно.</span><span class="sxs-lookup"><span data-stu-id="ac2c7-107">There is no way to undo the deletion of a relationship.</span></span> <span data-ttu-id="ac2c7-108">Можно создать связь повторно, но это действие потребует полного пересчета формул в модели.</span><span class="sxs-lookup"><span data-stu-id="ac2c7-108">You can re-create the relationship, but this action requires a complete recalculation of formulas in the model.</span></span> <span data-ttu-id="ac2c7-109">Таким образом, перед удалением связи всегда нужно сначала проверить, не используется ли она в формулах.</span><span class="sxs-lookup"><span data-stu-id="ac2c7-109">Therefore, always check first before deleting a relationship that is used in formulas.</span></span>  
  
-   <span data-ttu-id="ac2c7-110">Удаление связи между двумя таблицами может привести к ошибкам в формулах, которые ссылаются на данные таблицы.</span><span class="sxs-lookup"><span data-stu-id="ac2c7-110">Deleting a relationship between two tables can cause errors in formulas that reference these tables.</span></span>  
  
-   <span data-ttu-id="ac2c7-111">Функция выражений анализа данных (DAX) RELATED использует связи между таблицами для поиска связанных значений в другой таблице.</span><span class="sxs-lookup"><span data-stu-id="ac2c7-111">The Data Analysis Expression (DAX) RELATED function uses the relationships between tables to look up related values in another table.</span></span> <span data-ttu-id="ac2c7-112">После удаления связи она будет возвращать другие результаты.</span><span class="sxs-lookup"><span data-stu-id="ac2c7-112">It will return different results after the relationship is deleted.</span></span> <span data-ttu-id="ac2c7-113">Дополнительные сведения см. в описании функции RELATED (DAX).</span><span class="sxs-lookup"><span data-stu-id="ac2c7-113">For more information, see the RELATED Function (DAX).</span></span>  
  
-   <span data-ttu-id="ac2c7-114">Помимо изменения результатов сводной таблицы и формулы, операции создания и удаления связей приводят к пересчету книги, что может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="ac2c7-114">In addition to changing PivotTable and formula results, both the creation and deletion of relationships will cause the workbook to be recalculated, which can take some time.</span></span>  
  
## <a name="delete-relationships"></a><span data-ttu-id="ac2c7-115">Удаление связей</span><span class="sxs-lookup"><span data-stu-id="ac2c7-115">Delete Relationships</span></span>  
  
#### <a name="to-delete-a-relationship-by-using-diagram-view"></a><span data-ttu-id="ac2c7-116">Удаление связи с помощью представления диаграммы</span><span class="sxs-lookup"><span data-stu-id="ac2c7-116">To delete a relationship by using Diagram View</span></span>  
  
1.  <span data-ttu-id="ac2c7-117">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]в меню **Модель** укажите **Представление модели**и выберите пункт **Представление диаграммы**.</span><span class="sxs-lookup"><span data-stu-id="ac2c7-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Model** menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
2.  <span data-ttu-id="ac2c7-118">Правой кнопкой мыши щелкните линию связи между двумя таблицами и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ac2c7-118">Right-click a relationship line between two tables, and then click **Delete**.</span></span>  
  
#### <a name="to-delete-a-relationship-by-using-the-manage-relationships-dialog-box"></a><span data-ttu-id="ac2c7-119">Удаление связи с помощью диалогового окна «Управление связями»</span><span class="sxs-lookup"><span data-stu-id="ac2c7-119">To delete a relationship by using the Manage Relationships dialog box</span></span>  
  
1.  <span data-ttu-id="ac2c7-120">В среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]выберите меню **Таблица** и выберите команду **Управление связями**.</span><span class="sxs-lookup"><span data-stu-id="ac2c7-120">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Table** menu, and then click **Manage Relationships**.</span></span>  
  
2.  <span data-ttu-id="ac2c7-121">В диалоговом окне **Управление связями** выберите связи из списка.</span><span class="sxs-lookup"><span data-stu-id="ac2c7-121">In the **Manage Relationships** dialog box, select one or more relationships from the list.</span></span>  
  
     <span data-ttu-id="ac2c7-122">Чтобы выбрать несколько связей, щелкните каждую из них, удерживая нажатой клавишу CTRL.</span><span class="sxs-lookup"><span data-stu-id="ac2c7-122">To select multiple relationships, hold down CTRL while you click each relationship.</span></span>  
  
3.  <span data-ttu-id="ac2c7-123">Нажмите кнопку **Удалить связь**.</span><span class="sxs-lookup"><span data-stu-id="ac2c7-123">Click **Delete Relationship**.</span></span>  
  
4.  <span data-ttu-id="ac2c7-124">В диалоговом окне **Управление связями** нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="ac2c7-124">In the **Manage Relationships** dialog box, click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac2c7-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="ac2c7-125">See Also</span></span>  
 <span data-ttu-id="ac2c7-126">[Связи &#40;табличные&#41;SSAS](relationships-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="ac2c7-126">[Relationships &#40;SSAS Tabular&#41;](relationships-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="ac2c7-127">Создание связи между двумя таблицами (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="ac2c7-127">Create a Relationship Between Two Tables &#40;SSAS Tabular&#41;</span></span>](create-a-relationship-between-two-tables-ssas-tabular.md)  
  
  
