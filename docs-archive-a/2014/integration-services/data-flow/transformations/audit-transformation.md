---
title: Преобразование "Аудит" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.audittrans.f1
helpviewer_keywords:
- environment data in packages [Integration Services]
- Audit transformation
ms.assetid: 8c143682-9c81-4150-83d6-1d9678151d37
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e8e302f6dd1dc5666ae65af2eb9705a4922915c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728513"
---
# <a name="audit-transformation"></a><span data-ttu-id="87aa0-102">преобразование «Аудит»</span><span class="sxs-lookup"><span data-stu-id="87aa0-102">Audit Transformation</span></span>
  <span data-ttu-id="87aa0-103">Преобразование «Аудит» позволяет включать поток данных в пакет для передачи данных о среде, в которой запускается этот пакет.</span><span class="sxs-lookup"><span data-stu-id="87aa0-103">The Audit transformation enables the data flow in a package to include data about the environment in which the package runs.</span></span> <span data-ttu-id="87aa0-104">Например, в поток данных можно добавлять имя пакета, компьютера и оператора.</span><span class="sxs-lookup"><span data-stu-id="87aa0-104">For example, the name of the package, computer, and operator can be added to the data flow.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="87aa0-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] предусмотрены системные переменные, предоставляющие эти сведения.</span><span class="sxs-lookup"><span data-stu-id="87aa0-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes system variables that provide this information.</span></span>  
  
## <a name="system-variables"></a><span data-ttu-id="87aa0-106">Системные переменные</span><span class="sxs-lookup"><span data-stu-id="87aa0-106">System Variables</span></span>  
 <span data-ttu-id="87aa0-107">В приведенной ниже таблице описаны системные переменные, применяемые в преобразовании «Аудит».</span><span class="sxs-lookup"><span data-stu-id="87aa0-107">The following table describes the system variables that the Audit transformation can use.</span></span>  
  
|<span data-ttu-id="87aa0-108">Системная переменная</span><span class="sxs-lookup"><span data-stu-id="87aa0-108">System variable</span></span>|<span data-ttu-id="87aa0-109">Индекс</span><span class="sxs-lookup"><span data-stu-id="87aa0-109">Index</span></span>|<span data-ttu-id="87aa0-110">Description</span><span class="sxs-lookup"><span data-stu-id="87aa0-110">Description</span></span>|  
|---------------------|-----------|-----------------|  
|`ExecutionInstanceGUID`|<span data-ttu-id="87aa0-111">0</span><span class="sxs-lookup"><span data-stu-id="87aa0-111">0</span></span>|<span data-ttu-id="87aa0-112">Идентификатор GUID, определяющий экземпляр выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="87aa0-112">The GUID that identifies the execution instance of the package.</span></span>|  
|`PackageID`|<span data-ttu-id="87aa0-113">1</span><span class="sxs-lookup"><span data-stu-id="87aa0-113">1</span></span>|<span data-ttu-id="87aa0-114">Уникальный идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="87aa0-114">The unique identifier of the package.</span></span>|  
|`PackageName`|<span data-ttu-id="87aa0-115">2</span><span class="sxs-lookup"><span data-stu-id="87aa0-115">2</span></span>|<span data-ttu-id="87aa0-116">Имя пакета.</span><span class="sxs-lookup"><span data-stu-id="87aa0-116">The package name.</span></span>|  
|`VersionID`|<span data-ttu-id="87aa0-117">3</span><span class="sxs-lookup"><span data-stu-id="87aa0-117">3</span></span>|<span data-ttu-id="87aa0-118">Версия пакета.</span><span class="sxs-lookup"><span data-stu-id="87aa0-118">The version of the package.</span></span>|  
|`ExecutionStartTime`|<span data-ttu-id="87aa0-119">4</span><span class="sxs-lookup"><span data-stu-id="87aa0-119">4</span></span>|<span data-ttu-id="87aa0-120">Время начала выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="87aa0-120">The time the package started to run.</span></span>|  
|`MachineName`|<span data-ttu-id="87aa0-121">5</span><span class="sxs-lookup"><span data-stu-id="87aa0-121">5</span></span>|<span data-ttu-id="87aa0-122">имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="87aa0-122">The computer name.</span></span>|  
|`UserName`|<span data-ttu-id="87aa0-123">6</span><span class="sxs-lookup"><span data-stu-id="87aa0-123">6</span></span>|<span data-ttu-id="87aa0-124">Имя входа пользователя, который запустил пакет.</span><span class="sxs-lookup"><span data-stu-id="87aa0-124">The login name of the person who started the package.</span></span>|  
|`TaskName`|<span data-ttu-id="87aa0-125">7</span><span class="sxs-lookup"><span data-stu-id="87aa0-125">7</span></span>|<span data-ttu-id="87aa0-126">Имя задачи потока данных, с которой связано преобразование «Аудит».</span><span class="sxs-lookup"><span data-stu-id="87aa0-126">The name of the Data Flow task with which the Audit transformation is associated.</span></span>|  
|<span data-ttu-id="87aa0-127">**TaskId**</span><span class="sxs-lookup"><span data-stu-id="87aa0-127">**TaskId**</span></span>|<span data-ttu-id="87aa0-128">8</span><span class="sxs-lookup"><span data-stu-id="87aa0-128">8</span></span>|<span data-ttu-id="87aa0-129">Уникальный идентификатор задачи потока данных.</span><span class="sxs-lookup"><span data-stu-id="87aa0-129">The unique identifier of the Data Flow task.</span></span>|  
  
## <a name="configuration-of-the-audit-transformation"></a><span data-ttu-id="87aa0-130">Настройка преобразования «Аудит»</span><span class="sxs-lookup"><span data-stu-id="87aa0-130">Configuration of the Audit Transformation</span></span>  
 <span data-ttu-id="87aa0-131">Чтобы настроить преобразование «Аудит», необходимо добавить имя нового выходного столбца в выход преобразования, затем сопоставить системную переменную с выходным столбцом.</span><span class="sxs-lookup"><span data-stu-id="87aa0-131">You configure the Audit transformation by providing the name of a new output column to add to the transformation output, and then mapping the system variable to the output column.</span></span> <span data-ttu-id="87aa0-132">Можно сопоставить одну системную переменную с несколькими столбцами.</span><span class="sxs-lookup"><span data-stu-id="87aa0-132">You can map a single system variable to multiple columns.</span></span>  
  
 <span data-ttu-id="87aa0-133">Это преобразование имеет один вход и один выход.</span><span class="sxs-lookup"><span data-stu-id="87aa0-133">This transformation has one input and one output.</span></span> <span data-ttu-id="87aa0-134">Вывод ошибок не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="87aa0-134">It does not support an error output.</span></span>  
  
 <span data-ttu-id="87aa0-135">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="87aa0-135">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="87aa0-136">Дополнительные сведения о свойствах, которые можно установить в диалоговом окне **Редактор преобразования «Аудит»** см. в разделе [Audit Transformation Editor](../../audit-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="87aa0-136">For more information about the properties that you can set in the **Audit Transformation Editor** dialog box, see [Audit Transformation Editor](../../audit-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="87aa0-137">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="87aa0-137">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="87aa0-138">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="87aa0-138">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="87aa0-139">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="87aa0-139">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="87aa0-140">Пользовательские свойства преобразований</span><span class="sxs-lookup"><span data-stu-id="87aa0-140">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="87aa0-141">Дополнительные сведения о настройке свойств см. в разделе [Установление свойств компонента потока данных](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="87aa0-141">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
