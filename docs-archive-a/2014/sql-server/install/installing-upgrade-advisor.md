---
title: Установка советника по переходу | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Setup [Upgrade Advisor]
- Upgrade Advisor [SQL Server], installing
ms.assetid: 1b7d6eca-1df1-47df-bbba-0fc485706a95
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 40f214b01f3e2066708a060c5f3ad1e8aa4a0a23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730046"
---
# <a name="installing-upgrade-advisor"></a><span data-ttu-id="d935d-102">Установка помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="d935d-102">Installing Upgrade Advisor</span></span>
  <span data-ttu-id="d935d-103">Место установки помощника по обновлению SQL Server 2014 определяется областью анализа.</span><span class="sxs-lookup"><span data-stu-id="d935d-103">Where you install SQL Server 2014 Upgrade Advisor depends on what you will be analyzing.</span></span> <span data-ttu-id="d935d-104">Помощник по обновлению поддерживает удаленный анализ всех компонентов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , кроме служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d935d-104">Upgrade Advisor supports remote analysis of all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components except [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="d935d-105">Если просмотр экземпляров служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]не производится, помощник по обновлению может быть установлен на любой компьютер, который способен установить соединение с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]и соответствует [Upgrade Advisor Prerequisites](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="d935d-105">If you are not scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can install Upgrade Advisor on any computer that can connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and that meets the [Upgrade Advisor Prerequisites](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md).</span></span> <span data-ttu-id="d935d-106">Для просмотра экземпляров служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]следует установить помощник по обновлению на сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="d935d-106">If you are scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must install Upgrade Advisor on the report server.</span></span>  
  
 <span data-ttu-id="d935d-107">Чтобы установить помощника по обновлению, запустите файл **SQLUA.msi** .</span><span class="sxs-lookup"><span data-stu-id="d935d-107">Run the **SQLUA.msi** file to install Upgrade Advisor.</span></span> <span data-ttu-id="d935d-108">Командная строка позволяет производить установку в автоматическом режиме.</span><span class="sxs-lookup"><span data-stu-id="d935d-108">You can install from the command prompt for unattended and automated installations.</span></span> <span data-ttu-id="d935d-109">Синтаксис и примеры можно посмотреть в статье [Installing Upgrade Advisor from the Command Prompt](../../../2014/sql-server/install/installing-upgrade-advisor-from-the-command-prompt.md) .</span><span class="sxs-lookup"><span data-stu-id="d935d-109">See [Installing Upgrade Advisor from the Command Prompt](../../../2014/sql-server/install/installing-upgrade-advisor-from-the-command-prompt.md) for syntax and examples.</span></span>  
  
 <span data-ttu-id="d935d-110">Получить файл SQLUA.msi можно:</span><span class="sxs-lookup"><span data-stu-id="d935d-110">Get SQLUA.msi:</span></span>  
  
-   <span data-ttu-id="d935d-111">Из папки **redist** установочного носителя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d935d-111">In the **redist** folder of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] product media.</span></span>  
  
-   <span data-ttu-id="d935d-112">Как часть [загрузки пакета дополнительных компонентов SQL 2014](https://www.microsoft.com/download/details.aspx?id=42295).</span><span class="sxs-lookup"><span data-stu-id="d935d-112">As part of the [SQL 2014 Feature Pack download](https://www.microsoft.com/download/details.aspx?id=42295).</span></span>  
  
## <a name="uninstalling-upgrade-advisor"></a><span data-ttu-id="d935d-113">Удаление помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="d935d-113">Uninstalling Upgrade Advisor</span></span>  
 <span data-ttu-id="d935d-114">Помощник по обновлению может быть удален через средство **Установка и удаление программ**.</span><span class="sxs-lookup"><span data-stu-id="d935d-114">You can uninstall Upgrade Advisor by using **Add or Remove Programs**.</span></span> <span data-ttu-id="d935d-115">Синтаксис командной строки также поддерживает удаление.</span><span class="sxs-lookup"><span data-stu-id="d935d-115">The command prompt syntax also supports removal/uninstall.</span></span>  
  
  
