---
title: Добавление или замена следящего сервера зеркального отображения базы данных (среда SQL Server Management Studio) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], establishing
- database mirroring [SQL Server], witness
ms.assetid: 4b5ecffd-f025-4ab7-b69d-8958c6477127
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5dd14ace23956ceef114f1f032b5d4db5febcec7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657300"
---
# <a name="add-or-replace-a-database-mirroring-witness-sql-server-management-studio"></a><span data-ttu-id="15400-102">Добавление или замена следящего сервера зеркального отображения базы данных (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="15400-102">Add or Replace a Database Mirroring Witness (SQL Server Management Studio)</span></span>
  <span data-ttu-id="15400-103">Если конечные точки зеркального отображения базы данных используют проверку подлинности Windows, для добавления или замены следящего сервера можно использовать среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15400-103">If the database mirroring endpoints use Windows Authentication,, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to add or replace a witness.</span></span> <span data-ttu-id="15400-104">Добавление следящего сервера в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] изменяет текущий режим работы на режим высокого уровня безопасности с автоматической отработкой отказа.</span><span class="sxs-lookup"><span data-stu-id="15400-104">Adding a witness in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] also changes the operating mode to high-safety mode with automatic failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="15400-105">Настоятельно рекомендуется размещать следящий сервер на отдельном компьютере, не используемом ни одним из участников зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="15400-105">We strongly recommend that the witness reside on a separate computer from either of the partners.</span></span> <span data-ttu-id="15400-106">Учетная запись службы, используемая следящим сервером, должна располагаться в том же самом домене, что и учетные записи служб, используемые экземплярами основного и зеркального серверов, либо в доверенном домене.</span><span class="sxs-lookup"><span data-stu-id="15400-106">The service account used by the witness must be in the same domain as the service accounts used by the principal and mirror server instances, or it must be in a trusted domain.</span></span>  
  
### <a name="to-add-or-replace-a-witness"></a><span data-ttu-id="15400-107">Добавление или замена следящего сервера</span><span class="sxs-lookup"><span data-stu-id="15400-107">To Add or Replace a Witness</span></span>  
  
1.  <span data-ttu-id="15400-108">После подключения к экземпляру основного сервера в обозревателе объектов щелкните имя сервера, чтобы развернуть дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="15400-108">After connecting to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="15400-109">Разверните узел **Базы данных**и выберите основную базу данных сеанса, в котором добавляется или заменяется следящий сервер.</span><span class="sxs-lookup"><span data-stu-id="15400-109">Expand **Databases**, and select the principal database of the session to which you are adding or replacing a witness.</span></span>  
  
3.  <span data-ttu-id="15400-110">Щелкните базу данных правой кнопкой мыши, выберите **Задачи**, а затем **Зеркальное отображение**.</span><span class="sxs-lookup"><span data-stu-id="15400-110">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="15400-111">Откроется страница **Зеркальное отображение** диалогового окна **Свойства базы данных** .</span><span class="sxs-lookup"><span data-stu-id="15400-111">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="15400-112">Щелкните **Настройка безопасности**.</span><span class="sxs-lookup"><span data-stu-id="15400-112">Click **Configure Security**.</span></span>  
  
5.  <span data-ttu-id="15400-113">Если появилось окно **Мастер настройки безопасности зеркального отображения баз данных** , нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15400-113">If the **Configure Database Mirroring Security Wizard** welcome screen appears, click **Next**.</span></span>  
  
6.  <span data-ttu-id="15400-114">В диалоговом окне **Включение следящего сервера** установите переключатель **Да**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15400-114">In the **Include Witness Server** dialog box, click **Yes**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="15400-115">В диалоговом окне **Выбор серверов для настройки** будет автоматически установлен флажок **Экземпляр следящего сервера** .</span><span class="sxs-lookup"><span data-stu-id="15400-115">In the **Choose Servers to Configure** dialog box, the **Witness server instance** check box is automatically checked.</span></span> <span data-ttu-id="15400-116">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15400-116">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="15400-117">В диалоговом окне **Экземпляр основного сервера** сохраните указанный порт и конечную точку.</span><span class="sxs-lookup"><span data-stu-id="15400-117">On the **Principal Server Instance** dialog box, keep the existing port and endpoint.</span></span> <span data-ttu-id="15400-118">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15400-118">Click **Next**.</span></span>  
  
9. <span data-ttu-id="15400-119">В диалоговом окне **Экземпляр следящего сервера** нажмите кнопку **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="15400-119">On the **Witness Server Instance** dialog box, click **Connect**.</span></span>  
  
10. <span data-ttu-id="15400-120">В диалоговом окне **Соединение с сервером** в поле **Имя сервера** укажите экземпляр следящего сервера и использование проверки подлинности Windows (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="15400-120">In the **Connect to Server** dialog box, specify the witness server instance in the **Server name** field, and use Windows Authentication (the default).</span></span> <span data-ttu-id="15400-121">Нажмите кнопку **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="15400-121">Click **Connect**.</span></span>  
  
11. <span data-ttu-id="15400-122">После установления соединения прослушиваемый порт и конечная точка зеркального отображения базы данных экземпляра следящего сервера отображаются в диалоговом окне **Экземпляр следящего сервера** .</span><span class="sxs-lookup"><span data-stu-id="15400-122">Once a connection is established, the listener port and database mirroring endpoint of the witness server instance are displayed on the **Witness Server Instance** dialog box.</span></span> <span data-ttu-id="15400-123">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15400-123">Click **Next**.</span></span>  
  
12. <span data-ttu-id="15400-124">Диалоговое окно **Учетные записи служб** содержит поля доменных серверных учетных записей основного, зеркального и следящего экземпляров сервера.</span><span class="sxs-lookup"><span data-stu-id="15400-124">The **Service Accounts** dialog box contains fields for the domain service accounts of the principal, mirror, and witness server instances.</span></span>  
  
    -   <span data-ttu-id="15400-125">Если все экземпляры сервера используют одну и туже учетную запись, оставьте эти поля пустыми.</span><span class="sxs-lookup"><span data-stu-id="15400-125">If the server instances all use the same service account, leave the fields blank.</span></span>  
  
    -   <span data-ttu-id="15400-126">Если экземпляр следящего сервера использует не ту учетную запись, что другие участники, введите имя учетной записи в поля **Основной сервер**, **Зеркальный сервер**и **Следящий сервер** :</span><span class="sxs-lookup"><span data-stu-id="15400-126">If the witness server instance uses a different service account from either of the partners, fill in the **Principal**, **Mirror**, and **Witness** fields with the account name:</span></span>  
  
         <span data-ttu-id="15400-127">*ИМЯ_ДОМЕНА* **\\** *имя_пользователя*</span><span class="sxs-lookup"><span data-stu-id="15400-127">*DOMAINNAME* **\\** *username*</span></span>  
  
         <span data-ttu-id="15400-128">Имя домена должно содержать только символы верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="15400-128">The domain name must be in upper case.</span></span>  
  
     <span data-ttu-id="15400-129">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15400-129">Click **Next**.</span></span>  
  
13. <span data-ttu-id="15400-130">В итоговом окне **Завершение работы мастера** , в случае необходимости, проверьте конфигурацию следящего сервера и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="15400-130">On the **Complete the Wizard** summary screen, optionally, verify the witness configuration, and then click **Finish**.</span></span>  
  
14. <span data-ttu-id="15400-131">По завершении работы этот мастер возвращает в диалоговом окне **Свойства базы данных** сетевой адрес экземпляра следящего сервера, содержащийся в поле **Следящий сервер** .</span><span class="sxs-lookup"><span data-stu-id="15400-131">On finishing, the wizard returns you to the **Database Properties** dialog box where the server network address of the witness now appears in **Witness** field.</span></span> <span data-ttu-id="15400-132">Кроме того, автоматически выбирается режим **Высокая безопасность с автоматической отработкой отказа (синхронно)** , который необходим при работе со следящим сервером.</span><span class="sxs-lookup"><span data-stu-id="15400-132">Also, **High-safety mode with automatic failover (synchronous)**, which is required with a witness, is automatically selected.</span></span>  
  
     <span data-ttu-id="15400-133">Чтобы начать работу следящего сервера и изменить текущий режим работы на режим высокого уровня безопасности с автоматической отработкой отказа, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="15400-133">To enable the witness and change the session to high-safety mode with automatic failover, Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15400-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="15400-134">See Also</span></span>  
 <span data-ttu-id="15400-135">[Database Mirroring Witness](database-mirroring-witness.md) </span><span class="sxs-lookup"><span data-stu-id="15400-135">[Database Mirroring Witness](database-mirroring-witness.md) </span></span>  
 <span data-ttu-id="15400-136">[Зеркальное отображение базы данных (SQL Server)](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="15400-136">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="15400-137">[Свойства базы данных (страница "Зеркальное отображение")](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="15400-137">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="15400-138">[Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (среда SQL Server Management Studio)](establish-database-mirroring-session-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="15400-138">[Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) </span></span>  
 [<span data-ttu-id="15400-139">Следящий сервер зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="15400-139">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
