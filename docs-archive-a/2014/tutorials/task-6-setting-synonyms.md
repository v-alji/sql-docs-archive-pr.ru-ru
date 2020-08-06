---
title: Задача 6. Настройка синонимов | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: b7d35ee9-d1c9-41d9-bbc5-0ca7db93e54d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bde0c0ec7f230ba2325aa01328b191fd8fd67fa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654661"
---
# <a name="task-6-setting-synonyms"></a><span data-ttu-id="fb204-102">Задача 6. Задание синонимов</span><span class="sxs-lookup"><span data-stu-id="fb204-102">Task 6: Setting Synonyms</span></span>
  <span data-ttu-id="fb204-103">В этой задаче вы зададите два значения, **USA** и **США**, домена **Страна** как синонимы, при этом **США** будет начальным значением.</span><span class="sxs-lookup"><span data-stu-id="fb204-103">In this task, you set two domain values, **USA** and **United States**, of the **Country** domain as synonyms with **United States** as the leading value.</span></span> <span data-ttu-id="fb204-104">Поскольку параметр **Использовать начальные значения** был выбран при создании домена **Страна** , все значения **USA** для домена **Страна** будут выводиться как **США** (при этом «США» — начальное значение).</span><span class="sxs-lookup"><span data-stu-id="fb204-104">Since the **Use Leading Values** option was selected when creating the **Country** domain, any **USA** values for the **Country** domain will be output as **United States** (as United States is the leading value).</span></span> <span data-ttu-id="fb204-105">Дополнительные сведения см. в разделе [Изменение значений домена](https://msdn.microsoft.com/library/hh510408.aspx) .</span><span class="sxs-lookup"><span data-stu-id="fb204-105">See [Change Domain Values](https://msdn.microsoft.com/library/hh510408.aspx) for more details.</span></span>

1.  <span data-ttu-id="fb204-106">Выберите **Страна** в списке доменов.</span><span class="sxs-lookup"><span data-stu-id="fb204-106">Select **Country** from the list of domains.</span></span>

2.  <span data-ttu-id="fb204-107">Перейдите на вкладку **Значения домена** .</span><span class="sxs-lookup"><span data-stu-id="fb204-107">Switch to the **Domain Values** tab.</span></span>

3.  <span data-ttu-id="fb204-108">Нажмите кнопку **Добавить новое значение домена** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="fb204-108">Click **Add new domain value** button on the toolbar.</span></span>

4.  <span data-ttu-id="fb204-109">Введите **USA** и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="fb204-109">Type **USA** for the value and press **ENTER**.</span></span>

5.  <span data-ttu-id="fb204-110">Выберите **США** и **USA** с помощью клавиш CTRL или SHIFT, щелкните правой кнопкой выделенные элементы и выберите пункт **Установить как синонимы**.</span><span class="sxs-lookup"><span data-stu-id="fb204-110">Multiselect **United States** and **USA** using CTRL or SHIFT keys, right-click the selected items, and then click **Set as Synonyms**.</span></span> <span data-ttu-id="fb204-111">Службы DQS сгруппируют эти значения и назначат одно из значений в качестве ведущего, которым будут заменяться другие.</span><span class="sxs-lookup"><span data-stu-id="fb204-111">DQS groups these values and designate one of the values as the leading value that the other values are replaced with.</span></span>

     <span data-ttu-id="fb204-112">![Меню «Задать как синонимы»](../../2014/tutorials/media/et-settingsynonyms-01.jpg "Меню «Задать как синонимы»")</span><span class="sxs-lookup"><span data-stu-id="fb204-112">![Set as Synonyms Menu](../../2014/tutorials/media/et-settingsynonyms-01.jpg "Set as Synonyms Menu")</span></span>

6.  <span data-ttu-id="fb204-113">Обратите внимание, что значение **США** задано как начальное.</span><span class="sxs-lookup"><span data-stu-id="fb204-113">Notice that **United States** is set as the leading value.</span></span> <span data-ttu-id="fb204-114">Если вы хотите, чтобы «USA» было начальным значением, щелкните «USA» правой кнопкой мыши и выберите параметр **Установить в качестве ведущего** .</span><span class="sxs-lookup"><span data-stu-id="fb204-114">If you want USA to be the leading value, you can right-click on USA and select **Set as Leading** option.</span></span> <span data-ttu-id="fb204-115">В этом учебнике мы будем использовать значение **США** как начальное.</span><span class="sxs-lookup"><span data-stu-id="fb204-115">For this tutorial, we use **United States** as the leading value.</span></span>

     <span data-ttu-id="fb204-116">![«United States» и «USA» как синонимы](../../2014/tutorials/media/et-settingsynonyms-02.jpg "«United States» и «USA» как синонимы")</span><span class="sxs-lookup"><span data-stu-id="fb204-116">![United States and USA as Synonyms](../../2014/tutorials/media/et-settingsynonyms-02.jpg "United States and USA as Synonyms")</span></span>

## <a name="next-step"></a><span data-ttu-id="fb204-117">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="fb204-117">Next Step</span></span>
 [<span data-ttu-id="fb204-118">Задача 7. Создание составного домена</span><span class="sxs-lookup"><span data-stu-id="fb204-118">Task 7: Creating a Composite Domain</span></span>](../../2014/tutorials/task-7-creating-a-composite-domain.md)


