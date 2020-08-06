---
title: Параметры подключения | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], connections
- authentication [Upgrade Advisor]
- SQL Server Upgrade Advisor, connections
- connections [Upgrade Advisor]
- server instances [Upgrade Advisor]
- default server instances
- analyzing system [Upgrade Advisor], connections
ms.assetid: f754d038-637a-4d8e-85b0-b242e6499d26
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 27eb69dfd2c41710a47861e0992486267f692a3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657497"
---
# <a name="connection-parameters"></a><span data-ttu-id="b92fb-102">Параметры подключения</span><span class="sxs-lookup"><span data-stu-id="b92fb-102">Connection Parameters</span></span>
  <span data-ttu-id="b92fb-103">Для анализа определенных типов сервера, таких как [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], необходимо выбрать конкретный экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b92fb-103">To analyze certain server types, such as the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], you must select a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b92fb-104">Автоматически выбирается экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b92fb-104">The default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is automatically selected.</span></span> <span data-ttu-id="b92fb-105">Этот выбор можно изменить, однако советник по переходу одновременно может выполнять анализ только одного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b92fb-105">You can change this selection, but you can select only one instance at a time for analysis by Upgrade Advisor.</span></span> <span data-ttu-id="b92fb-106">Если выбран тип сервера, требующий проверки подлинности, необходимо указать режим проверки подлинности и ввести учетные данные.</span><span class="sxs-lookup"><span data-stu-id="b92fb-106">If you have included a server type that requires authentication, you must enter the authentication mode and credentials.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b92fb-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="b92fb-107">Options</span></span>  
 <span data-ttu-id="b92fb-108">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="b92fb-108">**Server name**</span></span>  
 <span data-ttu-id="b92fb-109">Заранее заданное имя компьютера, введенное на панели «Компоненты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]».</span><span class="sxs-lookup"><span data-stu-id="b92fb-109">Pre-populated with the computer name that you entered in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Components pane.</span></span>  
  
 <span data-ttu-id="b92fb-110">**Имя экземпляра**</span><span class="sxs-lookup"><span data-stu-id="b92fb-110">**Instance name**</span></span>  
 <span data-ttu-id="b92fb-111">Выберите из экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], имеющихся на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b92fb-111">Select from the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are available on the computer.</span></span> <span data-ttu-id="b92fb-112">Если не удается получить список экземпляров, используйте MSSQLSERVER для просмотра экземпляра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b92fb-112">If you do not see a list of instances, use MSSQLSERVER to scan the default instance.</span></span> <span data-ttu-id="b92fb-113">В особенности это относится к удаленным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="b92fb-113">This is especially relevant for remote computers.</span></span> <span data-ttu-id="b92fb-114">Для просмотра экземпляра по умолчанию можно также использовать слово «default».</span><span class="sxs-lookup"><span data-stu-id="b92fb-114">You can also use the word "default" to scan the default instance.</span></span>  
  
 <span data-ttu-id="b92fb-115">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="b92fb-115">**Authentication**</span></span>  
 <span data-ttu-id="b92fb-116">Выберите из списка имеющихся режимов проверки подлинности на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="b92fb-116">Select from the list of available authentication modes on this computer.</span></span> <span data-ttu-id="b92fb-117">По умолчанию установлен режим проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b92fb-117">By default, the authentication mode is Windows Authentication.</span></span>  
  
 <span data-ttu-id="b92fb-118">**User name**</span><span class="sxs-lookup"><span data-stu-id="b92fb-118">**User name**</span></span>  
 <span data-ttu-id="b92fb-119">При использовании проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] введите в поле имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="b92fb-119">If using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, enter a user name in the box.</span></span> <span data-ttu-id="b92fb-120">Рекомендуется, чтобы имя пользователя имело учетные данные администратора на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b92fb-120">We recommend that the user name have administrative credentials on the computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b92fb-121">Если выбран вариант Проверка подлинности Windows, то имя пользователя, вошедшего в систему, будет заполнено в текстовом поле **имя пользователя** .</span><span class="sxs-lookup"><span data-stu-id="b92fb-121">If you select Windows Authentication, the user name of the currently logged-on user is populated in the **User name** text box.</span></span>  
  
 <span data-ttu-id="b92fb-122">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="b92fb-122">**Password**</span></span>  
 <span data-ttu-id="b92fb-123">Введите пароль для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="b92fb-123">Enter the password for the specified user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b92fb-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="b92fb-124">See Also</span></span>  
 <span data-ttu-id="b92fb-125">[Работа с советником по переходу](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="b92fb-125">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="b92fb-126">Справочник по пользовательскому интерфейсу помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="b92fb-126">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
