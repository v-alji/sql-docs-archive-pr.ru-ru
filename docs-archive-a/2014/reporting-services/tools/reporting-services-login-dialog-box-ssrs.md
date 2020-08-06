---
title: Диалоговое окно имени для входа Reporting Services (SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.reportservicelogin.f1
ms.assetid: 2037d797-0b61-44c7-931f-6c689c3fc733
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 232ee51614a668b07263c3e3a4182f23652135bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736002"
---
# <a name="reporting-services-login-dialog-box-ssrs"></a><span data-ttu-id="dfc66-102">Диалоговое окно «Имя входа служб Reporting Services» (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="dfc66-102">Reporting Services Login Dialog Box (SSRS)</span></span>
  <span data-ttu-id="dfc66-103">В диалоговом окне **Имя входа служб Reporting Services** задаются учетные данные для публикации отчетов на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="dfc66-103">Use the **Reporting Services Login** dialog box to provide credentials to publish reports to the report server.</span></span>  
  
-   <span data-ttu-id="dfc66-104">**Примечание** . Если вы впервые опубликовали отчет на сервере отчетов, с момента **установки свойства Deployment** для проекта, убедитесь, что указанное имя сервера имеет вид `http://localhost/reportserver` , а не `http://localhost/reports` .</span><span class="sxs-lookup"><span data-stu-id="dfc66-104">**Note** If this is the first time you have published a report to a report server since set you set the deployment property **TargetServerURL** for a project, verify that the server name you specified is similar to `http://localhost/reportserver`, and not `http://localhost/reports`.</span></span> <span data-ttu-id="dfc66-105">Указание каталога `reports` на локальном сервере вместо каталога `reportserver` косвенно вызывает открытие этого диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="dfc66-105">Specifying the `reports` directory on the local server instead of the `reportserver` directory indirectly causes this dialog box to open.</span></span> <span data-ttu-id="dfc66-106">Дополнительные сведения о настройке параметра **TargetServerURL** см. в разделе [Задание свойств развертывания (службы Reporting Services)](set-deployment-properties-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="dfc66-106">For more information about setting **TargetServerURL**, see [Set Deployment Properties &#40;Reporting Services&#41;](set-deployment-properties-reporting-services.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="dfc66-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="dfc66-107">Options</span></span>  
 <span data-ttu-id="dfc66-108">**Server**</span><span class="sxs-lookup"><span data-stu-id="dfc66-108">**Server**</span></span>  
 <span data-ttu-id="dfc66-109">Отображает имя сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="dfc66-109">Displays the name of the report server.</span></span> <span data-ttu-id="dfc66-110">Например, `http://localhost/reportserver`.</span><span class="sxs-lookup"><span data-stu-id="dfc66-110">For example, `http://localhost/reportserver`.</span></span> <span data-ttu-id="dfc66-111">Для серверов отчетов, использующих порт, отличный от порта по умолчанию 80, включается номер порта.</span><span class="sxs-lookup"><span data-stu-id="dfc66-111">For report servers that use a different port than default port 80, include the port number.</span></span> <span data-ttu-id="dfc66-112">Например, `http://localhost:81/reportserver`.</span><span class="sxs-lookup"><span data-stu-id="dfc66-112">For example, `http://localhost:81/reportserver`.</span></span>  
  
 <span data-ttu-id="dfc66-113">**User name**</span><span class="sxs-lookup"><span data-stu-id="dfc66-113">**User name**</span></span>  
 <span data-ttu-id="dfc66-114">Введите имя пользователя для входа в данную веб-службу.</span><span class="sxs-lookup"><span data-stu-id="dfc66-114">Type the user name to log in to the Web service.</span></span>  
  
 <span data-ttu-id="dfc66-115">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="dfc66-115">**Password**</span></span>  
 <span data-ttu-id="dfc66-116">Введите пароль для входа в данную веб-службу.</span><span class="sxs-lookup"><span data-stu-id="dfc66-116">Type the password to log in to the Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc66-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="dfc66-117">See Also</span></span>  
 <span data-ttu-id="dfc66-118">[Подключения к данным, источники данных и строки подключения в Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="dfc66-118">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="dfc66-119">[Указание учетных данных и сведений о соединении для источников данных отчета](../report-data/specify-credential-and-connection-information-for-report-data-sources.md) [конструктор отчетов Справка F1](report-designer-f1-help.md)</span><span class="sxs-lookup"><span data-stu-id="dfc66-119">[Specify Credential and Connection Information for Report Data Sources](../report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Report Designer F1 Help](report-designer-f1-help.md)</span></span>  
  
  
