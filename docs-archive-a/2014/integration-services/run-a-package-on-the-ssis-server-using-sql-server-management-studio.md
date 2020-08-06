---
title: Запуск пакета на сервере служб SSIS с помощью SQL Server Management Studio | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 56dc1bf8-99d4-41dc-bdc4-f64f1ccfd688
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d17009988dea54621d4fd7ef542cf452bfe95c6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729558"
---
# <a name="run-a-package-on-the-ssis-server-using-sql-server-management-studio"></a><span data-ttu-id="a6c92-102">Выполнение пакета на сервере служб SSIS с использованием среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a6c92-102">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>
  <span data-ttu-id="a6c92-103">После развертывания проекта на сервере служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] пакет можно запускать на сервере.</span><span class="sxs-lookup"><span data-stu-id="a6c92-103">After you deploy your project to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, you can run the package on the server.</span></span>  
  
 <span data-ttu-id="a6c92-104">В отчетах об операциях можно просматривать сведения о выполненных или выполняемых в данный момент на сервере пакетах.</span><span class="sxs-lookup"><span data-stu-id="a6c92-104">You can use operations reports to view information about packages that have run, or are currently running, on the server.</span></span> <span data-ttu-id="a6c92-105">Дополнительные сведения см. в статье [Reports for the Integration Services Server](../../2014/integration-services/reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="a6c92-105">For more information, see [Reports for the Integration Services Server](../../2014/integration-services/reports-for-the-integration-services-server.md).</span></span>  
  
### <a name="to-run-a-package-on-the-server-using-sql-server-management-studio"></a><span data-ttu-id="a6c92-106">Запуск пакета на сервере с помощью среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a6c92-106">To run a package on the server using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="a6c92-107">Откройте среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] и подключитесь к экземпляру [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , в котором содержится каталог служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6c92-107">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that contains the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog.</span></span>  
  
2.  <span data-ttu-id="a6c92-108">В обозревателе объектов разверните узел служб **Integration Services Catalogs** , разверните узел **SSISDB** и перейдите к пакету, содержащемуся в развернутом вами проекте.</span><span class="sxs-lookup"><span data-stu-id="a6c92-108">In Object Explorer, expand the **Integration Services Catalogs** node, expand the **SSISDB** node, and navigate to the package contained in the project you deployed.</span></span>  
  
3.  <span data-ttu-id="a6c92-109">Щелкните имя пакета правой кнопкой мыши и выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a6c92-109">Right-click the package name and select **Execute**.</span></span>  
  
4.  <span data-ttu-id="a6c92-110">Настройте выполнение пакета с помощью параметров на вкладках **Параметры**, **Диспетчеры соединений**и **Расширенные** диалогового окна **Выполнение пакета** .</span><span class="sxs-lookup"><span data-stu-id="a6c92-110">Configure the package execution by using the settings on the **Parameters**, **Connection Managers**, and **Advanced** tabs in the **Execute Package** dialog box.</span></span>  
  
5.  <span data-ttu-id="a6c92-111">Нажмите кнопку **ОК** , чтобы выполнить пакет.</span><span class="sxs-lookup"><span data-stu-id="a6c92-111">Click **OK** to run the package.</span></span>  
  
     <span data-ttu-id="a6c92-112">-или-</span><span class="sxs-lookup"><span data-stu-id="a6c92-112">-or-</span></span>  
  
     <span data-ttu-id="a6c92-113">Используйте хранимую процедуру для запуска пакета.</span><span class="sxs-lookup"><span data-stu-id="a6c92-113">Use stored procedures to run the package.</span></span> <span data-ttu-id="a6c92-114">Щелкните **Скрипт** , чтобы сформировать инструкцию Transact-SQL, которая создает и запускает экземпляр выполнения.</span><span class="sxs-lookup"><span data-stu-id="a6c92-114">Click **Script** to generate the Transact-SQL statement that creates an instance of the execution and starts an instance of the execution.</span></span> <span data-ttu-id="a6c92-115">Инструкция включает в себя вызов хранимых процедур catalog.create_execution, catalog.set_execution_parameter_value и catalog.start_execution.</span><span class="sxs-lookup"><span data-stu-id="a6c92-115">The statement includes a call to the catalog.create_execution, catalog.set_execution_parameter_value, and catalog.start_execution stored procedures.</span></span> <span data-ttu-id="a6c92-116">Дополнительные сведения об этих хранимых процедурах см. в разделах [catalog.create_execution (база данных SSISDB)](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database), [catalog.set_execution_parameter_value (база данных SSISDB)](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database) и [catalog.start_execution (база данных SSISDB)](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="a6c92-116">For more information about these stored procedures, see [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database), [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database), and [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span></span>  
  
  
