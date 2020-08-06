---
title: Просмотр журнала приложений Windows (Windows) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- viewing logs
- application logs [SQL Server]
- logs [SQL Server], application
- monitoring Windows NT application log [SQL Server]
- Windows NT application logs [SQL Server]
- displaying logs
- monitoring [SQL Server], events
- logs [SQL Server], viewing
ms.assetid: 168a6c6e-12df-46a9-9904-55d63ca8fe14
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1255e95833d9fc56abd1700f5acb0d2f49ebf77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731549"
---
# <a name="view-the-windows-application-log-windows"></a><span data-ttu-id="c946f-102">Просмотр журнала приложений Windows (Windows)</span><span class="sxs-lookup"><span data-stu-id="c946f-102">View the Windows Application Log (Windows)</span></span>
  <span data-ttu-id="c946f-103">Когда [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] настроен на использование журнала приложений Windows, каждый сеанс [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] записывает новые события в этот журнал.</span><span class="sxs-lookup"><span data-stu-id="c946f-103">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to use the Windows application log, each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session writes new events to that log.</span></span> <span data-ttu-id="c946f-104">В отличие от журнала ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , новый журнал приложений не создается заново каждый раз при запуске экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c946f-104">Unlike the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, a new application log is not created each time you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-view-the-windows-application-log"></a><span data-ttu-id="c946f-105">Просмотр журнала приложений Windows</span><span class="sxs-lookup"><span data-stu-id="c946f-105">To view the Windows application log</span></span>  
  
1.  <span data-ttu-id="c946f-106">В меню **Пуск** укажите пункт **Все программы**, затем **Администрирование**и выберите пункт **Просмотр событий**.</span><span class="sxs-lookup"><span data-stu-id="c946f-106">On the **Start** menu, point to **All Programs**, point to **Administrative Tools**, and then click **Event Viewer**.</span></span>  
  
2.  <span data-ttu-id="c946f-107">В окне «Просмотр событий» щелкните элемент **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="c946f-107">In Event Viewer, click **Application**.</span></span>  
  
3.  <span data-ttu-id="c946f-108">События [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] идентифицируются записью **MSSQLSERVER** в столбце **Источник** (именованные экземпляры обозначаются как **MSSQL$** _<имя_экземпляра>_ ).</span><span class="sxs-lookup"><span data-stu-id="c946f-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events are identified by the entry **MSSQLSERVER** (named instances are identified with **MSSQL$**_<instance_name>_) in the **Source** column.</span></span> <span data-ttu-id="c946f-109">События агента SQL Server идентифицируются записью SQLSERVERAGENT (для именованных экземпляров сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] события агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] идентифицируются при помощи **SQLAgent$** \<*instance_name*>).</span><span class="sxs-lookup"><span data-stu-id="c946f-109">SQL Server Agent events are identified by the entry SQLSERVERAGENT (for named instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events are identified with **SQLAgent$**\<*instance_name*>).</span></span> <span data-ttu-id="c946f-110">События службы Microsoft Search идентифицируются записью **Microsoft Search**.</span><span class="sxs-lookup"><span data-stu-id="c946f-110">Microsoft Search service events are identified by the entry **Microsoft Search**.</span></span>  
  
4.  <span data-ttu-id="c946f-111">Чтобы просмотреть журнал другого компьютера, щелкните правой кнопкой мыши в окне **Просмотр событий**, выберите пункт **Подключение к другому компьютеру** и заполните диалоговое окно **Выбор компьютера**.</span><span class="sxs-lookup"><span data-stu-id="c946f-111">To view the log of a different computer, right-click **Event Viewer**, click **Connect to another computer,** and complete the **Select Computer**dialog box.</span></span>  
  
5.  <span data-ttu-id="c946f-112">Дополнительно для отображения только событий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в меню **Просмотр** выберите пункт **Фильтрация**и в списке **Источник событий** выберите **MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="c946f-112">Optionally, to display only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events, on the **View** menu click **Filter**, and in the **Event source** list, select **MSSQLSERVER**.</span></span> <span data-ttu-id="c946f-113">Чтобы просмотреть только события агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , в списке **Источник события** вместо этого выберите **SQLSERVERAGENT** .</span><span class="sxs-lookup"><span data-stu-id="c946f-113">To view only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events, instead select **SQLSERVERAGENT** in the **Event source** list.</span></span>  
  
6.  <span data-ttu-id="c946f-114">Чтобы просмотреть дополнительные сведения о событии, дважды щелкните событие.</span><span class="sxs-lookup"><span data-stu-id="c946f-114">To view more information about an event, double-click the event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c946f-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="c946f-115">See Also</span></span>  
 [<span data-ttu-id="c946f-116">Просмотр журнала ошибок SQL Server (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="c946f-116">View the SQL Server Error Log &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/sql-server-management-studio-ssms.md)  
  
  
