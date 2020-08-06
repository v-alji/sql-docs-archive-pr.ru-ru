---
title: Свойства SQL Server (вкладка "Вход в систему") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: f54be594-f290-4db2-bf18-fd2521728a4a
author: stevestein
ms.author: sstein
ms.openlocfilehash: a2fca58ee9b419613bc8f1dbd325481efc9069c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665689"
---
# <a name="report-server-properties-log-on-tab"></a><span data-ttu-id="7c56a-102">Свойства сервера отчетов (вкладка «Вход в систему»)</span><span class="sxs-lookup"><span data-stu-id="7c56a-102">Report Server Properties (Log On Tab)</span></span>
  <span data-ttu-id="7c56a-103">Используйте вкладку **Вход** в диалоговом окне **Свойства сервера отчетов** для указания учетной записи, используемой службой сервера отчетов, а также для запуска и остановки службы.</span><span class="sxs-lookup"><span data-stu-id="7c56a-103">Use the **Log On** tab of the **Report Server Properties** dialog box to specify the account used by the Report Server service, and to start and stop the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7c56a-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="7c56a-104">Options</span></span>  
 <span data-ttu-id="7c56a-105">**Локальная системная учетная запись**</span><span class="sxs-lookup"><span data-stu-id="7c56a-105">**Local System account**</span></span>  
 <span data-ttu-id="7c56a-106">Укажите локальную системную учетную запись, для которой не требуется пароль.</span><span class="sxs-lookup"><span data-stu-id="7c56a-106">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="7c56a-107">Однако локальная системная учетная запись может ограничить взаимодействие служб с другими серверами, это зависит от прав доступа, предоставленных этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="7c56a-107">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="7c56a-108">**Эта учетная запись**</span><span class="sxs-lookup"><span data-stu-id="7c56a-108">**This account**</span></span>  
 <span data-ttu-id="7c56a-109">Укажите локальную или доменную учетную запись пользователя, использующую проверку подлинности [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="7c56a-109">Specify a local or domain user account that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="7c56a-110">рекомендует использовать доменную учетную запись пользователя с минимальными правами.</span><span class="sxs-lookup"><span data-stu-id="7c56a-110">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="7c56a-111">Дополнительные сведения о выборе учетной записи см. в разделе «Настройка учетных записей служб Windows» электронной документации.</span><span class="sxs-lookup"><span data-stu-id="7c56a-111">For information about selecting an account, search Books Online for the topic Setting Up Windows Service Accounts.</span></span>  
  
 <span data-ttu-id="7c56a-112">**Account Name** (Имя учетной записи)</span><span class="sxs-lookup"><span data-stu-id="7c56a-112">**Account Name**</span></span>  
 <span data-ttu-id="7c56a-113">Укажите имя локальной или доменной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="7c56a-113">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="7c56a-114">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="7c56a-114">**Password**</span></span>  
 <span data-ttu-id="7c56a-115">Введите пароль для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="7c56a-115">Type the password of the account.</span></span>  
  
 <span data-ttu-id="7c56a-116">**Подтверждение пароля**</span><span class="sxs-lookup"><span data-stu-id="7c56a-116">**Confirm password**</span></span>  
 <span data-ttu-id="7c56a-117">Введите пароль для учетной записи еще раз.</span><span class="sxs-lookup"><span data-stu-id="7c56a-117">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="7c56a-118">**Начало**</span><span class="sxs-lookup"><span data-stu-id="7c56a-118">**Start**</span></span>  
 <span data-ttu-id="7c56a-119">Запускает службу.</span><span class="sxs-lookup"><span data-stu-id="7c56a-119">Start the service.</span></span>  
  
 <span data-ttu-id="7c56a-120">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="7c56a-120">**Stop**</span></span>  
 <span data-ttu-id="7c56a-121">Остановить службу.</span><span class="sxs-lookup"><span data-stu-id="7c56a-121">Stop the service.</span></span>  
  
 <span data-ttu-id="7c56a-122">**Приостановить**</span><span class="sxs-lookup"><span data-stu-id="7c56a-122">**Pause**</span></span>  
 <span data-ttu-id="7c56a-123">Приостановить службу.</span><span class="sxs-lookup"><span data-stu-id="7c56a-123">Pause the service.</span></span>  
  
 <span data-ttu-id="7c56a-124">**Возобновить**</span><span class="sxs-lookup"><span data-stu-id="7c56a-124">**Resume**</span></span>  
 <span data-ttu-id="7c56a-125">Возобновить приостановленную работу службы.</span><span class="sxs-lookup"><span data-stu-id="7c56a-125">Resume a paused service.</span></span>  
  
  
