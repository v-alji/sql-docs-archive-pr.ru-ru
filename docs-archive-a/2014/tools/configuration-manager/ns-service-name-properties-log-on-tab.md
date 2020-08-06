---
title: Свойства NS $ &lt; Service Name &gt; (вкладка «Вход в систему») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 5e6816ec-d4c5-4429-8033-b97427584890
author: stevestein
ms.author: sstein
ms.openlocfilehash: b175895f2385717a67642a41a44dc0d47a1d8d92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737325"
---
# <a name="nsltservice-namegt-properties-log-on-tab"></a><span data-ttu-id="f7070-102">Свойства NS$&lt;имя службы&gt; (вкладка "Вход в систему")</span><span class="sxs-lookup"><span data-stu-id="f7070-102">NS$&lt;service name&gt; Properties (Log On Tab)</span></span>
  <span data-ttu-id="f7070-103">Используйте вкладку **Вход** диалогового окна **Свойства служб Notification Services** для указания учетной записи, используемой службами [!INCLUDE[ssNS](../../includes/ssns-md.md)] , а также для запуска и остановки службы.</span><span class="sxs-lookup"><span data-stu-id="f7070-103">Use the **Log On** tab of the **Notification Services Properties** dialog box to specify the account used by the [!INCLUDE[ssNS](../../includes/ssns-md.md)] service, and to start and stop the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f7070-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="f7070-104">Options</span></span>  
 <span data-ttu-id="f7070-105">**Локальная системная учетная запись**</span><span class="sxs-lookup"><span data-stu-id="f7070-105">**Local System account**</span></span>  
 <span data-ttu-id="f7070-106">Укажите локальную системную учетную запись, для которой не требуется пароль.</span><span class="sxs-lookup"><span data-stu-id="f7070-106">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="f7070-107">Однако локальная системная учетная запись может ограничить взаимодействие служб с другими серверами, это зависит от прав доступа, предоставленных этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="f7070-107">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="f7070-108">**Эта учетная запись**</span><span class="sxs-lookup"><span data-stu-id="f7070-108">**This account**</span></span>  
 <span data-ttu-id="f7070-109">Укажите локальную или доменную учетную запись пользователя, использующую проверку подлинности [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="f7070-109">Specify a local or domain user account that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="f7070-110">рекомендует использовать доменную учетную запись пользователя с минимальными правами.</span><span class="sxs-lookup"><span data-stu-id="f7070-110">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="f7070-111">Дополнительные сведения о выборе учетной записи см. в разделе «Настройка учетных записей служб Windows» электронной документации.</span><span class="sxs-lookup"><span data-stu-id="f7070-111">For information about selecting an account, search Books Online for the topic, "Setting Up Windows Service Accounts."</span></span>  
  
 <span data-ttu-id="f7070-112">**Account Name** (Имя учетной записи)</span><span class="sxs-lookup"><span data-stu-id="f7070-112">**Account Name**</span></span>  
 <span data-ttu-id="f7070-113">Укажите имя локальной или доменной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="f7070-113">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="f7070-114">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="f7070-114">**Password**</span></span>  
 <span data-ttu-id="f7070-115">Введите пароль для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="f7070-115">Type the password of the account.</span></span>  
  
 <span data-ttu-id="f7070-116">**Подтверждение пароля**</span><span class="sxs-lookup"><span data-stu-id="f7070-116">**Confirm password**</span></span>  
 <span data-ttu-id="f7070-117">Введите пароль для учетной записи еще раз.</span><span class="sxs-lookup"><span data-stu-id="f7070-117">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="f7070-118">**Начало**</span><span class="sxs-lookup"><span data-stu-id="f7070-118">**Start**</span></span>  
 <span data-ttu-id="f7070-119">Запускает службу.</span><span class="sxs-lookup"><span data-stu-id="f7070-119">Start the service.</span></span>  
  
 <span data-ttu-id="f7070-120">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="f7070-120">**Stop**</span></span>  
 <span data-ttu-id="f7070-121">Остановить службу.</span><span class="sxs-lookup"><span data-stu-id="f7070-121">Stop the service.</span></span>  
  
 <span data-ttu-id="f7070-122">**Приостановить**</span><span class="sxs-lookup"><span data-stu-id="f7070-122">**Pause**</span></span>  
 <span data-ttu-id="f7070-123">Приостановить службу.</span><span class="sxs-lookup"><span data-stu-id="f7070-123">Pause the service.</span></span>  
  
 <span data-ttu-id="f7070-124">**Возобновить**</span><span class="sxs-lookup"><span data-stu-id="f7070-124">**Resume**</span></span>  
 <span data-ttu-id="f7070-125">Возобновить приостановленную работу службы.</span><span class="sxs-lookup"><span data-stu-id="f7070-125">Resume a paused service.</span></span>  
  
  
