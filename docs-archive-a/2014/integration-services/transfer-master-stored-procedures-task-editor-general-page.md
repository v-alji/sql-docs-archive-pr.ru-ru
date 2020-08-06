---
title: Редактор задачи «перенос главных хранимых процедур» (страница «Общие») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferstoredprocedurestask.general.f1
helpviewer_keywords:
- Transfer Stored Procedures Task Editor
ms.assetid: fa1abd4c-e2be-427f-be53-860e49c97227
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8a25a5c9c6ed3802e21ac522e94163ce5fb9e8c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734285"
---
# <a name="transfer-master-stored-procedures-task-editor-general-page"></a><span data-ttu-id="96a76-102">Редактор задачи «Передача главных хранимых процедур» (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="96a76-102">Transfer Master Stored Procedures Task Editor (General Page)</span></span>
  <span data-ttu-id="96a76-103">Используйте страницу **Общие** в диалоговом окне **Редактор задачи «Передача главных хранимых процедур»** , чтобы назвать и описать задачу переноса главных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="96a76-103">Use the **General** page of the **Transfer Master Stored Procedures Task Editor** dialog box to name and describe the Transfer Master Stored Procedures task.</span></span> <span data-ttu-id="96a76-104">Дополнительные сведения об этой задаче см. в разделе [Transfer Master Stored Procedures Task](control-flow/transfer-master-stored-procedures-task.md).</span><span class="sxs-lookup"><span data-stu-id="96a76-104">For more information about this task, see [Transfer Master Stored Procedures Task](control-flow/transfer-master-stored-procedures-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="96a76-105">Эта задача передает только пользовательские хранимые процедуры, принадлежащие **dbo** , из базы данных **master** на исходном сервере в базу данных **master** на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="96a76-105">This task transfers only user-defined stored procedures owned by **dbo** from a **master** database on the source server to a **master** database on the destination server.</span></span> <span data-ttu-id="96a76-106">Пользователям должно быть предоставлено разрешение CREATE PROCEDURE в базе данных **master** на целевом сервере, или они должны быть членами предопределенной роли сервера **sysadmin** на целевом сервере, чтобы создавать на нем хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="96a76-106">Users must be granted the CREATE PROCEDURE permission in the **master** database on the destination server or be members of the **sysadmin** fixed server role on the destination server to create stored procedures there.</span></span>  
  
## <a name="options"></a><span data-ttu-id="96a76-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="96a76-107">Options</span></span>  
 <span data-ttu-id="96a76-108">**Название**</span><span class="sxs-lookup"><span data-stu-id="96a76-108">**Name**</span></span>  
 <span data-ttu-id="96a76-109">Введите уникальное имя для задачи «Передача главных хранимых процедур».</span><span class="sxs-lookup"><span data-stu-id="96a76-109">Type a unique name for the Transfer Master Stored Procedures task.</span></span> <span data-ttu-id="96a76-110">Это имя используется в качестве метки для значка задачи.</span><span class="sxs-lookup"><span data-stu-id="96a76-110">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="96a76-111">Имена задач в пределах пакета должны быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="96a76-111">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="96a76-112">**Описание**</span><span class="sxs-lookup"><span data-stu-id="96a76-112">**Description**</span></span>  
 <span data-ttu-id="96a76-113">Введите описание для задачи «Передача главных хранимых процедур».</span><span class="sxs-lookup"><span data-stu-id="96a76-113">Type a description of the Transfer Master Stored Procedures task.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96a76-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="96a76-114">See Also</span></span>  
 <span data-ttu-id="96a76-115">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="96a76-115">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="96a76-116">[Задачи служб Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="96a76-116">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="96a76-117">[Редактор задачи "перенос главных хранимых процедур" &#40;страницу хранимых процедур&#41;](../../2014/integration-services/transfer-master-stored-procedures-task-editor-stored-procedures-page.md) </span><span class="sxs-lookup"><span data-stu-id="96a76-117">[Transfer Master Stored Procedures Task Editor &#40;Stored Procedures Page&#41;](../../2014/integration-services/transfer-master-stored-procedures-task-editor-stored-procedures-page.md) </span></span>  
 [<span data-ttu-id="96a76-118">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="96a76-118">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
