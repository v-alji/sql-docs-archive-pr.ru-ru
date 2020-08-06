---
title: 'Подключение к данным использует проверку подлинности Windows, а учетные данные нельзя делегировать. Не удалось обновить следующие соединения: данные PowerPivot | Документация Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d2006df1-d244-4786-b272-49d8996cc88c
author: minewiskan
ms.author: owend
ms.openlocfilehash: be4c61ad4514f3aa4f6f1eda1fe44ad97c4c064f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657962"
---
# <a name="the-data-connection-uses-windows-authentication-and-user-credentials-could-not-be-delegated-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="d5f49-103">Подключение к данным использует проверку подлинности Windows, а учетные данные нельзя делегировать.</span><span class="sxs-lookup"><span data-stu-id="d5f49-103">The data connection uses Windows Authentication and user credentials could not be delegated.</span></span> <span data-ttu-id="d5f49-104">Следующие соединения не удалось обновить: данные PowerPivot</span><span class="sxs-lookup"><span data-stu-id="d5f49-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="d5f49-105">Служба Excel Services возвращает эту ошибку для книг Excel, содержащих данные PowerPivot, если она не может подключиться к экземпляру сервера PowerPivot в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d5f49-105">For Excel workbooks that contain PowerPivot data, Excel Services returns this error if it cannot connect to a PowerPivot server instance in SharePoint.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d5f49-106">Сведения</span><span class="sxs-lookup"><span data-stu-id="d5f49-106">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d5f49-107">Применяется к</span><span class="sxs-lookup"><span data-stu-id="d5f49-107">Applies to</span></span>|<span data-ttu-id="d5f49-108">PowerPivot для SharePoint</span><span class="sxs-lookup"><span data-stu-id="d5f49-108">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="d5f49-109">Версия продукта</span><span class="sxs-lookup"><span data-stu-id="d5f49-109">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="d5f49-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5f49-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="d5f49-111">Причина</span><span class="sxs-lookup"><span data-stu-id="d5f49-111">Cause</span></span>|<span data-ttu-id="d5f49-112">Сбой соединения при попытке использовать поставщик данных PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="d5f49-112">Connection failed when attempting to use a PowerPivot data provider.</span></span>|  
|<span data-ttu-id="d5f49-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="d5f49-113">Message Text</span></span>|<span data-ttu-id="d5f49-114">Подключение к данным использует проверку подлинности Windows, а учетные данные нельзя делегировать.</span><span class="sxs-lookup"><span data-stu-id="d5f49-114">The data connection uses Windows Authentication and user credentials could not be delegated.</span></span> <span data-ttu-id="d5f49-115">Следующие соединения не удалось обновить: данные PowerPivot</span><span class="sxs-lookup"><span data-stu-id="d5f49-115">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d5f49-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="d5f49-116">Explanation</span></span>  
 <span data-ttu-id="d5f49-117">Есть несколько причин возникновения этого сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="d5f49-117">There are multiple causes for this error message.</span></span> <span data-ttu-id="d5f49-118">Общим для всех них является то, что служба Excel Services не может получить действительное удостоверение пользователя Windows из токена утверждений в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d5f49-118">The common factor behind all of them is that Excel Services cannot get a valid Windows user identity from a claims token in SharePoint.</span></span> <span data-ttu-id="d5f49-119">При работе с книгами Excel, которые содержат данные PowerPivot, эта ошибка возникает при наличии любого из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="d5f49-119">In the case of Excel workbooks that contain PowerPivot data, this error occurs when any of the following conditions exist:</span></span>  
  
-   <span data-ttu-id="d5f49-120">Служба Claims to Windows Token Service не работает.</span><span class="sxs-lookup"><span data-stu-id="d5f49-120">The Claims to Windows Token Service is not running.</span></span> <span data-ttu-id="d5f49-121">Подтвердить причину этой ошибки можно, открыв файл журнала SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d5f49-121">You can confirm the cause of this error by viewing the SharePoint log file.</span></span> <span data-ttu-id="d5f49-122">Если в журналах SharePoint есть сообщение «Конечная точка конвейера 'net.pipe://localhost/s4u/022694f3-9fbd-422b-b4b2-312e25dae2a2' не обнаружена на локальном компьютере», значит служба Claims to Windows Token Service не работает.</span><span class="sxs-lookup"><span data-stu-id="d5f49-122">If the SharePoint logs include the message "The pipe endpoint 'net.pipe://localhost/s4u/022694f3-9fbd-422b-b4b2-312e25dae2a2' could not be found on your local machine", the Claims to Windows Token Service is not running.</span></span> <span data-ttu-id="d5f49-123">Воспользуйтесь центром администрирования, чтобы запустить ее, а затем удостоверьтесь, что она работает в консольном приложении «Службы».</span><span class="sxs-lookup"><span data-stu-id="d5f49-123">To start it, use Central Administration and then verify the service is running in the Services console application.</span></span>  
  
-   <span data-ttu-id="d5f49-124">Контроллер домена недоступен для проверки удостоверения пользователя.</span><span class="sxs-lookup"><span data-stu-id="d5f49-124">A domain controller is not available to validate the user identity.</span></span> <span data-ttu-id="d5f49-125">Служба Claims to Windows Token Service не использует кэшированные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="d5f49-125">The Claims to Windows Token Service does not use cached credentials.</span></span> <span data-ttu-id="d5f49-126">Она проверяет удостоверение пользователя для каждого соединения.</span><span class="sxs-lookup"><span data-stu-id="d5f49-126">It validates the user identity for each connection.</span></span> <span data-ttu-id="d5f49-127">Подтвердить причину этой ошибки можно, открыв файл журнала SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d5f49-127">You can confirm the cause of this error by viewing the SharePoint log file.</span></span> <span data-ttu-id="d5f49-128">Если в журналах SharePoint есть сообщение «Не удалось получить WindowsIdentity от IClaimsIdentity», то подлинность удостоверения пользователя не удалось проверить.</span><span class="sxs-lookup"><span data-stu-id="d5f49-128">If the SharePoint logs include the message "Failed to get WindowsIdentity from IClaimsIdentity", the user identity could not be authenticated.</span></span>  
  
-   <span data-ttu-id="d5f49-129">Компьютеры должны входить в один домен или в домены с двусторонними отношениями доверия.</span><span class="sxs-lookup"><span data-stu-id="d5f49-129">The computers must be members of the same domain or in domains that have a two-way trust relationship.</span></span>  
  
-   <span data-ttu-id="d5f49-130">Необходимо использовать учетные записи пользователей домена Windows.</span><span class="sxs-lookup"><span data-stu-id="d5f49-130">You must use Windows domain user accounts.</span></span> <span data-ttu-id="d5f49-131">Учетные записи должны иметь универсальное имя участника (UPN).</span><span class="sxs-lookup"><span data-stu-id="d5f49-131">The accounts must have a Universal Principal Name (UPN).</span></span>  
  
-   <span data-ttu-id="d5f49-132">Чтобы запрашивать объект, учетная запись службы Excel Services должна иметь разрешения для Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d5f49-132">The Excel Services service account must have Active Directory permissions to query the object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d5f49-133">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="d5f49-133">User Action</span></span>  
 <span data-ttu-id="d5f49-134">Следуйте приведенным далее инструкциям для проверки состояния службы Claims to Windows Token Service.</span><span class="sxs-lookup"><span data-stu-id="d5f49-134">Use the following instructions to check the status of the Claims to Windows Token Service.</span></span>  
  
 <span data-ttu-id="d5f49-135">Сведения обо всех прочих сценариях можно получить у своего сетевого администратора.</span><span class="sxs-lookup"><span data-stu-id="d5f49-135">For all other scenarios, check with your network administrator.</span></span>  
  
#### <a name="enable-claims-to-windows-token-service"></a><span data-ttu-id="d5f49-136">Включите службу Claims to Windows Token Service</span><span class="sxs-lookup"><span data-stu-id="d5f49-136">Enable Claims to Windows Token Service</span></span>  
  
1.  <span data-ttu-id="d5f49-137">В центре администрирования в окне «Системные параметры» выберите пункт **Управление службами на сервере**.</span><span class="sxs-lookup"><span data-stu-id="d5f49-137">In Central Administration, in System Settings, click **Manage services on server**.</span></span>  
  
2.  <span data-ttu-id="d5f49-138">Выберите **Claims to Windows Token Service**, а затем нажмите кнопку **Пуск**.</span><span class="sxs-lookup"><span data-stu-id="d5f49-138">Select **Claims to Windows Token Service**, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="d5f49-139">Также убедитесь в том, что служба запущена, в консоли «Службы».</span><span class="sxs-lookup"><span data-stu-id="d5f49-139">Verify the service is also running in the Services console:</span></span>  
  
    1.  <span data-ttu-id="d5f49-140">В окне «Средства администрирования» выберите «Службы».</span><span class="sxs-lookup"><span data-stu-id="d5f49-140">In Administrative Tools, click Services.</span></span>  
  
    2.  <span data-ttu-id="d5f49-141">Запустите службу Claims to Windows Token Service, если она не работает.</span><span class="sxs-lookup"><span data-stu-id="d5f49-141">Start the Claims to Windows Token Service if it is not running.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5f49-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="d5f49-142">See Also</span></span>  
 [<span data-ttu-id="d5f49-143">Указание учетных записей служб PowerPivot</span><span class="sxs-lookup"><span data-stu-id="d5f49-143">Configure PowerPivot Service Accounts</span></span>](configure-power-pivot-service-accounts.md)  
  
  
