---
title: Задача 5. Настройка отношений на основе Терма | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6569d512-637d-4f7b-82e1-1e8582278b37
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1589ec5843053baa6c42a0b9b0dec019c887da9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735578"
---
# <a name="task-5-setting-term-based-relationships"></a><span data-ttu-id="56c5b-102">Задача 5. Задание связей на основе термина</span><span class="sxs-lookup"><span data-stu-id="56c5b-102">Task 5: Setting Term Based Relationships</span></span>
  <span data-ttu-id="56c5b-103">В этой задаче вы определяете несколько связей на основе термина для значений в домене **имени поставщика** .</span><span class="sxs-lookup"><span data-stu-id="56c5b-103">In this task, you define a few term-based relations for values for the **Supplier Name** domain.</span></span> <span data-ttu-id="56c5b-104">Связь на основе терма позволяет исправить терм, являющийся частью значения в домене.</span><span class="sxs-lookup"><span data-stu-id="56c5b-104">A term-based relation enables you to make a correction to a term that is part of a value in a domain.</span></span> <span data-ttu-id="56c5b-105">Это позволяет считать идентичными синонимами несколько значений, идентичных по написанию во всем, кроме отдельных частей.</span><span class="sxs-lookup"><span data-stu-id="56c5b-105">It enables multiple values that are identical except for the spelling of a common part of them to be considered identical synonyms.</span></span> <span data-ttu-id="56c5b-106">Например, **Inc.** можно исправить на « **включено**».</span><span class="sxs-lookup"><span data-stu-id="56c5b-106">For example, **Inc.** can be corrected to **Incorporated**.</span></span> <span data-ttu-id="56c5b-107">Службы DQS используют эти связи при обнаружении знаний, очистке и сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="56c5b-107">DQS uses these relations in the knowledge discovery, cleansing, or matching processes.</span></span> <span data-ttu-id="56c5b-108">Дополнительные сведения см. в разделе [Создание связей на основе термина](https://msdn.microsoft.com/library/hh510404.aspx) .</span><span class="sxs-lookup"><span data-stu-id="56c5b-108">See [Create Term-based Relations](https://msdn.microsoft.com/library/hh510404.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="56c5b-109">Выберите **имя поставщика** в **списке Домен**.</span><span class="sxs-lookup"><span data-stu-id="56c5b-109">Select **Supplier Name** in the **Domain list**.</span></span>  
  
2.  <span data-ttu-id="56c5b-110">Перейдите на вкладку **связи на основе термина** в правой области.</span><span class="sxs-lookup"><span data-stu-id="56c5b-110">Switch to the **Term-Based Relationships** tab in the right pane.</span></span>  
  
3.  <span data-ttu-id="56c5b-111">Нажмите кнопку **Добавить новую связь** на панели инструментов, чтобы добавить связь с таблицей.</span><span class="sxs-lookup"><span data-stu-id="56c5b-111">Click **Add new relation** button on the toolbar to add a relation to the table.</span></span>  
  
4.  <span data-ttu-id="56c5b-112">Введите **Co.** для поля **значения** и **компании** для поля **исправить на** .</span><span class="sxs-lookup"><span data-stu-id="56c5b-112">Type **Co.** for the **Value** field and **Company** for the **Correct To** field.</span></span>  
  
5.  <span data-ttu-id="56c5b-113">Повторите предыдущие два шага для следующих значений:</span><span class="sxs-lookup"><span data-stu-id="56c5b-113">Repeat the previous two steps for the following values:</span></span>  
  
    |<span data-ttu-id="56c5b-114">Значение</span><span class="sxs-lookup"><span data-stu-id="56c5b-114">Value</span></span>|<span data-ttu-id="56c5b-115">Исправить на</span><span class="sxs-lookup"><span data-stu-id="56c5b-115">Correct To</span></span>|  
    |-----------|----------------|  
    |<span data-ttu-id="56c5b-116">Corp.</span><span class="sxs-lookup"><span data-stu-id="56c5b-116">Corp.</span></span>|<span data-ttu-id="56c5b-117">Corporation</span><span class="sxs-lookup"><span data-stu-id="56c5b-117">Corporation</span></span>|  
    |<span data-ttu-id="56c5b-118">Inc.</span><span class="sxs-lookup"><span data-stu-id="56c5b-118">Inc.</span></span>|<span data-ttu-id="56c5b-119">Incorporated</span><span class="sxs-lookup"><span data-stu-id="56c5b-119">Incorporated</span></span>|  
  
     <span data-ttu-id="56c5b-120">![Связи на основе термина](../../2014/tutorials/media/et-settingtermbasedrelations.jpg "Связи на основе термина")</span><span class="sxs-lookup"><span data-stu-id="56c5b-120">![Term Based Relations](../../2014/tutorials/media/et-settingtermbasedrelations.jpg "Term Based Relations")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="56c5b-121">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="56c5b-121">Next Step</span></span>  
 [<span data-ttu-id="56c5b-122">Задача 6. Задание синонимов</span><span class="sxs-lookup"><span data-stu-id="56c5b-122">Task 6: Setting Synonyms</span></span>](../../2014/tutorials/task-6-setting-synonyms.md)  
  
  
