---
title: Задача "Уведомление оператора" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.notifyoperatortask.f1
helpviewer_keywords:
- Notify Operator task
- notifications [Integration Services]
- SQL Server Agent [Integration Services]
ms.assetid: 6c816c68-c6d6-44e4-bb34-c8e060a958a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ed5158a4ec5cfe8374fedbb2afbca1294b58f05e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750064"
---
# <a name="notify-operator-task"></a><span data-ttu-id="0bd5d-102">задача «Уведомление оператора»</span><span class="sxs-lookup"><span data-stu-id="0bd5d-102">Notify Operator Task</span></span>
  <span data-ttu-id="0bd5d-103">Задача «Уведомление оператора» отправляет сообщения уведомления операторам агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0bd5d-103">The Notify Operator task sends notification messages to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operators.</span></span> <span data-ttu-id="0bd5d-104">Оператор агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] является псевдонимом человека или группы, которые могут принимать электронные уведомления.</span><span class="sxs-lookup"><span data-stu-id="0bd5d-104">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operator is an alias for a person or group that can receive electronic notifications.</span></span> <span data-ttu-id="0bd5d-105">Дополнительные сведения об операторах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в разделе [Операторы](../../ssms/agent//operators.md).</span><span class="sxs-lookup"><span data-stu-id="0bd5d-105">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] operators, see [Operators](../../ssms/agent//operators.md).</span></span>  
  
 <span data-ttu-id="0bd5d-106">Используя задачу "Уведомление оператора", пакет может оповестить одного или нескольких операторов по электронной почте, интернет-пейджеру или с помощью команды **net send**.</span><span class="sxs-lookup"><span data-stu-id="0bd5d-106">By using the Notify Operator task, a package can notify one or more operators via e-mail, pager, or **net send**.</span></span> <span data-ttu-id="0bd5d-107">Каждый оператор может быть оповещен отдельным способом.</span><span class="sxs-lookup"><span data-stu-id="0bd5d-107">Each operator can be notified by different methods.</span></span> <span data-ttu-id="0bd5d-108">Например, OperatorA может быть извещен по электронной почте и интернет-пейджеру, а OperatorB — через интернет-пейджер и команду **net send**.</span><span class="sxs-lookup"><span data-stu-id="0bd5d-108">For example, OperatorA is notified by e-mail and pager, and OperatorB is notified by pager and **net send**.</span></span> <span data-ttu-id="0bd5d-109">Операторы, получающие уведомления при помощи этого задания, должны быть членами коллекции **OperatorNotify** задачи «Уведомление оператора».</span><span class="sxs-lookup"><span data-stu-id="0bd5d-109">The operators who receive notifications from the task must be members of the **OperatorNotify** collection on the Notify Operator task.</span></span>  
  
 <span data-ttu-id="0bd5d-110">Задача «Уведомление оператора» является единственной задачей обслуживания базы данных, которая не содержит инструкции Transact-SQL или команды DBCC.</span><span class="sxs-lookup"><span data-stu-id="0bd5d-110">The Notify Operator task is the only database maintenance task that does not encapsulate a Transact-SQL statement or a DBCC command.</span></span>  
  
## <a name="configuration-of-the-notify-operator-task"></a><span data-ttu-id="0bd5d-111">Настройка задачи «Уведомление оператора»</span><span class="sxs-lookup"><span data-stu-id="0bd5d-111">Configuration of the Notify Operator Task</span></span>  
 <span data-ttu-id="0bd5d-112">Свойства задаются с помощью конструктора служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0bd5d-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="0bd5d-113">Эта задача находится в разделе **Задачи плана обслуживания** **области элементов** в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0bd5d-113">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="0bd5d-114">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="0bd5d-114">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="0bd5d-115">Задача уведомления оператора (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="0bd5d-115">Notify Operator Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/notify-operator-task-maintenance-plan.md)  
  
 <span data-ttu-id="0bd5d-116">Дополнительные сведения об установке этих свойств в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="0bd5d-116">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="0bd5d-117">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="0bd5d-117">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
