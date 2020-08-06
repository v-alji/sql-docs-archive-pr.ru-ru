---
title: MSSQLSERVER_8525 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "8525"
helpviewer_keywords:
- 8525 (Database Engine error)
ms.assetid: 297867c1-691e-4d6b-a3be-a7575015ecfa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 36db48ca2a9afd08dadcd12abc13b9978e227b00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666080"
---
# <a name="mssqlserver_8525"></a><span data-ttu-id="55035-102">MSSQLSERVER_8525</span><span class="sxs-lookup"><span data-stu-id="55035-102">MSSQLSERVER_8525</span></span>
    
## <a name="details"></a><span data-ttu-id="55035-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="55035-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="55035-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="55035-104">Product Name</span></span>|<span data-ttu-id="55035-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="55035-105">SQL Server</span></span>|  
|<span data-ttu-id="55035-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="55035-106">Event ID</span></span>|<span data-ttu-id="55035-107">8525</span><span class="sxs-lookup"><span data-stu-id="55035-107">8525</span></span>|  
|<span data-ttu-id="55035-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="55035-108">Event Source</span></span>|<span data-ttu-id="55035-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="55035-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="55035-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="55035-110">Component</span></span>|<span data-ttu-id="55035-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="55035-111">SQLEngine</span></span>|  
|<span data-ttu-id="55035-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="55035-112">Symbolic Name</span></span>||  
|<span data-ttu-id="55035-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="55035-113">Message Text</span></span>|<span data-ttu-id="55035-114">Распределенная транзакция завершена.</span><span class="sxs-lookup"><span data-stu-id="55035-114">Distributed transaction completed.</span></span> <span data-ttu-id="55035-115">Прикрепите этот сеанс к новой транзакции или транзакции NULL.</span><span class="sxs-lookup"><span data-stu-id="55035-115">Either enlist this session in a new transaction or the NULL transaction.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="55035-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="55035-116">Explanation</span></span>  
 <span data-ttu-id="55035-117">Модель программирования, применяемая в координаторе распределенных транзакций с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], требует, чтобы приложения явно прикреплялись к распределенным транзакциям и исключались из них.</span><span class="sxs-lookup"><span data-stu-id="55035-117">The programming model for using the Distributed Transaction Coordinator with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires applications to explicitly enlist to and defect from a distributed transaction.</span></span>  
  
 <span data-ttu-id="55035-118">Это происходит, если выполняются перечисленные ниже условия.</span><span class="sxs-lookup"><span data-stu-id="55035-118">This error occurs when the following four conditions are met:</span></span>  
  
-   <span data-ttu-id="55035-119">Приложение прикреплено к распределенной транзакции.</span><span class="sxs-lookup"><span data-stu-id="55035-119">The application has enlisted into a distributed transaction.</span></span>  
  
-   <span data-ttu-id="55035-120">Транзакция завершилась фиксацией или откатом по любой причине.</span><span class="sxs-lookup"><span data-stu-id="55035-120">The transaction has ended, either committed or rolled back, for any reason.</span></span>  
  
-   <span data-ttu-id="55035-121">Приложение пользователя не отключилось явным образом от распределенной транзакции, либо не было явно прикреплено к новой.</span><span class="sxs-lookup"><span data-stu-id="55035-121">The user application has not explicitly defected from a distributed transaction or explicitly enlisted into a new distributed transaction.</span></span>  
  
-   <span data-ttu-id="55035-122">Приложение пытается выполнить транзакционную операцию, которая не является отключением от существующей распределенной транзакции или прикреплением к новой, например выполняет запрос или запускает локальную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="55035-122">The application tries to do any transactional operation other than defecting from existing distributed transaction or enlisting to a new distributed transaction, such as issuing a query or starting a local transaction.</span></span>  
  
 <span data-ttu-id="55035-123">Состояние ошибки 1 используется в тех случаях, когда приложение выполняет операцию, создающую локальные транзакции, а состояние 2 — когда приложение пытается прикрепиться к связанному сеансу.</span><span class="sxs-lookup"><span data-stu-id="55035-123">Error state 1 is used when the application performs an operation that creates local transactions, and state 2 is used when application tries to enlist to a bound session.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="55035-124">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="55035-124">User Action</span></span>  
 <span data-ttu-id="55035-125">После того как приложение прикрепится к распределенной транзакции, оно должно явным образом отключиться от распределенной транзакции или присоединиться к другой распределенной транзакции.</span><span class="sxs-lookup"><span data-stu-id="55035-125">After an application has enlisted into a distributed transaction, the application must explicitly defect from the distributed transaction or enlist to another distributed transaction.</span></span> <span data-ttu-id="55035-126">Это приведет к неявному отключению от предыдущей прикрепленной транзакции.</span><span class="sxs-lookup"><span data-stu-id="55035-126">This will implicitly defect from a previous enlisted transaction.</span></span> <span data-ttu-id="55035-127">Точный синтаксис отключения от распределенной транзакции или прикрепления к ней см. в руководстве по программному интерфейсу для приложения.</span><span class="sxs-lookup"><span data-stu-id="55035-127">For the exact syntax to defect from or enlist to a distributed transaction, see the programming interface manual for the application.</span></span>  
  
  
