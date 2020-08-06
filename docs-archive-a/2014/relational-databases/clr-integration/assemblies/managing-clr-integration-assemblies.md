---
title: Управление сборками интеграции со средой CLR | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- database objects [CLR integration], assemblies
- common language runtime [SQL Server], assemblies
- assemblies [CLR integration], managing
ms.assetid: bdbbf325-14f6-460e-a35a-d3861d3c961e
author: rothja
ms.author: jroth
ms.openlocfilehash: 191ccd73ca42ef4c26291e6de88f5f2b0cf565ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735325"
---
# <a name="managing-clr-integration-assemblies"></a><span data-ttu-id="7c8d5-102">Управление сборками интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="7c8d5-102">Managing CLR Integration Assemblies</span></span>
  <span data-ttu-id="7c8d5-103">Управляемый программный код компилируется и развертывается в виде модулей, которые называются сборками.</span><span class="sxs-lookup"><span data-stu-id="7c8d5-103">Managed code is compiled and then deployed in units called an assembly.</span></span> <span data-ttu-id="7c8d5-104">Сборка упакована в виде динамической библиотеки или исполняемого файла (.exe).</span><span class="sxs-lookup"><span data-stu-id="7c8d5-104">An assembly is packaged as a DLL or executable (.exe) file.</span></span> <span data-ttu-id="7c8d5-105">Исполняемый файл можно запускать, а для вызова динамической библиотеки нужно подключить ее к существующему приложению.</span><span class="sxs-lookup"><span data-stu-id="7c8d5-105">While an executable file can run on its own, a DLL must be hosted in an existing application.</span></span> <span data-ttu-id="7c8d5-106">Управляемые сборки DLL могут загружаться в и размещаться в [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7c8d5-106">Managed DLL assemblies can be loaded into and hosted by [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)].</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="7c8d5-107">база данных с помощью инструкции CREATE ASSEMBLY, прежде чем ее можно будет загрузить в процесс и использовать.</span><span class="sxs-lookup"><span data-stu-id="7c8d5-107">database using the CREATE ASSEMBLY statement, before it can be loaded in the process and used.</span></span> <span data-ttu-id="7c8d5-108">Сборки можно обновлять до более новой версии с помощью инструкции ALTER ASSEMBLY, а также удалять из [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с помощью инструкции DROP ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="7c8d5-108">Assemblies can also be updated from a more recent version using the ALTER ASSEMBLY statement, or removed from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] using the DROP ASSEMBLY statement.</span></span>  
  
 <span data-ttu-id="7c8d5-109">Информация о сборке хранится в таблице `sys.assembly_files` в базе данных, где установлена сборка.</span><span class="sxs-lookup"><span data-stu-id="7c8d5-109">Assembly information is stored in the `sys.assembly_files` table in the database where the assembly has been installed.</span></span> <span data-ttu-id="7c8d5-110">Таблица `sys.assembly_files` содержит следующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="7c8d5-110">The `sys.assembly_files` table contains the following columns.</span></span>  
  
|<span data-ttu-id="7c8d5-111">Столбец</span><span class="sxs-lookup"><span data-stu-id="7c8d5-111">Column</span></span>|<span data-ttu-id="7c8d5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7c8d5-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="7c8d5-113">assembly_id</span><span class="sxs-lookup"><span data-stu-id="7c8d5-113">assembly_id</span></span>|<span data-ttu-id="7c8d5-114">Идентификатор, определенный для сборки.</span><span class="sxs-lookup"><span data-stu-id="7c8d5-114">The identifier defined for the assembly.</span></span> <span data-ttu-id="7c8d5-115">Это число назначается всем объектам, относящимся к одной сборке.</span><span class="sxs-lookup"><span data-stu-id="7c8d5-115">This number is assigned to all objects relating to the same assembly.</span></span>|  
|<span data-ttu-id="7c8d5-116">name</span><span class="sxs-lookup"><span data-stu-id="7c8d5-116">name</span></span>|<span data-ttu-id="7c8d5-117">Имя объекта.</span><span class="sxs-lookup"><span data-stu-id="7c8d5-117">The name of the object.</span></span>|  
|<span data-ttu-id="7c8d5-118">file_id</span><span class="sxs-lookup"><span data-stu-id="7c8d5-118">file_id</span></span>|<span data-ttu-id="7c8d5-119">Идентификационный номер каждого из объектов. Первый объект, связанный с данным идентификатором сборки `assembly_id`, получает номер 1.</span><span class="sxs-lookup"><span data-stu-id="7c8d5-119">A number identifying each object, with the first object associated with a given `assembly_id` being given the value of 1.</span></span> <span data-ttu-id="7c8d5-120">Если существует несколько объектов, связанных с одним и тем же `assembly_id`, то каждое последующее значение `file_id` увеличивается на 1.</span><span class="sxs-lookup"><span data-stu-id="7c8d5-120">If multiple objects are associated with the same `assembly_id`, then each subsequent `file_id` value is incremented by 1.</span></span>|  
|<span data-ttu-id="7c8d5-121">содержимое</span><span class="sxs-lookup"><span data-stu-id="7c8d5-121">content</span></span>|<span data-ttu-id="7c8d5-122">Шестнадцатеричное представление сборки или файла.</span><span class="sxs-lookup"><span data-stu-id="7c8d5-122">The hexadecimal representation of the assembly or file.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="7c8d5-123">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="7c8d5-123">In This Section</span></span>  
 [<span data-ttu-id="7c8d5-124">Создание сборки</span><span class="sxs-lookup"><span data-stu-id="7c8d5-124">Creating an Assembly</span></span>](creating-an-assembly.md)  
 <span data-ttu-id="7c8d5-125">Обсуждается создание сборок с ключевыми словами SAFE, EXTERNAL_ACCESS и UNSAFE CLR в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c8d5-125">Discusses creating SAFE, EXTERNAL_ACCESS, and UNSAFE CLR assemblies in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="7c8d5-126">Изменение сборки</span><span class="sxs-lookup"><span data-stu-id="7c8d5-126">Altering an Assembly</span></span>](altering-an-assembly.md)  
 <span data-ttu-id="7c8d5-127">Описывается обновление сборок CLR в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c8d5-127">Describes updating CLR assemblies in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="7c8d5-128">Удаление сборки</span><span class="sxs-lookup"><span data-stu-id="7c8d5-128">Dropping an Assembly</span></span>](dropping-an-assembly.md)  
 <span data-ttu-id="7c8d5-129">Описывается удаление сборок CLR из [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c8d5-129">Discusses dropping CLR assemblies from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c8d5-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="7c8d5-130">See Also</span></span>  
 <span data-ttu-id="7c8d5-131">[Безопасность интеграции со средой CLR](../security/clr-integration-security.md) </span><span class="sxs-lookup"><span data-stu-id="7c8d5-131">[CLR Integration Security](../security/clr-integration-security.md) </span></span>  
 [<span data-ttu-id="7c8d5-132">Управление доступом для кода на основе интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="7c8d5-132">CLR Integration Code Access Security</span></span>](../security/clr-integration-code-access-security.md)  
  
  
