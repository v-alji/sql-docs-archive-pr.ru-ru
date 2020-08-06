---
title: Выбор объектов (обозреватель объектов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.common.selectobjects.f1
ms.assetid: 692477fe-dd7c-403d-acd2-bb108b6077f1
author: stevestein
ms.author: sstein
ms.openlocfilehash: ceec604d9fe07b339af11ed69226d41a7f616678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727858"
---
# <a name="select-objects-object-explorer"></a><span data-ttu-id="f896f-102">Выбор объектов (обозреватель объектов)</span><span class="sxs-lookup"><span data-stu-id="f896f-102">Select Objects (Object Explorer)</span></span>
  <span data-ttu-id="f896f-103">Используйте диалоговое окно **Выбор объектов**, чтобы добавить объект к списку в другом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="f896f-103">Use the **Select Objects** dialog box to add an object to a list in another dialog box.</span></span> <span data-ttu-id="f896f-104">Заголовок диалогового окна и параметры, доступные в нем, зависят от того, каким способом окно было открыто.</span><span class="sxs-lookup"><span data-stu-id="f896f-104">The dialog box title and the options available in the dialog box depend upon how it was opened.</span></span> <span data-ttu-id="f896f-105">Отображаются только доступные параметры; например доступны только имена входа, если необходимо выбрать владельца для нового объекта.</span><span class="sxs-lookup"><span data-stu-id="f896f-105">Only available options appear; for instance, only logins are available when you are selecting an owner for a new object.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f896f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f896f-106">Options</span></span>  
 <span data-ttu-id="f896f-107">**Выберите типы объектов**</span><span class="sxs-lookup"><span data-stu-id="f896f-107">**Select these object types**</span></span>  
 <span data-ttu-id="f896f-108">Отображает список типов, к которым принадлежат выбираемые объекты.</span><span class="sxs-lookup"><span data-stu-id="f896f-108">Displays a list of the types of which the objects to be selected belong.</span></span> <span data-ttu-id="f896f-109">В число этих типов входят основные и защищаемые типы уровня [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и уровня базы данных.</span><span class="sxs-lookup"><span data-stu-id="f896f-109">The types include [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] level and database level principals and securables.</span></span> <span data-ttu-id="f896f-110">Это окно заполняется значениями, которые были выбраны в диалоговом окне **Выбор типов объектов** , доступном при нажатии кнопки **Тип объектов** .</span><span class="sxs-lookup"><span data-stu-id="f896f-110">This box is populated from the selections made from the **Select Object Types** dialog box, accessed from the **Objects Type** button.</span></span>  
  
 <span data-ttu-id="f896f-111">**Введите имена объектов для выбора**</span><span class="sxs-lookup"><span data-stu-id="f896f-111">**Enter the object names to select**</span></span>  
 <span data-ttu-id="f896f-112">Введите разделенный точками с запятой список имен объектов, которые должны быть выбраны.</span><span class="sxs-lookup"><span data-stu-id="f896f-112">Enter a semicolon-separated list of names of the objects to be selected.</span></span> <span data-ttu-id="f896f-113">Выбираемые объекты должны принадлежать к типу из числа указанных в окне **Выберите типы объектов** .</span><span class="sxs-lookup"><span data-stu-id="f896f-113">Objects to be selected must be of a type listed in the **Select these object types** box.</span></span> <span data-ttu-id="f896f-114">Объекты могут быть выбраны из списка, доступного при нажатии кнопки **Обзор** .</span><span class="sxs-lookup"><span data-stu-id="f896f-114">Objects can be selected from a list accessed by clicking the **Browse** button.</span></span>  
  
 <span data-ttu-id="f896f-115">**Типы объектов**</span><span class="sxs-lookup"><span data-stu-id="f896f-115">**Object Types**</span></span>  
 <span data-ttu-id="f896f-116">Отображает список типов объектов.</span><span class="sxs-lookup"><span data-stu-id="f896f-116">Displays a list of object types.</span></span> <span data-ttu-id="f896f-117">Выберите один или несколько, установив флажки напротив соответствующих типов.</span><span class="sxs-lookup"><span data-stu-id="f896f-117">Select one or more by selecting the check box corresponding to the type.</span></span>  
  
 <span data-ttu-id="f896f-118">**Проверить имена**</span><span class="sxs-lookup"><span data-stu-id="f896f-118">**Check Names**</span></span>  
 <span data-ttu-id="f896f-119">Подтверждает правильность имен объектов в окне **Введите имена объектов для выбора** .</span><span class="sxs-lookup"><span data-stu-id="f896f-119">Validates the object names in the **Enter the object names to select** box.</span></span> <span data-ttu-id="f896f-120">Если в списке содержится недействительное имя объекта, отображается диалоговое окно **Имя не найдено** .</span><span class="sxs-lookup"><span data-stu-id="f896f-120">If an object name that is not valid is listed, the **Name not Found** dialog box is presented.</span></span> <span data-ttu-id="f896f-121">При помощи этого диалогового окна имя может быть исправлено или удалено из списка выбираемых объектов.</span><span class="sxs-lookup"><span data-stu-id="f896f-121">With this dialog box, the name can be corrected or removed from the list of objects to select.</span></span>  
  
 <span data-ttu-id="f896f-122">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="f896f-122">**Browse**</span></span>  
 <span data-ttu-id="f896f-123">Отображает диалоговое окно **Поиск объектов** .</span><span class="sxs-lookup"><span data-stu-id="f896f-123">Presents the **Browse for Objects** dialog box.</span></span> <span data-ttu-id="f896f-124">Оно содержит список объектов, принадлежащих к типам, перечисленным в окне **Выберите типы объектов** .</span><span class="sxs-lookup"><span data-stu-id="f896f-124">This contains a list of objects of the types listed in the **Select These Object Types** box.</span></span> <span data-ttu-id="f896f-125">Выберите объекты из этого списка, установив соответствующие флажки.</span><span class="sxs-lookup"><span data-stu-id="f896f-125">Select objects from this list by selecting the corresponding check boxes.</span></span>  
  
  
