---
title: Сохранение пакета служб SSIS (мастер экспорта и импорта SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.savedtspackage.f1
ms.assetid: 7bf8ac6a-5599-43ab-bf5c-e072c11b85a0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d4e582558a1f86b18d935fcc6235ba5839faa031
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666138"
---
# <a name="save-ssis-package-sql-server-import-and-export-wizard"></a><span data-ttu-id="d093d-102">Сохранение пакета служб SSIS (мастер экспорта и импорта SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d093d-102">Save SSIS Package (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="d093d-103">Страница **Сохранение пакета служб SSIS** используется для именования, описания и сохранения [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] пакета Integration Services ( [!INCLUDE[ssIS](../../includes/ssis-md.md)] ) в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` базе данных или в файле с расширением DTSX.</span><span class="sxs-lookup"><span data-stu-id="d093d-103">Use the **Save SSIS Package** page to name, describe, and save a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Integration Services ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) package to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` database or to a file that has the .dtsx extension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d093d-104">В выпуске [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] пакет, созданный при помощи мастера, сохранить нельзя.</span><span class="sxs-lookup"><span data-stu-id="d093d-104">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
 <span data-ttu-id="d093d-105">Дополнительные сведения о работе этого мастера см. в разделе [Мастер импорта и экспорта SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="d093d-105">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="d093d-106">Дополнительные сведения о параметрах запуска мастера и о разрешениях, необходимых для успешного запуска мастера, см. [в разделе Запуск мастера импорта и экспорта SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="d093d-106">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="d093d-107">Назначение мастера импорта и экспорта SQL Server заключается в копировании данных из исходного расположения в целевое.</span><span class="sxs-lookup"><span data-stu-id="d093d-107">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="d093d-108">Этот мастер может также создать целевую базу данных и целевые таблицы.</span><span class="sxs-lookup"><span data-stu-id="d093d-108">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="d093d-109">Однако если нужно скопировать несколько баз данных, таблиц или других объектов базы данных, следует использовать мастер копирования баз данных.</span><span class="sxs-lookup"><span data-stu-id="d093d-109">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="d093d-110">Дополнительные сведения см. в статье [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="d093d-110">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="d093d-111">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="d093d-111">Static Options</span></span>  
 <span data-ttu-id="d093d-112">**имя**;</span><span class="sxs-lookup"><span data-stu-id="d093d-112">**Name**</span></span>  
 <span data-ttu-id="d093d-113">Введите уникальное имя пакета.</span><span class="sxs-lookup"><span data-stu-id="d093d-113">Provide a unique name for the package.</span></span>  
  
 <span data-ttu-id="d093d-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d093d-114">**Description**</span></span>  
 <span data-ttu-id="d093d-115">Введите описание пакета.</span><span class="sxs-lookup"><span data-stu-id="d093d-115">Provide a description for the package.</span></span> <span data-ttu-id="d093d-116">Рекомендуется описывать пакеты в связи с их предназначением, чтобы пакеты описывали сами себя и их легко было обслуживать.</span><span class="sxs-lookup"><span data-stu-id="d093d-116">As a best practice, describe the package in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="d093d-117">**Цель**</span><span class="sxs-lookup"><span data-stu-id="d093d-117">**Target**</span></span>  
 <span data-ttu-id="d093d-118">Просмотрите цель ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или файл), которая ранее была назначена для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="d093d-118">View the target ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or file) that was previously specified for the destination file.</span></span>  
  
## <a name="target-dynamic-options"></a><span data-ttu-id="d093d-119">Целевые динамические параметры</span><span class="sxs-lookup"><span data-stu-id="d093d-119">Target Dynamic Options</span></span>  
  
### <a name="target--sql-server"></a><span data-ttu-id="d093d-120">Назначение = SQL Server</span><span class="sxs-lookup"><span data-stu-id="d093d-120">Target = SQL Server</span></span>  
 <span data-ttu-id="d093d-121">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="d093d-121">**Server name**</span></span>  
 <span data-ttu-id="d093d-122">Выбрав цель [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], введите или выберите имя целевого сервера.</span><span class="sxs-lookup"><span data-stu-id="d093d-122">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, type or select the destination server name.</span></span>  
  
 <span data-ttu-id="d093d-123">**Использовать проверку подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="d093d-123">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="d093d-124">Выбрав целевой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], укажите, следует ли устанавливать соединение с сервером, используя встроенную проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d093d-124">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, specify whether to connect to the server by using Windows Integrated Authentication.</span></span> <span data-ttu-id="d093d-125">Предпочтителен этот метод проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d093d-125">This is the preferred authentication method.</span></span>  
  
 <span data-ttu-id="d093d-126">**Использовать проверку подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="d093d-126">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="d093d-127">Выбрав целевой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], укажите, следует ли устанавливать соединение с сервером, используя проверку подлинности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d093d-127">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, specify whether to connect to the server by using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="d093d-128">**User name**</span><span class="sxs-lookup"><span data-stu-id="d093d-128">**User name**</span></span>  
 <span data-ttu-id="d093d-129">Выбрав целевой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и указав проверку подлинности SQL Server, введите имя пользователя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d093d-129">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, and have specified SQL Server Authentication, type the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user name.</span></span>  
  
 <span data-ttu-id="d093d-130">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="d093d-130">**Password**</span></span>  
 <span data-ttu-id="d093d-131">Выбрав целевой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и указав проверку подлинности SQL Server, введите пароль [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d093d-131">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, and have specified SQL Server Authentication, type the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] password.</span></span>  
  
### <a name="target--file-system"></a><span data-ttu-id="d093d-132">Назначение = Файловая система</span><span class="sxs-lookup"><span data-stu-id="d093d-132">Target = File System</span></span>  
 <span data-ttu-id="d093d-133">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="d093d-133">**File name**</span></span>  
 <span data-ttu-id="d093d-134">Выбрав назначение файла, введите путь к целевому файлу или нажмите кнопку **Обзор** .</span><span class="sxs-lookup"><span data-stu-id="d093d-134">When you have selected a file destination, type the path for the destination file, or use the **Browse** button.</span></span>  
  
 <span data-ttu-id="d093d-135">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="d093d-135">**Browse**</span></span>  
 <span data-ttu-id="d093d-136">Выбрав назначение файла, перейдите к целевому файлу с помощью диалогового окна **сохранить пакет** .</span><span class="sxs-lookup"><span data-stu-id="d093d-136">When you have selected a file destination, browse to the destination file by using the **Save Package** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d093d-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="d093d-137">See Also</span></span>  
 [<span data-ttu-id="d093d-138">Сохранение пакетов</span><span class="sxs-lookup"><span data-stu-id="d093d-138">Save Packages</span></span>](../save-packages.md)  
  
  
