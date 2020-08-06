---
title: Доступ к файлам, используемым пакетами | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SSIS packages, security
- packages [Integration Services], security
- configuration files [Integration Services]
- checkpoint files
- Integration Services packages, security
- logs [Integration Services], security
- files [Integration Services], security
- SQL Server Integration Services packages, security
ms.assetid: 2e3ddea9-5289-4289-a70e-11c018f34977
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8db9511c91c9f229b7002f5b16cf077910a4ccf0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656542"
---
# <a name="access-to-files-used-by-packages"></a><span data-ttu-id="22315-102">Доступ к файлам, используемым пакетами</span><span class="sxs-lookup"><span data-stu-id="22315-102">Access to Files Used by Packages</span></span>
  <span data-ttu-id="22315-103">Уровень защиты пакета не способен защитить файлы, хранимые вне пределов пакета.</span><span class="sxs-lookup"><span data-stu-id="22315-103">The package protection level does not protect files that are stored outside the package.</span></span> <span data-ttu-id="22315-104">Эти файлы включают в себя:</span><span class="sxs-lookup"><span data-stu-id="22315-104">These files include the following:</span></span>  
  
-   <span data-ttu-id="22315-105">Файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="22315-105">Configuration files</span></span>  
  
-   <span data-ttu-id="22315-106">файлы контрольных точек</span><span class="sxs-lookup"><span data-stu-id="22315-106">Checkpoint files</span></span>  
  
-   <span data-ttu-id="22315-107">Файлы журнала</span><span class="sxs-lookup"><span data-stu-id="22315-107">Log files</span></span>  
  
 <span data-ttu-id="22315-108">Эти файлы должны быть защищены отдельно, особенно если они содержат конфиденциальные сведения.</span><span class="sxs-lookup"><span data-stu-id="22315-108">These files must be protected separately, especially if they include sensitive information.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="22315-109">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="22315-109">Configuration Files</span></span>  
 <span data-ttu-id="22315-110">Если в файле конфигурации хранятся конфиденциальные сведения, такие как данные об имени входа и пароле, то следует сохранить файл в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]или использовать список управления доступом (ACL), чтобы защитить расположение или папку, где хранится этот файл, и разрешить доступ только для определенных учетных записей.</span><span class="sxs-lookup"><span data-stu-id="22315-110">If you have sensitive information in a configuration, such as login and password information, you should consider saving the configuration to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], or use an access control list (ACL) to restrict access to the location or folder where you store the files and allow access only to certain accounts.</span></span> <span data-ttu-id="22315-111">Обычно предоставляется доступ для тех учетных записей, которым разрешено запускать пакеты, управлять пакетами и разрешать проблемы, связанные с пакетами, в том числе проверять содержимое файла настройки, контрольные точки и файлы журнала.</span><span class="sxs-lookup"><span data-stu-id="22315-111">Typically, you would grant access to the accounts that you permit to run packages, and to the accounts that manage and troubleshoot packages, which may include reviewing the contents of configuration, checkpoint, and log files.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="22315-112">обеспечивает более безопасное хранение, так как предлагает защиту на уровне сервера и базы данных.</span><span class="sxs-lookup"><span data-stu-id="22315-112">provides the more secure storage because it offers protection at the server and database levels.</span></span> <span data-ttu-id="22315-113">Чтобы сохранить конфигурации в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], следует использовать тип конфигурации [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="22315-113">To save configurations to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration type.</span></span> <span data-ttu-id="22315-114">Чтобы сохранить в файловую систему, следует использовать тип конфигурации XML.</span><span class="sxs-lookup"><span data-stu-id="22315-114">To save to the file system, you use the XML configuration type.</span></span>  
  
 <span data-ttu-id="22315-115">Дополнительные сведения см. в разделах [Конфигурации пакетов](../../2014/integration-services/package-configurations.md), [Создание конфигураций пакетов](../../2014/integration-services/create-package-configurations.md)и [Вопросы безопасности при установке SQL Server](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="22315-115">For more information, see [Package Configurations](../../2014/integration-services/package-configurations.md), [Create Package Configurations](../../2014/integration-services/create-package-configurations.md), and [Security Considerations for a SQL Server Installation](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md).</span></span>  
  
## <a name="checkpoint-files"></a><span data-ttu-id="22315-116">файлы контрольных точек</span><span class="sxs-lookup"><span data-stu-id="22315-116">Checkpoint Files</span></span>  
 <span data-ttu-id="22315-117">Таким же образом, если используемый пакетом файл контрольных точек содержит конфиденциальные сведения, то следует использовать список управления доступом (ACL) для защиты расположения или папки, где хранится этот файл.</span><span class="sxs-lookup"><span data-stu-id="22315-117">Similarly, if the checkpoint file that the package uses includes sensitive information, you should use an access control list (ACL) to secure the location or folder where you store the file.</span></span> <span data-ttu-id="22315-118">Файлы контрольных точек сохраняют данные как о текущем состоянии пакета, так и о текущих значениях переменных.</span><span class="sxs-lookup"><span data-stu-id="22315-118">Checkpoint files save current state information on the progress of the package as well as the current values of variables.</span></span> <span data-ttu-id="22315-119">Например, пакет может включать в себя пользовательскую переменную, содержащую номер телефона.</span><span class="sxs-lookup"><span data-stu-id="22315-119">For example, the package may include a custom variable that contains a telephone number.</span></span> <span data-ttu-id="22315-120">Дополнительные сведения см. в разделе [Restart Packages by Using Checkpoints](packages/restart-packages-by-using-checkpoints.md).</span><span class="sxs-lookup"><span data-stu-id="22315-120">For more information, see [Restart Packages by Using Checkpoints](packages/restart-packages-by-using-checkpoints.md).</span></span>  
  
## <a name="log-files"></a><span data-ttu-id="22315-121">Файлы журнала</span><span class="sxs-lookup"><span data-stu-id="22315-121">Log Files</span></span>  
 <span data-ttu-id="22315-122">Записи журнала, сохраненные в файловой системе, также должны быть защищены с использованием списка управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="22315-122">Log entries that are written to the file system should also be secured using an access control list (ACL).</span></span> <span data-ttu-id="22315-123">Записи журнала также могут храниться в таблицах [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] и быть защищены системой безопасности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="22315-123">Log entries can also be stored in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tables and protected by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] security.</span></span> <span data-ttu-id="22315-124">Записи журнала могут содержать конфиденциальные сведения, например если пакет содержит задачу «Выполнение SQL», которая создает инструкцию SQL, ссылающуюся на номер телефона, то запись журнала для инструкции SQL содержит и номер телефона.</span><span class="sxs-lookup"><span data-stu-id="22315-124">Log entries may include sensitive information, For example, if the package contains an Execute SQL task that constructs an SQL statement that refers to a telephone number, the log entry for the SQL statement includes the telephone number.</span></span> <span data-ttu-id="22315-125">Инструкция SQL также может раскрыть закрытые данные об именах таблиц и столбцов данных.</span><span class="sxs-lookup"><span data-stu-id="22315-125">The SQL statement may also reveal private information about table and column names in databases.</span></span> <span data-ttu-id="22315-126">Дополнительные сведения см. в разделе [Ведение журналов в службах Integration Services (SSIS)](performance/integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="22315-126">For more information, see [Integration Services &#40;SSIS&#41; Logging](performance/integration-services-ssis-logging.md).</span></span>  
  
  
