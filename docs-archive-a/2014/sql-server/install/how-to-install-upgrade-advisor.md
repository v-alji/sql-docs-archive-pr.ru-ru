---
title: Руководство. Установка советника по переходу | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, installing
- Upgrade Advisor [SQL Server], installing
ms.assetid: 481b0704-ce79-4543-b141-67306128aa2b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3ed5b66522126bfabc94bfa8036ec6c31ac04500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668064"
---
# <a name="how-to-install-upgrade-advisor"></a><span data-ttu-id="af047-102">Установка помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="af047-102">How to: Install Upgrade Advisor</span></span>
  <span data-ttu-id="af047-103">Помощник по обновлению поддерживает удаленный анализ всех поддерживаемых компонентов, за исключением служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af047-103">Upgrade Advisor supports remote analysis of all supported components except [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="af047-104">Если просмотр экземпляров служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] не производится, помощник по обновлению может быть установлен на любой компьютер, который способен установить соединение с требуемым экземплярам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af047-104">If you are not scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can install Upgrade Advisor on any computer that can connect to your instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="af047-105">Компьютер также должен удовлетворять необходимым условиям для установки помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="af047-105">The computer must also meet Upgrade Advisor prerequisites.</span></span> <span data-ttu-id="af047-106">Для просмотра экземпляров служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]следует установить помощник по обновлению на сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="af047-106">If you are scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must install Upgrade Advisor on the report server.</span></span>  
  
 <span data-ttu-id="af047-107">Дополнительные сведения см. в разделе [Установка помощника по обновлению](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="af047-107">For more information, see [Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span></span>  
  
### <a name="to-install-upgrade-advisor"></a><span data-ttu-id="af047-108">Установка помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="af047-108">To install Upgrade Advisor</span></span>  
  
1.  <span data-ttu-id="af047-109">Запустите установку одним из следующих методов.</span><span class="sxs-lookup"><span data-stu-id="af047-109">Start the installation using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="af047-110">Если выполняется установка с [!INCLUDE[msCoName](../../includes/msconame-md.md)] веб-сайта, щелкните ссылку для **скачивания** и нажмите кнопку **выполнить** , чтобы начать установку.</span><span class="sxs-lookup"><span data-stu-id="af047-110">If you are installing from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Web site, click the **Download** link and then click the **Run** button to start the installation.</span></span>  
  
    -   <span data-ttu-id="af047-111">Если выполняется установка с носителя продукта, откройте папку **Redist** , откройте папку **советника по переходу** , а затем дважды щелкните **SQLUA.msi**.</span><span class="sxs-lookup"><span data-stu-id="af047-111">If you are installing from the product media, open the **redist** folder, open the **Upgrade Advisor** folder, and then double-click **SQLUA.msi**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="af047-112">Для удаления советника по переходу необходима платформа [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="af047-112">Upgrade Advisor requires the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework 4.</span></span> <span data-ttu-id="af047-113">Если платформа не установлена или установлена ее предварительная версия, будет выдано сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="af047-113">If it is not installed, or if you have a pre-release version, an error message will appear.</span></span> <span data-ttu-id="af047-114">Сначала удалите все предыдущие версии платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], а затем установите последнюю версию платформы .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="af047-114">Uninstall any earlier version of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] and then install the latest version of .NET Framework 4.</span></span>  
    >   
    >  <span data-ttu-id="af047-115">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom является необходимым условием для установки [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] помощника по обновлению и не устанавливается программой установки помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="af047-115">The [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom is a prerequisite for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor, and is not installed by Upgrade Advisor Setup.</span></span> <span data-ttu-id="af047-116">Для установки необходимо загрузить и установить [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom из [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] пакета дополнительных компонентов.</span><span class="sxs-lookup"><span data-stu-id="af047-116">The Setup requires you to download and install the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span></span>  
  
2.  <span data-ttu-id="af047-117">На странице **Добро пожаловать на страницу [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] установки советника по переходу** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="af047-117">On the **Welcome to the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor Setup** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="af047-118">На странице Лицензионное **соглашение** прочтите лицензионное соглашение.</span><span class="sxs-lookup"><span data-stu-id="af047-118">On the **License Agreement** page, read the license agreement.</span></span> <span data-ttu-id="af047-119">Если вы согласны, установите флажок **я принимаю условия лицензионного соглашения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="af047-119">If you agree, select **I accept the license agreement** and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="af047-120">На странице **сведения о регистрации** введите свое имя и название компании.</span><span class="sxs-lookup"><span data-stu-id="af047-120">On the **Registration Information** page, enter your name and company.</span></span>  
  
5.  <span data-ttu-id="af047-121">На странице **Выбор компонентов** проверьте значение параметра **путь установки** .</span><span class="sxs-lookup"><span data-stu-id="af047-121">On the **Feature Selection** page, review the **Installation path** value.</span></span> <span data-ttu-id="af047-122">При необходимости используйте кнопку **Обзор** , чтобы изменить расположение.</span><span class="sxs-lookup"><span data-stu-id="af047-122">If necessary, use the **Browse** button to change the location.</span></span> <span data-ttu-id="af047-123">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="af047-123">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="af047-124">На странице **все готово для установки программы** нажмите кнопку **установить** , чтобы установить советник по переходу.</span><span class="sxs-lookup"><span data-stu-id="af047-124">On the **Ready to Install the Program** page, click **Install** to install Upgrade Advisor.</span></span>  
  
7.  <span data-ttu-id="af047-125">Нажмите кнопку **Готово**, чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="af047-125">Click **Finish** to exit the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af047-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="af047-126">See Also</span></span>  
 [<span data-ttu-id="af047-127">Компоненты, необходимые для помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="af047-127">Upgrade Advisor Prerequisites</span></span>](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md)  
  
  
