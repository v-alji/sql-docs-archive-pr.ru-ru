---
title: MSSQLSERVER_17832 | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17828 (Database Engine error)
- maxtokensize
- 17832 (Database Engine error)
- login packet (bad)
ms.assetid: bd56ffe4-0855-4ada-8aca-251fbc6ff2ce
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dba214e2cce04ff2583e12ae7cee9b54373390a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729542"
---
# <a name="mssqlserver_17832"></a><span data-ttu-id="bc7c0-102">MSSQLSERVER_17832</span><span class="sxs-lookup"><span data-stu-id="bc7c0-102">MSSQLSERVER_17832</span></span>
    
## <a name="details"></a><span data-ttu-id="bc7c0-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="bc7c0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bc7c0-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="bc7c0-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="bc7c0-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="bc7c0-105">Event ID</span></span>|<span data-ttu-id="bc7c0-106">17832</span><span class="sxs-lookup"><span data-stu-id="bc7c0-106">17832</span></span>|  
|<span data-ttu-id="bc7c0-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="bc7c0-107">Event Source</span></span>|<span data-ttu-id="bc7c0-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bc7c0-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bc7c0-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="bc7c0-109">Component</span></span>|<span data-ttu-id="bc7c0-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bc7c0-110">SQLEngine</span></span>|  
|<span data-ttu-id="bc7c0-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="bc7c0-111">Symbolic Name</span></span>|<span data-ttu-id="bc7c0-112">SRV_BAD_LOGIN_PKT</span><span class="sxs-lookup"><span data-stu-id="bc7c0-112">SRV_BAD_LOGIN_PKT</span></span>|  
|<span data-ttu-id="bc7c0-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="bc7c0-113">Message Text</span></span>|<span data-ttu-id="bc7c0-114">Неправильная структура пакета входа, используемого для установления соединения. Соединение закрыто.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-114">The login packet used to open the connection is structurally invalid; the connection has been closed.</span></span> <span data-ttu-id="bc7c0-115">Свяжитесь с поставщиком клиентской библиотеки.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="bc7c0-115">Please contact the vendor of the client library.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bc7c0-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="bc7c0-116">Explanation</span></span>  
 <span data-ttu-id="bc7c0-117">Компьютер [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не смог обработать пакет входа клиента.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computer was unable to process the client login packet.</span></span> <span data-ttu-id="bc7c0-118">Причиной может быть неверно созданный пакет или повреждение пакета в процессе передачи.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-118">This may be because the packet was created improperly or because the packet was damaged during transmission.</span></span> <span data-ttu-id="bc7c0-119">Неполадка также может быть вызвана конфигурацией компьютера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc7c0-119">It can also be caused by the configuration of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computer.</span></span> <span data-ttu-id="bc7c0-120">Указанный IP-адрес является адресом клиентского компьютера.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-120">The IP address listed is the address of the client computer.</span></span>  
  
### <a name="more-information"></a><span data-ttu-id="bc7c0-121">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="bc7c0-121">More Information</span></span>  
 <span data-ttu-id="bc7c0-122">При использовании проверки подлинности Windows в среде Kerberos клиент получает билет Kerberos, в котором содержится сертификат атрибута прав доступа (PAC).</span><span class="sxs-lookup"><span data-stu-id="bc7c0-122">When using Windows Authentication in a Kerberos environment, a client receives a Kerberos ticket that contains a Privilege Attribute Certificate (PAC).</span></span> <span data-ttu-id="bc7c0-123">Сертификат PAC содержит различные типы авторизации данных, в том числе группы, членом которых является пользователь, права пользователя и политики, применяемые к пользователю.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-123">The PAC contains various types of authorization data including groups that the user is a member of, rights the user has, and what policies apply to the user.</span></span> <span data-ttu-id="bc7c0-124">Когда клиент получает билет Kerberos, сведения сертификата PAC используются для формирования токена доступа пользователя.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-124">When the client receives the Kerberos ticket, the information contained in the PAC is used to generate the user's access token.</span></span> <span data-ttu-id="bc7c0-125">Клиент представляет токен компьютеру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] как часть пакета входа.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-125">The client presents the token to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computer as part of the login packet.</span></span>  
  
 <span data-ttu-id="bc7c0-126">Если токен был неверно сформирован или поврежден при передаче, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не может выдать дополнительные сведения о неполадке.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-126">If the token was improperly created or damaged during transmission, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot offer additional information about the problem.</span></span>  
  
 <span data-ttu-id="bc7c0-127">Если пользователь является членом нескольких групп или имеет несколько политик, размер токена может стать слишком большим, что делает невозможным его просмотр.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-127">When the user is a member of many groups or has many policies, the token may grow larger than normal to list them all.</span></span> <span data-ttu-id="bc7c0-128">Если размер токена становится больше, чем значение **MaxTokenSize**, установленное на компьютере сервера, клиент при попытке установить соединение получает сообщение об "общей сетевой ошибке", а также может возвращаться ошибка 17832.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-128">If the token grows larger than the **MaxTokenSize** value of the server computer, the client fails to connect with a General Network Error (GNE) and error 17832 can occur.</span></span> <span data-ttu-id="bc7c0-129">Эта неполадка может затронуть лишь некоторых пользователей, которым соответствует несколько групп и политик.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-129">This problem may affect only some users: users with many groups or policies.</span></span> <span data-ttu-id="bc7c0-130">Если проблема заключается в значении **MaxTokenSize** на компьютере сервера, ошибка 17832 в журнале ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] будет сопровождаться ошибкой с состоянием 9.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-130">When the problem is the **MaxTokenSize** value of the server computer, error 17832 in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log will be accompanied by an error with state 9.</span></span> <span data-ttu-id="bc7c0-131">Дополнительные сведения о Kerberos и параметре **MaxTokenSize** см. в описании [KB327825](https://support.microsoft.com/kb/327825).</span><span class="sxs-lookup"><span data-stu-id="bc7c0-131">For additional details about the Kerberos and **MaxTokenSize**, see [KB327825](https://support.microsoft.com/kb/327825).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bc7c0-132">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="bc7c0-132">User Action</span></span>  
 <span data-ttu-id="bc7c0-133">Чтобы устранить эту проблему, увеличьте значение **MaxTokenSize** на компьютере сервера, чтобы оно было достаточным для самого большого токена любого пользователя в организации.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-133">To resolve this problem, increase the **MaxTokenSize** value of the server computer, to a size large enough to contain the largest token of any user in your organization.</span></span> <span data-ttu-id="bc7c0-134">Чтобы выяснить нужный размер токена для вашей организации, можно использовать программу **Tokensz**.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-134">To research the correct token size for your organization, consider using the **Tokensz** application.</span></span>   
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="bc7c0-135">**Изменение MaxTokenSize на компьютере сервера**</span><span class="sxs-lookup"><span data-stu-id="bc7c0-135">**To change the MaxTokenSize  on the server computer**</span></span>  
  
1.  <span data-ttu-id="bc7c0-136">В меню **Пуск** выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-136">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="bc7c0-137">Введите `regedit` , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-137">Type `regedit`, and then click **OK**.</span></span> <span data-ttu-id="bc7c0-138">(Если появится диалоговое окно **Контроль учетных записей**, нажмите в нем кнопку **Продолжить**).</span><span class="sxs-lookup"><span data-stu-id="bc7c0-138">(If the **User Account Control** dialog box appears, click **Continue**.)</span></span>  
  
3.  <span data-ttu-id="bc7c0-139">Перейдите к разделу **HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Lsa\Kerberos\Parameters**.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-139">Navigate to **HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Lsa\Kerberos\Parameters**.</span></span>  
  
4.  <span data-ttu-id="bc7c0-140">Если параметр **MaxTokenSize** отсутствует, щелкните правой кнопкой мыши **Параметры**, выберите пункт **Создать**, а затем формат значения **DWORD (32 бита)** .</span><span class="sxs-lookup"><span data-stu-id="bc7c0-140">If the **MaxTokenSize** parameter is not present, right-click **Parameters**, point to **New**, and then click **DWORD (32-bit)** Value.</span></span> <span data-ttu-id="bc7c0-141">Присвойте новому параметру реестра имя **MaxTokenSize**.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-141">Name the registry entry **MaxTokenSize**.</span></span>  
  
5.  <span data-ttu-id="bc7c0-142">Щелкните правой кнопкой мыши параметр **MaxTokenSize** и выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-142">Right-click **MaxTokenSize**, and then click **Modify**.</span></span>  
  
6.  <span data-ttu-id="bc7c0-143">В текстовом поле **Значение** введите нужное значение для **MaxTokenSize**.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-143">In the **Value data** box type the desired **MaxTokenSize** value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bc7c0-144">Шестнадцатеричное значение ffff (десятичное значение 65535) — максимальный рекомендуемый размер токена.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-144">Hexadecimal value ffff (decimal value 65535) is the maximum recommended token size.</span></span> <span data-ttu-id="bc7c0-145">Использование этого значения, вероятно, разрешит проблему, но может оказать негативное влияние на производительность всего компьютера.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-145">Providing this value would probably solve the problem, but could have negative computer-wide effects with regard to performance.</span></span> <span data-ttu-id="bc7c0-146">Мы рекомендуем вычислить и установить такое значение **MaxTokenSize**, которого будет достаточно для самого большого токена любого пользователя в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-146">We recommend that you establish the minimum **MaxTokenSize** value that allows for the largest token of any user in your organization and enter that value.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="bc7c0-147">Закройте **редактор реестра**.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-147">Close **Registry Editor**.</span></span>  
  
9. <span data-ttu-id="bc7c0-148">Перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="bc7c0-148">Restart the computer.</span></span>  
  
  
