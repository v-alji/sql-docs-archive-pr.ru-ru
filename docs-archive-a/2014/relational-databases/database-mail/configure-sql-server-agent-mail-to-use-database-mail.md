---
title: Настройка почты агента SQL Server на использование компонента Database Mail | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], SQL Server Agent Mail
- SQL Server Agent Mail
ms.assetid: 4b8b61bd-4bd1-43cd-b6e5-c6ed2e101dce
author: stevestein
ms.author: sstein
ms.openlocfilehash: 31d116c0bc8d7e148fc2ef6d2e344400516ad923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728346"
---
# <a name="configure-sql-server-agent-mail-to-use-database-mail"></a><span data-ttu-id="0beeb-102">Настройка почты агента SQL Server на использование компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="0beeb-102">Configure SQL Server Agent Mail to Use Database Mail</span></span>
  <span data-ttu-id="0beeb-103">В этом разделе описывается настройка в агенте [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] использования компонента Database Mail для отправки уведомлений и предупреждений в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0beeb-103">This topic describes how to configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to use Database Mail to send notification and alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="0beeb-104">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="0beeb-104">**Before you begin:**</span></span>  
  
-   [<span data-ttu-id="0beeb-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="0beeb-105">Prerequisites</span></span>](#Prerequisites)  
  
-   [<span data-ttu-id="0beeb-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="0beeb-106">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="0beeb-107">Настройка агента SQL Server на использование компонента Database Mail с помощью среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0beeb-107">To Configure SQL Server Agent to use Database Mail, using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="0beeb-108">Задачи дальнейших действий</span><span class="sxs-lookup"><span data-stu-id="0beeb-108">Follow-up Tasks</span></span>](#Follow_Up)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0beeb-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="0beeb-109">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="0beeb-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="0beeb-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="0beeb-111">Включить компонент Database Mail.</span><span class="sxs-lookup"><span data-stu-id="0beeb-111">Enable Database Mail.</span></span>  
  
-   <span data-ttu-id="0beeb-112">Создать учетную запись компонента Database Mail для агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0beeb-112">Create a Database Mail account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account to use.</span></span>  
  
-   <span data-ttu-id="0beeb-113">Создать профиль компонента Database Mail для учетной записи агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , чтобы сделать пользователя членом роли **DatabaseMailUserRole** в базе данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="0beeb-113">Create a Database Mail profile for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account to use and add the user to the **DatabaseMailUserRole** in the **msdb** database.</span></span>  
  
-   <span data-ttu-id="0beeb-114">Сделать профиль используемым по умолчанию в базе данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="0beeb-114">Set the profile as the default profile for the **msdb** database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0beeb-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="0beeb-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0beeb-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="0beeb-116">Permissions</span></span>  
 <span data-ttu-id="0beeb-117">Пользователь, создающий учетные записи профилей и выполняющий хранимые процедуры, должен быть членом предопределенной роли сервера sysadmin.</span><span class="sxs-lookup"><span data-stu-id="0beeb-117">The user creating the profiles accounts and executing stored procedures should be a member of the sysadmin fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0beeb-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0beeb-118">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="0beeb-119">**Настройка агента SQL Server на использование компонента Database Mail**</span><span class="sxs-lookup"><span data-stu-id="0beeb-119">**To configure SQL Server Agent to use Database Mail**</span></span>  
  
-   <span data-ttu-id="0beeb-120">Разверните экземпляр сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="0beeb-120">In Object Explorer, expand a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="0beeb-121">Щелкните правой кнопкой мыши **агент SQL Server**, затем выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0beeb-121">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
-   <span data-ttu-id="0beeb-122">Нажмите **Система предупреждений**.</span><span class="sxs-lookup"><span data-stu-id="0beeb-122">Click **Alert System**.</span></span>  
  
-   <span data-ttu-id="0beeb-123">Выберите **Включить почтовый профиль**.</span><span class="sxs-lookup"><span data-stu-id="0beeb-123">Select **Enable Mail Profile**.</span></span>  
  
-   <span data-ttu-id="0beeb-124">В списке **Почтовая система** выберите **Компонент Database Mail**.</span><span class="sxs-lookup"><span data-stu-id="0beeb-124">In the **Mail system** list, select **Database Mail**.</span></span>  
  
-   <span data-ttu-id="0beeb-125">В **Списке почтовых профилей**выберите почтовый профиль для компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="0beeb-125">In the **Mail profile list**, select a mail profile for Database Mail.</span></span>  
  
-   <span data-ttu-id="0beeb-126">Перезапустите агент SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0beeb-126">Restart SQL Server Agent.</span></span>  
  
##  <a name="follow-up-tasks"></a><a name="Follow_Up"></a> <span data-ttu-id="0beeb-127">Задачи дополнительной работы</span><span class="sxs-lookup"><span data-stu-id="0beeb-127">Follow-up Tasks</span></span>  
 <span data-ttu-id="0beeb-128">Следующие задачи необходимо выполнить для завершения конфигурации агента на отправку предупреждений и уведомлений.</span><span class="sxs-lookup"><span data-stu-id="0beeb-128">The following tasks are necessary to complete the configuration of Agent to send alerts and notifications.</span></span>  
  
-   [<span data-ttu-id="0beeb-129">Оповещения</span><span class="sxs-lookup"><span data-stu-id="0beeb-129">Alerts</span></span>](../../ssms/agent/alerts.md)  
  
     <span data-ttu-id="0beeb-130">Предупреждения могут быть настроены на уведомление оператора о возникновении в базе данных определенного события или о формировании в операционной системе определенных условий.</span><span class="sxs-lookup"><span data-stu-id="0beeb-130">Alerts can be configured to notify an operator of a particular database event or operating system condition.</span></span>  
  
-   [<span data-ttu-id="0beeb-131">Операторы</span><span class="sxs-lookup"><span data-stu-id="0beeb-131">Operators</span></span>](../../ssms/agent/operators.md)  
  
     <span data-ttu-id="0beeb-132">Операторы — это псевдонимы для людей или групп, которые могут получать электронные уведомления.</span><span class="sxs-lookup"><span data-stu-id="0beeb-132">Operators are aliases for people or groups that can receive electronic notification</span></span>  
  
  
