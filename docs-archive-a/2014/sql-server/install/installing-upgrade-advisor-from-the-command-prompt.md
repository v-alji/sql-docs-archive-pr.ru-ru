---
title: Установка помощника по обновлению из командной строки | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- command prompt [Upgrade Advisor]
- Setup [Upgrade Advisor]
- Upgrade Advisor [SQL Server], installing
ms.assetid: a6841cc2-ca13-4b1c-9343-9e4d54312c3a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b0c5193f0b235b6d37170992d9d7ca9568b1f675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730045"
---
# <a name="installing-upgrade-advisor-from-the-command-prompt"></a><span data-ttu-id="6713b-102">Установка помощника по обновлению из командной строки</span><span class="sxs-lookup"><span data-stu-id="6713b-102">Installing Upgrade Advisor from the Command Prompt</span></span>
  <span data-ttu-id="6713b-103">Установить помощник по обновлению можно как с помощью мастера установки, так и из командной строки.</span><span class="sxs-lookup"><span data-stu-id="6713b-103">You can install Upgrade Advisor either by using the Setup Wizard or from the command prompt.</span></span> <span data-ttu-id="6713b-104">С помощью командной строки можно производить установку в автоматическом режиме.</span><span class="sxs-lookup"><span data-stu-id="6713b-104">By using the command prompt you can perform unattended and automated installations.</span></span>  
  
## <a name="installation-syntax"></a><span data-ttu-id="6713b-105">Синтаксис установки</span><span class="sxs-lookup"><span data-stu-id="6713b-105">Installation Syntax</span></span>  
 <span data-ttu-id="6713b-106">Основной синтаксис установки помощника по обновлению из командной строки выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6713b-106">The basic syntax for installing Upgrade Advisor from the command prompt is as follows:</span></span>  
  
 `SQLUA.msi [options]`  
  
 <span data-ttu-id="6713b-107">В следующей таблице приведены наиболее часто применяемые параметры.</span><span class="sxs-lookup"><span data-stu-id="6713b-107">The following table shows the most common options.</span></span>  
  
|<span data-ttu-id="6713b-108">Аргумент</span><span class="sxs-lookup"><span data-stu-id="6713b-108">Argument</span></span>|<span data-ttu-id="6713b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="6713b-109">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="6713b-110">/q [n&#124;b&#124;r&#124;f]</span><span class="sxs-lookup"><span data-stu-id="6713b-110">/q[n&#124;b&#124;r&#124;f]</span></span>|<span data-ttu-id="6713b-111">Задает уровень пользовательского интерфейса (UI):</span><span class="sxs-lookup"><span data-stu-id="6713b-111">Sets user interface (UI) level:</span></span><br /><br /> <span data-ttu-id="6713b-112">n = без интерфейса</span><span class="sxs-lookup"><span data-stu-id="6713b-112">n = no UI</span></span><br /><br /> <span data-ttu-id="6713b-113">b = базовый интерфейс (только ход выполнения, без подсказок)</span><span class="sxs-lookup"><span data-stu-id="6713b-113">b = basic UI (progress only, no prompts)</span></span><br /><br /> <span data-ttu-id="6713b-114">r = сокращенный интерфейс (диалоговое окно в конце установки)</span><span class="sxs-lookup"><span data-stu-id="6713b-114">r = reduced UI (dialog box at the end of installation)</span></span><br /><br /> <span data-ttu-id="6713b-115">f = полный интерфейс</span><span class="sxs-lookup"><span data-stu-id="6713b-115">f = full UI</span></span>|  
|<span data-ttu-id="6713b-116">/L</span><span class="sxs-lookup"><span data-stu-id="6713b-116">/L</span></span>|<span data-ttu-id="6713b-117">Определяет параметры файла журнала.</span><span class="sxs-lookup"><span data-stu-id="6713b-117">Specifies log file options.</span></span> <span data-ttu-id="6713b-118">Чтобы записывать все сообщения в *log_file_name*, используйте **-L \* v**_log_file_name_.</span><span class="sxs-lookup"><span data-stu-id="6713b-118">To log all messages to *log_file_name*, use **-L\*v**_log_file_name_.</span></span> <span data-ttu-id="6713b-119">Чтобы регистрировать только сообщения об ошибках, используйте `-Le` *log_file_name*.</span><span class="sxs-lookup"><span data-stu-id="6713b-119">To log error messages only, use `-Le`*log_file_name*.</span></span>|  
|<span data-ttu-id="6713b-120">ADDLOCAL = ALL&#124; REMOVE = ALL&#124;REINSTALL = ALL</span><span class="sxs-lookup"><span data-stu-id="6713b-120">ADDLOCAL=ALL&#124; REMOVE=ALL&#124;REINSTALL=ALL</span></span>|<span data-ttu-id="6713b-121">Определяет, нужно ли установить (ADDLOCAL), удалить (REMOVE) или переустановить (REINSTALL) помощник по обновлению.</span><span class="sxs-lookup"><span data-stu-id="6713b-121">Specifies to install (ADDLOCAL), remove (REMOVE), or reinstall (REINSTALL) Upgrade Advisor.</span></span>|  
|<span data-ttu-id="6713b-122">UAINSTALLDIR=path</span><span class="sxs-lookup"><span data-stu-id="6713b-122">UAINSTALLDIR=path</span></span>|<span data-ttu-id="6713b-123">Устанавливает помощник по обновлению в местоположение, указанное в параметре path.</span><span class="sxs-lookup"><span data-stu-id="6713b-123">Installs Upgrade Advisor to the location specified by path.</span></span>|  
  
## <a name="installation-examples"></a><span data-ttu-id="6713b-124">Примеры установки</span><span class="sxs-lookup"><span data-stu-id="6713b-124">Installation Examples</span></span>  
 <span data-ttu-id="6713b-125">В следующих примерах показано, как установить помощник по обновлению с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="6713b-125">The following example shows how to install Upgrade Advisor by using the command prompt:</span></span>  
  
```  
SQLUA.msi /qn ADDLOCAL=ALL UAINSTALLDIR="C:\Upgrade Advisor"  
```  
  
 <span data-ttu-id="6713b-126">При запуске этой команды можно также использовать программу Msiexec.</span><span class="sxs-lookup"><span data-stu-id="6713b-126">You can also use the Msiexec program when you run this command:</span></span>  
  
```  
Msiexec.exe /i C:\Downloads\SQLUA.msi /qn ADDLOCAL=ALL UAINSTALLDIR="C:\Upgrade Advisor"  
```  
  
 <span data-ttu-id="6713b-127">Это может оказаться полезным, если есть необходимость в дополнительных параметрах установки.</span><span class="sxs-lookup"><span data-stu-id="6713b-127">This can be helpful if you have to use additional installation options.</span></span>  
  
## <a name="removal-examples"></a><span data-ttu-id="6713b-128">Примеры удаления</span><span class="sxs-lookup"><span data-stu-id="6713b-128">Removal Examples</span></span>  
 <span data-ttu-id="6713b-129">В следующих примерах показано, как удалить помощник по обновлению с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="6713b-129">The following example shows how to remove Upgrade Advisor by using the command prompt:</span></span>  
  
```  
SQLUA.msi /qn REMOVE=ALL  
```  
  
 <span data-ttu-id="6713b-130">При запуске этой команды можно также использовать программу Msiexec.</span><span class="sxs-lookup"><span data-stu-id="6713b-130">You can also use the Msiexec program when you run this command:</span></span>  
  
```  
Msiexec.exe /i C:\Downloads\SQLUA.msi /qn REMOVE=ALL  
```  
  
## <a name="see-also"></a><span data-ttu-id="6713b-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="6713b-131">See Also</span></span>  
 <span data-ttu-id="6713b-132">[Установка помощника по обновлению](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="6713b-132">[Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="6713b-133">Компоненты, необходимые для помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="6713b-133">Upgrade Advisor Prerequisites</span></span>](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md)  
  
  
