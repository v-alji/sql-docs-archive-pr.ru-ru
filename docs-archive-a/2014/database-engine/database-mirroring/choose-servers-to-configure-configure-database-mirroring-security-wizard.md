---
title: Выбор серверов для настройки (мастер настройки безопасности зеркального отображения баз данных) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.choosesrvrs.f1
ms.assetid: 59e23ff3-d7ee-4e32-9629-0b54d3a258f7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 18e36f5c8ec020b3859dc847d1bbfc019817bcd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657295"
---
# <a name="choose-servers-to-configure-configure-database-mirroring-security-wizard"></a><span data-ttu-id="549d7-102">Выбор серверов для настройки (мастер настройки безопасности зеркального отображения баз данных)</span><span class="sxs-lookup"><span data-stu-id="549d7-102">Choose Servers to Configure (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="549d7-103">Используйте данную страницу для задания экземпляров сервера, которые нужно настроить в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="549d7-103">Use this page to specify which server instances you want to configure now.</span></span> <span data-ttu-id="549d7-104">Перед продолжением выполнения мастера необходимо выбрать хотя бы один экземпляр сервера.</span><span class="sxs-lookup"><span data-stu-id="549d7-104">You must select at least one server instance before continuing the wizard.</span></span>  
  
 <span data-ttu-id="549d7-105">При снятии флажка для экземпляра сервера мастер не внесет в него никаких изменений.</span><span class="sxs-lookup"><span data-stu-id="549d7-105">If you clear the check box for a server instance, the wizard will not make any changes to it.</span></span> <span data-ttu-id="549d7-106">Мастер, однако, выдаст приглашение для ввода данных о данном экземпляре и сохранит эти данные в составе конфигурации других экземпляров сервера.</span><span class="sxs-lookup"><span data-stu-id="549d7-106">The wizard, however, will ask you to enter information about that instance and save this information as part of the configuration of the other server instances.</span></span> <span data-ttu-id="549d7-107">Например, если снять этот флажок для экземпляра следящего сервера, мастер выдаст запрос на ввод учетной записи службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] свидетеля, поскольку имя входа для этой учетной записи необходимо создать как часть конфигурации безопасности, сохраненной в экземплярах основного и зеркального сервера.</span><span class="sxs-lookup"><span data-stu-id="549d7-107">For example, if you clear the check box for the witness server instance, the wizard will ask you to enter the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account of the witness because a login for that account must be created as part of the security configuration saved at the principal and mirror server instances.</span></span>  
  
 <span data-ttu-id="549d7-108">**Настройка зеркального отображения базы данных в среде SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="549d7-108">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="549d7-109">Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="549d7-109">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="549d7-110">Запуск мастера настройки безопасности зеркального отображения баз данных (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="549d7-110">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="549d7-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="549d7-111">Options</span></span>  
 <span data-ttu-id="549d7-112">**Экземпляр основного сервера**</span><span class="sxs-lookup"><span data-stu-id="549d7-112">**Principal server instance**</span></span>  
 <span data-ttu-id="549d7-113">Выберите этот пункт для настройки безопасности основного сервера.</span><span class="sxs-lookup"><span data-stu-id="549d7-113">Select to configure security for the principal server.</span></span>  
  
 <span data-ttu-id="549d7-114">**Экземпляр зеркального сервера**</span><span class="sxs-lookup"><span data-stu-id="549d7-114">**Mirror server instance**</span></span>  
 <span data-ttu-id="549d7-115">Выберите этот пункт для настройки безопасности зеркального сервера.</span><span class="sxs-lookup"><span data-stu-id="549d7-115">Select to configure security for the mirror server.</span></span>  
  
 <span data-ttu-id="549d7-116">**Экземпляр следящего сервера**</span><span class="sxs-lookup"><span data-stu-id="549d7-116">**Witness server instance**</span></span>  
 <span data-ttu-id="549d7-117">Выберите этот пункт для настройки безопасности следящего сервера (при его наличии).</span><span class="sxs-lookup"><span data-stu-id="549d7-117">Select to configure security for the witness server (if present).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="549d7-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="549d7-118">See Also</span></span>  
 <span data-ttu-id="549d7-119">[Свойства базы данных (страница "Зеркальное отображение")](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="549d7-119">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 [<span data-ttu-id="549d7-120">Зеркальное отображение базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="549d7-120">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
