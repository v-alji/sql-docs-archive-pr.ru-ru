---
title: Выберите правую учетную запись службы агент SQL Server для многосерверных сред | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, service accounts
- multiserver environments [SQL Server], SQL Server Agent service account behavior
ms.assetid: a07e2f38-281c-495b-965b-13fad03ba548
author: stevestein
ms.author: sstein
ms.openlocfilehash: 94ef890f5d2ef2b85d2f4d1023a93747e903a7f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668600"
---
# <a name="choose-the-right-sql-server-agent-service-account-for-multiserver-environments"></a><span data-ttu-id="a9aa4-102">Выбор правильной учетной записи службы агента SQL Server для многосерверной среды</span><span class="sxs-lookup"><span data-stu-id="a9aa4-102">Choose the Right SQL Server Agent Service Account for Multiserver Environments</span></span>
  <span data-ttu-id="a9aa4-103">Данные учетной записи Windows, выбранной для службы « [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , агент», могут повлиять на поведение многосерверного окружения следующим образом.</span><span class="sxs-lookup"><span data-stu-id="a9aa4-103">The Windows account you choose for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service can affect the behavior of a multiserver environment, as follows:</span></span>  
  
-   <span data-ttu-id="a9aa4-104">При работе службы « [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , агент» под учетной записью, не являющейся элементом локальной группы администраторов в Windows, прикрепление целевых серверов к главным серверам может завершиться сбоем.</span><span class="sxs-lookup"><span data-stu-id="a9aa4-104">If you run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service under an account that is not a member of the local Windows Administrators group, enlisting target servers to master servers may fail.</span></span> <span data-ttu-id="a9aa4-105">Если такой сбой произошел, выводится следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="a9aa4-105">If it does, the following error message is returned:</span></span>  
  
     <span data-ttu-id="a9aa4-106">«Сбой операции прикрепления».</span><span class="sxs-lookup"><span data-stu-id="a9aa4-106">"The enlistment operation failed."</span></span>  
  
     <span data-ttu-id="a9aa4-107">Для решения данной проблемы перезапустите службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и « [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , агент».</span><span class="sxs-lookup"><span data-stu-id="a9aa4-107">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent services to resolve this issue.</span></span>  
  
-   <span data-ttu-id="a9aa4-108">При работе службы « [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , агент» под локальной учетной записью операции между целевым и главными серверами осуществляются только при условии, что оба сервера находятся на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a9aa4-108">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is run under the Local System account, master server-target server operations are supported only if both the master server and the target server reside on the same computer.</span></span> <span data-ttu-id="a9aa4-109">В случае использования такой конфигурации при прикреплении целевых серверов к главному серверу выводится следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="a9aa4-109">If you use this configuration, the following message is returned when you enlist target servers to a master server:</span></span>  
  
     <span data-ttu-id="a9aa4-110">"Убедитесь, что стартовая учетная запись агента для *<имя_компьютера_целевого_сервера>* имеет права для входа на сервер targetServer".</span><span class="sxs-lookup"><span data-stu-id="a9aa4-110">"Ensure the agent start-up account for *<target_server_computer_name>* has rights to log on as targetServer."</span></span>  
  
     <span data-ttu-id="a9aa4-111">Данное сообщение можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="a9aa4-111">You can ignore this informational message.</span></span> <span data-ttu-id="a9aa4-112">Операция прикрепления должна быть завершена успешно.</span><span class="sxs-lookup"><span data-stu-id="a9aa4-112">The enlistment operation should complete successfully.</span></span>  
  
 <span data-ttu-id="a9aa4-113">Дополнительные сведения о выборе учетной записи для службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в разделе [Выбор учетной записи для службы агента SQL Server](select-an-account-for-the-sql-server-agent-service.md).</span><span class="sxs-lookup"><span data-stu-id="a9aa4-113">For more information about choosing an account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md).</span></span>  
  
  
