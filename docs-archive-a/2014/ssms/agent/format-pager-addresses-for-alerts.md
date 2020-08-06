---
title: Форматирование адресов пейджеров для предупреждений | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- pager addresses [SQL Server]
- SQL Server Agent, alerts
- formats [SQL Server], pager addresses
- pager notifications [SQL Server]
- addresses [SQL Server]
- alerts [SQL Server], pager addresses
ms.assetid: a9797d01-1050-442c-9038-ed4bfee1e76a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 471f9a4958f51491b312d89239a2204c907e25e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654726"
---
# <a name="format-pager-addresses-for-alerts"></a><span data-ttu-id="ba39f-102">Format Pager Addresses for Alerts</span><span class="sxs-lookup"><span data-stu-id="ba39f-102">Format Pager Addresses for Alerts</span></span>
  <span data-ttu-id="ba39f-103">В этом разделе описывается форматирование адресов пейджера для [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предупреждений агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ba39f-103">This topic describes how to format pager addresses for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ba39f-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="ba39f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ba39f-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="ba39f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ba39f-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="ba39f-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ba39f-107">**Для форматирования адресов пейджера используется:**</span><span class="sxs-lookup"><span data-stu-id="ba39f-107">**To format pager addresses, using:**</span></span>  
  
     [<span data-ttu-id="ba39f-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ba39f-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ba39f-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="ba39f-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ba39f-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="ba39f-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ba39f-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="ba39f-111">Permissions</span></span>  
 <span data-ttu-id="ba39f-112">По умолчанию только члены предопределенной роли сервера **sysadmin** могут просматривать сведения о предупреждении.</span><span class="sxs-lookup"><span data-stu-id="ba39f-112">By default, members of the **sysadmin** fixed server role can view information about an alert.</span></span> <span data-ttu-id="ba39f-113">Другим пользователям должна быть предоставлена предопределенная роль базы данных **SQLAgentOperatorRole** в базе данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="ba39f-113">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ba39f-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ba39f-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-format-pager-addresses"></a><span data-ttu-id="ba39f-115">Форматирование адресов пейджера</span><span class="sxs-lookup"><span data-stu-id="ba39f-115">To format pager addresses</span></span>  
  
1.  <span data-ttu-id="ba39f-116">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть сервер, содержащий оповещение агента, которое необходимо отправить на пейджер.</span><span class="sxs-lookup"><span data-stu-id="ba39f-116">In **Object Explorer**, click the plus sign to expand the server that contains the alert that you want to send to a pager.</span></span>  
  
2.  <span data-ttu-id="ba39f-117">Щелкните правой кнопкой мыши элемент **Агент SQL Server** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ba39f-117">Right-click **SQL Server Agent** and select **Properties**</span></span>  
  
3.  <span data-ttu-id="ba39f-118">В разделе **Выбор страницы**выберите пункт **Система предупреждений**.</span><span class="sxs-lookup"><span data-stu-id="ba39f-118">Under **Select a page**, select **Alert System**.</span></span>  
  
4.  <span data-ttu-id="ba39f-119">В полях **Кому** и **Копия** в поле **Форматирование адреса для электронных сообщений на пейджер** введите префикс или суффикс адресов пейджеров.</span><span class="sxs-lookup"><span data-stu-id="ba39f-119">In the **To line** and **CC line** boxes of the **Address formatting for pager e-mails** field, enter the pager address prefix or suffix.</span></span> <span data-ttu-id="ba39f-120">При отправке уведомления подставляется действительный адрес пейджера оператора.</span><span class="sxs-lookup"><span data-stu-id="ba39f-120">The operator's actual pager address is inserted when a notification is sent.</span></span>  
  
5.  <span data-ttu-id="ba39f-121">В поле **Тема** введите префикс или суффикс, добавляемый к строке темы.</span><span class="sxs-lookup"><span data-stu-id="ba39f-121">In the **Subject** box, enter the subject line prefix or suffix.</span></span>  
  
6.  <span data-ttu-id="ba39f-122">Установите флажок **Включить тело сообщения электронной почты в сообщение уведомления** , чтобы в сообщение, отправляемое на пейджер, включался полный текст электронного сообщения (а не только строка темы).</span><span class="sxs-lookup"><span data-stu-id="ba39f-122">Select the **Include body of e-mail in notification page** check box to include the full e-mail message with the pager message (as opposed to the subject line only).</span></span>  
  
7.  <span data-ttu-id="ba39f-123">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ba39f-123">When finished, click **OK**.</span></span>  
  
  
