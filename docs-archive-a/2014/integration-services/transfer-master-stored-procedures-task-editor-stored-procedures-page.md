---
title: Редактор задачи «перенос главных хранимых процедур» (страница «хранимые процедуры») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferstoredprocedurestask.storedprocedures.f1
helpviewer_keywords:
- Transfer Stored Procedures Task Editor
ms.assetid: 5fcf171e-cc0b-4c24-8eb5-3a4b4775e64a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5f9fad408b54d4ef27d4c5d06b0d352f366ad9c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734281"
---
# <a name="transfer-master-stored-procedures-task-editor-stored-procedures-page"></a><span data-ttu-id="a176e-102">Редактор задачи «Передача главных хранимых процедур» (страница «Хранимые процедуры»)</span><span class="sxs-lookup"><span data-stu-id="a176e-102">Transfer Master Stored Procedures Task Editor (Stored Procedures Page)</span></span>
  <span data-ttu-id="a176e-103">На странице **Хранимые процедуры** диалогового окна **Редактор задачи "Передача главных хранимых процедур"** укажите свойства для копирования одной или нескольких пользовательских хранимых процедур из базы данных **master** одного экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] в базу данных **master** другого экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a176e-103">Use the **Stored Procedures** page of the **Transfer Master Stored Procedures Task Editor** dialog box to specify properties for copying one or more user-defined stored procedures from the **master** database in one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance to a **master** database in another instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a176e-104">Дополнительные сведения об этой задаче см. в разделе [Transfer Master Stored Procedures Task](control-flow/transfer-master-stored-procedures-task.md).</span><span class="sxs-lookup"><span data-stu-id="a176e-104">For more information about this task, see [Transfer Master Stored Procedures Task](control-flow/transfer-master-stored-procedures-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a176e-105">Эта задача передает только пользовательские хранимые процедуры, принадлежащие **dbo** , из базы данных **master** на исходном сервере в базу данных **master** на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="a176e-105">This task transfers only user-defined stored procedures owned by **dbo** from a **master** database on the source server to a **master** database on the destination server.</span></span> <span data-ttu-id="a176e-106">Пользователям должно быть предоставлено разрешение CREATE PROCEDURE в базе данных **master** на целевом сервере, или они должны быть членами предопределенной роли сервера **sysadmin** на целевом сервере, чтобы создавать на нем хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="a176e-106">Users must be granted the CREATE PROCEDURE permission in the **master** database on the destination server or be members of the **sysadmin** fixed server role on the destination server to create stored procedures there.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a176e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="a176e-107">Options</span></span>  
 <span data-ttu-id="a176e-108">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="a176e-108">**SourceConnection**</span></span>  
 <span data-ttu-id="a176e-109">Выберите из списка диспетчер подключений SMO или нажмите кнопку **\<New connection...>** , чтобы создать новое подключение к исходному серверу.</span><span class="sxs-lookup"><span data-stu-id="a176e-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="a176e-110">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="a176e-110">**DestinationConnection**</span></span>  
 <span data-ttu-id="a176e-111">Выберите из списка диспетчер подключений SMO или нажмите кнопку **\<New connection...>** , чтобы создать новое подключение к целевому серверу.</span><span class="sxs-lookup"><span data-stu-id="a176e-111">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="a176e-112">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="a176e-112">**IfObjectExists**</span></span>  
 <span data-ttu-id="a176e-113">Выберите, каким способом задача будет обрабатывать пользовательские хранимые процедуры с именами, уже существующими в базе данных **master** на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="a176e-113">Select how the task should handle user-defined stored procedures of the same name that already exist in the **master** database on the destination server.</span></span>  
  
 <span data-ttu-id="a176e-114">Параметры этого свойства приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a176e-114">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="a176e-115">Значение</span><span class="sxs-lookup"><span data-stu-id="a176e-115">Value</span></span>|<span data-ttu-id="a176e-116">Description</span><span class="sxs-lookup"><span data-stu-id="a176e-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a176e-117">**FailTask**</span><span class="sxs-lookup"><span data-stu-id="a176e-117">**FailTask**</span></span>|<span data-ttu-id="a176e-118">Если в базе данных **master** на целевом сервере уже существуют хранимые процедуры с теми же именами, задача завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a176e-118">Task fails if stored procedures of the same name already exist in the **master** database on the destination server.</span></span>|  
|<span data-ttu-id="a176e-119">**Overwrite**</span><span class="sxs-lookup"><span data-stu-id="a176e-119">**Overwrite**</span></span>|<span data-ttu-id="a176e-120">Задача перезаписывает хранимые процедуры с теми же именами в базе данных **master** на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="a176e-120">Task overwrites stored procedures of the same name in the **master** database on the destination server.</span></span>|  
|<span data-ttu-id="a176e-121">**Skip**</span><span class="sxs-lookup"><span data-stu-id="a176e-121">**Skip**</span></span>|<span data-ttu-id="a176e-122">Задача пропускает хранимые процедуры с теми же именами в базе данных **master** на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="a176e-122">Task skips stored procedures of the same name that exist in the **master** database on the destination server.</span></span>|  
  
 <span data-ttu-id="a176e-123">**TransferAllStoredProcedures**</span><span class="sxs-lookup"><span data-stu-id="a176e-123">**TransferAllStoredProcedures**</span></span>  
 <span data-ttu-id="a176e-124">Укажите, все ли пользовательские хранимые процедуры в базе данных **master** на исходном сервере следует копировать на целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="a176e-124">Select whether all user-defined stored procedures in the **master** database on the source server should be copied to the destination server.</span></span>  
  
|<span data-ttu-id="a176e-125">Значение</span><span class="sxs-lookup"><span data-stu-id="a176e-125">Value</span></span>|<span data-ttu-id="a176e-126">Описание</span><span class="sxs-lookup"><span data-stu-id="a176e-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a176e-127">**True**</span><span class="sxs-lookup"><span data-stu-id="a176e-127">**True**</span></span>|<span data-ttu-id="a176e-128">Копировать все пользовательские хранимые процедуры базы данных **master** .</span><span class="sxs-lookup"><span data-stu-id="a176e-128">Copy all user-defined stored procedures in the **master** database.</span></span>|  
|<span data-ttu-id="a176e-129">**False**</span><span class="sxs-lookup"><span data-stu-id="a176e-129">**False**</span></span>|<span data-ttu-id="a176e-130">Копировать только указанные хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="a176e-130">Copy only the specified stored procedures.</span></span>|  
  
 <span data-ttu-id="a176e-131">**StoredProceduresList**</span><span class="sxs-lookup"><span data-stu-id="a176e-131">**StoredProceduresList**</span></span>  
 <span data-ttu-id="a176e-132">Укажите, какие пользовательские хранимые процедуры в базе данных **master** на исходном сервере следует копировать в целевую базу данных **master** .</span><span class="sxs-lookup"><span data-stu-id="a176e-132">Select which user-defined stored procedures in the **master** database on the source server should be copied to the destination **master** database.</span></span> <span data-ttu-id="a176e-133">Этот параметр доступен, только если параметру **TransferAllStoredProcedures** присвоено значение **False**.</span><span class="sxs-lookup"><span data-stu-id="a176e-133">This option is only available when **TransferAllStoredProcedures** is set to **False**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a176e-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="a176e-134">See Also</span></span>  
 <span data-ttu-id="a176e-135">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a176e-135">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a176e-136">[Задачи служб Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="a176e-136">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="a176e-137">[Редактор задачи "перенос главных хранимых процедур" &#40;общие&#41;страницы](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="a176e-137">[Transfer Master Stored Procedures Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="a176e-138">[Страница «Выражения»](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="a176e-138">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="a176e-139">Диспетчер соединений SMO</span><span class="sxs-lookup"><span data-stu-id="a176e-139">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
