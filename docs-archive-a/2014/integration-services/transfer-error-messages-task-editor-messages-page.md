---
title: Редактор задачи «перенос сообщений об ошибках» (страница «сообщения») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfererrormessagestask.errormessages.F1
helpviewer_keywords:
- Transfer Error Messages Task Editor
ms.assetid: cb2226a0-3037-4fdf-966f-81eabc0da9cf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a0d626f01e05a30777810b26880da5aedc3e7ad3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669472"
---
# <a name="transfer-error-messages-task-editor-messages-page"></a><span data-ttu-id="bdaf8-102">Редактор задачи «Передача сообщений об ошибках» (страница «Сообщения»)</span><span class="sxs-lookup"><span data-stu-id="bdaf8-102">Transfer Error Messages Task Editor (Messages Page)</span></span>
  <span data-ttu-id="bdaf8-103">Используйте страницу **Сообщения** диалогового окна **Редактор задачи "Передача сообщений об ошибках"** , чтобы указать свойства копирования одного или более определенных пользователем сообщений об ошибках [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] из одного экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] в другой.</span><span class="sxs-lookup"><span data-stu-id="bdaf8-103">Use the **Messages** page of the **Transfer Error Messages Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] user-defined error messages from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="bdaf8-104">Дополнительные сведения об этой задаче см. в разделе [Transfer Error Messages Task](control-flow/transfer-error-messages-task.md).</span><span class="sxs-lookup"><span data-stu-id="bdaf8-104">For more information about this task, see [Transfer Error Messages Task](control-flow/transfer-error-messages-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="bdaf8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bdaf8-105">Options</span></span>  
 <span data-ttu-id="bdaf8-106">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="bdaf8-106">**SourceConnection**</span></span>  
 <span data-ttu-id="bdaf8-107">Выберите из списка диспетчер подключений SMO или нажмите кнопку **\<New connection...>** , чтобы создать новое подключение к исходному серверу.</span><span class="sxs-lookup"><span data-stu-id="bdaf8-107">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="bdaf8-108">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="bdaf8-108">**DestinationConnection**</span></span>  
 <span data-ttu-id="bdaf8-109">Выберите из списка диспетчер подключений SMO или нажмите кнопку **\<New connection...>** , чтобы создать новое подключение к целевому серверу.</span><span class="sxs-lookup"><span data-stu-id="bdaf8-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="bdaf8-110">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="bdaf8-110">**IfObjectExists**</span></span>  
 <span data-ttu-id="bdaf8-111">Выберите, следует ли при выполнении задачи перезаписать существующие пользовательские сообщения об ошибках, оставить их без изменения или зарегистрировать сбой в случае, если сообщения об ошибках с тем же именем уже существуют на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="bdaf8-111">Select whether the task should overwrite existing user-defined error messages, skip existing messages, or fail if error messages of the same name already exist on the destination server.</span></span>  
  
 <span data-ttu-id="bdaf8-112">**TransferAllErrorMessages**</span><span class="sxs-lookup"><span data-stu-id="bdaf8-112">**TransferAllErrorMessages**</span></span>  
 <span data-ttu-id="bdaf8-113">Выберите, следует ли при выполнении задачи копировать все или только указанные пользовательские сообщения с исходного сервера на целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="bdaf8-113">Select whether the task should copy all or only the specified user-defined messages from the source server to the destination server.</span></span>  
  
 <span data-ttu-id="bdaf8-114">Параметры этого свойства приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="bdaf8-114">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="bdaf8-115">Значение</span><span class="sxs-lookup"><span data-stu-id="bdaf8-115">Value</span></span>|<span data-ttu-id="bdaf8-116">Описание</span><span class="sxs-lookup"><span data-stu-id="bdaf8-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bdaf8-117">**True**</span><span class="sxs-lookup"><span data-stu-id="bdaf8-117">**True**</span></span>|<span data-ttu-id="bdaf8-118">Копировать все пользовательские сообщения.</span><span class="sxs-lookup"><span data-stu-id="bdaf8-118">Copy all user-defined messages.</span></span>|  
|<span data-ttu-id="bdaf8-119">**False**</span><span class="sxs-lookup"><span data-stu-id="bdaf8-119">**False**</span></span>|<span data-ttu-id="bdaf8-120">Копировать только указанные пользовательские сообщения.</span><span class="sxs-lookup"><span data-stu-id="bdaf8-120">Copy only the specified user-defined messages.</span></span>|  
  
 <span data-ttu-id="bdaf8-121">**ErrorMessagesList**</span><span class="sxs-lookup"><span data-stu-id="bdaf8-121">**ErrorMessagesList**</span></span>  
 <span data-ttu-id="bdaf8-122">Нажмите кнопку обзора, обозначенную многоточием **(...)** , чтобы выбрать сообщения об ошибках для копирования.</span><span class="sxs-lookup"><span data-stu-id="bdaf8-122">Click the browse button **(...)** to select the error messages to copy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bdaf8-123">Необходимо указать значение параметра **SourceConnection** прежде, чем можно будет выбрать сообщения об ошибках для копирования.</span><span class="sxs-lookup"><span data-stu-id="bdaf8-123">You must specify the **SourceConnection** before you can select error messages to copy.</span></span>  
  
 <span data-ttu-id="bdaf8-124">**ErrorMessageLanguagesList**</span><span class="sxs-lookup"><span data-stu-id="bdaf8-124">**ErrorMessageLanguagesList**</span></span>  
 <span data-ttu-id="bdaf8-125">Нажмите кнопку обзора, обозначенную многоточием **(...)** , чтобы выбрать языки, для которых должны быть скопированы на целевой сервер пользовательские сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="bdaf8-125">Click the browse button **(...)** to select the languages for which to copy user-defined error messages to the destination server.</span></span> <span data-ttu-id="bdaf8-126">Прежде чем можно будет передать на целевой сервер версии сообщения на других языках, на нем должна существовать англоязычная версия сообщения (кодовая страница 1033, us_english).</span><span class="sxs-lookup"><span data-stu-id="bdaf8-126">A us_english (code page 1033) version of the message must exist on the destination server before you can transfer other language versions of the message to that server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bdaf8-127">Необходимо указать значение параметра **SourceConnection** прежде, чем можно будет выбрать сообщения об ошибках для копирования.</span><span class="sxs-lookup"><span data-stu-id="bdaf8-127">You must specify the **SourceConnection** before you can select error messages to copy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdaf8-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="bdaf8-128">See Also</span></span>  
 <span data-ttu-id="bdaf8-129">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="bdaf8-129">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="bdaf8-130">[Задачи служб Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="bdaf8-130">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="bdaf8-131">[Редактор задачи "перенаправление сообщений об ошибках" &#40;общие&#41;страницы](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="bdaf8-131">[Transfer Error Messages Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="bdaf8-132">[Диспетчер соединений SMO](connection-manager/smo-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="bdaf8-132">[SMO Connection Manager](connection-manager/smo-connection-manager.md) </span></span>  
 <span data-ttu-id="bdaf8-133">[Редактор задачи "перенаправление сообщений об ошибках" &#40;общие&#41;страницы](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="bdaf8-133">[Transfer Error Messages Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="bdaf8-134">Диспетчер соединений SMO</span><span class="sxs-lookup"><span data-stu-id="bdaf8-134">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
