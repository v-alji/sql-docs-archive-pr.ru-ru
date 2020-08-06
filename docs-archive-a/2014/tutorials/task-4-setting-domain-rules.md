---
title: Задача 4. Настройка правил домена | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3a7162ba-cf2f-481f-830d-bb6a02823827
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 42bdbd0228fdd3515f68ce830581f445242768e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655453"
---
# <a name="task-4-setting-domain-rules"></a><span data-ttu-id="bfbed-102">Задача 4. Задание правил домена</span><span class="sxs-lookup"><span data-stu-id="bfbed-102">Task 4: Setting Domain Rules</span></span>
  <span data-ttu-id="bfbed-103">В этой задаче вы создадите правило для домена **Contact e-mail** , чтобы проверить, заканчивается ли адрес электронной почты с помощью \*\* \@ Adventure-Works.com\*\*.</span><span class="sxs-lookup"><span data-stu-id="bfbed-103">In this task, you create a rule for the **Contact Email** domain to verify if the email address ends with **\@adventure-works.com**.</span></span> <span data-ttu-id="bfbed-104">Дополнительные сведения о странице см. в разделе [Создание правила домена](https://msdn.microsoft.com/library/hh510397.aspx) .</span><span class="sxs-lookup"><span data-stu-id="bfbed-104">See [Creating a Domain Rule](https://msdn.microsoft.com/library/hh510397.aspx) topic for more details on the page.</span></span>  
  
1.  <span data-ttu-id="bfbed-105">Щелкните **контактный адрес электронной почты** в **списке доменов**.</span><span class="sxs-lookup"><span data-stu-id="bfbed-105">Click **Contact Email** in the **Domain list**.</span></span>  
  
2.  <span data-ttu-id="bfbed-106">Перейдите на вкладку **правила домена** в правой области.</span><span class="sxs-lookup"><span data-stu-id="bfbed-106">Switch to the **Domain Rules** tab in the right pane.</span></span>  
  
     <span data-ttu-id="bfbed-107">![Кнопка панели инструментов «Добавить новое правило для домена»](../../2014/tutorials/media/et-settingdomainrules-01.jpg "Кнопка панели инструментов «Добавить новое правило для домена»")</span><span class="sxs-lookup"><span data-stu-id="bfbed-107">![Add a New Domain Rule Toolbar Button](../../2014/tutorials/media/et-settingdomainrules-01.jpg "Add a New Domain Rule Toolbar Button")</span></span>  
  
3.  <span data-ttu-id="bfbed-108">На правой панели нажмите кнопку **Добавить новое правило домена** на панели инструментов (см. изображение), чтобы добавить правило.</span><span class="sxs-lookup"><span data-stu-id="bfbed-108">In the right pane, click **Add a new domain rule** button on the toolbar (see the image) to add a rule.</span></span>  
  
4.  <span data-ttu-id="bfbed-109">Введите **Проверка адреса электронной почты** для **имени правила** и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="bfbed-109">Type **Email Validation** for the **rule name** and press **ENTER**.</span></span> <span data-ttu-id="bfbed-110">Флажок **активно** должен быть установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bfbed-110">The **Active** check box should be checked by default.</span></span> <span data-ttu-id="bfbed-111">Этот элемент управления позволяет временно отключить правило.</span><span class="sxs-lookup"><span data-stu-id="bfbed-111">This control allows you to deactivate a rule temporarily.</span></span>  
  
5.  <span data-ttu-id="bfbed-112">На панели **Построение правила** щелкните **стрелку вниз**и выберите **значение заканчивается на**.</span><span class="sxs-lookup"><span data-stu-id="bfbed-112">In the **Build a Rule** pane, click **down arrow**, and select **Value ends with**.</span></span>  
  
6.  <span data-ttu-id="bfbed-113">Введите \*\* \@ Adventure-Works.com\*\* в текстовом поле и нажмите клавишу **Tab**.</span><span class="sxs-lookup"><span data-stu-id="bfbed-113">Type **\@adventure-works.com** in the text box and press **TAB**.</span></span> <span data-ttu-id="bfbed-114">Можно добавить дополнительные условия, нажав кнопку **Добавить новое условие на выбранном предложении** панели инструментов на панели **Создание правила** .</span><span class="sxs-lookup"><span data-stu-id="bfbed-114">You can add more conditions by clicking **Add a new condition to the selected clause** toolbar button in the **Build a Rule** pane.</span></span>  
  
     <span data-ttu-id="bfbed-115">![Правило проверки по электронной почте](../../2014/tutorials/media/et-settingdomainrules-02.jpg "Правило проверки по электронной почте")</span><span class="sxs-lookup"><span data-stu-id="bfbed-115">![Email Validation Rule](../../2014/tutorials/media/et-settingdomainrules-02.jpg "Email Validation Rule")</span></span>  
  
7.  <span data-ttu-id="bfbed-116">Нажмите кнопку **Запустить выбранное правило домена на тестовых данных** на панели инструментов в правой области, чтобы проверить правило на соответствие образцу данных.</span><span class="sxs-lookup"><span data-stu-id="bfbed-116">Click **Run the selected domain rule on test data** button on the toolbar in the right pane to test the rule against sample data.</span></span>  
  
     <span data-ttu-id="bfbed-117">![Кнопка панели инструментов «Запустить правило домена на тестовых данных»](../../2014/tutorials/media/et-settingdomainrules-03.jpg "Кнопка панели инструментов «Запустить правило домена на тестовых данных»")</span><span class="sxs-lookup"><span data-stu-id="bfbed-117">![Run the Domain Rule on Test Data Toolbar Button](../../2014/tutorials/media/et-settingdomainrules-03.jpg "Run the Domain Rule on Test Data Toolbar Button")</span></span>  
  
8.  <span data-ttu-id="bfbed-118">В диалоговом окне **Проверка правила домена** нажмите кнопку **Добавить новый тестовый термин для правила домена** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="bfbed-118">In the **Test Domain Rule** dialog box, click **Adds a new testing term for the domain rule** button on the toolbar.</span></span>  
  
     <span data-ttu-id="bfbed-119">![Диалоговое окно «Проверить правило домена»](../../2014/tutorials/media/et-settingdomainrules-04.jpg "Диалоговое окно «Проверить правило домена»")</span><span class="sxs-lookup"><span data-stu-id="bfbed-119">![Test Domain Rule Dialog Box](../../2014/tutorials/media/et-settingdomainrules-04.jpg "Test Domain Rule Dialog Box")</span></span>  
  
9. <span data-ttu-id="bfbed-120">Введите **frank7 \@ Adventure-Works.com** (допустимое значение) в столбце **контактный адрес электронной почты** .</span><span class="sxs-lookup"><span data-stu-id="bfbed-120">Type **frank7\@adventure-works.com** (a valid value) in the **Contact Email** column.</span></span>  
  
10. <span data-ttu-id="bfbed-121">Повторите предыдущие два шага, чтобы добавить **joe2 \@ Adventure-work.com** (недопустимое значение без ").</span><span class="sxs-lookup"><span data-stu-id="bfbed-121">Repeat previous two steps to add **joe2\@adventure-work.com** (an invalid value with no 's').</span></span>  
  
11. <span data-ttu-id="bfbed-122">Нажмите кнопку Последняя (**Проверьте правило домена на всех условиях**) на панели инструментов, чтобы проверить входные данные в соответствии с правилом.</span><span class="sxs-lookup"><span data-stu-id="bfbed-122">Click the last button (**Test the domain rule on all the terms**) on the toolbar to test the input data against the rule.</span></span>  
  
     <span data-ttu-id="bfbed-123">![Кнопка панели инструментов «Проверить правило домена на всех терминах»](../../2014/tutorials/media/et-settingdomainrules-05.jpg "Кнопка панели инструментов «Проверить правило домена на всех терминах»")</span><span class="sxs-lookup"><span data-stu-id="bfbed-123">![Test the Domain Rule on All Terms Toolbar Button](../../2014/tutorials/media/et-settingdomainrules-05.jpg "Test the Domain Rule on All Terms Toolbar Button")</span></span>  
  
12. <span data-ttu-id="bfbed-124">Обратите внимание, что первая запись отображается как допустимый элемент, а вторая — как недопустимый элемент.</span><span class="sxs-lookup"><span data-stu-id="bfbed-124">Notice that the first entry is shown as a valid item and the second one as an invalid item.</span></span>  
  
     <span data-ttu-id="bfbed-125">![Результаты проверки правила домена](../../2014/tutorials/media/et-settingdomainrules-06.jpg "Результаты проверки правила домена")</span><span class="sxs-lookup"><span data-stu-id="bfbed-125">![Test Domain Rule Results](../../2014/tutorials/media/et-settingdomainrules-06.jpg "Test Domain Rule Results")</span></span>  
  
13. <span data-ttu-id="bfbed-126">Нажмите кнопку **Закрыть** , чтобы закрыть диалоговое окно **Проверка правила домена** .</span><span class="sxs-lookup"><span data-stu-id="bfbed-126">Click **Close** to close the **Test Domain Rule** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="bfbed-127">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="bfbed-127">Next Step</span></span>  
 [<span data-ttu-id="bfbed-128">Задача 5. Задание связей на основе термина</span><span class="sxs-lookup"><span data-stu-id="bfbed-128">Task 5: Setting Term Based Relationships</span></span>](../../2014/tutorials/task-5-setting-term-based-relationships.md)  
  
  
