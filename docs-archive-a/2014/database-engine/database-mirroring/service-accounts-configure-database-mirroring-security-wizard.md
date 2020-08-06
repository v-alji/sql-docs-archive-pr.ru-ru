---
title: Учетные записи службы (мастер настройки безопасности зеркального отображения баз данных) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.serviceaccounts.f1
ms.assetid: d58d8f93-7888-4d66-af4d-969ef6a2dbee
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 58e49467a28e816c6592b1ded212b5aea0e6bc55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733054"
---
# <a name="service-accounts-configure-database-mirroring-security-wizard"></a><span data-ttu-id="4c047-102">Учетные записи службы (мастер настройки безопасности зеркального отображения баз данных)</span><span class="sxs-lookup"><span data-stu-id="4c047-102">Service Accounts (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="4c047-103">При использовании проверки подлинности Windows, в случае если экземпляры сервера используют разные учетные записи, задайте учетные записи службы для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c047-103">When using Windows Authentication, if the server instances use different accounts, specify the service accounts for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4c047-104">Эти учетные записи службы должны быть учетными записями домена (одного и того же или доверенных доменов).</span><span class="sxs-lookup"><span data-stu-id="4c047-104">These service accounts must all be domain accounts (in the same or trusted domains).</span></span>  
  
 <span data-ttu-id="4c047-105">Если все экземпляры сервера используют одну и ту же учетную запись домена или проверку подлинности, основанную на сертификатах, оставьте поля незаполненными.</span><span class="sxs-lookup"><span data-stu-id="4c047-105">If all the server instances use the same domain account or use certificate-based authentication, leave the fields blank.</span></span> <span data-ttu-id="4c047-106">Просто нажмите кнопку **Готово**, и мастер автоматически настроит учетные записи на основе учетной записи текущего мастера.</span><span class="sxs-lookup"><span data-stu-id="4c047-106">Simply click **Finish**, and the wizard automatically configures the accounts based on the account of the current wizard.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4c047-107">Если конечные точки зеркального отображения базы данных экземпляров сервера настроены для использования сертификатов, необходимо оставить все поля учетной записи службы пустыми.</span><span class="sxs-lookup"><span data-stu-id="4c047-107">If the database mirroring endpoints of the server instances are configured to use certificates, you must leave the service account fields empty.</span></span>  
  
 <span data-ttu-id="4c047-108">**Настройка зеркального отображения базы данных в среде SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="4c047-108">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="4c047-109">Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="4c047-109">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="4c047-110">Запуск мастера настройки безопасности зеркального отображения баз данных (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="4c047-110">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="4c047-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="4c047-111">Options</span></span>  
 <span data-ttu-id="4c047-112">**Основной**</span><span class="sxs-lookup"><span data-stu-id="4c047-112">**Principal**</span></span>  
 <span data-ttu-id="4c047-113">Укажите учетную запись службы экземпляра основного сервера.</span><span class="sxs-lookup"><span data-stu-id="4c047-113">Specify the service account of the principal server instance.</span></span> <span data-ttu-id="4c047-114">Введите имя домена прописными буквами:</span><span class="sxs-lookup"><span data-stu-id="4c047-114">Enter the domain name in upper case:</span></span>  
  
 <span data-ttu-id="4c047-115">*Имя_домена* \\ *имя пользователя*</span><span class="sxs-lookup"><span data-stu-id="4c047-115">*DOMAINNAME*\\*username*</span></span>  
  
 <span data-ttu-id="4c047-116">**Зеркальное отображение**</span><span class="sxs-lookup"><span data-stu-id="4c047-116">**Mirror**</span></span>  
 <span data-ttu-id="4c047-117">Укажите учетную запись службы экземпляра зеркального сервера.</span><span class="sxs-lookup"><span data-stu-id="4c047-117">Specify the service account of the mirror server instance.</span></span> <span data-ttu-id="4c047-118">Введите имя домена прописными буквами:</span><span class="sxs-lookup"><span data-stu-id="4c047-118">Enter the domain name in upper case:</span></span>  
  
 <span data-ttu-id="4c047-119">*Имя_домена* \\ *имя пользователя*</span><span class="sxs-lookup"><span data-stu-id="4c047-119">*DOMAINNAME*\\*username*</span></span>  
  
 <span data-ttu-id="4c047-120">**-**</span><span class="sxs-lookup"><span data-stu-id="4c047-120">**Witness**</span></span>  
 <span data-ttu-id="4c047-121">Укажите учетную запись службы экземпляра следящего сервера.</span><span class="sxs-lookup"><span data-stu-id="4c047-121">Specify the service account of the witness server instance.</span></span> <span data-ttu-id="4c047-122">Введите имя домена прописными буквами:</span><span class="sxs-lookup"><span data-stu-id="4c047-122">Enter the domain name in upper case:</span></span>  
  
 <span data-ttu-id="4c047-123">*Имя_домена* \\ *имя пользователя*</span><span class="sxs-lookup"><span data-stu-id="4c047-123">*DOMAINNAME*\\*username*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c047-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="4c047-124">See Also</span></span>  
 <span data-ttu-id="4c047-125">[Свойства базы данных (страница "Зеркальное отображение")](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="4c047-125">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="4c047-126">[Запуск монитора зеркального отображения баз данных (среда SQL Server Management Studio)](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="4c047-126">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="4c047-127">[Зеркальное отображение базы данных (SQL Server)](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4c047-127">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="4c047-128">Настройка учетных записей входа для зеркального отображения базы данных или группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c047-128">Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](set-up-login-accounts-database-mirroring-always-on-availability.md)  
  
  
