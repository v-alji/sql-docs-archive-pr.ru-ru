---
title: Изменить запрос источника OData во время выполнения | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: bcbba7f4-6e5d-46e6-a73a-3f17d3ff376a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b3dbc4d27f2d11537a9d66980ef6ca59b80811b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750043"
---
# <a name="modify-odata-source-query-at-runtime"></a><span data-ttu-id="278aa-102">Изменение запроса источника OData во время выполнения</span><span class="sxs-lookup"><span data-stu-id="278aa-102">Modify OData Source Query at Runtime</span></span>
  <span data-ttu-id="278aa-103">Можно изменить запрос источника OData во время выполнения, добавив выражение в свойство **[OData Source].[Query]** задачи потока данных.</span><span class="sxs-lookup"><span data-stu-id="278aa-103">You can modify the OData Source query at runtime by adding an expression to the **[OData Source].[Query]** property of the Data Flow task.</span></span>  
  
 <span data-ttu-id="278aa-104">Обратите внимание, что столбцы должны оставаться такими же, что и во время разработки. В противном случае произойдет ошибка при выполнении пакета.</span><span class="sxs-lookup"><span data-stu-id="278aa-104">Note that the columns must remain the same as what was used at design time; otherwise you will get an error when the package is executed.</span></span> <span data-ttu-id="278aa-105">Обязательно укажите те же столбцы (в том же порядке) при использовании параметра $select запроса.</span><span class="sxs-lookup"><span data-stu-id="278aa-105">Be sure to specify the same columns (in the same order) when using the $select query option.</span></span> <span data-ttu-id="278aa-106">Более безопасная альтернатива применению параметра $select состоит в том, чтобы отменить выбор ненужных столбцов непосредственно в пользовательском интерфейсе исходного компонента.</span><span class="sxs-lookup"><span data-stu-id="278aa-106">A safer alternative to using the $select option is to deselect the columns you don't want directly from the Source Component UI.</span></span>  
  
 <span data-ttu-id="278aa-107">Существует несколько способов для динамической установки значения запроса во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="278aa-107">There are a few different ways of dynamically setting the query value at runtime.</span></span> <span data-ttu-id="278aa-108">Ниже перечислены некоторые из наиболее распространенных методов.</span><span class="sxs-lookup"><span data-stu-id="278aa-108">Below are some of the more common methods.</span></span>  
  
## <a name="exposing-the-query-as-a-parameter"></a><span data-ttu-id="278aa-109">Предоставление запроса в качестве параметра</span><span class="sxs-lookup"><span data-stu-id="278aa-109">Exposing the Query as a Parameter</span></span>  
 <span data-ttu-id="278aa-110">Следующая процедура позволяет предоставить пакету доступ к запросу, используемому компонентом источника OData, в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="278aa-110">The following procedure has steps to expose query used by an OData Source component as a parameter to the package.</span></span>  
  
1.  <span data-ttu-id="278aa-111">Щелкните правой кнопкой мыши **Задача потока данных** и выберите пункт **Параметризация…** .</span><span class="sxs-lookup"><span data-stu-id="278aa-111">Right click on the **Data Flow task** and select the **Parameterize...** option.</span></span>  
  
2.  <span data-ttu-id="278aa-112">В диалоговом окне **Параметризация** выберите **[\<Name of the OData Source Component>].[Запрос]** для **Свойство**.</span><span class="sxs-lookup"><span data-stu-id="278aa-112">In the **Parameterize** dialog, select **[\<Name of the OData Source Component>].[Query]** for **Property**.</span></span>  
  
3.  <span data-ttu-id="278aa-113">Выберите, следует ли значение **создать новый параметр** или **использовать существующий параметр**.</span><span class="sxs-lookup"><span data-stu-id="278aa-113">Choose whether to **create new parameter** or **use an existing parameter**.</span></span>  
  
4.  <span data-ttu-id="278aa-114">Если установлен флажок **Создать новый параметр**, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="278aa-114">If you select **Create new parameter**, do the following:</span></span>  
  
    1.  <span data-ttu-id="278aa-115">Введите **имя** и **описание** для параметра.</span><span class="sxs-lookup"><span data-stu-id="278aa-115">Enter **name** and **description** for the parameter.</span></span>  
  
    2.  <span data-ttu-id="278aa-116">Укажите **значение** по умолчанию для данного параметра.</span><span class="sxs-lookup"><span data-stu-id="278aa-116">Specify default **value** for the parameter.</span></span>  
  
    3.  <span data-ttu-id="278aa-117">Укажите **область** (**пакет** или **проект**) для параметра.</span><span class="sxs-lookup"><span data-stu-id="278aa-117">Specify the **scope** (**package** or **project**) for the parameter.</span></span>  
  
    4.  <span data-ttu-id="278aa-118">Укажите, является ли параметр **обязательным** или нет.</span><span class="sxs-lookup"><span data-stu-id="278aa-118">Specify whether the parameter is **required** or not</span></span>  
  
5.  <span data-ttu-id="278aa-119">Чтобы закрыть диалоговое окно, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="278aa-119">Click **OK** to close the dialog box.</span></span>  
  
## <a name="using-an-expression"></a><span data-ttu-id="278aa-120">Использование выражения</span><span class="sxs-lookup"><span data-stu-id="278aa-120">Using an Expression</span></span>  
 <span data-ttu-id="278aa-121">Этот метод удобен для динамического построения строки запроса во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="278aa-121">This method is useful when you want to dynamically construct query string at runtime.</span></span> <span data-ttu-id="278aa-122">В этом примере переменная MaxRows будет установлена с помощью других средств (скрипт, параметр и т. д.).</span><span class="sxs-lookup"><span data-stu-id="278aa-122">In this example, MaxRows variable will be set through other means (script, parameter, etc).</span></span>  
  
1.  <span data-ttu-id="278aa-123">Выберите **задачу потока данных** , содержащую ваш **источник OData**.</span><span class="sxs-lookup"><span data-stu-id="278aa-123">Select the **Data Flow Task** which contains your **OData Source**.</span></span>  
  
2.  <span data-ttu-id="278aa-124">В окне **Свойства** выделите свойство **Выражения** .</span><span class="sxs-lookup"><span data-stu-id="278aa-124">In the **Properties** window, highlight the **Expressions** property.</span></span>  
  
3.  <span data-ttu-id="278aa-125">Нажмите кнопку... (многоточие), чтобы открыть **Редактор выражений свойств**.</span><span class="sxs-lookup"><span data-stu-id="278aa-125">Click the ... (ellipses) button to bring up the **Property Expressions Editor**.</span></span>  
  
4.  <span data-ttu-id="278aa-126">Выберите свойство **[OData Source].[Query]** .</span><span class="sxs-lookup"><span data-stu-id="278aa-126">Select the **[OData Source].[Query]** property.</span></span>  
  
5.  <span data-ttu-id="278aa-127">Нажмите кнопку... (многоточие) для **выражения**.</span><span class="sxs-lookup"><span data-stu-id="278aa-127">Click the ... (ellipses) button for **Expression**.</span></span>  
  
6.  <span data-ttu-id="278aa-128">Введите **выражение**.</span><span class="sxs-lookup"><span data-stu-id="278aa-128">Enter the **expression**.</span></span>  
  
7.  <span data-ttu-id="278aa-129">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="278aa-129">Click **OK**.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="278aa-130">Обратите внимание, что при использовании такого подхода необходимо убедиться, чтобы значения были правильно закодированы в URL-адресе.</span><span class="sxs-lookup"><span data-stu-id="278aa-130">Note that when using this approach you need to ensure that the values set are properly URL encoded.</span></span> <span data-ttu-id="278aa-131">При получении значений из входных данных пользователя (например, установке отдельных значений параметра запроса из параметра) необходимо убедиться, что значения проверяются, чтобы избежать потенциальных атак путем инжекции кода SQL.</span><span class="sxs-lookup"><span data-stu-id="278aa-131">When receiving values from user input (for example, setting individual query option values from a parameter), you must ensure that the values are validated to avoid potential SQL injection-type attacks.</span></span>  
  
  
