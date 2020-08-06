---
title: Задача 7. Создание составного домена | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: ae778647-1df0-4952-9a69-0ef6177eea9c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 42936d25e267bcad5ba8ae512750f9e12f041579
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654645"
---
# <a name="task-7-creating-a-composite-domain"></a><span data-ttu-id="ee06b-102">Задача 7. Создание составного домена</span><span class="sxs-lookup"><span data-stu-id="ee06b-102">Task 7: Creating a Composite Domain</span></span>
  <span data-ttu-id="ee06b-103">В этой задаче вы создадите составной домен, который является **проверкой адреса**, которая включает домены **адресов**, **городов**, **Штатов**и **ZIP** -доменов.</span><span class="sxs-lookup"><span data-stu-id="ee06b-103">In this task, you create a composite domain, **Address Validation**, which comprises **Address Line**, **City**, **State**, and **Zip** domains.</span></span> <span data-ttu-id="ee06b-104">Составной домен позволяет определить междоменное правило, включающее несколько доменов.</span><span class="sxs-lookup"><span data-stu-id="ee06b-104">A composite domain lets you define a cross-domain rule that involves multiple domains in a rule.</span></span> <span data-ttu-id="ee06b-105">Есть и другие преимущества составных доменов, например возможность анализировать значение поля в нескольких доменах.</span><span class="sxs-lookup"><span data-stu-id="ee06b-105">There are other advantages to a composite domain such as being able to parse a field value into multiple domains.</span></span>  <span data-ttu-id="ee06b-106">Например, значение для поля «Полное имя» может быть проанализировано в отдельных доменах «Имя», «Отчество» и «Фамилия».</span><span class="sxs-lookup"><span data-stu-id="ee06b-106">For example, a value for a Full Name field can be parsed into separate First Name, Middle Name, and Last Name domains.</span></span> <span data-ttu-id="ee06b-107">В этом учебнике вы определяете только междоменное правило.</span><span class="sxs-lookup"><span data-stu-id="ee06b-107">In this tutorial, you only define a cross-domain rule.</span></span> <span data-ttu-id="ee06b-108">Дополнительные сведения см. [в разделе Управление составным доменом](https://msdn.microsoft.com/library/hh510399.aspx) .</span><span class="sxs-lookup"><span data-stu-id="ee06b-108">See [Managing a Composite Domain](https://msdn.microsoft.com/library/hh510399.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="ee06b-109">В левой области нажмите кнопку **создать составной домен** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="ee06b-109">In the left pane, click **Create a composite domain** button on the toolbar.</span></span>  
  
     <span data-ttu-id="ee06b-110">![Кнопка панели инструментов «Создание составного домена»](../../2014/tutorials/media/et-creatingacompositedomain-01.jpg "Кнопка панели инструментов «Создание составного домена»")</span><span class="sxs-lookup"><span data-stu-id="ee06b-110">![Create a Composite Domain Toolbar Button](../../2014/tutorials/media/et-creatingacompositedomain-01.jpg "Create a Composite Domain Toolbar Button")</span></span>  
  
2.  <span data-ttu-id="ee06b-111">Введите **проверку адреса** для **имени составного домена**.</span><span class="sxs-lookup"><span data-stu-id="ee06b-111">Enter **Address Validation** for the **Composite Domain Name**.</span></span>  
  
     <span data-ttu-id="ee06b-112">![Составной домен проверки адреса](../../2014/tutorials/media/et-creatingacompositedomain-02.jpg "Составной домен проверки адреса")</span><span class="sxs-lookup"><span data-stu-id="ee06b-112">![Address Validation Composite Domain](../../2014/tutorials/media/et-creatingacompositedomain-02.jpg "Address Validation Composite Domain")</span></span>  
  
3.  <span data-ttu-id="ee06b-113">В списке Домен выберите **Строка адреса**, **город**, **штат**и **почтовый индекс** , а затем щелкните **стрелку вправо** , чтобы добавить их в список **домены в составном** списке доменов.</span><span class="sxs-lookup"><span data-stu-id="ee06b-113">From the domain list select **Address Line**, **City**, **State**, and **Zip** and click **right arrow** to add them to the **Domains in Composite Domain** list.</span></span>  
  
4.  <span data-ttu-id="ee06b-114">Чтобы закрыть диалоговое окно, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="ee06b-114">Click **OK** to close the dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="ee06b-115">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="ee06b-115">Next Step</span></span>  
 [<span data-ttu-id="ee06b-116">Задача 8. Создание правила составного домена</span><span class="sxs-lookup"><span data-stu-id="ee06b-116">Task 8: Creating a Composite Domain Rule</span></span>](../../2014/tutorials/task-8-creating-a-composite-domain-rule.md)  
  
  
