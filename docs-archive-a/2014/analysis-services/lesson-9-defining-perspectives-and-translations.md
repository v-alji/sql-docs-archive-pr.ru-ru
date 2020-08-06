---
title: Занятие 9. определение перспектив и переводов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a040fa65-d5d6-4156-9f2c-307a4d18e1a6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6a36449eb3156d9ff52d6cc7085f9e0cb929b51e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732170"
---
# <a name="lesson-9-defining-perspectives-and-translations"></a><span data-ttu-id="8d26d-102">Урок 9. Определение перспектив и преобразований</span><span class="sxs-lookup"><span data-stu-id="8d26d-102">Lesson 9: Defining Perspectives and Translations</span></span>
  <span data-ttu-id="8d26d-103">На этом занятии предстоит изучить, как определять перспективы и переводы.</span><span class="sxs-lookup"><span data-stu-id="8d26d-103">In this lesson, you learn to define perspectives and translations.</span></span> <span data-ttu-id="8d26d-104">Определение перспектив позволяет снизить сложность куба, а определение переводов позволяет пользователям просматривать метаданные куба на разных языках.</span><span class="sxs-lookup"><span data-stu-id="8d26d-104">You can define perspectives to reduce the apparent complexity of a cube, and define translations that let users view the cube metadata in the language of their choice.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8d26d-105">Завершенные проекты для всех занятий в этом учебнике доступны через Интернет.</span><span class="sxs-lookup"><span data-stu-id="8d26d-105">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="8d26d-106">Можно перейти вперед к любому занятию, используя в качестве отправной точки завершенный проект из предыдущего урока.</span><span class="sxs-lookup"><span data-stu-id="8d26d-106">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="8d26d-107">[Щелкните здесь](https://go.microsoft.com/fwlink/?LinkID=221866) для загрузки образцов проектов, прилагаемых к этому учебнику.</span><span class="sxs-lookup"><span data-stu-id="8d26d-107">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="8d26d-108">Это занятие содержит следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="8d26d-108">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="8d26d-109">Определение и поиск перспектив</span><span class="sxs-lookup"><span data-stu-id="8d26d-109">Defining and Browsing Perspectives</span></span>](multidimensional-models-olap-logical-cube-objects/perspectives.md)  
 <span data-ttu-id="8d26d-110">В данном задании предстоит определить и просмотреть перспективы с целью упрощения представления куба при его использовании разными пользователями для решения различных задач.</span><span class="sxs-lookup"><span data-stu-id="8d26d-110">In this task, you define and browse perspectives to simplify the view of the cube for specific users or uses.</span></span>  
  
 [<span data-ttu-id="8d26d-111">Определение и просмотр переводов</span><span class="sxs-lookup"><span data-stu-id="8d26d-111">Defining and Browsing Translations</span></span>](lesson-9-2-defining-and-browsing-translations.md)  
 <span data-ttu-id="8d26d-112">В данном задании предстоит определить и просмотреть переводы конкретных метаданных на указанные языки.</span><span class="sxs-lookup"><span data-stu-id="8d26d-112">In this task, you define and browse translations of specific metadata to certain languages.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="8d26d-113">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="8d26d-113">Next Lesson</span></span>  
 [<span data-ttu-id="8d26d-114">Урок 10. Определение административных ролей</span><span class="sxs-lookup"><span data-stu-id="8d26d-114">Lesson 10: Defining Administrative Roles</span></span>](lesson-10-defining-administrative-roles.md)  
  
## <a name="see-also"></a><span data-ttu-id="8d26d-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="8d26d-115">See Also</span></span>  
 <span data-ttu-id="8d26d-116">[Analysis Services сценарий учебника](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="8d26d-116">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="8d26d-117">[&#40;учебника по Adventure Works в многомерном моделировании&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="8d26d-117">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 <span data-ttu-id="8d26d-118">[Перспективы](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-cube-objects/perspectives) </span><span class="sxs-lookup"><span data-stu-id="8d26d-118">[Perspectives](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-cube-objects/perspectives) </span></span>  
 <span data-ttu-id="8d26d-119">[Перспективы в многомерных моделях](multidimensional-models/perspectives-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="8d26d-119">[Perspectives in Multidimensional Models](multidimensional-models/perspectives-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="8d26d-120">[Переводы измерений](multidimensional-models-olap-logical-dimension-objects/dimension-translations.md) </span><span class="sxs-lookup"><span data-stu-id="8d26d-120">[Dimension Translations](multidimensional-models-olap-logical-dimension-objects/dimension-translations.md) </span></span>  
 <span data-ttu-id="8d26d-121">[Переводы куба](multidimensional-models-olap-logical-cube-objects/cube-translations.md) </span><span class="sxs-lookup"><span data-stu-id="8d26d-121">[Cube Translations](multidimensional-models-olap-logical-cube-objects/cube-translations.md) </span></span>  
 [<span data-ttu-id="8d26d-122">Переводы &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8d26d-122">Translations &#40;Analysis Services&#41;</span></span>](translations-analysis-services.md)  
  
  
