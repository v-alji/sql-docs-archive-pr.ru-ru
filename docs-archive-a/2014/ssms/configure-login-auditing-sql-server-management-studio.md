---
title: Настройка аудита входа в систему (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- audits [SQL Server], logins
- logins [SQL Server], auditing
ms.assetid: 16961116-57ac-4eef-8037-791b26ade548
author: stevestein
ms.author: sstein
ms.openlocfilehash: b7e05f6c254e098a67a5ce00435c009cd450af44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668568"
---
# <a name="configure-login-auditing-sql-server-management-studio"></a><span data-ttu-id="058e2-102">Настройка аудита входа в систему (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="058e2-102">Configure Login Auditing (SQL Server Management Studio)</span></span>
  <span data-ttu-id="058e2-103">В этом разделе описывается, как настроить аудит входа в [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] для контроля подключения к компоненту [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="058e2-103">This topic describes how to configure login auditing in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] to monitor [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] login activity.</span></span> <span data-ttu-id="058e2-104">Аудит входа в систему может быть настроен на запись в журнал ошибок при следующих событиях.</span><span class="sxs-lookup"><span data-stu-id="058e2-104">Login auditing can be configured to write to the error log on the following events.</span></span>  
  
-   <span data-ttu-id="058e2-105">Неуспешные входы в систему</span><span class="sxs-lookup"><span data-stu-id="058e2-105">Failed logins</span></span>  
  
-   <span data-ttu-id="058e2-106">Успешные входы в систему</span><span class="sxs-lookup"><span data-stu-id="058e2-106">Successful logins</span></span>  
  
-   <span data-ttu-id="058e2-107">Все попытки входа</span><span class="sxs-lookup"><span data-stu-id="058e2-107">Both failed and successful logins</span></span>  
  
 <span data-ttu-id="058e2-108">Чтобы этот параметр вступил в силу, перезапустите [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="058e2-108">You must restart [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] before this option will take effect.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="058e2-109">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="058e2-109">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-login-auditing"></a><span data-ttu-id="058e2-110">Настройка аудита входа в систему</span><span class="sxs-lookup"><span data-stu-id="058e2-110">To configure login auditing</span></span>  
  
1.  <span data-ttu-id="058e2-111">В среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] с помощью обозревателя объектов.</span><span class="sxs-lookup"><span data-stu-id="058e2-111">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] with Object Explorer.</span></span>  
  
2.  <span data-ttu-id="058e2-112">В обозревателе объектов щелкните правой кнопкой мыши имя сервера и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="058e2-112">In Object Explorer, right-click the server name, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="058e2-113">На странице **Безопасность** щелкните желаемый параметр под аудитом **Имя входа** и закройте страницу **Свойства сервера** .</span><span class="sxs-lookup"><span data-stu-id="058e2-113">On the **Security** page, under **Login** auditing, click the desired option and close the **Server Properties** page.</span></span>  
  
4.  <span data-ttu-id="058e2-114">В обозревателе объектов щелкните правой кнопкой мыши имя сервера и выберите пункт **Перезапустить**.</span><span class="sxs-lookup"><span data-stu-id="058e2-114">In Object Explorer, right-click the server name, and then click **Restart**.</span></span>  
  
  
