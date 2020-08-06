---
title: Проверка наличия установленного и запущенного компонента Database Engine | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server, determining if installed
- verifying Database Engine installation
- viewing Database Engine installation
- installed Database Engine verification [SQL Server]
ms.assetid: babb02e4-3521-4b75-b5df-e09205594375
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0a912cf4a89f208543605cc84f480b63955214ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740418"
---
# <a name="determine-whether-the-database-engine-is-installed-and-started"></a><span data-ttu-id="d995b-102">Проверка наличия установленного и запущенного компонента Database Engine</span><span class="sxs-lookup"><span data-stu-id="d995b-102">Determine Whether the Database Engine Is Installed and Started</span></span>
  <span data-ttu-id="d995b-103">При успешной установке компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] создаются записи в реестре, устанавливаются файлы в файловой системе и несколько программ.</span><span class="sxs-lookup"><span data-stu-id="d995b-103">A successful installation of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] installs files to the file system, creates entries in the registry, and installs several tools.</span></span> <span data-ttu-id="d995b-104">В этом разделе описано, как определить, успешно ли установлен и запущен компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , с помощью диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d995b-104">This topic describes how to determine whether the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is installed and started in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d995b-105">Использование диспетчера конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="d995b-105">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="how-to-view-and-start-the-database-engine-by-using-sql-server-configuration-manager"></a><span data-ttu-id="d995b-106">Просмотр состояния и запуск ядра СУБД при помощи диспетчера конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="d995b-106">How to view and start the Database Engine by using SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="d995b-107">В меню **Пуск**последовательно наведите указатель мыши на пункты **Программы**, **Microsoft SQL Server**, **Средства настройки**и выберите пункт **Диспетчер конфигурации SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d995b-107">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
     <span data-ttu-id="d995b-108">Если эти пункты отсутствуют в меню **Пуск** , то [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не был установлен корректно.</span><span class="sxs-lookup"><span data-stu-id="d995b-108">If you do not have these entries on the **Start** menu, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not correctly installed.</span></span> <span data-ttu-id="d995b-109">Запустите программу Setup для установки [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d995b-109">Run Setup to install the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="d995b-110">В **Диспетчере конфигурации SQL Server**на левой панели выберите **Службы SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d995b-110">In **SQL Server Configuration Manager**, on the left pane, click **SQL Server Services**.</span></span> <span data-ttu-id="d995b-111">В правой панели содержится список служб, связанных с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d995b-111">The right pane lists several services that are related to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d995b-112">Если установлен компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)], то служба [!INCLUDE[ssDE](../../includes/ssde-md.md)] указана как **SQL Server (MSSQLSERVER)** , если это — экземпляр по умолчанию, или как **SQL Server (** \<*instance_name*> **)** , если [!INCLUDE[ssDE](../../includes/ssde-md.md)] установлен как именованный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="d995b-112">If the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is installed, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service is listed as **SQL Server (MSSQLSERVER)** if it is the default instance; or **SQL Server (**\<*instance_name*>**)**, if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is installed as a named instance.</span></span> <span data-ttu-id="d995b-113">До изменения имени этого экземпляра [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] устанавливает этот экземпляр с именем **SQLEXPRESS**.</span><span class="sxs-lookup"><span data-stu-id="d995b-113">Unless the instance name is changed, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs as a named instance with the name **SQLEXPRESS**.</span></span> <span data-ttu-id="d995b-114">Значок в виде зеленого треугольника означает, что компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] запущен.</span><span class="sxs-lookup"><span data-stu-id="d995b-114">A green triangle icon indicates that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is running.</span></span> <span data-ttu-id="d995b-115">Значок в виде красного квадрата означает, что компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] остановлен.</span><span class="sxs-lookup"><span data-stu-id="d995b-115">A red square icon indicates that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is stopped.</span></span>  
  
3.  <span data-ttu-id="d995b-116">Для запуска компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)]на правой панели щелкните правой кнопкой мыши компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)]и выберите **Пуск**.</span><span class="sxs-lookup"><span data-stu-id="d995b-116">To start the [!INCLUDE[ssDE](../../includes/ssde-md.md)], in the right pane, right-click the [!INCLUDE[ssDE](../../includes/ssde-md.md)], and then click **Start**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d995b-117">Во время установки пользователь может выбрать, куда устанавливать файлы программ и баз данных.</span><span class="sxs-lookup"><span data-stu-id="d995b-117">During setup, the user can select a location in which to install the program files and the database files.</span></span> <span data-ttu-id="d995b-118">По умолчанию файлы устанавливаются в папки [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)] и C:\Program Files\Microsoft SQL Server\MSSQL.*x*, где *x* является числом.</span><span class="sxs-lookup"><span data-stu-id="d995b-118">If the user accepts the default location, the files are installed to [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)] and C:\Program Files\Microsoft SQL Server\MSSQL.*x*, where *x* is a number.</span></span>  
  
  
