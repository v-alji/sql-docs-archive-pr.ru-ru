---
title: Редактор задачи «FTP» (страница «Общие») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftptask.general.f1
helpviewer_keywords:
- File Transfer Protocol Task Editor
ms.assetid: 28b46fdd-b04a-4f97-a99f-883f5735a6d9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0cb4ffe2fa44e76890f6b70912f84dbcaa8f2cd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657155"
---
# <a name="ftp-task-editor-general-page"></a><span data-ttu-id="254c0-102">Редактор задачи «FTP» (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="254c0-102">FTP Task Editor (General Page)</span></span>
  <span data-ttu-id="254c0-103">Используйте страницу **Общие** диалогового окна **Редактор задачи «FTP»** для задания диспетчера FTP-соединений, выполняющего соединение с FTP-сервером, с которым задача обменивается данными.</span><span class="sxs-lookup"><span data-stu-id="254c0-103">Use the **General** page of the **FTP Task Editor** dialog box to specify the FTP connection manager that connects to the FTP server that the task communicates with.</span></span> <span data-ttu-id="254c0-104">Также здесь можно указать имя и описание задачи «FTP».</span><span class="sxs-lookup"><span data-stu-id="254c0-104">You can also name and describe the FTP task.</span></span>  
  
 <span data-ttu-id="254c0-105">Дополнительные сведения об этой задаче см. в разделе [Задача FTP](control-flow/ftp-task.md).</span><span class="sxs-lookup"><span data-stu-id="254c0-105">To learn about this task, see [FTP Task](control-flow/ftp-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="254c0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="254c0-106">Options</span></span>  
 <span data-ttu-id="254c0-107">**FtpConnection**</span><span class="sxs-lookup"><span data-stu-id="254c0-107">**FtpConnection**</span></span>  
 <span data-ttu-id="254c0-108">Выберите существующий диспетчер подключений FTP или создайте его, щелкнув пункт \<**New connection...**>.</span><span class="sxs-lookup"><span data-stu-id="254c0-108">Select an existing FTP connection manager, or click \<**New connection...**> to create a connection manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="254c0-109">Диспетчер FTP-соединений поддерживает только анонимную проверку подлинности и обычную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="254c0-109">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="254c0-110">Проверка подлинности Windows не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="254c0-110">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="254c0-111">**См. также**: [Диспетчер FTP-сеансов](connection-manager/ftp-connection-manager.md), [Редактор диспетчера FTP-сеансов](../../2014/integration-services/ftp-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="254c0-111">**Related Topics**: [FTP Connection Manager](connection-manager/ftp-connection-manager.md), [FTP Connection Manager Editor](../../2014/integration-services/ftp-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="254c0-112">**StopOnFailure**</span><span class="sxs-lookup"><span data-stu-id="254c0-112">**StopOnFailure**</span></span>  
 <span data-ttu-id="254c0-113">Укажите, следует ли завершить задачу «FTP» в случае ошибки операции с FTP.</span><span class="sxs-lookup"><span data-stu-id="254c0-113">Indicate whether the FTP task terminates if an FTP operation fails.</span></span>  
  
 <span data-ttu-id="254c0-114">**имя**;</span><span class="sxs-lookup"><span data-stu-id="254c0-114">**Name**</span></span>  
 <span data-ttu-id="254c0-115">Задайте уникальное имя задачи «FTP».</span><span class="sxs-lookup"><span data-stu-id="254c0-115">Provide a unique name for the FTP task.</span></span> <span data-ttu-id="254c0-116">Это имя используется в качестве метки для значка задачи.</span><span class="sxs-lookup"><span data-stu-id="254c0-116">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="254c0-117">Имена задач в пределах пакета должны быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="254c0-117">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="254c0-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="254c0-118">**Description**</span></span>  
 <span data-ttu-id="254c0-119">Введите описание задачи «FTP».</span><span class="sxs-lookup"><span data-stu-id="254c0-119">Type a description of the FTP task.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="254c0-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="254c0-120">See Also</span></span>  
 <span data-ttu-id="254c0-121">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="254c0-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="254c0-122">[Редактор задачи "FTP" &#40;страницу "перенос файлов"&#41;](../../2014/integration-services/ftp-task-editor-file-transfer-page.md) </span><span class="sxs-lookup"><span data-stu-id="254c0-122">[FTP Task Editor &#40;File Transfer Page&#41;](../../2014/integration-services/ftp-task-editor-file-transfer-page.md) </span></span>  
 [<span data-ttu-id="254c0-123">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="254c0-123">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
