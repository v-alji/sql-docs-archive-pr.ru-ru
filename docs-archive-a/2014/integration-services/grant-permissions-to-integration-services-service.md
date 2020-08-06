---
title: Предоставление разрешений Integration Services службе | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0c2caa68-7834-4ea0-bd77-4f3a7c86d634
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0e7ab0c2f482e5a0b1bfeaa06f38ec5a886420a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655847"
---
# <a name="grant-permissions-to-integration-services-service"></a><span data-ttu-id="0a95f-102">Предоставление разрешений службам Integration Services</span><span class="sxs-lookup"><span data-stu-id="0a95f-102">Grant Permissions to Integration Services Service</span></span>
  <span data-ttu-id="0a95f-103">В предыдущих версиях [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]по умолчанию при установке [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] все пользователи в группе пользователей имели доступ к службе [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a95f-103">In previous versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], by default when you installed [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] all users in the Users group had access to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="0a95f-104">При установке текущего выпуска [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]пользователи не имеют доступа к службе [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a95f-104">When you install the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], users do not have access to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="0a95f-105">По умолчанию эта служба является защищенной.</span><span class="sxs-lookup"><span data-stu-id="0a95f-105">The service is secure by default.</span></span> <span data-ttu-id="0a95f-106">После завершения установки [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] администратор должен предоставить доступ к службе.</span><span class="sxs-lookup"><span data-stu-id="0a95f-106">After [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is installed, the administrator must grant access to the service.</span></span>  
  
### <a name="to-grant-access-to-the-integration-services-service"></a><span data-ttu-id="0a95f-107">Предоставление доступа к службе Integration Services</span><span class="sxs-lookup"><span data-stu-id="0a95f-107">To grant access to the Integration Services service</span></span>  
  
1.  <span data-ttu-id="0a95f-108">Запустите файл Dcomcnfg.exe.</span><span class="sxs-lookup"><span data-stu-id="0a95f-108">Run Dcomcnfg.exe.</span></span> <span data-ttu-id="0a95f-109">Программа Dcomcnfg.exe предоставляет пользовательский интерфейс для изменения определенных параметров в реестре.</span><span class="sxs-lookup"><span data-stu-id="0a95f-109">Dcomcnfg.exe provides a user interface for modifying certain settings in the registry.</span></span>  
  
2.  <span data-ttu-id="0a95f-110">В диалоговом окне **Службы и компоненты** последовательно разверните "Службы и компоненты" > "Компьютеры" > "Мой компьютер" > "Настройка DCOM".</span><span class="sxs-lookup"><span data-stu-id="0a95f-110">In the **Component Services** dialog, expand the Component Services > Computers > My Computer > DCOM Config node.</span></span>  
  
3.  <span data-ttu-id="0a95f-111">Щелкните правой кнопкой мыши **Microsoft SQL Server Integration Services 12,0**и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="0a95f-111">Right-click **Microsoft SQL Server Integration Services 12.0**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="0a95f-112">На вкладке **Безопасность** нажмите кнопку **Правка** в области **Разрешение на запуск и активацию** .</span><span class="sxs-lookup"><span data-stu-id="0a95f-112">On the **Security** tab, click **Edit** in the **Launch and Activation Permissions** area.</span></span>  
  
5.  <span data-ttu-id="0a95f-113">Добавьте пользователей и назначьте им соответствующие разрешения, а затем нажмите кнопку «ОК».</span><span class="sxs-lookup"><span data-stu-id="0a95f-113">Add users and assign appropriate permissions, and then click Ok.</span></span>  
  
6.  <span data-ttu-id="0a95f-114">Повторите шаги 4 - 5 для назначения разрешений на доступ.</span><span class="sxs-lookup"><span data-stu-id="0a95f-114">Repeat steps 4 - 5 for Access Permissions.</span></span>  
  
7.  <span data-ttu-id="0a95f-115">Перезапустите среду SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="0a95f-115">Restart SQL Server Management Studio.</span></span>  
  
8.  <span data-ttu-id="0a95f-116">Перезапустите службу [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a95f-116">Restart the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Service.</span></span>  
  
  
