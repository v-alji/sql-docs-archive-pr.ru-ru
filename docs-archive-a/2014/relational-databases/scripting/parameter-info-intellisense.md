---
title: Сведения о параметре (технология IntelliSense)
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Parameter Info option [IntelliSense]
- stored function parameter completion [Intellisense]
- language references [SQL Server]
- IntelliSense [SQL Server], Parameter Info option
ms.assetid: 56c2aac9-c65c-4679-b62c-d9f689876dde
author: rothja
ms.author: jroth
ms.openlocfilehash: b7e5e7496753006808f75378182db0d3cb606d4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667677"
---
# <a name="parameter-info-intellisense"></a><span data-ttu-id="6bbd2-102">Сведения о параметре (технология IntelliSense)</span><span class="sxs-lookup"><span data-stu-id="6bbd2-102">Parameter Info (IntelliSense)</span></span>
  <span data-ttu-id="6bbd2-103">Параметр [!INCLUDE[msCoName](../../includes/msconame-md.md)] IntelliSense **Сведения о параметре** позволяет открыть список параметров, содержащий сведения о количестве, именах и типах параметров функции или хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="6bbd2-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] IntelliSense **Parameter Info** option opens a parameters list that provides information about the number, names, and types of the parameters that are required by a function or stored procedure.</span></span> <span data-ttu-id="6bbd2-104">При вводе функции или системной хранимой процедуры следующий обязательный параметр отображается полужирным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="6bbd2-104">The parameter in bold indicates the next parameter that is required as you type a function or stored procedure.</span></span>  
  
 <span data-ttu-id="6bbd2-105">Список параметров отображается также и для вложенных функций.</span><span class="sxs-lookup"><span data-stu-id="6bbd2-105">The parameter list is also displayed for nested functions.</span></span> <span data-ttu-id="6bbd2-106">Если функция вводится в качестве параметра другой функции, в списке параметров перечисляются параметры для этой вложенной функции.</span><span class="sxs-lookup"><span data-stu-id="6bbd2-106">If you type a function as a parameter to another function, the parameter list displays the parameters for the inner function.</span></span> <span data-ttu-id="6bbd2-107">Затем, когда список параметров вложенной функции заполнен, в списке продолжается отображение параметров внешней функции.</span><span class="sxs-lookup"><span data-stu-id="6bbd2-107">Then, when the inner function parameter list is complete, the parameter list reverts to displaying the outer function parameters.</span></span>  
  
#### <a name="to-view-parameter-info-for-functions-or-stored-procedures"></a><span data-ttu-id="6bbd2-108">Просмотр сведений о параметрах для функций или хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="6bbd2-108">To view Parameter Info for functions or stored procedures</span></span>  
  
1.  <span data-ttu-id="6bbd2-109">После имени функции введите открывающую скобку, как это обычно делается для открытия списка параметров.</span><span class="sxs-lookup"><span data-stu-id="6bbd2-109">After the name of a function, type an open parenthesis as you usually type to open the parameters list.</span></span> <span data-ttu-id="6bbd2-110">Набрав имя хранимой процедуры, введите пробел, как это обычно делается для получения данных о параметрах процедур.</span><span class="sxs-lookup"><span data-stu-id="6bbd2-110">After you type the name of a stored procedure, type a space as you usually type to obtain information about the procedure parameters.</span></span>  
  
     <span data-ttu-id="6bbd2-111">Технология IntelliSense отобразит полное объявление функции либо параметры хранимой процедуры во всплывающем окне сразу после позиции ввода.</span><span class="sxs-lookup"><span data-stu-id="6bbd2-111">IntelliSense displays the complete declaration for the function or the parameters for a stored procedure in a pop-up window just under the insertion point.</span></span> <span data-ttu-id="6bbd2-112">Первый параметр в списке будет выделен полужирным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="6bbd2-112">The first parameter in the list appears in bold.</span></span>  
  
2.  <span data-ttu-id="6bbd2-113">По мере набора параметров выделение будет смещаться к следующему параметру, который необходимо ввести.</span><span class="sxs-lookup"><span data-stu-id="6bbd2-113">As you type the parameters, the bold font changes to reflect the next parameter that you need to enter.</span></span>  
  
3.  <span data-ttu-id="6bbd2-114">Нажав клавишу ESC, в любой момент можно закрыть список, в противном случае набор будет продолжен до заполнения функции.</span><span class="sxs-lookup"><span data-stu-id="6bbd2-114">Press ESC at any time to close the list, or continue typing until you have completed the function.</span></span>  
  
     <span data-ttu-id="6bbd2-115">Для функции ввод закрывающей скобки закроет список параметров.</span><span class="sxs-lookup"><span data-stu-id="6bbd2-115">For a function, if you type the closing parenthesis you also close the parameter list.</span></span>  
  
#### <a name="to-manually-start-parameter-info"></a><span data-ttu-id="6bbd2-116">Открытие списка «Сведения о параметре» вручную</span><span class="sxs-lookup"><span data-stu-id="6bbd2-116">To manually start Parameter Info</span></span>  
  
1.  <span data-ttu-id="6bbd2-117">В меню **Правка** выберите пункт **IntelliSense** , а затем пункт **Сведения о параметре**.</span><span class="sxs-lookup"><span data-stu-id="6bbd2-117">On the **Edit** menu, select **IntelliSense** and then select **Parameter Info**.</span></span>  
  
2.  <span data-ttu-id="6bbd2-118">Нажмите сочетание клавиш CTRL + SHIFT + ПРОБЕЛ.</span><span class="sxs-lookup"><span data-stu-id="6bbd2-118">Press the CTRL+SHIFT+SPACE keyboard shortcut.</span></span>  
  
 <span data-ttu-id="6bbd2-119">Дополнительные сведения см. в статье [Настройка IntelliSense (среда SQL Server Management Studio)](configure-intellisense-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="6bbd2-119">For more information, see [Configure IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6bbd2-120">Параметр **Сведения о параметре** доступен только для редактора запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] и редактора XML-запросов.</span><span class="sxs-lookup"><span data-stu-id="6bbd2-120">The **Parameter Info** option is available only for the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor and the XML Query Editor.</span></span>  
  
  
