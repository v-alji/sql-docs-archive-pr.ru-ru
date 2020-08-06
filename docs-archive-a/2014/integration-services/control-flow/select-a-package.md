---
title: Выбор пакета | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.selectapackage.f1
helpviewer_keywords:
- Select a Package dialog box
ms.assetid: 92b47a2b-21b5-460a-885d-6cc4bb567249
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b35276791b004a011a1c2656057046be05ed6770
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654441"
---
# <a name="select-a-package"></a><span data-ttu-id="d171b-102">Выбор пакета</span><span class="sxs-lookup"><span data-stu-id="d171b-102">Select a Package</span></span>
  <span data-ttu-id="d171b-103">Используйте диалоговое окно **Выбор пакета** , чтобы указать пакет, из которого задача «Очередь сообщений» может получать сообщения.</span><span class="sxs-lookup"><span data-stu-id="d171b-103">Use the **Select a Package** dialog box to specify the package from which the Message Queue task can receive messages.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="d171b-104">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="d171b-104">Static Options</span></span>  
 <span data-ttu-id="d171b-105">**Местоположение**</span><span class="sxs-lookup"><span data-stu-id="d171b-105">**Location**</span></span>  
 <span data-ttu-id="d171b-106">Определяет местонахождение пакета.</span><span class="sxs-lookup"><span data-stu-id="d171b-106">Specify the location of the package.</span></span> <span data-ttu-id="d171b-107">Это свойство имеет параметры, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d171b-107">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="d171b-108">Значение</span><span class="sxs-lookup"><span data-stu-id="d171b-108">Value</span></span>|<span data-ttu-id="d171b-109">Description</span><span class="sxs-lookup"><span data-stu-id="d171b-109">Description</span></span>|  
|-----------|-----------------|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<span data-ttu-id="d171b-110">Установите местонахождение экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d171b-110">Set the location to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d171b-111">При выборе данного значения отображаются динамические параметры, **Сервер**, **Использовать проверку подлинности Windows**, **Использовать проверку подлинности SQL Server**, **Имя пользователя**и **Пароль**.</span><span class="sxs-lookup"><span data-stu-id="d171b-111">Selecting this value displays the dynamic options, **Server**, **Use Windows Authentication**, **Use SQL Server Authentication**, **User name**, and **Password**.</span></span>|  
|<span data-ttu-id="d171b-112">Файл DTSX</span><span class="sxs-lookup"><span data-stu-id="d171b-112">DTSX file</span></span>|<span data-ttu-id="d171b-113">Установите местонахождение для файла DTSX.</span><span class="sxs-lookup"><span data-stu-id="d171b-113">Set the location to a DTSX file.</span></span> <span data-ttu-id="d171b-114">При выборе этого значения отображается динамический параметр **Имя файла**.</span><span class="sxs-lookup"><span data-stu-id="d171b-114">Selecting this value displays the dynamic option, **File name**.</span></span>|  
  
## <a name="location-dynamic-options"></a><span data-ttu-id="d171b-115">Динамические параметры местоположения</span><span class="sxs-lookup"><span data-stu-id="d171b-115">Location Dynamic Options</span></span>  
  
### <a name="location--sql-server"></a><span data-ttu-id="d171b-116">Местонахождение = SQL Server</span><span class="sxs-lookup"><span data-stu-id="d171b-116">Location = SQL Server</span></span>  
 <span data-ttu-id="d171b-117">**Имя пакета**</span><span class="sxs-lookup"><span data-stu-id="d171b-117">**Package name**</span></span>  
 <span data-ttu-id="d171b-118">Выберите пакет, хранимый на указанном сервере.</span><span class="sxs-lookup"><span data-stu-id="d171b-118">Select a package that is stored on the specified server.</span></span>  
  
 <span data-ttu-id="d171b-119">**Server**</span><span class="sxs-lookup"><span data-stu-id="d171b-119">**Server**</span></span>  
 <span data-ttu-id="d171b-120">Введите имя сервера или выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="d171b-120">Provide a server name or select a server from the list.</span></span>  
  
 <span data-ttu-id="d171b-121">**Использовать проверку подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="d171b-121">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="d171b-122">Выберите для использования проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d171b-122">Click to use Windows Authentication.</span></span>  
  
 <span data-ttu-id="d171b-123">**Использовать проверку подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="d171b-123">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="d171b-124">Выберите для использования проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d171b-124">Click to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="d171b-125">**User name**</span><span class="sxs-lookup"><span data-stu-id="d171b-125">**User name**</span></span>  
 <span data-ttu-id="d171b-126">При использовании проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] введите имя пользователя, которое необходимо использовать для входа на сервер.</span><span class="sxs-lookup"><span data-stu-id="d171b-126">If using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, provide a user name to use when logging on to the server.</span></span>  
  
 <span data-ttu-id="d171b-127">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="d171b-127">**Password**</span></span>  
 <span data-ttu-id="d171b-128">При использовании проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] укажите пароль.</span><span class="sxs-lookup"><span data-stu-id="d171b-128">If using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
### <a name="location--dtsx-file"></a><span data-ttu-id="d171b-129">Местонахождение = файл DTSX</span><span class="sxs-lookup"><span data-stu-id="d171b-129">Location = DTSX file</span></span>  
 <span data-ttu-id="d171b-130">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="d171b-130">**File name**</span></span>  
 <span data-ttu-id="d171b-131">Укажите путь к пакету или нажмите кнопку обзора **(...)** и определите его расположение.</span><span class="sxs-lookup"><span data-stu-id="d171b-131">Provide the path of a package or click the browse button **(...)** and locate the package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d171b-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="d171b-132">See Also</span></span>  
 [<span data-ttu-id="d171b-133">Задача «Очередь сообщений»</span><span class="sxs-lookup"><span data-stu-id="d171b-133">Message Queue Task</span></span>](message-queue-task.md)  
  
  
