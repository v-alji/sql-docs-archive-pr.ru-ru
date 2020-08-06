---
title: Неизвестная служба (вкладка "вход в систему") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: e9b35cb5-d8ae-42ea-b59e-deedc99c4823
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0bda49cd95475d4f922f41ebe1701a814c3f60fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656131"
---
# <a name="unknown-service-log-on-tab"></a><span data-ttu-id="cd71f-102">Неизвестная служба (вкладка «Вход в систему»)</span><span class="sxs-lookup"><span data-stu-id="cd71f-102">Unknown Service (Log On Tab)</span></span>
  <span data-ttu-id="cd71f-103">Диспетчеру конфигурации [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удается идентифицировать эту службу.</span><span class="sxs-lookup"><span data-stu-id="cd71f-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager is unable to identify this service.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cd71f-104">получает служебные данные от поставщика инструментария WMI на компьютере, где запущена служба.</span><span class="sxs-lookup"><span data-stu-id="cd71f-104">Configuration Manager receives service information from the WMI provider on the computer running the service.</span></span> <span data-ttu-id="cd71f-105">Произошла ошибка при считывании свойств службы или свойства службы являются неполными.</span><span class="sxs-lookup"><span data-stu-id="cd71f-105">Either there was an error while reading the service properties, or the service properties are not complete.</span></span> <span data-ttu-id="cd71f-106">Чтобы разрешить проблему, попытайтесь закрыть и заново открыть диспетчер конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или проверьте поставщика инструментария WMI на компьютере, где запущена служба.</span><span class="sxs-lookup"><span data-stu-id="cd71f-106">To resolve the problem, try closing and reopening [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or check the WMI provider on the computer running the service.</span></span>  
  
 <span data-ttu-id="cd71f-107">Поставщик WMI является компонентом Windows.</span><span class="sxs-lookup"><span data-stu-id="cd71f-107">The WMI provider is a Windows component.</span></span> <span data-ttu-id="cd71f-108">Сведения о том, как проверить разрешения на поставщика WMI, см. в статье "Инструкции. Настройка инструментария WMI для отображения состояния сервера в средствах SQL Server" в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cd71f-108">For information on how to check permissions on the WMI provider, see "How to: Configure WMI to Show Server Status in SQL Server Tools" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="cd71f-109">Если вы уверены, что просматриваете правильную службу, то для указания учетной записи, используемой службой, а также для запуска и остановки службы используйте вкладку **Вход** в диалоговом окне **Свойства неизвестной службы** .</span><span class="sxs-lookup"><span data-stu-id="cd71f-109">If you believe you are viewing the correct service, use the **Log On** tab of the **Unknown Service Properties** dialog box to specify the account used by this service, and to start and stop the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cd71f-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="cd71f-110">Options</span></span>  
 <span data-ttu-id="cd71f-111">**Локальная системная учетная запись**</span><span class="sxs-lookup"><span data-stu-id="cd71f-111">**Local System account**</span></span>  
 <span data-ttu-id="cd71f-112">Укажите локальную системную учетную запись, для которой не требуется пароль.</span><span class="sxs-lookup"><span data-stu-id="cd71f-112">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="cd71f-113">Однако локальная системная учетная запись может препятствовать взаимодействию служб с другими серверами, в зависимости от прав доступа, предоставленных этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="cd71f-113">However, the local system account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="cd71f-114">**Эта учетная запись**</span><span class="sxs-lookup"><span data-stu-id="cd71f-114">**This account**</span></span>  
 <span data-ttu-id="cd71f-115">Укажите локальную или доменную учетную запись, использующую аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="cd71f-115">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="cd71f-116">Для служб рекомендуется использовать доменную учетную запись с минимальными правами.</span><span class="sxs-lookup"><span data-stu-id="cd71f-116">We recommend using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="cd71f-117">Дополнительные сведения о выборе учетной записи см. в разделе «Настройка учетных записей служб Windows» электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cd71f-117">For information about selecting an account, "Setting Up Windows Service Accounts" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="cd71f-118">**Account Name** (Имя учетной записи)</span><span class="sxs-lookup"><span data-stu-id="cd71f-118">**Account Name**</span></span>  
 <span data-ttu-id="cd71f-119">Укажите имя локальной или доменной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="cd71f-119">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="cd71f-120">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="cd71f-120">**Password**</span></span>  
 <span data-ttu-id="cd71f-121">Введите пароль для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="cd71f-121">Type the password of the account.</span></span>  
  
 <span data-ttu-id="cd71f-122">**Подтверждение пароля**</span><span class="sxs-lookup"><span data-stu-id="cd71f-122">**Confirm password**</span></span>  
 <span data-ttu-id="cd71f-123">Введите пароль для учетной записи еще раз.</span><span class="sxs-lookup"><span data-stu-id="cd71f-123">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="cd71f-124">**Начало**</span><span class="sxs-lookup"><span data-stu-id="cd71f-124">**Start**</span></span>  
 <span data-ttu-id="cd71f-125">Запускает службу.</span><span class="sxs-lookup"><span data-stu-id="cd71f-125">Start the service.</span></span>  
  
 <span data-ttu-id="cd71f-126">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="cd71f-126">**Stop**</span></span>  
 <span data-ttu-id="cd71f-127">Остановить службу.</span><span class="sxs-lookup"><span data-stu-id="cd71f-127">Stop the service.</span></span>  
  
 <span data-ttu-id="cd71f-128">**Приостановить**</span><span class="sxs-lookup"><span data-stu-id="cd71f-128">**Pause**</span></span>  
 <span data-ttu-id="cd71f-129">Приостановить службу.</span><span class="sxs-lookup"><span data-stu-id="cd71f-129">Pause the service.</span></span>  
  
 <span data-ttu-id="cd71f-130">**Возобновить**</span><span class="sxs-lookup"><span data-stu-id="cd71f-130">**Resume**</span></span>  
 <span data-ttu-id="cd71f-131">Возобновить приостановленную работу службы.</span><span class="sxs-lookup"><span data-stu-id="cd71f-131">Resume a paused service.</span></span>  
  
  
