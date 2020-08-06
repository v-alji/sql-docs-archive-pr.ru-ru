---
title: Свойства предупреждения — Создание предупреждения (страница "ответ") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.response.f1
ms.assetid: 72daf008-f9ea-4077-b217-5048e7759d3e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 34e7f11ff3210ec4fc1835751bc35b140d3fa0ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737490"
---
# <a name="alert-properties-new-alert-response-page"></a><span data-ttu-id="2fac6-102">Свойства предупреждения — Создание предупреждения (страница «ответ»)</span><span class="sxs-lookup"><span data-stu-id="2fac6-102">Alert Properties-New Alert (Response Page)</span></span>
  <span data-ttu-id="2fac6-103">Используйте эту страницу, чтобы указать задание, которое требуется запустить, и получить список операторов, которые должны получать уведомления в ответ на [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предупреждение агента.</span><span class="sxs-lookup"><span data-stu-id="2fac6-103">Use this page to specify a job that you want to run and to obtain a list of operators to be notified in response to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2fac6-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="2fac6-104">Options</span></span>  
 <span data-ttu-id="2fac6-105">**Выполнить задание**</span><span class="sxs-lookup"><span data-stu-id="2fac6-105">**Execute job**</span></span>  
 <span data-ttu-id="2fac6-106">Включает параметры **Список заданий**, **Создать задание** и **Просмотреть задание** .</span><span class="sxs-lookup"><span data-stu-id="2fac6-106">Enables the **Job list**, **New job** and **View job** options.</span></span>  
  
 <span data-ttu-id="2fac6-107">**Создать задание**</span><span class="sxs-lookup"><span data-stu-id="2fac6-107">**New job**</span></span>  
 <span data-ttu-id="2fac6-108">Откройте диалоговое окно **Создать задание** .</span><span class="sxs-lookup"><span data-stu-id="2fac6-108">Open the **New Job** dialog box.</span></span> <span data-ttu-id="2fac6-109">Эта кнопка недоступна, если не установлен флажок **Выполнить задание** .</span><span class="sxs-lookup"><span data-stu-id="2fac6-109">This button is not available when **Execute job** is not selected.</span></span>  
  
 <span data-ttu-id="2fac6-110">**Просмотр задания**</span><span class="sxs-lookup"><span data-stu-id="2fac6-110">**View job**</span></span>  
 <span data-ttu-id="2fac6-111">Просмотреть или изменить выбранное задание.</span><span class="sxs-lookup"><span data-stu-id="2fac6-111">View or modify the selected job.</span></span> <span data-ttu-id="2fac6-112">Этот параметр недоступен, если не установлен флажок **Выполнить задание** .</span><span class="sxs-lookup"><span data-stu-id="2fac6-112">This option is not available when **Execute job** is not selected.</span></span>  
  
 <span data-ttu-id="2fac6-113">**Уведомить операторов**</span><span class="sxs-lookup"><span data-stu-id="2fac6-113">**Notify operators**</span></span>  
 <span data-ttu-id="2fac6-114">Включает элементы управления, которые используются для добавления, удаления и изменения операторов.</span><span class="sxs-lookup"><span data-stu-id="2fac6-114">Enables the controls that allow you to add, remove, or change operators.</span></span>  
  
 <span data-ttu-id="2fac6-115">**Список операторов**</span><span class="sxs-lookup"><span data-stu-id="2fac6-115">**Operator list**</span></span>  
 <span data-ttu-id="2fac6-116">Перечисляет операторов, которые должны получать уведомления при появлении предупреждения.</span><span class="sxs-lookup"><span data-stu-id="2fac6-116">Lists the operators to notify when an alert occurs.</span></span> <span data-ttu-id="2fac6-117">Чтобы указать метод уведомления, установите флажок **Электронная почта**, **Пейджер**или **Net send** , отображаемый после имени оператора. Этот параметр недоступен, если флажок **Уведомить операторов** не установлен.</span><span class="sxs-lookup"><span data-stu-id="2fac6-117">To specify a notification method, select the **E-mail**, **Pager**, or **Net send** check box that is displayed after the operator name.This option not available when **Notify operators** is not selected.</span></span>  
  
 <span data-ttu-id="2fac6-118">**Электронных**</span><span class="sxs-lookup"><span data-stu-id="2fac6-118">**E-mail**</span></span>  
 <span data-ttu-id="2fac6-119">Использовать электронную почту, чтобы уведомить оператора.</span><span class="sxs-lookup"><span data-stu-id="2fac6-119">Use e-mail to notify the operator.</span></span>  
  
 <span data-ttu-id="2fac6-120">**Пейджер**</span><span class="sxs-lookup"><span data-stu-id="2fac6-120">**Pager**</span></span>  
 <span data-ttu-id="2fac6-121">Использовать адрес электронной почты пейджера, чтобы уведомить оператора.</span><span class="sxs-lookup"><span data-stu-id="2fac6-121">Use the pager e-mail address to notify the operator.</span></span>  
  
 <span data-ttu-id="2fac6-122">**NET SEND**</span><span class="sxs-lookup"><span data-stu-id="2fac6-122">**Net send**</span></span>  
 <span data-ttu-id="2fac6-123">Использовать команду **net send** , чтобы уведомить оператора.</span><span class="sxs-lookup"><span data-stu-id="2fac6-123">Use **net send** to notify the operator.</span></span>  
  
 <span data-ttu-id="2fac6-124">**Оператор New**</span><span class="sxs-lookup"><span data-stu-id="2fac6-124">**New operator**</span></span>  
 <span data-ttu-id="2fac6-125">Отображает диалоговое окно **Создать оператора** , которое используется для создания новых операторов.</span><span class="sxs-lookup"><span data-stu-id="2fac6-125">Displays the **New Operator** dialog box, which you can use to create a new operator.</span></span>  
  
 <span data-ttu-id="2fac6-126">**Просмотр оператора**</span><span class="sxs-lookup"><span data-stu-id="2fac6-126">**View operator**</span></span>  
 <span data-ttu-id="2fac6-127">Отображается диалоговое окно **Свойства** для текущего выбранного оператора.</span><span class="sxs-lookup"><span data-stu-id="2fac6-127">Displays the **Properties** dialog box for the currently selected operator.</span></span> <span data-ttu-id="2fac6-128">Свойства операторов можно просматривать и изменять в диалоговом окне **Свойства оператора**.</span><span class="sxs-lookup"><span data-stu-id="2fac6-128">You can view and modified operator properties on the **Operator Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fac6-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="2fac6-129">See Also</span></span>  
 <span data-ttu-id="2fac6-130">[Alerts](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="2fac6-130">[Alerts](alerts.md) </span></span>  
 <span data-ttu-id="2fac6-131">[Создание предупреждения с использованием уровня серьезности](create-an-alert-using-severity-level.md) </span><span class="sxs-lookup"><span data-stu-id="2fac6-131">[Create an Alert Using Severity Level](create-an-alert-using-severity-level.md) </span></span>  
 <span data-ttu-id="2fac6-132">[Alerts](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="2fac6-132">[Alerts](alerts.md) </span></span>  
 <span data-ttu-id="2fac6-133">[Изменение оповещения](edit-an-alert.md) </span><span class="sxs-lookup"><span data-stu-id="2fac6-133">[Edit an Alert](edit-an-alert.md) </span></span>  
 [<span data-ttu-id="2fac6-134">Удаление предупреждения</span><span class="sxs-lookup"><span data-stu-id="2fac6-134">Delete an Alert</span></span>](delete-an-alert.md)  
  
  
