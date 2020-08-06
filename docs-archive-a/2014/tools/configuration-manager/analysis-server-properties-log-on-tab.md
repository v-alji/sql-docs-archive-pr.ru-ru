---
title: Свойства сервера анализа данных (вкладка "Вход в систему") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: a82e0c98-efaa-4b0b-9582-3c879ee42444
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8db5576e48e7f12ef1733175875d2cd065e376fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750412"
---
# <a name="analysis-server-properties-log-on-tab"></a><span data-ttu-id="ec9ab-102">Свойства сервера анализа данных (вкладка «Вход в систему»)</span><span class="sxs-lookup"><span data-stu-id="ec9ab-102">Analysis Server Properties (Log On Tab)</span></span>
  <span data-ttu-id="ec9ab-103">Используйте вкладку **Вход** в диалоговом окне **Свойства сервера анализа данных** , чтобы указать учетную запись, используемую службами [!INCLUDE[ssAS](../../includes/ssas-md.md)] , и запустить или остановить службу.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-103">Use the **Log On** tab of the **Analysis Server Properties** dialog box to specify the account used by the [!INCLUDE[ssAS](../../includes/ssas-md.md)] service, and to start and stop the service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec9ab-104">Для изменения параметра **Имя учетной записи** , используемого службой в кластеризованном экземпляре, новая учетная запись должна быть членом группы домена, заданной во время установки изменяемой службы, или должно иметься разрешение на добавление членов в эту группу.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-104">When changing the **Account Name** used by a service on a clustered instance, the new account must either be a member of the domain group specified during setup for the service being changed, or you must have permission to add members to that group.</span></span> <span data-ttu-id="ec9ab-105">Если нет разрешения на изменение состава группы, свяжитесь с администратором домена.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-105">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ec9ab-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ec9ab-106">Options</span></span>  
 <span data-ttu-id="ec9ab-107">**Локальная системная учетная запись**</span><span class="sxs-lookup"><span data-stu-id="ec9ab-107">**Local System account**</span></span>  
 <span data-ttu-id="ec9ab-108">Укажите локальную системную учетную запись, для которой не требуется пароль.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-108">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="ec9ab-109">Однако локальная системная учетная запись может ограничить взаимодействие служб с другими серверами, это зависит от прав доступа, предоставленных этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-109">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="ec9ab-110">**Эта учетная запись**</span><span class="sxs-lookup"><span data-stu-id="ec9ab-110">**This account**</span></span>  
 <span data-ttu-id="ec9ab-111">Укажите локальную или доменную учетную запись пользователя, использующую проверку подлинности [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-111">Specify a local or domain user account that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="ec9ab-112">рекомендует использовать доменную учетную запись пользователя с минимальными правами.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-112">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="ec9ab-113">Дополнительные сведения о выборе учетной записи см. в разделе «Настройка учетных записей служб Windows» электронной документации.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-113">For information about selecting an account, search Books Online for the topic Setting Up Windows Service Accounts.</span></span>  
  
 <span data-ttu-id="ec9ab-114">**Account Name** (Имя учетной записи)</span><span class="sxs-lookup"><span data-stu-id="ec9ab-114">**Account Name**</span></span>  
 <span data-ttu-id="ec9ab-115">Укажите имя локальной или доменной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-115">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="ec9ab-116">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="ec9ab-116">**Password**</span></span>  
 <span data-ttu-id="ec9ab-117">Введите пароль для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-117">Type the password of the account.</span></span>  
  
 <span data-ttu-id="ec9ab-118">**Подтверждение пароля**</span><span class="sxs-lookup"><span data-stu-id="ec9ab-118">**Confirm password**</span></span>  
 <span data-ttu-id="ec9ab-119">Введите пароль для учетной записи еще раз.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-119">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="ec9ab-120">**Начало**</span><span class="sxs-lookup"><span data-stu-id="ec9ab-120">**Start**</span></span>  
 <span data-ttu-id="ec9ab-121">Запускает службу.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-121">Start the service.</span></span>  
  
 <span data-ttu-id="ec9ab-122">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="ec9ab-122">**Stop**</span></span>  
 <span data-ttu-id="ec9ab-123">Остановить службу.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-123">Stop the service.</span></span>  
  
 <span data-ttu-id="ec9ab-124">**Приостановить**</span><span class="sxs-lookup"><span data-stu-id="ec9ab-124">**Pause**</span></span>  
 <span data-ttu-id="ec9ab-125">Приостановить службу.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-125">Pause the service.</span></span>  
  
 <span data-ttu-id="ec9ab-126">**Возобновить**</span><span class="sxs-lookup"><span data-stu-id="ec9ab-126">**Resume**</span></span>  
 <span data-ttu-id="ec9ab-127">Возобновить приостановленную работу службы.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-127">Resume a paused service.</span></span>  
  
  
