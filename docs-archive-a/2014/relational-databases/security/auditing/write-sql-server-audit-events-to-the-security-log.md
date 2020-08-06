---
title: Запись событий подсистемы аудита SQL Server в журнал безопасности | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], Security Log
- server audit [SQL Server]
- audits [SQL Server], writing to Security Log
- security logs [SQL Server]
ms.assetid: 6fabeea3-7a42-4769-a0f3-7e04daada314
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: d59134b278f29c9b604208d8cab7e982144b9c9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656284"
---
# <a name="write-sql-server-audit-events-to-the-security-log"></a><span data-ttu-id="789da-102">Запись событий подсистемы аудита SQL Server в журнал безопасности</span><span class="sxs-lookup"><span data-stu-id="789da-102">Write SQL Server Audit Events to the Security Log</span></span>
  <span data-ttu-id="789da-103">В среде с повышенной безопасностью подходящим местом для записи событий доступа к объектам является журнал безопасности Windows.</span><span class="sxs-lookup"><span data-stu-id="789da-103">In a high security environment, the Windows Security log is the appropriate location to write events that record object access.</span></span> <span data-ttu-id="789da-104">Другие местонахождения аудита поддерживаются, но они более уязвимы для вторжения злоумышленников.</span><span class="sxs-lookup"><span data-stu-id="789da-104">Other audit locations are supported but are more subject to tampering.</span></span>  
  
 <span data-ttu-id="789da-105">Для записи событий аудита сервера [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в журнал безопасности Windows существует два основных требования.</span><span class="sxs-lookup"><span data-stu-id="789da-105">There are two key requirements for writing [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] server audits to the Windows Security log:</span></span>  
  
-   <span data-ttu-id="789da-106">Параметр аудита доступа к объектам должен быть настроен для записи событий.</span><span class="sxs-lookup"><span data-stu-id="789da-106">The audit object access setting must be configured to capture the events.</span></span> <span data-ttu-id="789da-107">Программа политики аудита (`auditpol.exe`) предоставляет доступ к ряду внутренних параметров политик в категории **Аудит доступа к объектам** .</span><span class="sxs-lookup"><span data-stu-id="789da-107">The audit policy tool (`auditpol.exe`) exposes a variety of sub-policies settings in the **audit object access** category.</span></span> <span data-ttu-id="789da-108">Чтобы позволить [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] проводить аудит доступа к объектам, нужно настроить параметр **формируется приложением** .</span><span class="sxs-lookup"><span data-stu-id="789da-108">To allow [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to audit object access, configure the **application generated** setting.</span></span>  
  
-   <span data-ttu-id="789da-109">Для записи в журнал безопасности Windows учетная запись, из-под которой выполняется служба [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , должна иметь разрешение **Создание аудитов безопасности** .</span><span class="sxs-lookup"><span data-stu-id="789da-109">The account that the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service is running under must have the **generate security audits** permission to write to the Windows Security log.</span></span> <span data-ttu-id="789da-110">По умолчанию этим разрешением обладают учетные записи и Locale Service и Network Service.</span><span class="sxs-lookup"><span data-stu-id="789da-110">By default, the LOCAL SERVICE and the NETWORK SERVICE accounts have this permission.</span></span> <span data-ttu-id="789da-111">Если служба [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] выполняется от имени одной из этих учетных записей, данный шаг не требуется.</span><span class="sxs-lookup"><span data-stu-id="789da-111">This step is not required if [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is running under one of those accounts.</span></span>  
  
 <span data-ttu-id="789da-112">Политика аудита Windows может повлиять на аудит [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , если включена запись в журнал безопасности Windows, при этом существует опасность потери событий, если политика аудита настроена неправильно.</span><span class="sxs-lookup"><span data-stu-id="789da-112">The Windows audit policy can affect [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] auditing if it is configured to write to the Windows Security log, with the potential of losing events if the audit policy is incorrectly configured.</span></span> <span data-ttu-id="789da-113">Обычно журнал безопасности Windows перезаписывает более старые события.</span><span class="sxs-lookup"><span data-stu-id="789da-113">Typically, the Windows Security log is set to overwrite the older events.</span></span> <span data-ttu-id="789da-114">В результате сохраняются самые последние события.</span><span class="sxs-lookup"><span data-stu-id="789da-114">This preserves the most recent events.</span></span> <span data-ttu-id="789da-115">Однако, если журнал безопасности Windows не настроен на перезапись более старых событий, при заполнении журнала безопасности система создаст событие Windows 1104 (журнал заполнен).</span><span class="sxs-lookup"><span data-stu-id="789da-115">However, if the Windows Security log is not set to overwrite older events, then if the Security log is full, the system will issue Windows event 1104 (Log is full).</span></span> <span data-ttu-id="789da-116">После этого:</span><span class="sxs-lookup"><span data-stu-id="789da-116">At that point:</span></span>  
  
-   <span data-ttu-id="789da-117">Последующие события безопасности не будут регистрироваться</span><span class="sxs-lookup"><span data-stu-id="789da-117">No further security events will be recorded</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="789da-118">не сможет установить, что система не регистрирует события в журнале безопасности, в результате чего возможна потеря событий аудита</span><span class="sxs-lookup"><span data-stu-id="789da-118">will not be able to detect that the system is not able to record the events in the Security log, resulting in the potential loss of audit events</span></span>  
  
-   <span data-ttu-id="789da-119">После того как администратор настроит журнал безопасности, режим записи в журнал вернется в нормальное состояние.</span><span class="sxs-lookup"><span data-stu-id="789da-119">After the box administrator fixes the Security log, the logging behavior will return to normal.</span></span>  
  
 <span data-ttu-id="789da-120">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="789da-120">**In This Topic**</span></span>  
  
-   <span data-ttu-id="789da-121">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="789da-121">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="789da-122">Ограничения</span><span class="sxs-lookup"><span data-stu-id="789da-122">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="789da-123">Безопасность</span><span class="sxs-lookup"><span data-stu-id="789da-123">Security</span></span>](#Security)  
  
-   <span data-ttu-id="789da-124">**Чтобы записывать события подсистемы аудита SQL Server в журнал безопасности:**</span><span class="sxs-lookup"><span data-stu-id="789da-124">**To write SQL Server audit events to the Security Log:**</span></span>  
  
     [<span data-ttu-id="789da-125">Настройте параметр аудита доступа к объектам в Windows с помощью средства auditpol</span><span class="sxs-lookup"><span data-stu-id="789da-125">Configure the audit object access setting in Windows using auditpol</span></span>](#auditpolAccess)  
  
     [<span data-ttu-id="789da-126">Настройте параметр аудита доступа к объектам в Windows с помощью средства secpol</span><span class="sxs-lookup"><span data-stu-id="789da-126">Configure the audit object access setting in Windows using secpol</span></span>](#secpolAccess)  
  
     [<span data-ttu-id="789da-127">Предоставьте разрешения на создание аудитов безопасности конкретной учетной записи с помощью средства secpol</span><span class="sxs-lookup"><span data-stu-id="789da-127">Grant the generate security audits permission to an account using secpol</span></span>](#secpolPermission)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="789da-128">Перед началом</span><span class="sxs-lookup"><span data-stu-id="789da-128">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="789da-129">Ограничения</span><span class="sxs-lookup"><span data-stu-id="789da-129">Limitations and Restrictions</span></span>  
 <span data-ttu-id="789da-130">Администраторы компьютера с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] должны учитывать, что локальные параметры журнала безопасности могут быть переопределены политикой домена.</span><span class="sxs-lookup"><span data-stu-id="789da-130">Administrators of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] computer should understand that local settings for the Security log can be overwritten by a domain policy.</span></span> <span data-ttu-id="789da-131">В этом случае политика домена может перезаписывать параметр подкатегории (**auditpol /get /subcategory:"application generated"** ).</span><span class="sxs-lookup"><span data-stu-id="789da-131">In this case, the domain policy might overwrite the subcategory setting (**auditpol /get /subcategory:"application generated"**).</span></span> <span data-ttu-id="789da-132">Это может повлиять на способность [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] регистрировать события, причем будет невозможно определить, что события, для которых [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] пытается провести аудит, не регистрируются.</span><span class="sxs-lookup"><span data-stu-id="789da-132">This can affect [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ability to log events without having any way to detect that the events that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is trying to audit are not going to be recorded.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="789da-133">безопасность</span><span class="sxs-lookup"><span data-stu-id="789da-133">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="789da-134">Permissions</span><span class="sxs-lookup"><span data-stu-id="789da-134">Permissions</span></span>  
 <span data-ttu-id="789da-135">Для настройки этих параметров необходимо быть администратором Windows.</span><span class="sxs-lookup"><span data-stu-id="789da-135">You must be a Windows administrator to configure these settings.</span></span>  
  
##  <a name="to-configure-the-audit-object-access-setting-in-windows-using-auditpol"></a><a name="auditpolAccess"></a> <span data-ttu-id="789da-136">Настройка параметра аудита доступа к объектам в Windows с помощью средства auditpol</span><span class="sxs-lookup"><span data-stu-id="789da-136">To configure the audit object access setting in Windows using auditpol</span></span>  
  
1.  <span data-ttu-id="789da-137">Откройте командную строку с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="789da-137">Open a command prompt with administrative permissions.</span></span>  
  
    1.  <span data-ttu-id="789da-138">В меню **Пуск** последовательно укажите пункты **Все программы**, **Стандартные**, щелкните правой кнопкой мыши пункт **Командная строка**и выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="789da-138">On the **Start** menu, point to **All Programs**, point to **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>  
  
    2.  <span data-ttu-id="789da-139">В диалоговом окне **Контроль учетных записей** нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="789da-139">If the **User Account Control** dialog box opens, click **Continue**.</span></span>  
  
2.  <span data-ttu-id="789da-140">Выполните следующую инструкцию для включения аудита из [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="789da-140">Execute the following statement to enable auditing from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
    ```  
    auditpol /set /subcategory:"application generated" /success:enable /failure:enable  
    ```  
  
3.  <span data-ttu-id="789da-141">Закройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="789da-141">Close the command prompt window.</span></span>  
  
##  <a name="to-grant-the-generate-security-audits-permission-to-an-account-using-secpol"></a><a name="secpolAccess"></a> <span data-ttu-id="789da-142">Предоставление разрешения на создание аудитов безопасности конкретной учетной записи с помощью средства secpol</span><span class="sxs-lookup"><span data-stu-id="789da-142">To grant the generate security audits permission to an account using secpol</span></span>  
  
1.  <span data-ttu-id="789da-143">В любой версии операционной системы Windows в меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="789da-143">For any Windows operating system, on the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="789da-144">Введите **secpol.msc** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="789da-144">Type **secpol.msc** and then click **OK**.</span></span> <span data-ttu-id="789da-145">В диалоговом окне **Управление доступом на уровне пользователей** нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="789da-145">If the **User Access Control** dialog box appears, click **Continue**.</span></span>  
  
3.  <span data-ttu-id="789da-146">В средстве «Локальная политика безопасности» разверните узел **Настройки безопасности**, разверните узел **Локальные политики**, а затем щелкните **Назначение прав пользователя**.</span><span class="sxs-lookup"><span data-stu-id="789da-146">In the Local Security Policy tool, expand **Security Settings**, expand **Local Policies**, and then click **User Rights Assignment**.</span></span>  
  
4.  <span data-ttu-id="789da-147">На панели результатов дважды щелкните **Создание аудитов безопасности**.</span><span class="sxs-lookup"><span data-stu-id="789da-147">In the results pane, double-click **Generate security audits**.</span></span>  
  
5.  <span data-ttu-id="789da-148">На вкладке **Параметр локальной безопасности** нажмите кнопку **Добавить пользователя или группу**.</span><span class="sxs-lookup"><span data-stu-id="789da-148">On the **Local Security Setting** tab, click **Add User or Group**.</span></span>  
  
6.  <span data-ttu-id="789da-149">В диалоговом окне **Выбор: пользователи, компьютеры или группы** либо введите имя учетной записи, например **домен1\пользователь1** , а затем нажмите кнопку **ОК**, либо нажмите кнопку **Дополнительно...** и найдите нужную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="789da-149">In the **Select Users, Computers, or Groups** dialog box, either type the name of the user account, such as **domain1\user1** and then click **OK**, or click **Advanced** and search for the account.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="789da-150">Закройте средство политики безопасности.</span><span class="sxs-lookup"><span data-stu-id="789da-150">Close the Security Policy tool.</span></span>  
  
9. <span data-ttu-id="789da-151">Перезапустите [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , чтобы включить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="789da-151">Restart [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to enable this setting.</span></span>  
  
##  <a name="to-configure-the-audit-object-access-setting-in-windows-using-secpol"></a><a name="secpolPermission"></a> <span data-ttu-id="789da-152">Настройка параметра аудита доступа к объектам в Windows с помощью средства secpol</span><span class="sxs-lookup"><span data-stu-id="789da-152">To configure the audit object access setting in Windows using secpol</span></span>  
  
1.  <span data-ttu-id="789da-153">Если операционная система имеет более раннюю версию, чем [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] или Windows Server 2008, в меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="789da-153">If the operating system is earlier than [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] or Windows Server 2008, on the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="789da-154">Введите **secpol.msc** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="789da-154">Type **secpol.msc** and then click **OK**.</span></span> <span data-ttu-id="789da-155">В диалоговом окне **Управление доступом на уровне пользователей** нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="789da-155">If the **User Access Control** dialog box appears, click **Continue**.</span></span>  
  
3.  <span data-ttu-id="789da-156">В средстве «Локальная политика безопасности» разверните узел **Настройки безопасности**, разверните узел **Локальные политики**, а затем **Политика аудита**.</span><span class="sxs-lookup"><span data-stu-id="789da-156">In the Local Security Policy tool, expand **Security Settings**, expand **Local Policies**, and then click **Audit Policy**.</span></span>  
  
4.  <span data-ttu-id="789da-157">На панели результатов дважды щелкните **Аудит доступа к объектам**.</span><span class="sxs-lookup"><span data-stu-id="789da-157">In the results pane, double-click **Audit object access**.</span></span>  
  
5.  <span data-ttu-id="789da-158">На вкладке **Параметр локальной безопасности** в области **Вести аудит следующих попыток доступа** выберите оба параметра: **Успешно** и **Ошибка**.</span><span class="sxs-lookup"><span data-stu-id="789da-158">On the **Local Security Setting** tab, in the **Audit these attempts** area, select both **Success** and **Failure**.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="789da-159">Закройте средство политики безопасности.</span><span class="sxs-lookup"><span data-stu-id="789da-159">Close the Security Policy tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="789da-160">См. также:</span><span class="sxs-lookup"><span data-stu-id="789da-160">See Also</span></span>  
 [<span data-ttu-id="789da-161">Подсистема аудита SQL Server (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="789da-161">SQL Server Audit &#40;Database Engine&#41;</span></span>](sql-server-audit-database-engine.md)  
  
  
