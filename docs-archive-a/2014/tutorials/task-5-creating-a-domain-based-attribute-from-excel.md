---
title: Задача 5. Создание атрибута на основе домена из Excel | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 07cbc624-2c6b-4568-96e4-f18663a05d80
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b866478150fb4c06a3c4ea1ee6c227527f963219
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732202"
---
# <a name="task-5-creating-a-domain-based-attribute-from-excel"></a><span data-ttu-id="e5e0d-102">Задача 5. Создание атрибута на основе домена в Excel</span><span class="sxs-lookup"><span data-stu-id="e5e0d-102">Task 5: Creating a Domain-Based Attribute from Excel</span></span>
  <span data-ttu-id="e5e0d-103">В этой задаче вы преобразуете атрибут **State** сущности **поставщика** в качестве **атрибута на основе домена**.</span><span class="sxs-lookup"><span data-stu-id="e5e0d-103">In this task, you convert the **State** attribute of the **Supplier** entity as a **domain-based attribute**.</span></span> <span data-ttu-id="e5e0d-104">После настройки атрибута State на основе домена и его публикации в службах MDS новая сущность с именем **State** будет создана на сервере MDS со всеми значениями в столбце, а атрибут **State** сущности **поставщика** будет заполнен значениями из сущности **State** .</span><span class="sxs-lookup"><span data-stu-id="e5e0d-104">After you configure the State attribute to be a domain-based one and publish it to MDS, a new entity named **State** will be created on MDS server with all the values in the column and the **State** attribute of the **Supplier** entity will be populated with values from the **State** entity.</span></span> <span data-ttu-id="e5e0d-105">Теперь модель **поставщиков** должна иметь две сущности: **поставщик** и **состояние** , в которых атрибут **State** сущности « **поставщик** » является атрибутом на основе домена, который зависит от сущности **состояния** .</span><span class="sxs-lookup"><span data-stu-id="e5e0d-105">Now, the **Suppliers** model should have two entities: **Supplier** and **State** where the **State** attribute of the **Supplier** entity is a domain-based attribute that depends on **State** entity.</span></span>  
  
1.  <span data-ttu-id="e5e0d-106">Перейдите в окно **Excel** , которое было **очищено и сопоставлено Suppliers.xlsx** открыть.</span><span class="sxs-lookup"><span data-stu-id="e5e0d-106">Switch to **Excel** window that has **Cleansed and Matched Suppliers.xlsx** open.</span></span>  
  
2.  <span data-ttu-id="e5e0d-107">Нажмите кнопку **Обновить** на ленте, чтобы получить последние обновления из MDS.</span><span class="sxs-lookup"><span data-stu-id="e5e0d-107">Click **Refresh** button on the ribbon to get the latest updates from MDS.</span></span> <span data-ttu-id="e5e0d-108">Если вы выполнили необязательную **задачу 4**, вы увидите еще две записи.</span><span class="sxs-lookup"><span data-stu-id="e5e0d-108">You should see the two more records if you have performed the optional **Task 4**.</span></span>  
  
3.  <span data-ttu-id="e5e0d-109">В **строке заголовка**щелкните имя столбца **State** (ячейка **I1**).</span><span class="sxs-lookup"><span data-stu-id="e5e0d-109">Click column name **State** (cell **I1**) in the **header row**.</span></span>  
  
     <span data-ttu-id="e5e0d-110">![Excel — кнопка «Свойства атрибута»](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-01.jpg "Excel — кнопка «Свойства атрибута»")</span><span class="sxs-lookup"><span data-stu-id="e5e0d-110">![Excel - Attribute Properties Button](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-01.jpg "Excel - Attribute Properties Button")</span></span>  
  
4.  <span data-ttu-id="e5e0d-111">На ленте щелкните **свойства атрибута** .</span><span class="sxs-lookup"><span data-stu-id="e5e0d-111">Click **Attribute Properties** on the ribbon.</span></span>  
  
5.  <span data-ttu-id="e5e0d-112">В диалоговом окне **свойства атрибута** выберите **ограниченный список (на основе домена)** для **типа атрибута**.</span><span class="sxs-lookup"><span data-stu-id="e5e0d-112">In the **Attribute Properties** dialog box, select **Constrained list (Domain-based)** for the **Attribute type**.</span></span>  
  
6.  <span data-ttu-id="e5e0d-113">Введите **состояние** для **нового имени сущности** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e5e0d-113">Type **State** for the **New entity name** and click **OK**.</span></span>  
  
     <span data-ttu-id="e5e0d-114">![Excel — диалоговое окно «Свойства атрибута»](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-02.jpg "Excel — диалоговое окно «Свойства атрибута»")</span><span class="sxs-lookup"><span data-stu-id="e5e0d-114">![Excel - Attribute Properties Dialog Box](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-02.jpg "Excel - Attribute Properties Dialog Box")</span></span>  
  
7.  <span data-ttu-id="e5e0d-115">Теперь в Excel при щелчке любого значения в столбце **состояние** отображается **стрелка вниз** .</span><span class="sxs-lookup"><span data-stu-id="e5e0d-115">Now, in Excel, you should see **down arrow** when you click any value in the **State** column.</span></span> <span data-ttu-id="e5e0d-116">При необходимости это значение можно изменить, выбрав новое значение в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="e5e0d-116">You can change the value by using the drop-down list if you need.</span></span>  
  
     <span data-ttu-id="e5e0d-117">![Excel — раскрывающийся список со штатами](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-03.jpg "Excel — раскрывающийся список со штатами")</span><span class="sxs-lookup"><span data-stu-id="e5e0d-117">![Excel - Drop Down List with States](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-03.jpg "Excel - Drop Down List with States")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="e5e0d-118">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="e5e0d-118">Next Step</span></span>  
 [<span data-ttu-id="e5e0d-119">Задача 6. Проверка создания атрибута на основе домена в диспетчере основных данных</span><span class="sxs-lookup"><span data-stu-id="e5e0d-119">Task 6: Verify that the Domain-Based Attribute is Created using Master Data Manager</span></span>](../../2014/tutorials/task-6-verify-domain-based-attribute-master-data-manager.md)  
  
  
