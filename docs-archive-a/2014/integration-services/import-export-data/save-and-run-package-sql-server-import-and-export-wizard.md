---
title: Сохранение и выполнение пакета (SQL Server мастер импорта и экспорта) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.saveschedule.f1
ms.assetid: b582c462-3d7a-4a4c-a2a2-2c79fedab75a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a23f69bf66ca3355f1e1c62cc42d51e4aea3da5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666142"
---
# <a name="save-and-execute-package-sql-server-import-and-export-wizard"></a><span data-ttu-id="b4aaa-102">Сохранение и выполнение пакета (мастер экспорта и импорта SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b4aaa-102">Save and Execute Package (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="b4aaa-103">Используйте диалоговое окно **Сохранение и выполнение пакета** , чтобы немедленно запустить пакет, сохранить его для последующего выполнения или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-103">Use the **Save and Execute Package** dialog box to run the package immediately, save it to run later, or both.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4aaa-104"> Если остановить пакет до окончания его выполнения, пакет не сохраняется, даже если установлен флажок **Сохранить** .</span><span class="sxs-lookup"><span data-stu-id="b4aaa-104">If you stop a package before it finishes running, the package is not saved, even if you selected the **Save** check box.</span></span>  
  
 <span data-ttu-id="b4aaa-105">Дополнительные сведения о работе этого мастера см. в разделе [Мастер импорта и экспорта SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="b4aaa-105">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="b4aaa-106">Дополнительные сведения о параметрах запуска мастера, а также о разрешениях, необходимых для успешного запуска мастера, см. в разделе [Запуск мастера импорта и экспорта SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="b4aaa-106">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="b4aaa-107">Назначение мастера импорта и экспорта SQL Server заключается в копировании данных из исходного расположения в целевое.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-107">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="b4aaa-108">Этот мастер может также создать целевую базу данных и целевые таблицы.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-108">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="b4aaa-109">Однако если нужно скопировать несколько баз данных, таблиц или других объектов базы данных, следует использовать мастер копирования баз данных.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-109">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="b4aaa-110">Дополнительные сведения см. в статье [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="b4aaa-110">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b4aaa-111">Варианты</span><span class="sxs-lookup"><span data-stu-id="b4aaa-111">Options</span></span>  
 <span data-ttu-id="b4aaa-112">**Выполнить немедленно**</span><span class="sxs-lookup"><span data-stu-id="b4aaa-112">**Execute immediately**</span></span>  
 <span data-ttu-id="b4aaa-113">Этот параметр выбирается для немедленного запуска пакета.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-113">Select this option to run the package immediately.</span></span>  
  
 <span data-ttu-id="b4aaa-114">**Сохранить пакет служб SSIS**</span><span class="sxs-lookup"><span data-stu-id="b4aaa-114">**Save SSIS Package**</span></span>  
 <span data-ttu-id="b4aaa-115">Сохранение пакета для последующего выполнения с параметром немедленного выполнения.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-115">Save the package to run later, with the option to run it immediately.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4aaa-116">В выпуске [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] пакет, созданный при помощи мастера, сохранить нельзя.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-116">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
 <span data-ttu-id="b4aaa-117">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b4aaa-117">**SQL Server**</span></span>  
 <span data-ttu-id="b4aaa-118">Выберите этот параметр, чтобы сохранить пакет в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` базе данных.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-118">Select this option to save the package to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4aaa-119">Этот параметр доступен, только если выбран параметр **сохранить пакет служб SSIS** .</span><span class="sxs-lookup"><span data-stu-id="b4aaa-119">This option is available only if you have selected the **Save SSIS Package** option.</span></span>  
  
 <span data-ttu-id="b4aaa-120">**Файловая система**</span><span class="sxs-lookup"><span data-stu-id="b4aaa-120">**File system**</span></span>  
 <span data-ttu-id="b4aaa-121">При выборе этого параметра пакет сохраняется в файле с расширением DTSX.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-121">Select this option to save the package as a file that has the .dtsx extension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4aaa-122">Этот параметр доступен, только если выбран параметр **сохранить пакет служб SSIS** .</span><span class="sxs-lookup"><span data-stu-id="b4aaa-122">This option is available only if you have selected the **Save SSIS Package** option.</span></span>  
  
 <span data-ttu-id="b4aaa-123">**Уровень защиты пакета**</span><span class="sxs-lookup"><span data-stu-id="b4aaa-123">**Package protection level**</span></span>  
 <span data-ttu-id="b4aaa-124">Выберите уровень защиты из списка.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-124">Select a protection level from the list.</span></span>  
  
 <span data-ttu-id="b4aaa-125">Уровень защиты определяет метод защиты (пароль или ключ пользователя) и область защиты пакетов.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-125">The protection level determines the protection method, the password or user key, and the scope of package protection.</span></span> <span data-ttu-id="b4aaa-126">Защита может охватывать все данные или только конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-126">Protection can include all data or sensitive data only.</span></span> <span data-ttu-id="b4aaa-127">Сведения о требованиях и вариантах безопасности пакетов см. [в статье Управление доступом для конфиденциальных данных в](../security/access-control-for-sensitive-data-in-packages.md) разделе "пакеты и [безопасность" &#40;Integration Services&#41;](../security/security-overview-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="b4aaa-127">To understand the requirements and options for package security, see [Access Control for Sensitive Data in Packages](../security/access-control-for-sensitive-data-in-packages.md) and [Security Overview &#40;Integration Services&#41;](../security/security-overview-integration-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4aaa-128">Этот параметр доступен, только если выбран параметр **сохранить пакет служб SSIS** .</span><span class="sxs-lookup"><span data-stu-id="b4aaa-128">This option is available only if you have selected the **Save SSIS Package** option.</span></span>  
  
 <span data-ttu-id="b4aaa-129">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="b4aaa-129">**Password**</span></span>  
 <span data-ttu-id="b4aaa-130">Введите пароль.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-130">Type a password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4aaa-131">Этот параметр доступен, только если установлен параметр **уровень защиты пакета** для **шифрования конфиденциальных данных с помощью пароля** или **шифрования всех данных с паролем**.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-131">This option is available only if you have set the **Package protection level** option to either **Encrypt sensitive data with password** or **Encrypt all data with password**.</span></span>  
  
 <span data-ttu-id="b4aaa-132">**Введите пароль еще раз**</span><span class="sxs-lookup"><span data-stu-id="b4aaa-132">**Retype password**</span></span>  
 <span data-ttu-id="b4aaa-133">Введите пароль еще раз.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-133">Type the password again.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4aaa-134">Этот параметр доступен, только если установлен параметр **уровень защиты пакета** для **шифрования конфиденциальных данных с помощью пароля** или **шифрования всех данных с паролем**.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-134">This option is available only if you have set the **Package protection level** option to either **Encrypt sensitive data with password** or **Encrypt all data with password**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4aaa-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="b4aaa-135">See Also</span></span>  
 <span data-ttu-id="b4aaa-136">[Запуск проектов и пакетов](../packages/run-integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="b4aaa-136">[Execution of Projects and Packages](../packages/run-integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="b4aaa-137">Сохранение пакетов</span><span class="sxs-lookup"><span data-stu-id="b4aaa-137">Save Packages</span></span>](../save-packages.md)  
  
  
