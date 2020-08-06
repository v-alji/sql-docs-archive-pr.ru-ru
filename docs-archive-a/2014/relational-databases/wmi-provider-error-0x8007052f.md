---
title: Ошибка WMI 0x8007052f | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- 0x8007052f (WMI error)
ms.assetid: a33f12bd-15c4-42a8-b343-de44c3e87729
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d6e857e0ccaad9b6f34bbdc9b88aea2e6d7291d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752015"
---
# <a name="wmi-error-0x8007052f"></a><span data-ttu-id="1cc99-102">WMI Error 0x8007052f</span><span class="sxs-lookup"><span data-stu-id="1cc99-102">WMI Error 0x8007052f</span></span>
    
## <a name="details"></a><span data-ttu-id="1cc99-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="1cc99-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1cc99-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="1cc99-104">Product Name</span></span>|<span data-ttu-id="1cc99-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1cc99-105">SQL Server</span></span>|  
|<span data-ttu-id="1cc99-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="1cc99-106">Event ID</span></span>|<span data-ttu-id="1cc99-107">0x8007052f</span><span class="sxs-lookup"><span data-stu-id="1cc99-107">0x8007052f</span></span>|  
|<span data-ttu-id="1cc99-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="1cc99-108">Event Source</span></span>|<span data-ttu-id="1cc99-109">Ошибка поставщика WMI</span><span class="sxs-lookup"><span data-stu-id="1cc99-109">WMI Provider Error</span></span>|  
|<span data-ttu-id="1cc99-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="1cc99-110">Component</span></span>|<span data-ttu-id="1cc99-111">Диспетчер конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="1cc99-111">SQL Server Configuration Manager</span></span>|  
|<span data-ttu-id="1cc99-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="1cc99-112">Symbolic Name</span></span>|<span data-ttu-id="1cc99-113">Н/Д</span><span class="sxs-lookup"><span data-stu-id="1cc99-113">NA</span></span>|  
|<span data-ttu-id="1cc99-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="1cc99-114">Message Text</span></span>|<span data-ttu-id="1cc99-115">Ошибка входа в систему: ограничение учетной записи.</span><span class="sxs-lookup"><span data-stu-id="1cc99-115">Logon failure: user account restriction.</span></span> <span data-ttu-id="1cc99-116">Возможные причины: запрещено использование пустых паролей, имеется ограничение по времени входа или применено ограничение, предусмотренное политикой.</span><span class="sxs-lookup"><span data-stu-id="1cc99-116">Possible reasons are blank passwords not allowed, login hour restrictions, or a policy restriction has been enforced.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1cc99-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="1cc99-117">Explanation</span></span>  
 <span data-ttu-id="1cc99-118">Эта ошибка может произойти при использовании диспетчера конфигурации [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] для переключения на встроенные учетные записи (сетевой службы, локальной службы или локальной системы) в случаях, если [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] работает в кластере Windows Server или на контроллере домена Windows Server.</span><span class="sxs-lookup"><span data-stu-id="1cc99-118">This error can occur when using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager to switch to the built-in accounts (Network Service, Local Service, or Local System) when [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is running on a Windows Server Cluster or Windows Server Domain Controller.</span></span> <span data-ttu-id="1cc99-119">Не запускайте службы от имени встроенных учетных записей в кластере Windows Server или на контроллере домена Windows Server.</span><span class="sxs-lookup"><span data-stu-id="1cc99-119">Do not run services under built-in accounts on a Windows Server Cluster or Windows Server Domain Controller.</span></span> <span data-ttu-id="1cc99-120">Дополнительные сведения об учетных записях см. в разделе «Настройка учетных записей служб Windows» электронной документации по [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1cc99-120">For recommendations on service accounts, see the topic Setting Up Windows Service Accounts in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1cc99-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="1cc99-121">User Action</span></span>  
 <span data-ttu-id="1cc99-122">Настройте [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] на использование учетной записи домена.</span><span class="sxs-lookup"><span data-stu-id="1cc99-122">Configure [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to use a domain account.</span></span>  
  
  
