---
title: Скрипт развертывания экземпляра CDC | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8fa82822-ac99-48ef-a18d-f4f3a77105b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6deea884168c2329e312eeaa2be16c28a955cca3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750096"
---
# <a name="cdc-instance-deployment-script"></a><span data-ttu-id="bb797-102">Скрипт развертывания экземпляра CDC</span><span class="sxs-lookup"><span data-stu-id="bb797-102">CDC Instance Deployment Script</span></span>
  <span data-ttu-id="bb797-103">Диалоговое окно «Скрипт развертывания экземпляра CDC», в котором отображается скрипт развертывания экземпляра CDC.</span><span class="sxs-lookup"><span data-stu-id="bb797-103">The CDC Instance Deployment Script dialog box that displays the CDC instance deployment script.</span></span> <span data-ttu-id="bb797-104">С помощью этого скрипта можно воссоздавать базу данных CDC со всеми ее артефактами на другом экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb797-104">This script can be used to re-create the CDC database with all of its artifacts on a different [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="bb797-105">После выполнения скрипта развертывания необходимо проверить следующее.</span><span class="sxs-lookup"><span data-stu-id="bb797-105">At the completion of the deployment script, you should make sure of the following:</span></span>  
  
-   <span data-ttu-id="bb797-106">Скрипт развертывания предполагает, что целевой экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] был подготовлен для CDC в консоли настройки службы CDC Oracle или с помощью **скрипта подготовки** , сформированный этой программой.</span><span class="sxs-lookup"><span data-stu-id="bb797-106">The deployment script assumes that the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance was prepared for Oracle CDC, by using the Oracle CDC Service Configuration Console or by using **prepare script** that program creates.</span></span>  
  
-   <span data-ttu-id="bb797-107">Часть скрипта, которая используется для обеспечения работы CDC в базе данных, должен запускать `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="bb797-107">The part of the script that is used to enable the database for CDC needs to be run by a `sysadmin`.</span></span>  
  
-   <span data-ttu-id="bb797-108">Скрипт не сохраняет пароль Oracle для интеллектуального анализа журнала.</span><span class="sxs-lookup"><span data-stu-id="bb797-108">The script does not preserve the Oracle log-mining password.</span></span> <span data-ttu-id="bb797-109">Его необходимо задать вручную после завершения работы скрипта и запуска службы CDC Oracle.</span><span class="sxs-lookup"><span data-stu-id="bb797-109">This needs to be set manually after the script is run and the Oracle CDC Service is started.</span></span>  
  
 <span data-ttu-id="bb797-110">В диалоговом окне **Скрипт развертывания экземпляра CDC** выберите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="bb797-110">Select the following options in the **CDC Instance Deployment Script** dialog box.</span></span>  
  
 <span data-ttu-id="bb797-111">**Сохранить как**</span><span class="sxs-lookup"><span data-stu-id="bb797-111">**Save As**</span></span>  
 <span data-ttu-id="bb797-112">Сохранение скрипта в текстовый файл, который можно разместить в любом каталоге.</span><span class="sxs-lookup"><span data-stu-id="bb797-112">Saves the script in a text file that you can save in any location you want.</span></span> <span data-ttu-id="bb797-113">Файл со скриптом можно скопировать на любой другой сервер, чтобы выполнить его там.</span><span class="sxs-lookup"><span data-stu-id="bb797-113">You can copy the file with the script to any other server to run it there.</span></span>  
  
 <span data-ttu-id="bb797-114">**Copy**.</span><span class="sxs-lookup"><span data-stu-id="bb797-114">**Copy**</span></span>  
 <span data-ttu-id="bb797-115">Копирует скрипт в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="bb797-115">Copies the script to the clipboard.</span></span> <span data-ttu-id="bb797-116">Затем скрипт можно будет вставить в среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или любой текстовый редактор для последующего выполнения.</span><span class="sxs-lookup"><span data-stu-id="bb797-116">You can then paste the script into the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or any text editor to run the scripts later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb797-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb797-117">See Also</span></span>  
 [<span data-ttu-id="bb797-118">Подготовка SQL Server для CDC</span><span class="sxs-lookup"><span data-stu-id="bb797-118">Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
