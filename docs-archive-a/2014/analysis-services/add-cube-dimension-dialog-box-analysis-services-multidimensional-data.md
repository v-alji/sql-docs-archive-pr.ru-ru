---
title: Диалоговое окно «Добавление измерения куба» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.addcubedimensiondialog.f1
helpviewer_keywords:
- Add Cube Dimension dialog box
ms.assetid: 625a3b1f-183b-445f-9bb7-96945c324767
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0de75c02c39b0690184f35f2b0b6a07d7ed9a4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656057"
---
# <a name="add-cube-dimension-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="7858c-102">Диалоговое окно «Добавление измерения куба» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="7858c-102">Add Cube Dimension Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="7858c-103">Используйте диалоговое окно **Добавление измерения куба** среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для добавления к кубу ссылки на измерение базы данных.</span><span class="sxs-lookup"><span data-stu-id="7858c-103">Use the **Add Cube Dimension** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to add a reference to a database dimension to a cube.</span></span> <span data-ttu-id="7858c-104">Чтобы открыть диалоговое окно **Добавление измерения куба** , выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="7858c-104">You can display the **Add Cube Dimension** dialog box by doing one of the following:</span></span>  
  
-   <span data-ttu-id="7858c-105">Нажмите **Добавить измерение куба** на **панели инструментов** вкладок **Структура куба** или **Использование измерений** в конструкторе кубов.</span><span class="sxs-lookup"><span data-stu-id="7858c-105">Click **Add Cube Dimension** in the **Toolbar** pane on the **Cube Structure** or **Dimension Usage** tab in Cube Designer.</span></span>  
  
-   <span data-ttu-id="7858c-106">Щелкните правой кнопкой мыши панель **Измерения** на вкладке **Структура куба** в конструкторе кубов и выберите в контекстном меню **Добавить измерение куба** .</span><span class="sxs-lookup"><span data-stu-id="7858c-106">Right-click the **Dimensions** pane on the **Cube Structure** tab in Cube Designer and select **Add Cube Dimension** from the context menu.</span></span>  
  
-   <span data-ttu-id="7858c-107">Щелкните правой кнопкой мыши панель **Сетка** на вкладке **Использование измерений** в конструкторе кубов и выберите в контекстном меню **Добавить измерение куба** .</span><span class="sxs-lookup"><span data-stu-id="7858c-107">Right-click the **Grid** pane on the **Dimension Usage** tab in Cube Designer and select **Add Cube Dimension** from the context menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7858c-108">У каждого измерения куба может быть только одна взаимосвязь с группой мер.</span><span class="sxs-lookup"><span data-stu-id="7858c-108">Each cube dimension can have only one relationship to a measure group.</span></span> <span data-ttu-id="7858c-109">Тем не менее если измерение базы данных, на которой основано измерение куба, связано с группами мер через несколько взаимосвязей в представлении источника данных, то можно создать несколько измерений кубов и добавить их в куб.</span><span class="sxs-lookup"><span data-stu-id="7858c-109">However, you can create more than one cube dimension and add it to the cube, if the database dimension on which the cube dimension is based is related to measure groups through more than one relationship in the data source view.</span></span> <span data-ttu-id="7858c-110">Такие измерения называются ролевыми и, как правило, встречаются в измерениях времени.</span><span class="sxs-lookup"><span data-stu-id="7858c-110">Such dimensions are referred to as role-playing dimensions and commonly occur with time dimensions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7858c-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="7858c-111">Options</span></span>  
 <span data-ttu-id="7858c-112">**Выберите измерение**</span><span class="sxs-lookup"><span data-stu-id="7858c-112">**Select dimension**</span></span>  
 <span data-ttu-id="7858c-113">Выберите существующее измерение базы данных для добавления основанного на нем измерения куба в выбранный куб.</span><span class="sxs-lookup"><span data-stu-id="7858c-113">Select an existing database dimension to add a cube dimension based on it to the selected cube.</span></span> <span data-ttu-id="7858c-114">На основе одного и того же измерения базы данных может быть определено несколько измерений кубов.</span><span class="sxs-lookup"><span data-stu-id="7858c-114">Multiple cube dimensions can be defined from the same database dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7858c-115">Если в куб добавляется несколько измерений куба на основе одного и того же измерения базы данных, то дополнительные измерения куба называются ролевыми измерениями.</span><span class="sxs-lookup"><span data-stu-id="7858c-115">If more than one cube dimension based on the same database dimension is added to a cube, the additional cube dimensions are called role-playing dimensions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7858c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7858c-116">See Also</span></span>  
 [<span data-ttu-id="7858c-117">Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7858c-117">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
