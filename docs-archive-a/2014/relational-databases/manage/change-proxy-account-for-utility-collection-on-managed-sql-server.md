---
title: Изменение учетной записи-посредника для набора элементов сбора служебной программы на Управляемый экземпляр SQL Server (служебная программа SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: ff37ba8b-a08c-4109-b6e2-5748c995a52c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19f60c607ed661ef42c1c1c0e48854cdfd69a912
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656407"
---
# <a name="change-the-proxy-account-for-the-utility-collection-set-on-a-managed-instance-of-sql-server-sql-server-utility"></a><span data-ttu-id="80d8a-102">Изменение учетной записи-посредника для набора элементов сбора служебной программы на управляемом экземпляре SQL Server (служебная программа SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80d8a-102">Change the Proxy Account for the Utility Collection Set on a Managed Instance of SQL Server (SQL Server Utility)</span></span>
  <span data-ttu-id="80d8a-103">В этом разделе описано, как изменить учетную запись-посредник для набора элементов сбора служебной программы на управляемом экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80d8a-103">This topic describes how to change the proxy account for the Utility Collection Set on a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="80d8a-104">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="80d8a-104">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-proxy-account-for-the-utility-collection-set-on-a-managed-instance-of-sql-server"></a><span data-ttu-id="80d8a-105">Изменение учетной записи-посредника для набора элементов сбора служебной программы на управляемом экземпляре SQL Server</span><span class="sxs-lookup"><span data-stu-id="80d8a-105">To change the proxy account for the utility collection set on a managed instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="80d8a-106">Удалите управляемый экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из программы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="80d8a-106">Remove the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
    -   <span data-ttu-id="80d8a-107">В **Обозревателе программ** среды SSMS щелкните узел **Управляемые экземпляры** .</span><span class="sxs-lookup"><span data-stu-id="80d8a-107">In **Utility Explorer** in SSMS, click on the **Managed Instances** node.</span></span>  
  
    -   <span data-ttu-id="80d8a-108">В списке **обозревателя программ** щелкните правой кнопкой мыши имя экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и выберите команду **Удалить управляемый экземпляр…** . Дополнительные сведения см. в разделе [Удаление экземпляра SQL Server из служебной программы SQL Server](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="80d8a-108">In the **Utility Explorer** list view, right-click the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name, and select **Remove Managed Instance...**. For more information, see [Remove an Instance of SQL Server from the SQL Server Utility](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span></span>  
  
2.  <span data-ttu-id="80d8a-109">Снова зарегистрируйте экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в программе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="80d8a-109">Enroll the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility again.</span></span>  
  
    -   <span data-ttu-id="80d8a-110">В **обозревателе программ** среды SSMS щелкните правой кнопкой мыши узел **Управляемые экземпляры** и выберите команду **Добавить управляемый экземпляр…** .</span><span class="sxs-lookup"><span data-stu-id="80d8a-110">In **Utility Explorer** in SSMS, right-click on the **Managed Instances** node, and select **Add Managed Instance...**.</span></span>  
  
    -   <span data-ttu-id="80d8a-111">Выполните предлагаемые мастером действия, указав новую учетную запись-посредник.</span><span class="sxs-lookup"><span data-stu-id="80d8a-111">Follow prompts to complete the wizard, specifying the new proxy account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80d8a-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="80d8a-112">See Also</span></span>  
 <span data-ttu-id="80d8a-113">[Функции и задачи служебной программы SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="80d8a-113">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 [<span data-ttu-id="80d8a-114">Устранение неполадок служебной программы SQL Server</span><span class="sxs-lookup"><span data-stu-id="80d8a-114">Troubleshoot the SQL Server Utility</span></span>](../../database-engine/troubleshoot-the-sql-server-utility.md)  
  
  
