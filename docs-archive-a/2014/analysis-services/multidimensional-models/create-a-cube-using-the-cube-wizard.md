---
title: Создание куба с помощью мастера кубов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cubes [Analysis Services], creating
ms.assetid: d46d659c-3a4e-4364-94ac-f5eb6ba0ec25
author: minewiskan
ms.author: owend
ms.openlocfilehash: 441c296c0fd71b2a9c2b8332743da6224839a471
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737097"
---
# <a name="create-a-cube-using-the-cube-wizard"></a><span data-ttu-id="a8139-102">Создание куба с помощью мастера кубов</span><span class="sxs-lookup"><span data-stu-id="a8139-102">Create a Cube Using the Cube Wizard</span></span>
  <span data-ttu-id="a8139-103">Новый куб можно создать с помощью мастера кубов в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8139-103">You can create a new cube by using the Cube Wizard in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="to-create-a-new-cube"></a><span data-ttu-id="a8139-104">Создание нового куба</span><span class="sxs-lookup"><span data-stu-id="a8139-104">To create a new cube</span></span>  
  
1.  <span data-ttu-id="a8139-105">В **Обозреватель решений**щелкните правой кнопкой мыши элемент **Кубы**и выберите команду **создать куб**.</span><span class="sxs-lookup"><span data-stu-id="a8139-105">In **Solution Explorer**, right-click **Cubes**, and then click **New Cube**.</span></span>  
  
2.  <span data-ttu-id="a8139-106">На странице мастера кубов **Выбор метода создания** выберите параметр **Использовать существующие таблицы**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a8139-106">On the **Select Creation Method** page of the Cube Wizard, select **Use existing tables**, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a8139-107">Иногда может потребоваться создание куба без использования существующих таблиц.</span><span class="sxs-lookup"><span data-stu-id="a8139-107">You might occasionally have to create a cube without using existing tables.</span></span> <span data-ttu-id="a8139-108">Чтобы создать пустой куб, выберите команду **Создать пустой куб**.</span><span class="sxs-lookup"><span data-stu-id="a8139-108">To create an empty cube, select **Create an empty cube**.</span></span> <span data-ttu-id="a8139-109">Чтобы сформировать таблицы, выберите команду **Создать таблицы в источнике данных**.</span><span class="sxs-lookup"><span data-stu-id="a8139-109">To generate tables, select **Generate tables in the data source**.</span></span>  
  
3.  <span data-ttu-id="a8139-110">На странице **Выбор таблиц групп мер** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a8139-110">On the **Select Measure Group Tables** page, do the following procedures:</span></span>  
  
    1.  <span data-ttu-id="a8139-111">В списке **Представление источника данных** выберите представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="a8139-111">In the **Data source view** list, select a data source view.</span></span>  
  
    2.  <span data-ttu-id="a8139-112">Из списка **Таблицы группы мер** выберите таблицы, используемые для создания групп мер.</span><span class="sxs-lookup"><span data-stu-id="a8139-112">In the **Measure group tables** list, select the tables that will be used to create measure groups.</span></span>  
  
    3.  <span data-ttu-id="a8139-113">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a8139-113">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="a8139-114">На странице **Выбор мер** выберите меры, которые нужно включить в куб, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a8139-114">On the **Select Measures** page, select the measures that you want to include in the cube, and then click **Next**.</span></span>  
  
     <span data-ttu-id="a8139-115">При необходимости имена мер и групп мер можно изменить.</span><span class="sxs-lookup"><span data-stu-id="a8139-115">Optionally, you can change the names of the measures and measure groups.</span></span>  
  
5.  <span data-ttu-id="a8139-116">На странице **Выбор существующих измерений** выберите существующие измерения, которые нужно включить в куб, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a8139-116">On the **Select Existing Dimensions** page, select the existing dimensions to include in the cube, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a8139-117"> Страница **Выбор существующих измерений** отображается, если в базе данных уже имеются измерения для любой выбранной группы мер.</span><span class="sxs-lookup"><span data-stu-id="a8139-117">The **Select Existing Dimensions** page appears if dimensions already exist in the database for any of the selected measure groups.</span></span>  
  
6.  <span data-ttu-id="a8139-118">На странице **Выбор новых измерений** выберите новые измерения, которые требуется создать, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a8139-118">On the **Select New Dimensions** page, select the new dimensions to create, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a8139-119"> Страница **Выбор новых измерений** отображается, если какие-либо таблицы могут быть хорошими кандидатами для использования в качестве таблиц измерений и не используются существующими измерениями.</span><span class="sxs-lookup"><span data-stu-id="a8139-119">The **Select New Dimensions** page appears if any tables would be good candidates for dimension tables, and the tables have not already been used by existing dimensions.</span></span>  
  
7.  <span data-ttu-id="a8139-120">На странице **Выбор отсутствующих ключей измерения** выберите для измерения ключ и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a8139-120">On the **Select Missing Dimension Keys** page, select a key for the dimension, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a8139-121"> Страница **Выбор отсутствующих ключей измерения** отображается, если для какой-либо из указанных таблиц измерения не был задан ключ.</span><span class="sxs-lookup"><span data-stu-id="a8139-121">The **Select Missing Dimension Keys** page appears if any of the dimension tables that you specified do not have a key defined.</span></span>  
  
8.  <span data-ttu-id="a8139-122">На странице **Завершение работы мастера** введите имя нового куба и просмотрите структуру этого куба.</span><span class="sxs-lookup"><span data-stu-id="a8139-122">On the **Completing the Wizard** page, enter a name for the new cube and review the cube structure.</span></span> <span data-ttu-id="a8139-123">Если надо что-либо изменить, нажмите кнопку **Назад**, если нет, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="a8139-123">If you want to make changes, click **Back**; otherwise, click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a8139-124">После завершения работы мастера кубов можно воспользоваться конструктором кубов, чтобы настроить куб.</span><span class="sxs-lookup"><span data-stu-id="a8139-124">You can use Cube Designer after you complete the Cube Wizard to configure the cube.</span></span> <span data-ttu-id="a8139-125">Кроме того, добавить, удалить и настроить атрибуты и иерархии в созданном измерении можно с помощью конструктора изменений.</span><span class="sxs-lookup"><span data-stu-id="a8139-125">You can also use Dimension Designer to add, remove, and configure attributes and hierarchies in the dimensions that you created.</span></span>  
  
  
