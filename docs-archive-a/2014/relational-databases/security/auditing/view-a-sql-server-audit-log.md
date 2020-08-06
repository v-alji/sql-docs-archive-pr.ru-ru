---
title: Просмотр журнала подсистемы аудита SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- audits [SQL Server], viewing logs
- viewing audit logs
- logs [SQL Server], audit
ms.assetid: e8feaca0-7852-422b-895a-319b965d8d9b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 8f9902a4fc92ef0b35bae62eb80170762c52fdec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656287"
---
# <a name="view-a-sql-server-audit-log"></a><span data-ttu-id="75c03-102">Просмотр журнала подсистемы аудита SQL Server</span><span class="sxs-lookup"><span data-stu-id="75c03-102">View a SQL Server Audit Log</span></span>
  <span data-ttu-id="75c03-103">В этом разделе описано, как просмотреть журнал аудита SQL Server в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75c03-103">This topic describes how to view a SQL Server audit log in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="75c03-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="75c03-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="75c03-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="75c03-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="75c03-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="75c03-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="75c03-107">**Просмотр журнала подсистемы аудита SQL Server с помощью:**</span><span class="sxs-lookup"><span data-stu-id="75c03-107">**To view a SQL Server audit log, using:**</span></span>  
  
     [<span data-ttu-id="75c03-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="75c03-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="75c03-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="75c03-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="75c03-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="75c03-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="75c03-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="75c03-111">Permissions</span></span>  
 <span data-ttu-id="75c03-112">Требуется разрешение `CONTROL SERVER`.</span><span class="sxs-lookup"><span data-stu-id="75c03-112">Requires the `CONTROL SERVER` permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="75c03-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="75c03-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-a-sql-server-audit-log"></a><span data-ttu-id="75c03-114">Просмотр журнала подсистемы аудита SQL Server</span><span class="sxs-lookup"><span data-stu-id="75c03-114">To view a SQL Server audit log</span></span>  
  
1.  <span data-ttu-id="75c03-115">В обозревателе объектов раскройте папку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="75c03-115">In Object Explorer, expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="75c03-116">Разверните папку **Аудит** .</span><span class="sxs-lookup"><span data-stu-id="75c03-116">Expand the **Audits** folder.</span></span>  
  
3.  <span data-ttu-id="75c03-117">Щелкните правой кнопкой мыши журнал аудита, который необходимо просмотреть, и выберите пункт **Просмотр журналов аудита**.</span><span class="sxs-lookup"><span data-stu-id="75c03-117">Right-click the audit log that you want to view and select **View Audit Logs**.</span></span> <span data-ttu-id="75c03-118">Откроется диалоговое окно **Просмотр файла журнала —**_server_name_ .</span><span class="sxs-lookup"><span data-stu-id="75c03-118">This opens the **Log File Viewer -**_server_name_ dialog box.</span></span> <span data-ttu-id="75c03-119">Дополнительные сведения см. в статье [Log File Viewer F1 Help](../../logs/log-file-viewer-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="75c03-119">For more information, see [Log File Viewer F1 Help](../../logs/log-file-viewer-f1-help.md).</span></span>  
  
4.  <span data-ttu-id="75c03-120">После завершения нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="75c03-120">When finished, click **Close**.</span></span>  
  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="75c03-121">рекомендует просматривать журнал аудита, используя средство просмотра файлов журнала.</span><span class="sxs-lookup"><span data-stu-id="75c03-121">recommends viewing the audit log by using the Log File Viewer.</span></span> <span data-ttu-id="75c03-122">Однако при создании автоматизированной системы мониторинга информацию в файле аудита можно просматривать напрямую с помощью функции [sys.fn_get_audit_file (Transact-SQL)](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="75c03-122">However, if you are creating an automated monitoring system, the information in the audit file can be read directly by using the [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql) function.</span></span> <span data-ttu-id="75c03-123">При чтении файла напрямую данные возвращаются в несколько ином (необработанном) формате.</span><span class="sxs-lookup"><span data-stu-id="75c03-123">Reading the file directly returns data in a slightly different (unprocessed) format.</span></span> <span data-ttu-id="75c03-124">Дополнительные сведения см. в разделе **sys. fn_get_audit_file** .</span><span class="sxs-lookup"><span data-stu-id="75c03-124">See **sys.fn_get_audit_file** for more information</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75c03-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="75c03-125">See Also</span></span>  
 <span data-ttu-id="75c03-126">[Подсистема аудита SQL Server (компонент Database Engine)](sql-server-audit-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="75c03-126">[SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md) </span></span>  
 [<span data-ttu-id="75c03-127">Запись событий подсистемы аудита SQL Server в журнал безопасности</span><span class="sxs-lookup"><span data-stu-id="75c03-127">Write SQL Server Audit Events to the Security Log</span></span>](write-sql-server-audit-events-to-the-security-log.md)  
  
  
