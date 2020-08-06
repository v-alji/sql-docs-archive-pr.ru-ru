---
title: Импорт (службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.importing.f1
ms.assetid: f1681be4-c543-4e77-875d-b13eeb75cf77
author: minewiskan
ms.author: owend
ms.openlocfilehash: 95ea60385014e5ca8b998b986a66c384f7151081
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667938"
---
# <a name="importing-ssas"></a><span data-ttu-id="995a7-102">Импорт (SSAS)</span><span class="sxs-lookup"><span data-stu-id="995a7-102">Importing (SSAS)</span></span>
  <span data-ttu-id="995a7-103">На этой странице **мастера импорта таблиц** можно просмотреть ход выполнения операции импорта.</span><span class="sxs-lookup"><span data-stu-id="995a7-103">This page of the **Table Import Wizard** enables you to view the progress of the import operation.</span></span> <span data-ttu-id="995a7-104">Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="995a7-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="995a7-105">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="995a7-105">UI element list</span></span>  
 <span data-ttu-id="995a7-106">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="995a7-106">**Details**</span></span>  
 <span data-ttu-id="995a7-107">Отображает следующие сведения по каждой операции импорта данных.</span><span class="sxs-lookup"><span data-stu-id="995a7-107">Displays the following information for each data import operation.</span></span>  
  
|<span data-ttu-id="995a7-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="995a7-108">Column</span></span>|<span data-ttu-id="995a7-109">Описание</span><span class="sxs-lookup"><span data-stu-id="995a7-109">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="995a7-110">**Рабочий элемент**</span><span class="sxs-lookup"><span data-stu-id="995a7-110">**Work Item**</span></span>|<span data-ttu-id="995a7-111">Отображает имя импортируемой таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="995a7-111">Displays the name of the table or view that is being imported.</span></span>|  
|<span data-ttu-id="995a7-112">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="995a7-112">**Status**</span></span>|<span data-ttu-id="995a7-113">Указывает, были ли таблица или представление успешно импортированы, и показывает количество импортированных строк.</span><span class="sxs-lookup"><span data-stu-id="995a7-113">Indicates whether the table or view was successfully imported and the number of rows that were imported.</span></span>|  
|<span data-ttu-id="995a7-114">**Message**</span><span class="sxs-lookup"><span data-stu-id="995a7-114">**Message**</span></span>|<span data-ttu-id="995a7-115">Если импорт таблицы или представления завершился ошибкой, отображает ссылку для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="995a7-115">If the table or view import failed, displays a link to more information.</span></span> <span data-ttu-id="995a7-116">Эта информация отображается в окне «Сведения».</span><span class="sxs-lookup"><span data-stu-id="995a7-116">This information is displayed in the Details window.</span></span><br /><br /> <span data-ttu-id="995a7-117">Чтобы повторить попытку импорта таблицы или представления, следует выйти из мастера и запустить его снова.</span><span class="sxs-lookup"><span data-stu-id="995a7-117">To try again to import the table or view, exit the wizard and run it again.</span></span>|  
  
 <span data-ttu-id="995a7-118">**Остановка импорта**</span><span class="sxs-lookup"><span data-stu-id="995a7-118">**Stop Import**</span></span>  
 <span data-ttu-id="995a7-119">Нажмите, чтобы прервать операцию импорта до ее завершения.</span><span class="sxs-lookup"><span data-stu-id="995a7-119">Click to stop the import operation before it is finished.</span></span> <span data-ttu-id="995a7-120">Уже импортированные таблицы и представления будут отображаться в конструкторе [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="995a7-120">Tables and views that have already been imported will be displayed in the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] designer.</span></span> <span data-ttu-id="995a7-121">Таблицы и представления, не прошедшие импорт, не будут импортированы.</span><span class="sxs-lookup"><span data-stu-id="995a7-121">Tables and views that have not been imported yet will not be imported.</span></span>  
  
  
