---
title: Задача 8. Создание правила составного домена | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: cff3b662-7876-4445-9bdd-96be35b3ca0c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4766a1206eb09e98bb20d3712a63762126b682b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666906"
---
# <a name="task-8-creating-a-composite-domain-rule"></a><span data-ttu-id="f7c0a-102">Задача 8. Создание правила составного домена</span><span class="sxs-lookup"><span data-stu-id="f7c0a-102">Task 8: Creating a Composite Domain Rule</span></span>
  <span data-ttu-id="f7c0a-103">В этой задаче вы создадите правило для составного домена **Проверка адреса** .</span><span class="sxs-lookup"><span data-stu-id="f7c0a-103">In this task, you create a rule for the **Address Validation** composite domain.</span></span> <span data-ttu-id="f7c0a-104">Вы определяете междоменное правило: Если **город** — **Лос-Анджелес**, **штат** должен быть **CA** , где **City** и **State** — два домена.</span><span class="sxs-lookup"><span data-stu-id="f7c0a-104">You define a cross-domain rule: if **City** is **Los Angeles**, **State** must be **CA** where **City** and **State** are two domains.</span></span>  
  
1.  <span data-ttu-id="f7c0a-105">На панели справа перейдите на вкладку **правила компакт-диска** .</span><span class="sxs-lookup"><span data-stu-id="f7c0a-105">In the right pane, switch to the **CD Rules** tab.</span></span>  
  
2.  <span data-ttu-id="f7c0a-106">Щелкните **Добавить новое правило домена** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="f7c0a-106">Click **Add a new domain rule** from the toolbar.</span></span>  
  
3.  <span data-ttu-id="f7c0a-107">Введите **правило состояния города** для **имени** и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="f7c0a-107">Type **City-State Rule** for **Name** and press **ENTER**.</span></span>  
  
4.  <span data-ttu-id="f7c0a-108">На панели **Построение правила** выберите **город** в списке домен, а для параметра условие выберите **значение** и введите **Los-Анджелес** для значения.</span><span class="sxs-lookup"><span data-stu-id="f7c0a-108">In the **Build a Rule** pane, select **City** in the domain list, and select condition **Value is equal to** and type **Los Angeles** for the value.</span></span>  
  
5.  <span data-ttu-id="f7c0a-109">В области **затем** выберите в списке домен **состояние** и выберите **значение равно**, введите **CA** для значения и нажмите клавишу **Tab**.</span><span class="sxs-lookup"><span data-stu-id="f7c0a-109">In the **Then** pane, select **State** in the domain list, and select **Value is equal to**, type **CA** for the value, and press **TAB**.</span></span>  
  
     <span data-ttu-id="f7c0a-110">![Правило составного домена](../../2014/tutorials/media/et-creatingacompositedomainrule.jpg "Правило составного домена")</span><span class="sxs-lookup"><span data-stu-id="f7c0a-110">![Composite Domain Rule](../../2014/tutorials/media/et-creatingacompositedomainrule.jpg "Composite Domain Rule")</span></span>  
  
6.  <span data-ttu-id="f7c0a-111">Нажмите кнопку **Закрыть** в нижней части страницы, чтобы перейти на главную страницу клиента DQS.</span><span class="sxs-lookup"><span data-stu-id="f7c0a-111">Click **Close** button at the bottom of the page to switch to the main page of DQS Client.</span></span> <span data-ttu-id="f7c0a-112">На следующем занятии вы опубликуете базу знаний.</span><span class="sxs-lookup"><span data-stu-id="f7c0a-112">You will publish the knowledge base in the next lesson.</span></span> <span data-ttu-id="f7c0a-113">Обратите внимание, что база знаний находится в заблокированном состоянии (значок блокировки).</span><span class="sxs-lookup"><span data-stu-id="f7c0a-113">Notice that the knowledge base is in locked state (lock icon).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="f7c0a-114">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="f7c0a-114">Next Step</span></span>  
 [<span data-ttu-id="f7c0a-115">Задача 9. Настройка службы эталонных данных</span><span class="sxs-lookup"><span data-stu-id="f7c0a-115">Task 9: Configuring a Reference Data Service</span></span>](../../2014/tutorials/task-9-configuring-a-reference-data-service.md)  
  
  
