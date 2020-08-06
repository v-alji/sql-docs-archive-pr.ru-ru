---
title: Построитель выражений | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.expressionbuilder.f1
helpviewer_keywords:
- Expression Builder dialog box
ms.assetid: 4717ce33-bd4e-44bc-81e0-002de075b4d1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 812b0d744d415d5419d54176359ddcd5837dd206
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658928"
---
# <a name="expression-builder"></a><span data-ttu-id="3d48d-102">Построитель выражений</span><span class="sxs-lookup"><span data-stu-id="3d48d-102">Expression Builder</span></span>
  <span data-ttu-id="3d48d-103">Диалоговое окно **Построитель выражений** используется для создания и редактирования выражения свойства или написания выражения, определяющего значение переменной, с помощью графического интерфейса, содержащего список переменных и встроенные ссылки на функции, приведения типов и операторы, включенные в язык выражений служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3d48d-103">Use the **Expression Builder** dialog box to create and edit a property expression or write the expression that sets the value of a variable using a graphical user interface that lists variables and provides a built-in reference to the functions, type casts, and operators that the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language includes.</span></span>  
  
 <span data-ttu-id="3d48d-104">Выражение свойства представляет собой выражение, которое присваивается свойству.</span><span class="sxs-lookup"><span data-stu-id="3d48d-104">A property expression is an expression that is assigned to a property.</span></span> <span data-ttu-id="3d48d-105">При вычислении выражения свойство динамически обновляется для использования результатов вычисления выражения.</span><span class="sxs-lookup"><span data-stu-id="3d48d-105">When the expression is evaluated, the property is dynamically updated to use the evaluation result of the expression.</span></span> <span data-ttu-id="3d48d-106">Аналогичным образом, выражение, которое используется в переменной, позволяет присваивать переменной результаты вычисления выражения в качестве нового значения.</span><span class="sxs-lookup"><span data-stu-id="3d48d-106">Likewise, an expression that is used in a variable enables the variable value to be updated with the evaluation result of the expression.</span></span>  
  
 <span data-ttu-id="3d48d-107">Существует множество способов использования выражений:</span><span class="sxs-lookup"><span data-stu-id="3d48d-107">There are many ways to use expressions:</span></span>  
  
-   <span data-ttu-id="3d48d-108">**Задачи** Обновление строки "Кому", в которую задача "Отправка почты" вставляет хранящийся в переменной адрес электронной почты, или обновление строки "Тема" с помощью объединения строки "Продажи за:" и текущей даты, возвращенной функцией GETDATE.</span><span class="sxs-lookup"><span data-stu-id="3d48d-108">**Tasks** Update the To line that a Send Mail task uses by inserting an e-mail address that is stored in a variable; or update the Subject line by concatenating a string such as "Sales for: " and the current date returned by the GETDATE function.</span></span>  
  
-   <span data-ttu-id="3d48d-109">**Переменные** Задание значения переменной, равного текущему месяцу, с помощью выражения, подобного `DATEPART("mm",GETDATE())`, или задание значения строки с помощью объединения строкового литерала и текущей даты с использованием такого выражения, как `"Today's date is " + (DT_WSTR,30)(GETDATE())`.</span><span class="sxs-lookup"><span data-stu-id="3d48d-109">**Variables** Set the value of a variable to the current month by using an expression like `DATEPART("mm",GETDATE())`; or set the value of a string by concatenating the string literal and the current date by using the expression `"Today's date is " + (DT_WSTR,30)(GETDATE())`.</span></span>  
  
-   <span data-ttu-id="3d48d-110">**Диспетчеры соединений** Задание кодовой страницы диспетчера соединений с неструктурированными файлами с помощью переменной, содержащей другой идентификатор кодовой страницы, или указание количества строк в файле данных, которые должны быть пропущены, с помощью ввода положительного числа, такого как 3.</span><span class="sxs-lookup"><span data-stu-id="3d48d-110">**Connection Managers** Set the code page of a Flat File connection manager by using a variable that contains a different code page identifier; or specify the number of rows in the data file to skip by entering a positive integer like 3 in the expression.</span></span>  
  
 <span data-ttu-id="3d48d-111">Дополнительные сведения о написании выражений и использовании выражений свойств см. в разделах [Использование выражений свойств в пакетах](use-property-expressions-in-packages.md) и [Выражения служб Integration Services (SSIS)](integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3d48d-111">To learn more about property expressions and writing expressions, see [Use Property Expressions in Packages](use-property-expressions-in-packages.md) and [Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="3d48d-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d48d-112">Options</span></span>  
  
|<span data-ttu-id="3d48d-113">Термин</span><span class="sxs-lookup"><span data-stu-id="3d48d-113">Term</span></span>|<span data-ttu-id="3d48d-114">Определение</span><span class="sxs-lookup"><span data-stu-id="3d48d-114">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="3d48d-115">**Переменные**</span><span class="sxs-lookup"><span data-stu-id="3d48d-115">**Variables**</span></span>|<span data-ttu-id="3d48d-116">Откройте папку **Переменные** и перетащите переменные в окно **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="3d48d-116">Expand the **Variables** folder and drag variables to the **Expression** box.</span></span>|  
|<span data-ttu-id="3d48d-117">**Математические функции**</span><span class="sxs-lookup"><span data-stu-id="3d48d-117">**Mathematical Functions**</span></span><br /><br /> <span data-ttu-id="3d48d-118">**Строковые функции**</span><span class="sxs-lookup"><span data-stu-id="3d48d-118">**String Functions**</span></span><br /><br /> <span data-ttu-id="3d48d-119">**Функции даты/времени**</span><span class="sxs-lookup"><span data-stu-id="3d48d-119">**Date/Time Functions**</span></span><br /><br /> <span data-ttu-id="3d48d-120">**Функции работы со значением NULL**</span><span class="sxs-lookup"><span data-stu-id="3d48d-120">**NULL Functions**</span></span><br /><br /> <span data-ttu-id="3d48d-121">**Приведения типов**</span><span class="sxs-lookup"><span data-stu-id="3d48d-121">**Type Casts**</span></span><br /><br /> <span data-ttu-id="3d48d-122">**Операторы**</span><span class="sxs-lookup"><span data-stu-id="3d48d-122">**Operators**</span></span>|<span data-ttu-id="3d48d-123">Откройте папки и перетащите функции, приведения типов и операторы в окно **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="3d48d-123">Expand the folders and drag functions, type casts, and operators to the **Expression** box.</span></span>|  
|<span data-ttu-id="3d48d-124">**Выражение**</span><span class="sxs-lookup"><span data-stu-id="3d48d-124">**Expression**</span></span>|<span data-ttu-id="3d48d-125">Отредактируйте или введите выражение.</span><span class="sxs-lookup"><span data-stu-id="3d48d-125">Edit or type an expression.\`</span></span>|  
|<span data-ttu-id="3d48d-126">**Рассчитанное значение**</span><span class="sxs-lookup"><span data-stu-id="3d48d-126">**Evaluated value**</span></span>|<span data-ttu-id="3d48d-127">Список результатов вычислений выражения.</span><span class="sxs-lookup"><span data-stu-id="3d48d-127">Lists the evaluation result of the expression.</span></span>|  
|<span data-ttu-id="3d48d-128">**Вычислить значение выражения**</span><span class="sxs-lookup"><span data-stu-id="3d48d-128">**Evaluate Expression**</span></span>|<span data-ttu-id="3d48d-129">Чтобы просмотреть результаты вычислений выражения, выберите параметр **Вычислить значение выражения** .</span><span class="sxs-lookup"><span data-stu-id="3d48d-129">Click **Evaluate Expression** to view the evaluation result of the expression.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d48d-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="3d48d-130">See Also</span></span>  
 <span data-ttu-id="3d48d-131">[Страница «Выражения»](expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="3d48d-131">[Expressions Page](expressions-page.md) </span></span>  
 <span data-ttu-id="3d48d-132">[Редактор выражений свойств](property-expressions-editor.md) </span><span class="sxs-lookup"><span data-stu-id="3d48d-132">[Property Expressions Editor](property-expressions-editor.md) </span></span>  
 <span data-ttu-id="3d48d-133">[Переменные в службах Integration Services (SSIS)](../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="3d48d-133">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="3d48d-134">Системные переменные</span><span class="sxs-lookup"><span data-stu-id="3d48d-134">System Variables</span></span>](../system-variables.md)  
  
  
