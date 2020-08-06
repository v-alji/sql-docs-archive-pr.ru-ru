---
title: Свойства агента SQL Server (страница "Общие") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.general.f1
ms.assetid: b51601e9-5454-43c6-bb5e-24eb2ff043c8
author: stevestein
ms.author: sstein
ms.openlocfilehash: a67d5431be4025c18b11d6791b016fa83e957810
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667526"
---
# <a name="sql-server-agent-properties-general-page"></a><span data-ttu-id="2dfff-102">Свойства агента SQL Server (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="2dfff-102">SQL Server Agent Properties (General Page)</span></span>
  <span data-ttu-id="2dfff-103">Эта страница используется для просмотра и изменения общих свойств [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] службы агента.</span><span class="sxs-lookup"><span data-stu-id="2dfff-103">Use this page to view and modify the general properties of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2dfff-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="2dfff-104">Options</span></span>  
 <span data-ttu-id="2dfff-105">**Состояние службы**</span><span class="sxs-lookup"><span data-stu-id="2dfff-105">**Service state**</span></span>  
 <span data-ttu-id="2dfff-106">Отображается текущее состояние службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2dfff-106">Displays the current state of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
 <span data-ttu-id="2dfff-107">**Автоматический перезапуск SQL Server в случае его неожиданной остановки**</span><span class="sxs-lookup"><span data-stu-id="2dfff-107">**Auto restart SQL Server if it stops unexpectedly**</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2dfff-108">Агент перезапускает [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при непредвиденной остановке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2dfff-108">Agent restarts [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stops unexpectedly.</span></span>  
  
 <span data-ttu-id="2dfff-109">**Автоматический перезапуск агента SQL Server в случае его неожиданной остановки**</span><span class="sxs-lookup"><span data-stu-id="2dfff-109">**Auto restart SQL Server Agent if it stops unexpectedly**</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2dfff-110">перезапускает агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при непредвиденной остановке агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2dfff-110">restarts [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent stops unexpectedly.</span></span>  
  
 <span data-ttu-id="2dfff-111">**Файлов**</span><span class="sxs-lookup"><span data-stu-id="2dfff-111">**Filename**</span></span>  
 <span data-ttu-id="2dfff-112">Укажите имя файла для журнала ошибок.</span><span class="sxs-lookup"><span data-stu-id="2dfff-112">Specify the file name for the error log.</span></span>  
  
 <span data-ttu-id="2dfff-113">**...**</span><span class="sxs-lookup"><span data-stu-id="2dfff-113">**...**</span></span>  
 <span data-ttu-id="2dfff-114">Перейдите к файлу журнала ошибок.</span><span class="sxs-lookup"><span data-stu-id="2dfff-114">Browse to the error log file.</span></span>  
  
 <span data-ttu-id="2dfff-115">**Включая трассировочные сообщения**</span><span class="sxs-lookup"><span data-stu-id="2dfff-115">**Include execution trace messages**</span></span>  
 <span data-ttu-id="2dfff-116">Сообщения трассировки выполнения включаются в журнал ошибок.</span><span class="sxs-lookup"><span data-stu-id="2dfff-116">Includes execution trace messages in the error log.</span></span> <span data-ttu-id="2dfff-117">Сообщения трассировки предоставляют подробные сведения о работе агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2dfff-117">Trace messages provide detailed information on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operation.</span></span> <span data-ttu-id="2dfff-118">Поэтому при выборе этого параметра для файла журнала необходимо дополнительное место на диске.</span><span class="sxs-lookup"><span data-stu-id="2dfff-118">Therefore, the log file requires more disk space when this option is selected.</span></span> <span data-ttu-id="2dfff-119">Этот параметр нужно выбирать только для устранения неполадок, связанных с агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2dfff-119">This option should only be selected while troubleshooting a problem that may involve [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
 <span data-ttu-id="2dfff-120">**Записать файл OEM**</span><span class="sxs-lookup"><span data-stu-id="2dfff-120">**Write OEM file**</span></span>  
 <span data-ttu-id="2dfff-121">Запись файла журнала ошибок производится не в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="2dfff-121">Writes the error log file as a non-Unicode file.</span></span> <span data-ttu-id="2dfff-122">Это позволяет уменьшить место на диске, необходимое для файла журнала.</span><span class="sxs-lookup"><span data-stu-id="2dfff-122">This reduces the amount of disk space consumed by the log file.</span></span> <span data-ttu-id="2dfff-123">Однако при включении этого параметра могут возникнуть трудности с чтением сообщений, содержащих данные в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="2dfff-123">However, messages that include Unicode data may be more difficult to read when this option is enabled.</span></span>  
  
 <span data-ttu-id="2dfff-124">**Получатель для команды net send**</span><span class="sxs-lookup"><span data-stu-id="2dfff-124">**Net send recipient**</span></span>  
 <span data-ttu-id="2dfff-125">Введите имя оператора, получающего уведомления, отправленные командой net send, с сообщениями, которые агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] записывает в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="2dfff-125">Type the name of an operator to receive net send notification of messages that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent writes to the log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dfff-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="2dfff-126">See Also</span></span>  
 <span data-ttu-id="2dfff-127">[Операторы](operators.md) </span><span class="sxs-lookup"><span data-stu-id="2dfff-127">[Operators](operators.md) </span></span>  
 [<span data-ttu-id="2dfff-128">Журнал ошибок агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="2dfff-128">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
