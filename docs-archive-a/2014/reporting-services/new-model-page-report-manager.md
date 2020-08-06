---
title: Страница «Создание модели» (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 27d5bf66-b0e7-489e-a830-ffe2ec8e5350
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ed591108585b494ebb4498c1a0ab3e782693a45b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666456"
---
# <a name="new-model-page-report-manager"></a><span data-ttu-id="a88a6-102">Страница «Создание модели» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="a88a6-102">New Model Page (Report Manager)</span></span>
  <span data-ttu-id="a88a6-103">Эта страница позволяет создать модель отчетов по умолчанию на основе общего источника данных.</span><span class="sxs-lookup"><span data-stu-id="a88a6-103">Use this page to generate a default report model from a shared data source.</span></span> <span data-ttu-id="a88a6-104">Модели отчетов можно создавать только из многомерных источников данных службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , реляционных источников данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] и реляционных источников данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="a88a6-104">You can only generate report models from [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] multidimensional data sources, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] relational data sources, and Oracle relational data sources.</span></span>  
  
 <span data-ttu-id="a88a6-105">Модели, создаваемые в диспетчере отчетов, основаны на схеме общего источника данных.</span><span class="sxs-lookup"><span data-stu-id="a88a6-105">Models that you generate in Report Manager are based on the schema of the shared data source.</span></span> <span data-ttu-id="a88a6-106">Для всех таблиц и столбцов источника данных создаются сущности, папки и поля.</span><span class="sxs-lookup"><span data-stu-id="a88a6-106">Entities, folders, and fields are created for all tables and columns in the data source.</span></span> <span data-ttu-id="a88a6-107">Исключать элементы нельзя, и невозможно задавать параметры, определяющие способ создания модели.</span><span class="sxs-lookup"><span data-stu-id="a88a6-107">You cannot exclude items, nor can you set options that determine how the model is generated.</span></span> <span data-ttu-id="a88a6-108">Если модель необходимо настроить или уточнить, вместо этого следует использовать конструктор моделей.</span><span class="sxs-lookup"><span data-stu-id="a88a6-108">If you want to customize or refine a model, you must use Model Designer instead.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="a88a6-109">Навигация</span><span class="sxs-lookup"><span data-stu-id="a88a6-109">Navigation</span></span>  
 <span data-ttu-id="a88a6-110">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="a88a6-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-model-page"></a><span data-ttu-id="a88a6-111">Открытие страницы «Создать модель»</span><span class="sxs-lookup"><span data-stu-id="a88a6-111">To open the New Model page</span></span>  
  
1.  <span data-ttu-id="a88a6-112">Откройте диспетчер отчетов и найдите общий источник данных, с помощью которого необходимо создать модель.</span><span class="sxs-lookup"><span data-stu-id="a88a6-112">Open Report Manager, and locate the shared data source from which you want to generate a model.</span></span>  
  
2.  <span data-ttu-id="a88a6-113">Подведите курсор к источнику данных и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="a88a6-113">Hover over the data source, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="a88a6-114">В раскрывающемся меню выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="a88a6-114">In the drop-down menu, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="a88a6-115">Нажмите кнопку **Создать модель отчета** , чтобы открыть страницу «Создать модель».</span><span class="sxs-lookup"><span data-stu-id="a88a6-115">Click **Generate Report Model** to open the New Model page.</span></span>  
  
    -   <span data-ttu-id="a88a6-116">Выберите **Управление** , чтобы открыть страницу свойств отчета «Общие».</span><span class="sxs-lookup"><span data-stu-id="a88a6-116">Click **Manage** to open the General properties page for the report.</span></span> <span data-ttu-id="a88a6-117">Затем нажмите кнопку **Создать модель отчета** , чтобы открыть страницу «Создать модель».</span><span class="sxs-lookup"><span data-stu-id="a88a6-117">Then click **Generate Model** to open the New Model page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a88a6-118">Параметры</span><span class="sxs-lookup"><span data-stu-id="a88a6-118">Options</span></span>  
 <span data-ttu-id="a88a6-119">**имя**;</span><span class="sxs-lookup"><span data-stu-id="a88a6-119">**Name**</span></span>  
 <span data-ttu-id="a88a6-120">Указывает имя модели.</span><span class="sxs-lookup"><span data-stu-id="a88a6-120">Specifies the name of the model.</span></span> <span data-ttu-id="a88a6-121">Имя должно содержать хотя бы одну букву или цифру.</span><span class="sxs-lookup"><span data-stu-id="a88a6-121">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="a88a6-122">В него могут также входить пробелы и другие символы.</span><span class="sxs-lookup"><span data-stu-id="a88a6-122">It can also include spaces and some symbols.</span></span> <span data-ttu-id="a88a6-123">При задании имени нельзя использовать следующие символы:</span><span class="sxs-lookup"><span data-stu-id="a88a6-123">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="a88a6-124">; ?</span><span class="sxs-lookup"><span data-stu-id="a88a6-124">; ?</span></span> <span data-ttu-id="a88a6-125">: \@ & = +, $/\* \< > | " /</span><span class="sxs-lookup"><span data-stu-id="a88a6-125">: \@ & = + , $ / \* \< > | " /</span></span>  
  
 <span data-ttu-id="a88a6-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a88a6-126">**Description**</span></span>  
 <span data-ttu-id="a88a6-127">Показывает описание модели.</span><span class="sxs-lookup"><span data-stu-id="a88a6-127">Shows a description of the model.</span></span> <span data-ttu-id="a88a6-128">Пользователям, просматривающим этот элемент с помощью диспетчера отчетов, это описание предоставляется при просмотре иерархии папок.</span><span class="sxs-lookup"><span data-stu-id="a88a6-128">Users who view this item through Report Manager see this description when browsing the folder hierarchy.</span></span>  
  
 <span data-ttu-id="a88a6-129">**Изменение местоположения**</span><span class="sxs-lookup"><span data-stu-id="a88a6-129">**Change Location**</span></span>  
 <span data-ttu-id="a88a6-130">Показывает папку, в которой будет размещена новая модель.</span><span class="sxs-lookup"><span data-stu-id="a88a6-130">Shows the folder location for the new model.</span></span> <span data-ttu-id="a88a6-131">Чтобы выбрать другое местоположение, нажмите кнопку **Изменить местоположение** .</span><span class="sxs-lookup"><span data-stu-id="a88a6-131">You can click the **Change Location** button to select a different location.</span></span>  
  
  
