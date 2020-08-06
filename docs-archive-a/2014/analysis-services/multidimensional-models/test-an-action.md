---
title: Тестирование действия | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0ec7feb3-a6b2-4be1-8036-c72b9fbc3562
author: minewiskan
ms.author: owend
ms.openlocfilehash: 45ad40fc0836d70c31a9f7ed3f1142f13c61b4f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667910"
---
# <a name="test-an-action"></a><span data-ttu-id="c8a17-102">Проверка действия</span><span class="sxs-lookup"><span data-stu-id="c8a17-102">Test an Action</span></span>
  <span data-ttu-id="c8a17-103">Проверка действия выполняется с использованием представления обозревателя в конструкторе кубов.</span><span class="sxs-lookup"><span data-stu-id="c8a17-103">You test an action by using the Browser view in Cube Designer.</span></span> <span data-ttu-id="c8a17-104">Доступ к конструктору кубов можно получить из среды [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8a17-104">Cube Designer can be accessed from [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="c8a17-105">После создания действия до его проверки необходимо обработать куб.</span><span class="sxs-lookup"><span data-stu-id="c8a17-105">After you create the action, you must process the cube before the action can be tested.</span></span> <span data-ttu-id="c8a17-106">Дополнительные сведения см. в разделе [Обработка объектов многомерной модели](processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="c8a17-106">For more information, see [Multidimensional Model Object Processing](processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
### <a name="to-test-an-action"></a><span data-ttu-id="c8a17-107">Проверка действия</span><span class="sxs-lookup"><span data-stu-id="c8a17-107">To test an action</span></span>  
  
1.  <span data-ttu-id="c8a17-108">Откройте куб, содержащий действие, которое необходимо проверить, затем в **Представление**выберите **Обозреватель**.</span><span class="sxs-lookup"><span data-stu-id="c8a17-108">Open the cube that contains the action that you want to test, then under **View**, click **Browser**.</span></span>  
  
2.  <span data-ttu-id="c8a17-109">Перетащите целевой объект в окно **Перетащите сюда поля столбцов** или **Перетащите сюда поля строк**.</span><span class="sxs-lookup"><span data-stu-id="c8a17-109">Drag the target object to either **Drop Column Fields Here** or **Drop Row Fields Here**.</span></span>  
  
3.  <span data-ttu-id="c8a17-110">На панели представления щелкните правой кнопкой мыши объект, с которым связано действие (например, ячейку).</span><span class="sxs-lookup"><span data-stu-id="c8a17-110">In the view pane, right-click the object to which the action is attached (for example, a cell).</span></span> <span data-ttu-id="c8a17-111">Имя действия будет отображаться в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="c8a17-111">The action name will appear in the context menu.</span></span>  
  
4.  <span data-ttu-id="c8a17-112">Щелкните имя действия, чтобы проверить действие.</span><span class="sxs-lookup"><span data-stu-id="c8a17-112">Click the action name to test the action.</span></span>  
  
  
