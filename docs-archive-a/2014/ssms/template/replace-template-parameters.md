---
title: Замена параметров шаблона | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.templates.replaceparameters.f1
helpviewer_keywords:
- template parameters [Template Explorer]
- templates [Transact-SQL], replacing parameters
- Replace (Query) Template Parameters dialog box
- replacing template parameters
ms.assetid: 1234aa14-3464-4a3e-922a-5cfb8fb23627
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1d87b17a110efe118f7796487448e4d3bae30375
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665734"
---
# <a name="replace-template-parameters"></a><span data-ttu-id="46814-102">Замена параметров шаблона</span><span class="sxs-lookup"><span data-stu-id="46814-102">Replace Template Parameters</span></span>
  <span data-ttu-id="46814-103">Шаблоны содержат параметры, которым можно присваивать требуемые значения для каждой конкретной реализации при каждом использовании данного шаблона.</span><span class="sxs-lookup"><span data-stu-id="46814-103">Templates contain parameters that can be replaced by implementation-specific values each time the template is used.</span></span> <span data-ttu-id="46814-104">После открытия шаблона в редакторе кода можно заменить параметры значениями, которые требуются в данной реализации.</span><span class="sxs-lookup"><span data-stu-id="46814-104">After opening a template in a code editor, you can replace the parameters with values relevant to your implementation.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="46814-105">Перед началом</span><span class="sxs-lookup"><span data-stu-id="46814-105">Before You Begin</span></span>  
 <span data-ttu-id="46814-106">Диалоговое окно **Задание значений для параметров шаблона** представляет собой сетку с тремя столбцами.</span><span class="sxs-lookup"><span data-stu-id="46814-106">The **Specify Values for Template Parameters** dialog is a grid with three columns.</span></span> <span data-ttu-id="46814-107">Столбцы **Параметр** и **Тип** доступны только для чтения и не могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="46814-107">The **Parameter** and **Type** columns are read-only and cannot be changed.</span></span> <span data-ttu-id="46814-108">Просмотрите содержимое столбца **Значение** и замените любое из значений по умолчанию значением, требуемым для данной реализации.</span><span class="sxs-lookup"><span data-stu-id="46814-108">Review the contents of the **Value** column, and change any of the defaults to values appropriate for your implementation.</span></span>  
  
 <span data-ttu-id="46814-109">Чтобы использовать это диалоговое окно, необходимо заключить параметры в скрипте в угловые скобки (`< >`) в формате `<`*имя_параметра*`,` *тип_данных*`,` *значение_по_умолчанию*`>`.</span><span class="sxs-lookup"><span data-stu-id="46814-109">To use this dialog box, you must have parameters in your script enclosed in angle brackets (`< >`) in the format `<`*parameter_name*`,` *data_type*`,` *default_value*`>`.</span></span>  
  
## <a name="replace-template-parameters"></a><span data-ttu-id="46814-110">Замена параметров шаблона</span><span class="sxs-lookup"><span data-stu-id="46814-110">Replace Template Parameters</span></span>  
 <span data-ttu-id="46814-111">После открытия шаблона в окне редактора кода выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="46814-111">After opening the template in a code editor window:</span></span>  
  
1.  <span data-ttu-id="46814-112">В меню **Запрос** выберите пункт **Указать значения для параметров шаблона**.</span><span class="sxs-lookup"><span data-stu-id="46814-112">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
2.  <span data-ttu-id="46814-113">В диалоговом окне **Задание значений для параметров шаблона** в столбце **Значения** содержится предлагаемое значение параметра.</span><span class="sxs-lookup"><span data-stu-id="46814-113">In the **Specify Values for Template Parameters** dialog box, the **Values** column contains a suggested value for each parameter.</span></span> <span data-ttu-id="46814-114">Примите значение или замените его новым значением.</span><span class="sxs-lookup"><span data-stu-id="46814-114">Accept the value or replace it with a new value.</span></span>  
  
3.  <span data-ttu-id="46814-115">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Замена параметров шаблона** , и отредактируйте скрипт в редакторе запросов.</span><span class="sxs-lookup"><span data-stu-id="46814-115">Click **OK** to close the **Replace Template Parameters** dialog box and modify the script in the query editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46814-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="46814-116">See Also</span></span>  
 <span data-ttu-id="46814-117">[Обозреватель шаблонов](template-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="46814-117">[Template Explorer](template-explorer.md) </span></span>  
 [<span data-ttu-id="46814-118">Открытие шаблона</span><span class="sxs-lookup"><span data-stu-id="46814-118">Open a Template</span></span>](open-a-template.md)  
  
  
