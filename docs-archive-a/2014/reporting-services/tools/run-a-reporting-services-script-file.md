---
title: Запуск файла скрипта служб Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services], running
ms.assetid: 0de4995c-85ec-4d4c-aaef-fbd30edfb20f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c787d860838a57a2bd0f51aac1e9159833f038d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735977"
---
# <a name="run-a-reporting-services-script-file"></a><span data-ttu-id="69a23-102">Запуск файла скрипта для служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="69a23-102">Run a Reporting Services Script File</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="69a23-103">Файлы скриптов служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] выполняются из командной строки с помощью среды скриптов служб (программа rs.exe).</span><span class="sxs-lookup"><span data-stu-id="69a23-103">script files are run from the command prompt using the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] script environment (RS.exe).</span></span> <span data-ttu-id="69a23-104">В программе rs.exe доступно множество аргументов командной строки.</span><span class="sxs-lookup"><span data-stu-id="69a23-104">RS.exe has many command prompt arguments available for you to use.</span></span> <span data-ttu-id="69a23-105">Дополнительные сведения о параметрах командной строки см. в разделе [Служебная программа RS.exe (службы SSRS)](rs-exe-utility-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="69a23-105">For more information about the command prompt options, see [RS.exe Utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span></span> <span data-ttu-id="69a23-106">Образцы скриптов см. на странице [Образцы продуктов служб SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="69a23-106">For more script samples, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="sample-command-lines"></a><span data-ttu-id="69a23-107">Образцы команд в командной строке</span><span class="sxs-lookup"><span data-stu-id="69a23-107">Sample Command Lines</span></span>  
  
-   <span data-ttu-id="69a23-108">Запустите файл Script.rss в среде выполнения скриптов, при этом укажите целевой сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="69a23-108">Run Script.rss in the script environment designating the target report server.</span></span> <span data-ttu-id="69a23-109">По умолчанию применяется проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="69a23-109">Windows Authentication is applied by default:</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver  
    ```  
  
-   <span data-ttu-id="69a23-110">Запустите файл Script.rss в среде выполнения скриптов, при этом задайте имя пользователя и пароль для ответа на вызовы веб-службы.</span><span class="sxs-lookup"><span data-stu-id="69a23-110">Run Script.rss in the script environment specifying a user name and password for authenticating the Web service calls:</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -u myusername -p mypassword  
    ```  
  
-   <span data-ttu-id="69a23-111">Запустите файл Script.rss в среде выполнения скриптов, задайте лимит времени ожидания для сервера в 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="69a23-111">Run Script.rss in the script environment specifying a server time-out of 30 seconds:</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -l 30  
    ```  
  
-   <span data-ttu-id="69a23-112">Запустите файл Script.rss в среде выполнения скриптов, при этом укажите глобальную переменную скрипта с именем *report*.</span><span class="sxs-lookup"><span data-stu-id="69a23-112">Run Script.rss in the script environment specifying a global script variable called *report*.</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -v report="Company Sales"  
    ```  
  
-   <span data-ttu-id="69a23-113">Запустите файл Script.rss в среде выполнения скриптов, при этом укажите, что операции веб-службы в файле скриптов должны выполняться в виде пакета.</span><span class="sxs-lookup"><span data-stu-id="69a23-113">Run Script.rss in the script environment specifying that the Web service operations in the script file are run as a batch.</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -b  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="69a23-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="69a23-114">See Also</span></span>  
 [<span data-ttu-id="69a23-115">Технический справочник (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="69a23-115">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
