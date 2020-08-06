---
title: Свойства служб SQL Server Integration Services (вкладка "Вход в систему") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c0eb1b87-6bb0-475e-8492-0fd3c3f910ea
author: stevestein
ms.author: sstein
ms.openlocfilehash: dfef02a82872ea1df25e7ccb8526e488aaa5f406
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737307"
---
# <a name="sql-server-integration-services-properties-log-on-tab"></a><span data-ttu-id="30d83-102">Свойства служб SQL Server Integration Services (вкладка «Вход в систему»)</span><span class="sxs-lookup"><span data-stu-id="30d83-102">SQL Server Integration Services Properties (Log On Tab)</span></span>
  <span data-ttu-id="30d83-103">Используйте вкладку **Вход** в диалоговом окне [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]Свойства**в** для указания учетной записи, используемой службой [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], а также для запуска и остановки службы.</span><span class="sxs-lookup"><span data-stu-id="30d83-103">Use the **Log On** tab of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] **Properties** dialog box to specify the account used by the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service, and to start and stop the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="30d83-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="30d83-104">Options</span></span>  
 <span data-ttu-id="30d83-105">**Локальная системная учетная запись**</span><span class="sxs-lookup"><span data-stu-id="30d83-105">**Local System account**</span></span>  
 <span data-ttu-id="30d83-106">Укажите локальную системную учетную запись, для которой не требуется пароль.</span><span class="sxs-lookup"><span data-stu-id="30d83-106">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="30d83-107">Однако локальная системная учетная запись может ограничить взаимодействие служб с другими серверами, это зависит от прав доступа, предоставленных этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="30d83-107">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="30d83-108">**Эта учетная запись**</span><span class="sxs-lookup"><span data-stu-id="30d83-108">**This account**</span></span>  
 <span data-ttu-id="30d83-109">Укажите локальную или доменную учетную запись пользователя, использующую проверку подлинности [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="30d83-109">Specify a local or domain user account that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="30d83-110">рекомендует использовать доменную учетную запись пользователя с минимальными правами.</span><span class="sxs-lookup"><span data-stu-id="30d83-110">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="30d83-111">Дополнительные сведения о выборе учетной записи см. в разделе «Настройка учетных записей служб Windows» электронной документации.</span><span class="sxs-lookup"><span data-stu-id="30d83-111">For information about selecting an account, search Books Online for the topic, "Setting Up Windows Service Accounts."</span></span>  
  
 <span data-ttu-id="30d83-112">**Account Name** (Имя учетной записи)</span><span class="sxs-lookup"><span data-stu-id="30d83-112">**Account Name**</span></span>  
 <span data-ttu-id="30d83-113">Укажите имя локальной или доменной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="30d83-113">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="30d83-114">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="30d83-114">**Password**</span></span>  
 <span data-ttu-id="30d83-115">Введите пароль для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="30d83-115">Type the password of the account.</span></span>  
  
 <span data-ttu-id="30d83-116">**Подтверждение пароля**</span><span class="sxs-lookup"><span data-stu-id="30d83-116">**Confirm password**</span></span>  
 <span data-ttu-id="30d83-117">Введите пароль для учетной записи еще раз.</span><span class="sxs-lookup"><span data-stu-id="30d83-117">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="30d83-118">**Начало**</span><span class="sxs-lookup"><span data-stu-id="30d83-118">**Start**</span></span>  
 <span data-ttu-id="30d83-119">Запускает службу.</span><span class="sxs-lookup"><span data-stu-id="30d83-119">Start the service.</span></span>  
  
 <span data-ttu-id="30d83-120">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="30d83-120">**Stop**</span></span>  
 <span data-ttu-id="30d83-121">Остановить службу.</span><span class="sxs-lookup"><span data-stu-id="30d83-121">Stop the service.</span></span>  
  
 <span data-ttu-id="30d83-122">**Приостановить**</span><span class="sxs-lookup"><span data-stu-id="30d83-122">**Pause**</span></span>  
 <span data-ttu-id="30d83-123">Приостановить службу.</span><span class="sxs-lookup"><span data-stu-id="30d83-123">Pause the service.</span></span>  
  
 <span data-ttu-id="30d83-124">**Возобновить**</span><span class="sxs-lookup"><span data-stu-id="30d83-124">**Resume**</span></span>  
 <span data-ttu-id="30d83-125">Возобновить приостановленную работу службы.</span><span class="sxs-lookup"><span data-stu-id="30d83-125">Resume a paused service.</span></span>  
  
  
