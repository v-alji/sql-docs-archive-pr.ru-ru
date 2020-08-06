---
title: План обслуживания, страница "Отчеты и ведение журнала" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.reportinglogging.f1
ms.assetid: 3a30b17a-3deb-446f-900a-62f88934a90f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c7a95a7092ce2cdac4aa0540a5cb57d86b48497
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658241"
---
# <a name="maintenance-plan-reporting-and-logging-page"></a><span data-ttu-id="08b2a-102">План обслуживания (страница «Отчеты и ведение журнала»)</span><span class="sxs-lookup"><span data-stu-id="08b2a-102">Maintenance Plan (Reporting and Logging Page)</span></span>
  <span data-ttu-id="08b2a-103">Диалоговое окно **Отчеты и ведение журнала** используется для настройки отчетов и журналов, созданных при выполнении планов обслуживания.</span><span class="sxs-lookup"><span data-stu-id="08b2a-103">Use the **Reporting and Logging** dialog box to configure the reports and logs that are generated when maintenance plans are executed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="08b2a-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="08b2a-104">Options</span></span>  
 <span data-ttu-id="08b2a-105">**Сформировать текстовый файл отчета**</span><span class="sxs-lookup"><span data-stu-id="08b2a-105">**Generate a text file report**</span></span>  
 <span data-ttu-id="08b2a-106">Задайте это значение, если требуется, чтобы [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] записал отчет в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="08b2a-106">Specify if you want [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to write a text file report.</span></span>  
  
 <span data-ttu-id="08b2a-107">**Создать новый файл**</span><span class="sxs-lookup"><span data-stu-id="08b2a-107">**Create a new file**</span></span>  
 <span data-ttu-id="08b2a-108">Создайте новый файл отчета для каждого выполнения плана обслуживания.</span><span class="sxs-lookup"><span data-stu-id="08b2a-108">Create a new report file for each execution of the maintenance plan.</span></span> <span data-ttu-id="08b2a-109">По умолчанию файлы отчетов записываются на тот компьютер, где установлен экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , содержащий план обслуживания, в папку, указанную во время настройки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в качестве папки журналов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08b2a-109">By default, the report files are written to the computer hosting the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that contains this maintenance plan, in the folder established as the default log folder during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup.</span></span> <span data-ttu-id="08b2a-110">Чтобы указать другую папку, введите полный путь папки в поле **Папка** или нажмите кнопку "Обзор" ( **...** ) и перейдите в нужную папку.</span><span class="sxs-lookup"><span data-stu-id="08b2a-110">To specify a different folder, enter the full path of the folder in the **Folder** text box, or click the browse button (**...**) and navigate to the desired folder.</span></span>  
  
 <span data-ttu-id="08b2a-111">**Добавить к файлу**</span><span class="sxs-lookup"><span data-stu-id="08b2a-111">**Append to file**</span></span>  
 <span data-ttu-id="08b2a-112">Добавлять отчет после каждого выполнения плана к файлу, заданному в текстовом поле **Имя файла** .</span><span class="sxs-lookup"><span data-stu-id="08b2a-112">Append the report from each plan execution to the file specified in the **File name** text box.</span></span> <span data-ttu-id="08b2a-113">Также можно задать файл, нажав кнопку обзора и выбрав файл из диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="08b2a-113">You may also specify a file by clicking the browse button and selecting a file from the dialog box.</span></span>  
  
 <span data-ttu-id="08b2a-114">**Отправить отчет адресату по электронной почте**</span><span class="sxs-lookup"><span data-stu-id="08b2a-114">**Send report to an e-mail recipient**</span></span>  
 <span data-ttu-id="08b2a-115">Передайте результат выполнения плана обслуживания по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="08b2a-115">Transmit the outcome of a maintenance plan execution via e-mail.</span></span> <span data-ttu-id="08b2a-116">Данный параметр доступен только, если включен и надлежащим образом настроен компонент Database Mail.</span><span class="sxs-lookup"><span data-stu-id="08b2a-116">This option is only available if Database Mail is enabled and properly configured.</span></span>  
  
 <span data-ttu-id="08b2a-117">**Оператор агента**</span><span class="sxs-lookup"><span data-stu-id="08b2a-117">**Agent operator**</span></span>  
 <span data-ttu-id="08b2a-118">Выберите из списка агента оператора, который будет являться получателем электронной почты.</span><span class="sxs-lookup"><span data-stu-id="08b2a-118">Select an agent operator from the list who will be the recipient of the e-mail.</span></span> <span data-ttu-id="08b2a-119">Данный параметр доступен, только если включена и надлежащим образом настроена почта.</span><span class="sxs-lookup"><span data-stu-id="08b2a-119">This option is only available if mail is enabled and properly</span></span>  
  
 <span data-ttu-id="08b2a-120">**Записывать подробные данные в журнал**</span><span class="sxs-lookup"><span data-stu-id="08b2a-120">**Log extended information**</span></span>  
 <span data-ttu-id="08b2a-121">Включите дополнительные данные в журнал.</span><span class="sxs-lookup"><span data-stu-id="08b2a-121">Include more information in the log.</span></span> <span data-ttu-id="08b2a-122">Включение данного параметра приведет к увеличению размера хранимого журнала планов обслуживания.</span><span class="sxs-lookup"><span data-stu-id="08b2a-122">Including this option will increase the size of the stored maintenance plan history.</span></span>  
  
 <span data-ttu-id="08b2a-123">**Войти на удаленный сервер**</span><span class="sxs-lookup"><span data-stu-id="08b2a-123">**Log to remote server**</span></span>  
 <span data-ttu-id="08b2a-124">Записывает журнал плана обслуживания на удаленном сервере.</span><span class="sxs-lookup"><span data-stu-id="08b2a-124">Logs maintenance plan history to a remote server.</span></span>  
  
 <span data-ttu-id="08b2a-125">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="08b2a-125">**Connection**</span></span>  
 <span data-ttu-id="08b2a-126">Задает сведения о соединении, которые записываются в журнал плана обслуживания на удаленном сервере.</span><span class="sxs-lookup"><span data-stu-id="08b2a-126">Specifies the connection information to use when logging to a remote server.</span></span>  
  
 <span data-ttu-id="08b2a-127">**Создать**</span><span class="sxs-lookup"><span data-stu-id="08b2a-127">**New**</span></span>  
 <span data-ttu-id="08b2a-128">Вызывает диалоговое окно **Свойства соединения** .</span><span class="sxs-lookup"><span data-stu-id="08b2a-128">Displays the **Connection Properties** dialog box.</span></span> <span data-ttu-id="08b2a-129">Используется для указания новых сведений о соединении, которые записываются в журнал плана обслуживания на удаленном сервере.</span><span class="sxs-lookup"><span data-stu-id="08b2a-129">Used to configure new connection information for logging to a remote server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08b2a-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="08b2a-130">See Also</span></span>  
 <span data-ttu-id="08b2a-131">[Планы обслуживания](maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="08b2a-131">[Maintenance Plans](maintenance-plans.md) </span></span>  
 [<span data-ttu-id="08b2a-132">Database Mail</span><span class="sxs-lookup"><span data-stu-id="08b2a-132">Database Mail</span></span>](../database-mail/database-mail.md)  
  
  
