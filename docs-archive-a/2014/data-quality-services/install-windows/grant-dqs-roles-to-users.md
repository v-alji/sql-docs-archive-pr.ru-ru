---
title: Предоставление ролей DQS пользователям | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: afb445b5-bdbe-4bfe-844f-344766cdc2b2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 62ff5eb03fa46279ee1b8a1329c58bd69361ef82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736791"
---
# <a name="grant-dqs-roles-to-users"></a><span data-ttu-id="0e5cc-102">Предоставление ролей DQS пользователям</span><span class="sxs-lookup"><span data-stu-id="0e5cc-102">Grant DQS Roles to Users</span></span>
  <span data-ttu-id="0e5cc-103">В этом разделе описывается создание имен входа SQL Server на основе участников Windows и предоставление им ролей служб [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) в базе данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="0e5cc-103">This topic describes how to create SQL logins based on a Windows principal, and grant [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) roles on the DQS_MAIN database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0e5cc-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="0e5cc-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="0e5cc-105">Необходимо, чтобы установка сервера [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] , запускаемая с помощью файла DQSInstaller.exe, была завершена.</span><span class="sxs-lookup"><span data-stu-id="0e5cc-105">You must have completed the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] installation by running the DQSInstaller.exe file.</span></span> <span data-ttu-id="0e5cc-106">Дополнительные сведения см. в разделе [Запуск файла DQSInstaller.exe для завершения установки сервера служб DQS](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="0e5cc-106">For more information, see [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
-   <span data-ttu-id="0e5cc-107">Учетная запись пользователя Windows должна входить в соответствующую предопределенную роль сервера (например, securityadmin, serveradmin или sysadmin) для создания имен входа SQL Server и предоставления им ролей DQS.</span><span class="sxs-lookup"><span data-stu-id="0e5cc-107">Your Windows user account must be a member of the appropriate fixed server role (such as securityadmin, serveradmin, or sysadmin) to create SQL login, and grant them DQS roles.</span></span>  
  
### <a name="to-create-sql-login-and-grant-dqs-roles"></a><span data-ttu-id="0e5cc-108">Создание имени входа SQL Server и предоставление ролей DQS</span><span class="sxs-lookup"><span data-stu-id="0e5cc-108">To create SQL login and grant DQS roles</span></span>  
  
1.  <span data-ttu-id="0e5cc-109">Запустите среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e5cc-109">Start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="0e5cc-110">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]разверните экземпляр SQL Server, а затем узел **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="0e5cc-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand your SQL Server instance, and then expand **Security**.</span></span>  
  
3.  <span data-ttu-id="0e5cc-111">Щелкните папку **Безопасность** правой кнопкой мыши, наведите указатель на пункт **Создать**и выберите пункт **Имя входа**.</span><span class="sxs-lookup"><span data-stu-id="0e5cc-111">Right-click the **Security** folder, point to **New**, and then click **Login**.</span></span>  
  
4.  <span data-ttu-id="0e5cc-112">В диалоговом окне **Создание имени входа** укажите имя пользователя Windows в поле **Имя для входа**, выберите тип проверки подлинности **Проверка подлинности Windows** и нажмите кнопку **Поиск** для проверки пользователя.</span><span class="sxs-lookup"><span data-stu-id="0e5cc-112">In the **Login - New** dialog box, specify the name of a Windows user in the **Login name** box, specify the type of authentication as **Windows authentication**, and click **Search** to validate the user.</span></span>  
  
5.  <span data-ttu-id="0e5cc-113">После проверки пользователя щелкните страницу **Сопоставление пользователей** в левой части окна.</span><span class="sxs-lookup"><span data-stu-id="0e5cc-113">After the user is validated, click the **User Mapping** page in the left pane.</span></span>  
  
6.  <span data-ttu-id="0e5cc-114">В правой области установите флажок в столбце **Сопоставление** для базы данных **DQS_MAIN** , а затем на панели **Членство в роли базы данных для: DQS_MAIN**установите флажок **dqs_administrator**, **dqs_kb_editor** или **dqs_kb_operator** в зависимости от уровня доступа, который требуется пользователю.</span><span class="sxs-lookup"><span data-stu-id="0e5cc-114">In the right pane, select the check box under the **Map** column for the **DQS_MAIN** database, and then select the **dqs_administrator**, **dqs_kb_editor**, or **dqs_kb_operator** check box in the **Database role membership for: DQS_MAIN** pane, depending on the access level needed for the user.</span></span> <span data-ttu-id="0e5cc-115">Дополнительные сведения о трех ролях служб DQS см. в разделе [DQS Security](../dqs-security.md).</span><span class="sxs-lookup"><span data-stu-id="0e5cc-115">For information about the three DQS roles, see [DQS Security](../dqs-security.md).</span></span>  
  
7.  <span data-ttu-id="0e5cc-116">В диалоговом окне **Создание имени входа** нажмите кнопку **ОК**, чтобы применить изменения.</span><span class="sxs-lookup"><span data-stu-id="0e5cc-116">In the **Login - New** dialog box, click **OK** to apply the changes.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0e5cc-117">Если пользователю предоставляется роль **dqs_administrator** , примените изменения, а затем повторно проверьте разрешения пользователя; флажки двух других ролей DQS (**dq_kb_editor** и **dqs_kb_operator**) также должны быть установлены.</span><span class="sxs-lookup"><span data-stu-id="0e5cc-117">If you grant the **dqs_administrator** role to a user, apply the changes, and then recheck the user permissions, the other two DQS roles check boxes (**dq_kb_editor** and **dqs_kb_operator**) are also selected.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0e5cc-118">Next Steps</span><span class="sxs-lookup"><span data-stu-id="0e5cc-118">Next Steps</span></span>  
 <span data-ttu-id="0e5cc-119">Выполните вход на сервер [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] с использованием учетной записи пользователя Windows, для которой только что было создано имя входа SQL Server и предоставлена роль DQS.</span><span class="sxs-lookup"><span data-stu-id="0e5cc-119">Try logging on to [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] by using the Windows user account for which you just created a SQL login, and granted a DQS role.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e5cc-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="0e5cc-120">See Also</span></span>  
 <span data-ttu-id="0e5cc-121">[Install Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="0e5cc-121">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 [<span data-ttu-id="0e5cc-122">Создание имени входа</span><span class="sxs-lookup"><span data-stu-id="0e5cc-122">Create a Login</span></span>](../../relational-databases/security/authentication-access/create-a-login.md)  
  
  
