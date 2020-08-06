---
title: Редактор преобразования "Аудит" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.audittransformation.f1
helpviewer_keywords:
- Audit Transformation Editor
ms.assetid: 32786a34-5870-4fde-83c7-ec74d62404b8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: af6490643a0bef60cca961dc9a0564c5f6b46484
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740241"
---
# <a name="audit-transformation-editor"></a><span data-ttu-id="16e53-102">редактор преобразования «Аудит»</span><span class="sxs-lookup"><span data-stu-id="16e53-102">Audit Transformation Editor</span></span>
  <span data-ttu-id="16e53-103">Преобразование «Аудит» позволяет включать поток данных в пакет для передачи данных о среде, в которой запускается этот пакет.</span><span class="sxs-lookup"><span data-stu-id="16e53-103">The Audit transformation enables the data flow in a package to include data about the environment in which the package runs.</span></span> <span data-ttu-id="16e53-104">Например, в поток данных можно добавлять имя пакета, компьютера и оператора.</span><span class="sxs-lookup"><span data-stu-id="16e53-104">For example, the name of the package, computer, and operator can be added to the data flow.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="16e53-105">предусмотрены системные переменные, предоставляющие эти сведения.</span><span class="sxs-lookup"><span data-stu-id="16e53-105">includes system variables that provide this information.</span></span>  
  
 <span data-ttu-id="16e53-106">Дополнительные сведения о преобразовании «Аудит» см. в разделе [Audit Transformation](data-flow/transformations/audit-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="16e53-106">To learn more about the Audit transformation, see [Audit Transformation](data-flow/transformations/audit-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="16e53-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="16e53-107">Options</span></span>  
 <span data-ttu-id="16e53-108">**Имя выходного столбца**</span><span class="sxs-lookup"><span data-stu-id="16e53-108">**Output column name**</span></span>  
 <span data-ttu-id="16e53-109">Введите имя для нового выходного столбца, который будет содержать данные аудита.</span><span class="sxs-lookup"><span data-stu-id="16e53-109">Provide the name for a new output column that will contain the audit information.</span></span>  
  
 <span data-ttu-id="16e53-110">**Тип аудита**</span><span class="sxs-lookup"><span data-stu-id="16e53-110">**Audit type**</span></span>  
 <span data-ttu-id="16e53-111">Выберите доступную системную переменную для предоставления данных аудита.</span><span class="sxs-lookup"><span data-stu-id="16e53-111">Select an available system variable to supply the audit information.</span></span>  
  
|<span data-ttu-id="16e53-112">Значение</span><span class="sxs-lookup"><span data-stu-id="16e53-112">Value</span></span>|<span data-ttu-id="16e53-113">Описание</span><span class="sxs-lookup"><span data-stu-id="16e53-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="16e53-114">**Идентификатор GUID экземпляра выполнения**</span><span class="sxs-lookup"><span data-stu-id="16e53-114">**Execution instance GUID**</span></span>|<span data-ttu-id="16e53-115">Укажите идентификатор GUID, который уникально идентифицирует экземпляр выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="16e53-115">Insert the GUID that uniquely identifies the execution instance of the package.</span></span>|  
|<span data-ttu-id="16e53-116">**Идентификатор пакета**</span><span class="sxs-lookup"><span data-stu-id="16e53-116">**Package ID**</span></span>|<span data-ttu-id="16e53-117">Укажите идентификатор GUID, который уникально идентифицирует пакет.</span><span class="sxs-lookup"><span data-stu-id="16e53-117">Insert the GUID that uniquely identifies the package.</span></span>|  
|<span data-ttu-id="16e53-118">**Имя пакета**</span><span class="sxs-lookup"><span data-stu-id="16e53-118">**Package name**</span></span>|<span data-ttu-id="16e53-119">Укажите имя пакета.</span><span class="sxs-lookup"><span data-stu-id="16e53-119">Insert the package name.</span></span>|  
|<span data-ttu-id="16e53-120">**Идентификатор версии**</span><span class="sxs-lookup"><span data-stu-id="16e53-120">**Version ID**</span></span>|<span data-ttu-id="16e53-121">Укажите идентификатор GUID, который уникально идентифицирует версию пакета.</span><span class="sxs-lookup"><span data-stu-id="16e53-121">Insert the GUID that uniquely identifies the version of the package.</span></span>|  
|<span data-ttu-id="16e53-122">**Время начала выполнения**</span><span class="sxs-lookup"><span data-stu-id="16e53-122">**Execution start time**</span></span>|<span data-ttu-id="16e53-123">Укажите время, когда было начато выполнение пакета.</span><span class="sxs-lookup"><span data-stu-id="16e53-123">Insert the time at which package execution started.</span></span>|  
|<span data-ttu-id="16e53-124">**Имя компьютера**</span><span class="sxs-lookup"><span data-stu-id="16e53-124">**Machine name**</span></span>|<span data-ttu-id="16e53-125">Укажите имя компьютера, на котором был запущен пакет.</span><span class="sxs-lookup"><span data-stu-id="16e53-125">Insert the name of the computer on which the package was launched.</span></span>|  
|<span data-ttu-id="16e53-126">**User name**</span><span class="sxs-lookup"><span data-stu-id="16e53-126">**User name**</span></span>|<span data-ttu-id="16e53-127">Укажите имя входа пользователя, который запустил пакет.</span><span class="sxs-lookup"><span data-stu-id="16e53-127">Insert the login name of the user who launched the package.</span></span>|  
|<span data-ttu-id="16e53-128">**Имя задачи**</span><span class="sxs-lookup"><span data-stu-id="16e53-128">**Task name**</span></span>|<span data-ttu-id="16e53-129">Укажите имя задачи потока данных, с которой связано преобразование «Аудит».</span><span class="sxs-lookup"><span data-stu-id="16e53-129">Insert the name of the Data Flow task with which the Audit transformation is associated.</span></span>|  
|<span data-ttu-id="16e53-130">**Идентификатор задачи**</span><span class="sxs-lookup"><span data-stu-id="16e53-130">**Task ID**</span></span>|<span data-ttu-id="16e53-131">Укажите идентификатор GUID, который уникально идентифицирует задачу потока данных, с которой связано преобразование «Аудит».</span><span class="sxs-lookup"><span data-stu-id="16e53-131">Insert the GUID that uniquely identifies the Data Flow task with which the Audit transformation is associated.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16e53-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="16e53-132">See Also</span></span>  
 [<span data-ttu-id="16e53-133">Справочник по сообщениям об ошибках служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="16e53-133">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
