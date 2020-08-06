---
title: Работа с объектами базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- database objects [SMO]
- objects [SMO]
ms.assetid: 702fd63d-8734-4a02-872e-aecfb037c787
author: stevestein
ms.author: sstein
ms.openlocfilehash: 14dd0c0175a23f809fc925c5104ac15ac408805b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739662"
---
# <a name="working-with-database-objects"></a><span data-ttu-id="8eadf-102">Работа с объектами базы данных</span><span class="sxs-lookup"><span data-stu-id="8eadf-102">Working with Database Objects</span></span>
  <span data-ttu-id="8eadf-103">Создание объектов SMO включает следующие этапы:</span><span class="sxs-lookup"><span data-stu-id="8eadf-103">The stages of SMO object creation are as follows:</span></span>  
  
1.  <span data-ttu-id="8eadf-104">создание экземпляра объекта;</span><span class="sxs-lookup"><span data-stu-id="8eadf-104">Create an instance of the object.</span></span>  
  
2.  <span data-ttu-id="8eadf-105">настройка свойств объекта;</span><span class="sxs-lookup"><span data-stu-id="8eadf-105">Set the object properties.</span></span>  
  
3.  <span data-ttu-id="8eadf-106">создание экземпляров дочерних объектов;</span><span class="sxs-lookup"><span data-stu-id="8eadf-106">Create instances of the child objects.</span></span>  
  
4.  <span data-ttu-id="8eadf-107">настройка свойств дочерних объектов;</span><span class="sxs-lookup"><span data-stu-id="8eadf-107">Set the child object properties.</span></span>  
  
5.  <span data-ttu-id="8eadf-108">создание объекта.</span><span class="sxs-lookup"><span data-stu-id="8eadf-108">Create the object.</span></span>  
  
 <span data-ttu-id="8eadf-109">При создании в приложении SMO экземпляров объектов SMO они не будут существовать в экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], пока не будет вызван метод `Create`.</span><span class="sxs-lookup"><span data-stu-id="8eadf-109">When instances of SMO objects are created in an SMO application, they do not exist on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] until the `Create` method is issued.</span></span> <span data-ttu-id="8eadf-110">Однако не обязательно запускать метод `Create` для каждого отдельного объекта.</span><span class="sxs-lookup"><span data-stu-id="8eadf-110">However, it is not necessary to issue a `Create` method for every individual object.</span></span> <span data-ttu-id="8eadf-111">Если объект имеет набор дочерних объектов, метод `Create` необходимо вызвать только для родительского объекта.</span><span class="sxs-lookup"><span data-stu-id="8eadf-111">If an object has a set of child objects, only the parent object is required to run the `Create` method.</span></span> <span data-ttu-id="8eadf-112">Например, при определении таблицы требуется, чтобы она содержала хотя бы один столбец.</span><span class="sxs-lookup"><span data-stu-id="8eadf-112">For example, the definition of a table requires that it contains at least one column to exist.</span></span> <span data-ttu-id="8eadf-113">А столбец, в свою очередь, не может существовать без таблицы.</span><span class="sxs-lookup"><span data-stu-id="8eadf-113">Also, a column cannot exist in isolation without a table.</span></span> <span data-ttu-id="8eadf-114">Ниже представлена связь между таблицей и ее столбцами.</span><span class="sxs-lookup"><span data-stu-id="8eadf-114">There is a codependent relationship between the table and its columns.</span></span>  
  
 <span data-ttu-id="8eadf-115">Метод <xref:Microsoft.SqlServer.Management.Dmf.Policy.Alter%2A> позволяет вносить изменения в объект.</span><span class="sxs-lookup"><span data-stu-id="8eadf-115">The <xref:Microsoft.SqlServer.Management.Dmf.Policy.Alter%2A> method lets you make changes to an object.</span></span> <span data-ttu-id="8eadf-116">Несколько изменений объекта, например добавление дочерних объектов к одному из объектов коллекции или изменение значения свойства, объединяются в пакет и выполняются как одно изменение.</span><span class="sxs-lookup"><span data-stu-id="8eadf-116">Several changes to an object, such as adding child objects to one of the object's collections or changing a property value, are batched together and run as one.</span></span> <span data-ttu-id="8eadf-117">Метод `Alter` уменьшает сетевой трафик и повышает общую производительность.</span><span class="sxs-lookup"><span data-stu-id="8eadf-117">The `Alter` method reduces network traffic and improves overall performance.</span></span>  
  
 <span data-ttu-id="8eadf-118">Инструкция `Drop` используется для удаления объекта и всех взаимозависимых дочерних объектов, которые требовались для первоначального создания объекта.</span><span class="sxs-lookup"><span data-stu-id="8eadf-118">The `Drop` statement is used to remove an object and all its codependent child objects that were required to create the object initially.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eadf-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="8eadf-119">See Also</span></span>  
 [<span data-ttu-id="8eadf-120">Объектная модель SMO</span><span class="sxs-lookup"><span data-stu-id="8eadf-120">SMO Object Model</span></span>](../smo-object-model.md)  
  
  
