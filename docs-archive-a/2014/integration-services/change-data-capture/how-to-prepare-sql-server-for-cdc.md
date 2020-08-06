---
title: Как подготовить SQL Server для CDC | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a327fa18-58f4-4e69-bb87-44faf47e20ef
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fbd285faaa55a28ad82beb673fa783570809bd04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727306"
---
# <a name="how-to-prepare-sql-server-for-cdc"></a><span data-ttu-id="767e6-102">Как подготовить SQL Server для CDC</span><span class="sxs-lookup"><span data-stu-id="767e6-102">How to Prepare SQL Server for CDC</span></span>
  <span data-ttu-id="767e6-103">Для службы Oracle CDC требуется, чтобы все целевые экземпляры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] содержали базу данных MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="767e6-103">The Oracle CDC service requires all target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances to contain the MSXDBCDC database.</span></span> <span data-ttu-id="767e6-104">Эта база данных создается с помощью операции «Подготовка SQL Server» в консоли конфигурации служб CDC. Это действие выполняется только один раз для каждого целевого экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="767e6-104">You create this database using the Prepare SQL Server action in the CDC Service Configuration Console.This task is done one time only for each target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="767e6-105">Ниже описана подготовка базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для службы системы отслеживания измененных данных Oracle при помощи консоли конфигурации службы CDC.</span><span class="sxs-lookup"><span data-stu-id="767e6-105">The following describes how to prepare a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database for Oracle Change Data Capture using the CDC Service Configuration Console.</span></span> <span data-ttu-id="767e6-106">Этот процесс создает базу данных MSXDBCDC и определяет необходимые таблицы, хранимые процедуры и другие требуемые артефакты.</span><span class="sxs-lookup"><span data-stu-id="767e6-106">This process creates the MSXDBCDC database and defines the required tables, stored procedures, and other required artifacts.</span></span>  
  
 <span data-ttu-id="767e6-107">Подготовка SQL Server для Oracle CDC осуществляется администратором службы Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="767e6-107">Preparing the SQL Server for Oracle CDC is done by the Oracle CDC Service Administrator.</span></span> <span data-ttu-id="767e6-108">Дополнительные сведения о роли администратора службы CDC см. в разделе [роли пользователей для Change Data Capture Service для Oracle by Attunity](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="767e6-108">For more information about the CDC Service Administrator role, see [User Roles for Change Data Capture Service for Oracle by Attunity](user-roles.md).</span></span>  
  
### <a name="to-enable-sql-server-for-cdc"></a><span data-ttu-id="767e6-109">Включение SQL Server для CDC</span><span class="sxs-lookup"><span data-stu-id="767e6-109">To enable SQL Server for CDC</span></span>  
  
1.  <span data-ttu-id="767e6-110">В меню **Пуск** выберите пункт **Конфигурация служб CDC для Oracle**.</span><span class="sxs-lookup"><span data-stu-id="767e6-110">From the **Start** menu, select the **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="767e6-111">На левой панели выберите **Локальные службы CDC** , затем на панели **Действия** щелкните пункт **Подготовка SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="767e6-111">From the left pane, select **Local CDC Services** then from the **Actions** pane, click **Prepare SQL Server**.</span></span>  
  
     <span data-ttu-id="767e6-112">Можно также щелкнуть правой кнопкой **Локальные службы CDC** и выбрать **Подготовить SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="767e6-112">You can also right-click **Local CDC Services** and select **Prepare SQL Server**.</span></span>  
  
3.  <span data-ttu-id="767e6-113">Введите необходимую информацию в диалоговом окне «Подготовка экземпляра SQL Server для Oracle CDC».</span><span class="sxs-lookup"><span data-stu-id="767e6-113">Enter the required information in the Preparing SQL Server Instance for Oracle CDC dialog box.</span></span> <span data-ttu-id="767e6-114">Дополнительную информацию о вводе данных в этом диалоговом окне см. в разделе [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span><span class="sxs-lookup"><span data-stu-id="767e6-114">For information on how to enter the required information into this dialog box, see [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span></span>  
  
     <span data-ttu-id="767e6-115">Для подготовки экземпляра SQL Server для Oracle CDC имя входа должно иметь разрешение на запись в базу данных MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="767e6-115">To Prepare the SQL Server instance for Oracle CDC, the login must have write permission to the MSXDBCDC database.</span></span> <span data-ttu-id="767e6-116">Введите учетные данные для имени входа, имеющего разрешение на запись в базу данных MSXDBCDC. Это может быть член роли `sysasmin` .</span><span class="sxs-lookup"><span data-stu-id="767e6-116">Enter the credentials for a login that has write permission to the MSXDBCDC database, such as a member of the `sysasmin` role.</span></span>  
  
 <span data-ttu-id="767e6-117">**Примечание**. Можно щелкнуть пункт **Просмотреть скрипт** для просмотра версии скрипта установки, предназначенной только для чтения.</span><span class="sxs-lookup"><span data-stu-id="767e6-117">**Note**: You can click **View Script** to view a read-only version of the setup script.</span></span> <span data-ttu-id="767e6-118">Системный администратор [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при необходимости может скопировать этот скрипт в консоль управления [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и выполнить его.</span><span class="sxs-lookup"><span data-stu-id="767e6-118">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator can copy this script into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Console to edit and execute it, if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="767e6-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="767e6-119">See Also</span></span>  
 [<span data-ttu-id="767e6-120">Подготовка SQL Server для CDC</span><span class="sxs-lookup"><span data-stu-id="767e6-120">Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
