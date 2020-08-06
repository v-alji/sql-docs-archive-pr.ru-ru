---
title: Свойства агента SQL Server (вкладка "Вход в систему") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 01fc6329-5d6b-4186-9565-395f375477bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: cd899e8824adacd07fa1d8d7d51b2143d10cadd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659048"
---
# <a name="sql-server-agent-properties-log-on-tab"></a><span data-ttu-id="e1c13-102">Свойства агента SQL Server (вкладка «Вход в систему»)</span><span class="sxs-lookup"><span data-stu-id="e1c13-102">SQL Server Agent Properties (Log On Tab)</span></span>
  <span data-ttu-id="e1c13-103">Используйте вкладку **Вход** диалогового окна **Свойства агента SQL Server** , чтобы указать учетную запись, используемую службой « [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , агент», а также выполнить запуск или остановку службы.</span><span class="sxs-lookup"><span data-stu-id="e1c13-103">Use the **Log On** tab of the **SQL Server Agent Properties** dialog box to specify the account used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, and to start and stop the service.</span></span> <span data-ttu-id="e1c13-104">Изменение пароля учетной записи вступает в силу немедленно, без перезапуска службы.</span><span class="sxs-lookup"><span data-stu-id="e1c13-104">Changing the password of an account takes effect immediately without restarting the service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e1c13-105">При изменении имени учетной записи, используемой службой в кластеризованном экземпляре, новая учетная запись должна быть членом группы домена, заданной во время установки изменяемой службы, или же текущий пользователь должен иметь разрешение на добавление членов в эту группу.</span><span class="sxs-lookup"><span data-stu-id="e1c13-105">When changing the account name used by a service on a clustered instance, the new account must be a member of the domain group specified during setup for the service being changed, or you must have permission to add members to that group.</span></span> <span data-ttu-id="e1c13-106">Если нет разрешения на изменение состава группы, свяжитесь с администратором домена.</span><span class="sxs-lookup"><span data-stu-id="e1c13-106">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e1c13-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e1c13-107">Options</span></span>  
 <span data-ttu-id="e1c13-108">**Локальная системная учетная запись**</span><span class="sxs-lookup"><span data-stu-id="e1c13-108">**Local System account**</span></span>  
 <span data-ttu-id="e1c13-109">Укажите локальную системную учетную запись, для которой не требуется пароль.</span><span class="sxs-lookup"><span data-stu-id="e1c13-109">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="e1c13-110">Однако локальная системная учетная запись может ограничить взаимодействие служб с другими серверами, это зависит от прав доступа, предоставленных этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="e1c13-110">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="e1c13-111">**Эта учетная запись**</span><span class="sxs-lookup"><span data-stu-id="e1c13-111">**This account**</span></span>  
 <span data-ttu-id="e1c13-112">Укажите локальную или доменную учетную запись, использующую аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="e1c13-112">Specify a local or domain user account that uses Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="e1c13-113">рекомендует использовать доменную учетную запись пользователя с минимальными правами.</span><span class="sxs-lookup"><span data-stu-id="e1c13-113">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="e1c13-114">Дополнительные сведения о выборе учетной записи см. в разделе «Настройка учетных записей служб Windows» электронной документации.</span><span class="sxs-lookup"><span data-stu-id="e1c13-114">For information about selecting an account, search Books Online for "Setting Up Windows Service Accounts."</span></span>  
  
 <span data-ttu-id="e1c13-115">**Account Name** (Имя учетной записи)</span><span class="sxs-lookup"><span data-stu-id="e1c13-115">**Account Name**</span></span>  
 <span data-ttu-id="e1c13-116">Укажите имя локальной или доменной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="e1c13-116">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="e1c13-117">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="e1c13-117">**Password**</span></span>  
 <span data-ttu-id="e1c13-118">Введите пароль для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="e1c13-118">Type the password of the account.</span></span>  
  
 <span data-ttu-id="e1c13-119">**Подтверждение пароля**</span><span class="sxs-lookup"><span data-stu-id="e1c13-119">**Confirm password**</span></span>  
 <span data-ttu-id="e1c13-120">Введите пароль для учетной записи еще раз.</span><span class="sxs-lookup"><span data-stu-id="e1c13-120">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="e1c13-121">**Начало**</span><span class="sxs-lookup"><span data-stu-id="e1c13-121">**Start**</span></span>  
 <span data-ttu-id="e1c13-122">Запускает службу.</span><span class="sxs-lookup"><span data-stu-id="e1c13-122">Start the service.</span></span>  
  
 <span data-ttu-id="e1c13-123">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="e1c13-123">**Stop**</span></span>  
 <span data-ttu-id="e1c13-124">Остановить службу.</span><span class="sxs-lookup"><span data-stu-id="e1c13-124">Stop the service.</span></span>  
  
 <span data-ttu-id="e1c13-125">**Приостановить**</span><span class="sxs-lookup"><span data-stu-id="e1c13-125">**Pause**</span></span>  
 <span data-ttu-id="e1c13-126">Приостановить службу.</span><span class="sxs-lookup"><span data-stu-id="e1c13-126">Pause the service.</span></span>  
  
 <span data-ttu-id="e1c13-127">**Возобновить**</span><span class="sxs-lookup"><span data-stu-id="e1c13-127">**Resume**</span></span>  
 <span data-ttu-id="e1c13-128">Возобновить приостановленную работу службы.</span><span class="sxs-lookup"><span data-stu-id="e1c13-128">Resume a paused service.</span></span>  
  
  
