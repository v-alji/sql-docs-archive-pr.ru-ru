---
title: Разрешения для папок и файлов (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- security [Master Data Services], file and folder
- folders [Master Data Services]
- files [Master Data Services]
ms.assetid: 6402d81d-7349-47b1-95ca-99b0c0f4f373
author: lrtoyou1223
ms.author: lle
robots: noindex,nofollow
ms.openlocfilehash: 6dc356e074574a4c520b1f4de2f41db0e983c4df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731830"
---
# <a name="folder-and-file-permissions-master-data-services"></a><span data-ttu-id="81cee-102">Разрешения для папок и файлов (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="81cee-102">Folder and File Permissions (Master Data Services)</span></span>
  <span data-ttu-id="81cee-103">При установке [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]папки и файлы устанавливаются по указанному для общих компонентов [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] пути установки в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="81cee-103">When you install [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], folders and files are installed in the file system at the installation path you specify for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] shared features.</span></span> <span data-ttu-id="81cee-104">При использовании пути установки по умолчанию для [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] общих компонентов путь установки для [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] — *диск*: \Program Files\Microsoft SQL Server\120\Master Data Services.</span><span class="sxs-lookup"><span data-stu-id="81cee-104">If you use the default installation path for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] shared features, the installation path for [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] is *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services.</span></span> <span data-ttu-id="81cee-105">Хотя путь установки общих компонентов можно изменить, следует учитывать разрешения, наследуемые от родительской папки, а также явно заданные для [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]разрешения.</span><span class="sxs-lookup"><span data-stu-id="81cee-105">Although you can change the shared features installation path, be aware of permissions that are inherited from the parent folder and permissions that are explicitly set for [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span>  
  
## <a name="inherited-permissions"></a><span data-ttu-id="81cee-106">Наследуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="81cee-106">Inherited Permissions</span></span>  
 <span data-ttu-id="81cee-107">Папка **Microsoft SQL Server** , папка **Master Data Services** , а также большинство вложенных папок и файлов наследуют разрешения родительской папки, заданной в программе установки [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81cee-107">The **Microsoft SQL Server** folder, the **Master Data Services** folder, and most subfolders and files inherit permissions from the parent folder specified in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Setup.</span></span> <span data-ttu-id="81cee-108">Если было выбрано расположение установки по умолчанию, то родительской папкой, от которой наследуются разрешения, будет *диск*:\Program Files.</span><span class="sxs-lookup"><span data-stu-id="81cee-108">If you choose the default installation location, the parent folder that permissions are inherited from is *drive*:\Program Files.</span></span> <span data-ttu-id="81cee-109">В приведенной далее таблице описаны разрешения по умолчанию для папки **Program Files**.</span><span class="sxs-lookup"><span data-stu-id="81cee-109">The following table describes the default permissions for **Program Files**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="81cee-110">Если изменить разрешения по умолчанию для **Program Files**или выбрать другое расположение для установки, то папки и файлы [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] унаследуют разрешения соответствующей родительской папки, и эти разрешения могут отличаться от приведенных в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="81cee-110">If you modify default permissions for **Program Files**, or you choose a different installation location, the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] folders and files inherit permissions from their parent folder accordingly, and the permissions might differ from those described in the following table.</span></span>  
  
###### <a name="program-files-default-permissions"></a><span data-ttu-id="81cee-111">Разрешения по умолчанию для папки Program Files</span><span class="sxs-lookup"><span data-stu-id="81cee-111">Program Files Default Permissions</span></span>  
  
|<span data-ttu-id="81cee-112">Имя группы или учетной записи</span><span class="sxs-lookup"><span data-stu-id="81cee-112">Group or account name</span></span>|<span data-ttu-id="81cee-113">Разрешения</span><span class="sxs-lookup"><span data-stu-id="81cee-113">Permissions</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="81cee-114">CREATOR OWNER</span><span class="sxs-lookup"><span data-stu-id="81cee-114">CREATOR OWNER</span></span>|<span data-ttu-id="81cee-115">Специальные разрешения</span><span class="sxs-lookup"><span data-stu-id="81cee-115">Special permissions</span></span>|  
|<span data-ttu-id="81cee-116">SYSTEM</span><span class="sxs-lookup"><span data-stu-id="81cee-116">SYSTEM</span></span>|<span data-ttu-id="81cee-117">Специальные разрешения</span><span class="sxs-lookup"><span data-stu-id="81cee-117">Special permissions</span></span>|  
|<span data-ttu-id="81cee-118">Администраторы</span><span class="sxs-lookup"><span data-stu-id="81cee-118">Administrators</span></span>|<span data-ttu-id="81cee-119">Специальные разрешения</span><span class="sxs-lookup"><span data-stu-id="81cee-119">Special permissions</span></span>|  
|<span data-ttu-id="81cee-120">Пользователи</span><span class="sxs-lookup"><span data-stu-id="81cee-120">Users</span></span>|<span data-ttu-id="81cee-121">Чтение и выполнение, Просмотр содержимого папки, Чтение</span><span class="sxs-lookup"><span data-stu-id="81cee-121">Read & execute, List folder contents, Read</span></span>|  
|<span data-ttu-id="81cee-122">TrustedInstaller</span><span class="sxs-lookup"><span data-stu-id="81cee-122">TrustedInstaller</span></span>|<span data-ttu-id="81cee-123">Просмотр содержимого папки, Специальные разрешения</span><span class="sxs-lookup"><span data-stu-id="81cee-123">List folder contents, Special permissions</span></span>|  
  
## <a name="explicit-permissions"></a><span data-ttu-id="81cee-124">Явные разрешения</span><span class="sxs-lookup"><span data-stu-id="81cee-124">Explicit Permissions</span></span>  
 <span data-ttu-id="81cee-125">Папка **MDSTempDir** и файл [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web.config (в папке **WebApplication** ) не наследуют разрешения.</span><span class="sxs-lookup"><span data-stu-id="81cee-125">The **MDSTempDir** folder and the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web.config file (in the **WebApplication** folder) do not inherit permissions.</span></span> <span data-ttu-id="81cee-126">Для них разрешения задаются явно при установке [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], независимо от выбранного пути установки.</span><span class="sxs-lookup"><span data-stu-id="81cee-126">They have permissions that are set explicitly when you install [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], regardless of the installation path you choose.</span></span> <span data-ttu-id="81cee-127">Изменять эти разрешения не следует.</span><span class="sxs-lookup"><span data-stu-id="81cee-127">Do not modify these permissions.</span></span>  
  
###### <a name="mdstempdir-permissions"></a><span data-ttu-id="81cee-128">Разрешения MDSTempDir</span><span class="sxs-lookup"><span data-stu-id="81cee-128">MDSTempDir Permissions</span></span>  
  
|<span data-ttu-id="81cee-129">Имя группы или учетной записи</span><span class="sxs-lookup"><span data-stu-id="81cee-129">Group or account name</span></span>|<span data-ttu-id="81cee-130">Разрешения</span><span class="sxs-lookup"><span data-stu-id="81cee-130">Permissions</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="81cee-131">SYSTEM</span><span class="sxs-lookup"><span data-stu-id="81cee-131">SYSTEM</span></span>|<span data-ttu-id="81cee-132">Изменение, Чтение и выполнение, Просмотр содержимого папки, Чтение, Запись</span><span class="sxs-lookup"><span data-stu-id="81cee-132">Modify, Read & execute, List folder contents, Read, Write</span></span>|  
|<span data-ttu-id="81cee-133">Администраторы</span><span class="sxs-lookup"><span data-stu-id="81cee-133">Administrators</span></span>|<span data-ttu-id="81cee-134">Изменение, Чтение и выполнение, Просмотр содержимого папки, Чтение, Запись</span><span class="sxs-lookup"><span data-stu-id="81cee-134">Modify, Read & execute, List folder contents, Read, Write</span></span>|  
|<span data-ttu-id="81cee-135">MDS_ServiceAccounts</span><span class="sxs-lookup"><span data-stu-id="81cee-135">MDS_ServiceAccounts</span></span>|<span data-ttu-id="81cee-136">Изменение, Чтение и выполнение, Просмотр содержимого папки, Чтение, Запись</span><span class="sxs-lookup"><span data-stu-id="81cee-136">Modify, Read & execute, List folder contents, Read, Write</span></span>|  
  
###### <a name="webconfig-permissions"></a><span data-ttu-id="81cee-137">Разрешения Web.config</span><span class="sxs-lookup"><span data-stu-id="81cee-137">Web.config Permissions</span></span>  
  
|<span data-ttu-id="81cee-138">Имя группы или учетной записи</span><span class="sxs-lookup"><span data-stu-id="81cee-138">Group or account name</span></span>|<span data-ttu-id="81cee-139">Разрешения</span><span class="sxs-lookup"><span data-stu-id="81cee-139">Permissions</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="81cee-140">SYSTEM</span><span class="sxs-lookup"><span data-stu-id="81cee-140">SYSTEM</span></span>|<span data-ttu-id="81cee-141">Полный доступ, Изменение, Чтение и выполнение, Чтение, Запись</span><span class="sxs-lookup"><span data-stu-id="81cee-141">Full control, Modify, Read & execute, Read, Write</span></span>|  
|<span data-ttu-id="81cee-142">Администраторы</span><span class="sxs-lookup"><span data-stu-id="81cee-142">Administrators</span></span>|<span data-ttu-id="81cee-143">Полный доступ, Изменение, Чтение и выполнение, Чтение, Запись</span><span class="sxs-lookup"><span data-stu-id="81cee-143">Full control, Modify, Read & execute, Read, Write</span></span>|  
|<span data-ttu-id="81cee-144">MDS_ServiceAccounts</span><span class="sxs-lookup"><span data-stu-id="81cee-144">MDS_ServiceAccounts</span></span>|<span data-ttu-id="81cee-145">Чтение и выполнение, Чтение</span><span class="sxs-lookup"><span data-stu-id="81cee-145">Read & execute, Read</span></span>|  
  
 <span data-ttu-id="81cee-146">Дополнительные сведения о содержимом файла [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web.config см. в разделе [Раздел "Веб-конфигурация" (службы Master Data Services)](web-configuration-reference-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="81cee-146">For more information about the contents of the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web.config file, see [Web Configuration Reference &#40;Master Data Services&#41;](web-configuration-reference-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81cee-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="81cee-147">See Also</span></span>  
 [<span data-ttu-id="81cee-148">Установка служб Master Data Services</span><span class="sxs-lookup"><span data-stu-id="81cee-148">Install Master Data Services</span></span>](install-windows/install-master-data-services.md)  
  
  
