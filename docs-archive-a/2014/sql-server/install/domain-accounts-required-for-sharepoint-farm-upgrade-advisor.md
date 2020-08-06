---
title: Учетные записи домена, необходимые для фермы SharePoint (советник по переходу) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 90cd6d3e-a271-4cb8-81f2-fc555b2d3cab
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 7d180fbc12a264256156c878916838f7caeec723
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668622"
---
# <a name="domain-accounts-required-for-sharepoint-farm-upgrade-advisor"></a><span data-ttu-id="cd53b-102">Для фермы SharePoint требуются учетные записи домена (советник по переходу)</span><span class="sxs-lookup"><span data-stu-id="cd53b-102">Domain accounts required for SharePoint farm (Upgrade Advisor)</span></span>
  <span data-ttu-id="cd53b-103">Продукты SharePoint, которые настроены для среды ферм, требуют использования учетных записей домена.</span><span class="sxs-lookup"><span data-stu-id="cd53b-103">SharePoint products that are configured for a farm environment require that you use domain accounts.</span></span>  
  
||  
|-|  
|<span data-ttu-id="cd53b-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Режим интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cd53b-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="cd53b-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="cd53b-105">Component</span></span>  
 [!INCLUDE[ssRS](../../includes/ssrs.md)]  
  
### <a name="description"></a><span data-ttu-id="cd53b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="cd53b-106">Description</span></span>  
 <span data-ttu-id="cd53b-107">Продукты SharePoint, настроенные для среды ферм, требуют использования учетных записей домена для служб и подключений к базе данных.</span><span class="sxs-lookup"><span data-stu-id="cd53b-107">SharePoint products that are configured for a farm environment require that you use domain accounts for services and database connections.</span></span> <span data-ttu-id="cd53b-108">Это касается учетной записи, заданной в качестве учетной записи службы Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="cd53b-108">This includes the account you have specified for the Reporting Services service account.</span></span>  
  
 <span data-ttu-id="cd53b-109">Страницы центра администрирования SharePoint 2010 — единственное место, где можно увидеть ошибки, если для службы Reporting Services не используется учетная запись пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="cd53b-109">SharePoint 2010 Central Administration pages are one place you will see problems if you are not using a domain user account for Reporting Services.</span></span> <span data-ttu-id="cd53b-110">При попытке настройки интеграции служб Reporting Services будет выдано сообщение об ошибке следующего содержания:</span><span class="sxs-lookup"><span data-stu-id="cd53b-110">When you try to configure Reporting Services integration, you will see an error message similar to the following:</span></span>  
  
 <span data-ttu-id="cd53b-111">«Сервер отчетов запущен от имени встроенной учетной записи NT AUTHORITY\NETWORK SERVICE, которая не поддерживается установкой фермы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cd53b-111">"The report server is running under the built-in NT AUTHORITY\NETWORK SERVICE account, which is not supported by a SharePoint farm installation.</span></span> <span data-ttu-id="cd53b-112">Необходимо повторно настроить службу сервера отчетов для запуска от имени учетной записи пользователя домена».</span><span class="sxs-lookup"><span data-stu-id="cd53b-112">Please reconfigure the report server to run under a domain account."</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="cd53b-113">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="cd53b-113">Corrective Action</span></span>  
 <span data-ttu-id="cd53b-114">Для [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] и предыдущих версий используйте диспетчер конфигурации служб Reporting Services, чтобы изменить учетную запись, назначенную в качестве учетной записи службы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="cd53b-114">For [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and previous versions, use the Reporting Services Configuration Manager to change the account that is assigned as the report server service account.</span></span>  
  
#### <a name="to-change-the-service-account-from-configuration-manager"></a><span data-ttu-id="cd53b-115">Изменение учетной записи службы, используйте диспетчер конфигурации</span><span class="sxs-lookup"><span data-stu-id="cd53b-115">To change the service account from Configuration Manager</span></span>  
  
1.  <span data-ttu-id="cd53b-116">В меню **Пуск** выберите **все программы**, а затем щелкните **Microsoft SQL Server 2008 R2**.</span><span class="sxs-lookup"><span data-stu-id="cd53b-116">From the **Start** menu, select **All Programs**, and then click **Microsoft SQL Server 2008 R2**.</span></span>  
  
2.  <span data-ttu-id="cd53b-117">Выберите **средства настройки**и щелкните **Диспетчер конфигурации служб Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="cd53b-117">Select **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="cd53b-118">В Configuration Manager выберите вкладку **учетная запись службы** .</span><span class="sxs-lookup"><span data-stu-id="cd53b-118">In Configuration Manager, select the **Service Account** tab.</span></span>  
  
4.  <span data-ttu-id="cd53b-119">Выберите **использовать другую учетную запись** и введите учетные данные для учетной записи домена.</span><span class="sxs-lookup"><span data-stu-id="cd53b-119">Select **Use another account** and enter the credentials for a domain account.</span></span>  
  
5.  <span data-ttu-id="cd53b-120">Щелкните **Применить**.</span><span class="sxs-lookup"><span data-stu-id="cd53b-120">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd53b-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="cd53b-121">See Also</span></span>  
 [<span data-ttu-id="cd53b-122">Настройка учетной записи службы сервера отчетов (диспетчер конфигурации служб SSRS)</span><span class="sxs-lookup"><span data-stu-id="cd53b-122">Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../../reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)  
  
  
