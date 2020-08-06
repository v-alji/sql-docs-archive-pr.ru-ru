---
title: Управление пользователями DQS в SSMS | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 955af01d-00da-4c51-9311-f3848749df54
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bf8789abb59d168f39562f6486bb5c54bfc0fc50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667893"
---
# <a name="manage-dqs-users-in-ssms"></a><span data-ttu-id="b3aca-102">Управление пользователями DQS в среде SSMS</span><span class="sxs-lookup"><span data-stu-id="b3aca-102">Manage DQS Users in SSMS</span></span>
  <span data-ttu-id="b3aca-103">В этом разделе описывается создание дополнительных пользователей в экземпляре SQL Server с помощью SQL Server Management Studio, а также предоставление соответствующих ролей [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) в базе данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="b3aca-103">This topic describes how to create additional users in the SQL Server instance using SQL Server Management Studio, and grant them appropriate [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) roles on the DQS_MAIN database.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b3aca-104">Перед началом</span><span class="sxs-lookup"><span data-stu-id="b3aca-104">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b3aca-105">безопасность</span><span class="sxs-lookup"><span data-stu-id="b3aca-105">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b3aca-106">Permissions</span><span class="sxs-lookup"><span data-stu-id="b3aca-106">Permissions</span></span>  
 <span data-ttu-id="b3aca-107">Учетная запись пользователя Windows должна быть членом соответствующей предопределенной роли сервера (например, securityadmin, serveradmin или sysadmin) для создания имен входа SQL Server и предоставления соответствующих ролей DQS.</span><span class="sxs-lookup"><span data-stu-id="b3aca-107">Your Windows user account must be a member of the appropriate fixed server role (such as securityadmin, serveradmin, or sysadmin) to create SQL login, and grant appropriate DQS roles.</span></span>  
  
##  <a name="create-a-sql-login-and-grant-dqs-role"></a><a name="GrantRoles"></a><span data-ttu-id="b3aca-108">Создание имени входа SQL и предоставление роли DQS</span><span class="sxs-lookup"><span data-stu-id="b3aca-108">Create a SQL Login and Grant DQS Role</span></span>  
  
1.  <span data-ttu-id="b3aca-109">Запустите среду Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="b3aca-109">Start Microsoft SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="b3aca-110">В среде Microsoft SQL Server Management Studio разверните экземпляр SQL Server, а затем разверните **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="b3aca-110">In Microsoft SQL Server Management Studio, expand your SQL Server instance, and then expand **Security**.</span></span>  
  
3.  <span data-ttu-id="b3aca-111">Щелкните папку **Безопасность** правой кнопкой мыши, наведите указатель на пункт **Создать**и выберите пункт **Имя входа**.</span><span class="sxs-lookup"><span data-stu-id="b3aca-111">Right-click the **Security** folder, point to **New**, and then click **Login**.</span></span>  
  
4.  <span data-ttu-id="b3aca-112">В диалоговом окне **Создание имени входа** укажите имя пользователя Windows в поле **Имя для входа**, выберите тип проверки подлинности **Проверка подлинности Windows** и нажмите кнопку **Поиск** для проверки пользователя.</span><span class="sxs-lookup"><span data-stu-id="b3aca-112">In the **Login - New** dialog box, specify the name of a Windows user in the **Login name** box, specify the type of authentication as **Windows authentication**, and click **Search** to validate the user.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b3aca-113">Службы DQS поддерживают только проверку подлинности Windows. Проверка подлинности SQL Server не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b3aca-113">DQS only supports Windows authentication; SQL Server authentication is not supported.</span></span>  
  
5.  <span data-ttu-id="b3aca-114">После проверки пользователя щелкните страницу **Сопоставление пользователей** в левой части окна.</span><span class="sxs-lookup"><span data-stu-id="b3aca-114">After the user is validated, click the **User Mapping** page in the left pane.</span></span>  
  
6.  <span data-ttu-id="b3aca-115">В правой области установите флажок в столбце **Сопоставление** для базы данных **DQS_MAIN** , а затем на панели **Членство в роли базы данных для: DQS_MAIN**установите флажок **dqs_administrator**, **dqs_kb_editor** или **dqs_kb_operator** в зависимости от уровня доступа, который требуется пользователю.</span><span class="sxs-lookup"><span data-stu-id="b3aca-115">In the right pane, select the check box under the **Map** column for the **DQS_MAIN** database, and then select the **dqs_administrator**, **dqs_kb_editor**, or **dqs_kb_operator** check box in the **Database role membership for: DQS_MAIN** pane, depending on the access level needed for the user.</span></span>  
  
7.  <span data-ttu-id="b3aca-116">В диалоговом окне **Создание имени входа** нажмите кнопку **ОК**, чтобы применить изменения.</span><span class="sxs-lookup"><span data-stu-id="b3aca-116">In the **Login - New** dialog box, click **OK** to apply the changes.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b3aca-117">Если пользователю предоставляется роль **dqs_administrator** , примените изменения, а затем повторно проверьте разрешения пользователя; флажки двух других ролей DQS (**dq_kb_editor** и **dqs_kb_operator**) также должны быть установлены.</span><span class="sxs-lookup"><span data-stu-id="b3aca-117">If you grant the **dqs_administrator** role to a user, apply the changes, and then recheck the user permissions, the other two DQS roles check boxes (**dq_kb_editor** and **dqs_kb_operator**) are also selected.</span></span>  
  
  
