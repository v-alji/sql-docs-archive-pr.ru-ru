---
title: 'Следующие функции не поддерживаются службами Excel и могут не отображаться или отображаться только частично: комментарии, фигуры или другие объекты | Документация Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ade92e15-dfbf-496b-9378-a00bd83ba750
author: minewiskan
ms.author: owend
ms.openlocfilehash: 67c2989ab89f242fdce2ca64f3c2f361e17d49ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732085"
---
# <a name="the-following-features-are-not-supported-by-excel-services-and-may-not-display-or-may-display-only-partially-comments-shapes-or-other-objects"></a><span data-ttu-id="ad8fa-102">Следующие объекты не поддерживаются службой Excel Services и могут не отображаться совсем или отображаться лишь частично: комментарии, фигуры или другие объекты.</span><span class="sxs-lookup"><span data-stu-id="ad8fa-102">The following features are not supported by Excel Services and may not display or may display only partially: Comments, Shapes, or other objects</span></span>
  <span data-ttu-id="ad8fa-103">Эта ошибка возникает при добавлении в книгу PowerPivot срезов из списка полей PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="ad8fa-103">This error occurs when you add Slicers to a PowerPivot workbook from a PowerPivot Field List.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ad8fa-104">Подробности</span><span class="sxs-lookup"><span data-stu-id="ad8fa-104">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ad8fa-105">Применяется к</span><span class="sxs-lookup"><span data-stu-id="ad8fa-105">Applies to</span></span>|<span data-ttu-id="ad8fa-106">PowerPivot для SharePoint</span><span class="sxs-lookup"><span data-stu-id="ad8fa-106">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="ad8fa-107">Версия продукта</span><span class="sxs-lookup"><span data-stu-id="ad8fa-107">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="ad8fa-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad8fa-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="ad8fa-109">Причина</span><span class="sxs-lookup"><span data-stu-id="ad8fa-109">Cause</span></span>|<span data-ttu-id="ad8fa-110">Веб-служба доступа Excel не может обработать объект «Фигура», который используется для управления расположением и форматированием срезов, добавленных в книгу из списка полей PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="ad8fa-110">Excel Web Access cannot render the Shape object used to control positioning and formatting of Slicers added to a workbook from the PowerPivot Field List.</span></span>|  
|<span data-ttu-id="ad8fa-111">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="ad8fa-111">Message Text</span></span>|<span data-ttu-id="ad8fa-112">Следующие объекты не поддерживаются службой Excel Services и могут не отображаться совсем или отображаться лишь частично:</span><span class="sxs-lookup"><span data-stu-id="ad8fa-112">The following features are not supported by Excel Services and may not display or may display only partially:</span></span><br /><br /> <span data-ttu-id="ad8fa-113">комментарии, фигуры или другие объекты.</span><span class="sxs-lookup"><span data-stu-id="ad8fa-113">Comments, Shapes, or other objects</span></span><br /><br /> <span data-ttu-id="ad8fa-114">Некоторые функции, например запросы внешних данных, отображают данные из кэша, которые можно обновить только в Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="ad8fa-114">Some features, such as external data queries, display cached data which can only be refreshed in Microsoft Excel.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ad8fa-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ad8fa-115">Explanation</span></span>  
 <span data-ttu-id="ad8fa-116">Excel Веб-доступ выводит эту ошибку при открытии книги PowerPivot в браузере и нажатии кнопки **сведения** для сообщения **неподдерживаемые функции. Эта книга может отображаться ненужным образом**.</span><span class="sxs-lookup"><span data-stu-id="ad8fa-116">Excel Web Access shows this error when you open a PowerPivot workbook in a browser and you click the **Details** button for the message, **Unsupported Features This workbook may not display as intended**.</span></span>  
  
 <span data-ttu-id="ad8fa-117">Эта ошибка возникает потому, что книга PowerPivot содержит срезы, параметры которых управляются скрытым объектом «Фигура» в Excel.</span><span class="sxs-lookup"><span data-stu-id="ad8fa-117">This error occurs because the PowerPivot workbook contains Slicers whose layout is controlled by a hidden Shape object in Excel.</span></span> <span data-ttu-id="ad8fa-118">Объект «Фигура» отвечает за форматирование и расположение срезов по горизонтали и вертикали.</span><span class="sxs-lookup"><span data-stu-id="ad8fa-118">The Shape object controls the formatting and positioning of the Slicers in horizontal and vertical placements.</span></span>  
  
 <span data-ttu-id="ad8fa-119">Служба Excel Services не может обработать объект «Фигура» для отображения, но, поскольку объект является скрытым, тот факт, что он не отображается, не является проблемой.</span><span class="sxs-lookup"><span data-stu-id="ad8fa-119">Excel Services cannot render a Shape object, but because the object is hidden, the fact that it does not render is not an issue.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ad8fa-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="ad8fa-120">User Action</span></span>  
 <span data-ttu-id="ad8fa-121">Эту ошибку можно пропускать.</span><span class="sxs-lookup"><span data-stu-id="ad8fa-121">This error can be ignored.</span></span> <span data-ttu-id="ad8fa-122">Нажмите кнопку **ОК** , чтобы закрыть сообщение об ошибке и продолжить использовать книгу и срезы без проблем.</span><span class="sxs-lookup"><span data-stu-id="ad8fa-122">Click **OK** to close the error message and proceed to use the workbook and Slicers with no problem.</span></span>  
  
  
