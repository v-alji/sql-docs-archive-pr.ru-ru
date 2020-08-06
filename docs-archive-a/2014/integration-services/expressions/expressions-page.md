---
title: Страница "Выражения" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.expressionspage.f1
helpviewer_keywords:
- Expressions Page dialog box
ms.assetid: c9016ec6-11c1-4ebd-b2a7-0fa6631fd9e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ba4e73ea495456e8f9e452108ab09106a65543ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658929"
---
# <a name="expressions-page"></a><span data-ttu-id="ca72c-102">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="ca72c-102">Expressions Page</span></span>
  <span data-ttu-id="ca72c-103">На странице **Выражения** можно изменить выражения свойств и открыть диалоговые окна **Редактор выражений свойств** и **Построитель выражений для свойств** .</span><span class="sxs-lookup"><span data-stu-id="ca72c-103">Use the **Expressions** page to edit property expressions and to access the **Property Expressions Editor** and **Property Expression Builder** dialog boxes.</span></span>  
  
 <span data-ttu-id="ca72c-104">Выражения свойств обновляют значения свойств при выполнении пакета.</span><span class="sxs-lookup"><span data-stu-id="ca72c-104">Property expressions update the values of properties when the package is run.</span></span> <span data-ttu-id="ca72c-105">Выражения свойств можно использовать вместе со свойствами пакетов, задач, контейнеров, диспетчеров соединений, а также с некоторыми компонентами потока данных.</span><span class="sxs-lookup"><span data-stu-id="ca72c-105">Property expressions can be used with the properties of packages, tasks, containers, connection managers, as well as some data flow components.</span></span> <span data-ttu-id="ca72c-106">Выражения оцениваются, и их результаты используются вместо значений свойств, которые устанавливаются при конфигурации пакета и объектов пакета.</span><span class="sxs-lookup"><span data-stu-id="ca72c-106">The expressions are evaluated and their results are used instead of the values to which you set the properties when you configured the package and package objects.</span></span> <span data-ttu-id="ca72c-107">Выражения могут включать переменные, а также функции и операторы, предоставляемые языком выражений.</span><span class="sxs-lookup"><span data-stu-id="ca72c-107">The expressions can include variables and the functions and operators that the expression language provides.</span></span> <span data-ttu-id="ca72c-108">К примеру, можно создать строку темы сообщения для задачи «Отправка почты» путем объединения значения переменной, в которой содержится строка «Прогноз погоды на », и возвращаемых результатов функции GETDATE(), чтобы получить строку вида «Прогноз погоды на 4/5/2006».</span><span class="sxs-lookup"><span data-stu-id="ca72c-108">For example, you can generate the subject line for the Send Mail task by concatenating the value of a variable that contains the string "Weather forecast for " and the return results of the GETDATE() function to make the string "Weather forecast for 4/5/2006".</span></span>  
  
 <span data-ttu-id="ca72c-109">Дополнительные сведения о написании выражений и использовании выражений свойств см. в разделах [Выражения служб Integration Services (SSIS)](integration-services-ssis-expressions.md) и [Использование выражений свойств в пакетах](use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="ca72c-109">To learn more about writing expressions and using property expressions, see [Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md) and [Use Property Expressions in Packages](use-property-expressions-in-packages.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ca72c-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="ca72c-110">Options</span></span>  
 <span data-ttu-id="ca72c-111">**Выражения (...)**</span><span class="sxs-lookup"><span data-stu-id="ca72c-111">**Expressions (...)**</span></span>  
 <span data-ttu-id="ca72c-112">Нажмите кнопку с многоточием, чтобы открыть диалоговое окно **Редактор выражений свойств** .</span><span class="sxs-lookup"><span data-stu-id="ca72c-112">Click the ellipsis to open the **Property Expressions Editor** dialog box.</span></span> <span data-ttu-id="ca72c-113">Дополнительные сведения см. в статье [Property Expressions Editor](property-expressions-editor.md).</span><span class="sxs-lookup"><span data-stu-id="ca72c-113">For more information, see [Property Expressions Editor](property-expressions-editor.md).</span></span>  
  
 **\<property name>**  
 <span data-ttu-id="ca72c-114">Нажмите кнопку с многоточием, чтобы открыть диалоговое окно **Построитель выражений** .</span><span class="sxs-lookup"><span data-stu-id="ca72c-114">Click the ellipsis to open the **Expression Builder** dialog box.</span></span> <span data-ttu-id="ca72c-115">Дополнительные сведения см. в статье [Expression Builder](expression-builder.md).</span><span class="sxs-lookup"><span data-stu-id="ca72c-115">For more information, see [Expression Builder](expression-builder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca72c-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="ca72c-116">See Also</span></span>  
 <span data-ttu-id="ca72c-117">[Переменные в службах Integration Services (SSIS)](../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="ca72c-117">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="ca72c-118">[Системные переменные](../system-variables.md) </span><span class="sxs-lookup"><span data-stu-id="ca72c-118">[System Variables](../system-variables.md) </span></span>  
 [<span data-ttu-id="ca72c-119">Выражения служб Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="ca72c-119">Integration Services &#40;SSIS&#41; Expressions</span></span>](integration-services-ssis-expressions.md)  
  
  
