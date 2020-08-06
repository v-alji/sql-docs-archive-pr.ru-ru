---
title: Приложение sqlagent90 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- starting SQL Server Agent
- sqlagent90 application
- SQL Server Agent, starting
- command prompt utilities [SQL Server], sqlagent90
ms.assetid: e8b80e8d-d0c9-4500-a868-0ce08233da08
author: stevestein
ms.author: sstein
ms.openlocfilehash: 290cb69f39aa3b08bb290c210b2d37977614a1ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657438"
---
# <a name="sqlagent90-application"></a><span data-ttu-id="ac5ce-102">sqlagent90, приложение</span><span class="sxs-lookup"><span data-stu-id="ac5ce-102">sqlagent90 Application</span></span>
  <span data-ttu-id="ac5ce-103">Приложение **sqlagent90** запускает агент [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] из командной строки.</span><span class="sxs-lookup"><span data-stu-id="ac5ce-103">The **sqlagent90** application starts [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent from the command prompt.</span></span> <span data-ttu-id="ac5ce-104">Обычно агент [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] должен запускаться из среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] или с помощью методов SQL-DMO в приложении.</span><span class="sxs-lookup"><span data-stu-id="ac5ce-104">Usually, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should be run from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or by using SQL-SMO methods in an application.</span></span> <span data-ttu-id="ac5ce-105">Запускайте приложение **sqlagent90** из командной строки только, когда выполняется диагностика агента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] или если такое указание получено от основного поставщика поддержки.</span><span class="sxs-lookup"><span data-stu-id="ac5ce-105">Only run **sqlagent90** from the command prompt when you are diagnosing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent, or when you are directed to it by your primary support provider.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac5ce-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac5ce-106">Syntax</span></span>  
  
```  
  
sqlagent90  
-c [-v] [-iinstance_name]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ac5ce-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ac5ce-107">Arguments</span></span>  
 <span data-ttu-id="ac5ce-108">**-c**</span><span class="sxs-lookup"><span data-stu-id="ac5ce-108">**-c**</span></span>  
 <span data-ttu-id="ac5ce-109">Указывает, что агент [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] запускается из командной строки и не зависит от диспетчера управления службами Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="ac5ce-109">Indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent is running from the command prompt and is independent of the Microsoft Windows Services Control Manager.</span></span> <span data-ttu-id="ac5ce-110">При использовании параметра **-c** агентом [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] нельзя управлять с помощью оснастки "Службы" в элементе "Администрирование" панели управления и из диспетчера конфигурации [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac5ce-110">When **-c** is used, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent cannot be controlled from either the Services application in Administrative Tools or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="ac5ce-111">Этот аргумент является обязательным.</span><span class="sxs-lookup"><span data-stu-id="ac5ce-111">This argument is mandatory.</span></span>  
  
 <span data-ttu-id="ac5ce-112">**-v**</span><span class="sxs-lookup"><span data-stu-id="ac5ce-112">**-v**</span></span>  
 <span data-ttu-id="ac5ce-113">Указывает, что агент [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] работает в подробном режиме и производит запись диагностических данных в окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="ac5ce-113">Indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent runs in verbose mode and writes diagnostic information to the command-prompt window.</span></span> <span data-ttu-id="ac5ce-114">Диагностические данные — это те же данные, которые записываются в журнал ошибок агента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac5ce-114">The diagnostic information is the same as the information written to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent error log.</span></span>  
  
 <span data-ttu-id="ac5ce-115">**-i** *имя_экземпляра*</span><span class="sxs-lookup"><span data-stu-id="ac5ce-115">**-i** *instance_name*</span></span>  
 <span data-ttu-id="ac5ce-116">Указывает, что агент [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] подключается к именованному экземпляру [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , определенному аргументом *имя_экземпляра*.</span><span class="sxs-lookup"><span data-stu-id="ac5ce-116">Indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent connects to the named [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance specified by *instance_name*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac5ce-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="ac5ce-117">Remarks</span></span>  
 <span data-ttu-id="ac5ce-118">После отображения сообщения с указанием авторских прав приложение **sqlagent90** отображает выводимые данные в окне командной строки, только если указан параметр **-v** .</span><span class="sxs-lookup"><span data-stu-id="ac5ce-118">After displaying a copyright message, **sqlagent90** displays output in the command prompt window only when the **-v** switch is specified.</span></span> <span data-ttu-id="ac5ce-119">Чтобы остановить работу приложения **sqlagent90**, нажмите клавиши CTRL+C в командной строке.</span><span class="sxs-lookup"><span data-stu-id="ac5ce-119">To stop **sqlagent90**, press CTRL+C at the command prompt.</span></span> <span data-ttu-id="ac5ce-120">Не закрывайте окно командной строки перед остановкой работы приложения **sqlagent90**.</span><span class="sxs-lookup"><span data-stu-id="ac5ce-120">Do not close the command-prompt window before stopping **sqlagent90**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac5ce-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="ac5ce-121">See Also</span></span>  
 [<span data-ttu-id="ac5ce-122">Задачи автоматизированного администрирования (агент SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ac5ce-122">Automated Administration Tasks &#40;SQL Server Agent&#41;</span></span>](../ssms/agent/automated-administration-tasks-sql-server-agent.md)  
  
  
