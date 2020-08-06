---
title: Диалоговое окно "Свойства источника данных" — "учетные данные" (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10017"
ms.assetid: 4531f09f-d653-4c05-a120-d7788838bc99
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9e47ba571e2b0adf2738499c1d027a4edde86e3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665855"
---
# <a name="data-source-properties-dialog-box-credentials-report-builder"></a><span data-ttu-id="e2646-102">Диалоговое окно «Свойства источника данных» — «Учетные данные» (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="e2646-102">Data Source Properties Dialog Box, Credentials (Report Builder)</span></span>
  <span data-ttu-id="e2646-103">Вкладка **Учетные данные** в диалоговом окне **Свойства источника данных** позволяет просмотреть и изменить учетные данные, используемые для подключения к источнику данных, внедренному в отчет.</span><span class="sxs-lookup"><span data-stu-id="e2646-103">Select **Credentials** on the **Data Source Properties** dialog box to display and modify credentials to connect to an embedded data source in the report.</span></span> <span data-ttu-id="e2646-104">Указанные учетные данные используются для доступа к источнику данных во время просмотра отчетов.</span><span class="sxs-lookup"><span data-stu-id="e2646-104">The credentials that you provide are used to access the data source for previewing reports.</span></span> <span data-ttu-id="e2646-105">Дополнительные сведения об учетных данных см. в разделе [Указание учетных данных в построителе отчетов](../../2014/reporting-services/specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e2646-105">For more information about credentials, see [Specify Credentials in Report Builder](../../2014/reporting-services/specify-credentials-in-report-builder.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e2646-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="e2646-106">Options</span></span>  
 <span data-ttu-id="e2646-107">**Использовать проверку подлинности Windows (встроенная безопасность)**</span><span class="sxs-lookup"><span data-stu-id="e2646-107">**Use Windows Authentication (integrated security)**</span></span>  
 <span data-ttu-id="e2646-108">Выберите этот параметр, чтобы использовать проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e2646-108">Select this option to use Windows Authentication.</span></span>  
  
 <span data-ttu-id="e2646-109">**Использовать имя пользователя и пароль**</span><span class="sxs-lookup"><span data-stu-id="e2646-109">**Use this user name and password**</span></span>  
 <span data-ttu-id="e2646-110">Выберите этот параметр, чтобы использовать определенное имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="e2646-110">Select this option to provide a specific user name and password.</span></span> <span data-ttu-id="e2646-111">Для встроенных источников данных: при публикации проекта сервера отчетов на целевом сервере имя пользователя и пароль сохраняются как хранимые учетные данные для базы данных.</span><span class="sxs-lookup"><span data-stu-id="e2646-111">For embedded data sources: when you publish the report server project to the target server, the user name and password are saved as the stored credentials for the database.</span></span> <span data-ttu-id="e2646-112">Если необходимо использовать имя пользователя и пароль как учетные данные Windows, можно изменить свойства опубликованного общего источника данных на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="e2646-112">If you want to use the user name and password as Windows credentials, you can change the properties for the published shared data source on the target server.</span></span> <span data-ttu-id="e2646-113">Дополнительные сведения см. в разделе [Создание, удаление или изменение общего источника данных (диспетчер отчетов)](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md) документации к [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [электронной документации](https://go.microsoft.com/fwlink/?linkid=121312) по .</span><span class="sxs-lookup"><span data-stu-id="e2646-113">For more information, see [Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md) in the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
  
 <span data-ttu-id="e2646-114">**User name**</span><span class="sxs-lookup"><span data-stu-id="e2646-114">**User name**</span></span>  
 <span data-ttu-id="e2646-115">Введите имя пользователя для получения доступа к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="e2646-115">Type a user name to log on to the data source.</span></span>  
  
 <span data-ttu-id="e2646-116">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="e2646-116">**Password**</span></span>  
 <span data-ttu-id="e2646-117">Введите пароль для получения доступа к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="e2646-117">Type a password to log on to the data source.</span></span>  
  
 <span data-ttu-id="e2646-118">**Запрос учетных данных**</span><span class="sxs-lookup"><span data-stu-id="e2646-118">**Prompt for credentials**</span></span>  
 <span data-ttu-id="e2646-119">Выберите этот параметр, чтобы учетные данные запрашивались при запуске отчета.</span><span class="sxs-lookup"><span data-stu-id="e2646-119">Select this option to prompt for credentials when the report runs.</span></span>  
  
 <span data-ttu-id="e2646-120">**Введите строку приглашения**</span><span class="sxs-lookup"><span data-stu-id="e2646-120">**Enter prompt string**</span></span>  
 <span data-ttu-id="e2646-121">Введите предложение пользователю ввести учетные данные входа для источника данных.</span><span class="sxs-lookup"><span data-stu-id="e2646-121">Type a sentence to instruct the user to provide login credentials for the data source.</span></span>  
  
 <span data-ttu-id="e2646-122">**Нет учетных данных**</span><span class="sxs-lookup"><span data-stu-id="e2646-122">**No credentials**</span></span>  
 <span data-ttu-id="e2646-123">Выберите этот параметр, чтобы учетные данные не запрашивались при доступе к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="e2646-123">Select this option to provide no credentials for the data source.</span></span> <span data-ttu-id="e2646-124">Этот параметр работает, только если источник данных не принимает учетные данные или если учетные данные передаются каким-то другим способом.</span><span class="sxs-lookup"><span data-stu-id="e2646-124">This option only works if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
 <span data-ttu-id="e2646-125">Для некоторых модулей обработки данных необходимо настроить на сервере отчетов учетную запись автоматического выполнения.</span><span class="sxs-lookup"><span data-stu-id="e2646-125">From some data extensions, the unattended execution account must be configured on the report server.</span></span>  
  
 <span data-ttu-id="e2646-126">Дополнительные сведения см. в разделе по соответствующему типу источника данных: [Добавление данных из внешних источников данных (службы SSRS)](report-data/add-data-from-external-data-sources-ssrs.md) и [Настройка учетной записи автоматического выполнения (диспетчер конфигурации служб SSRS)](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) в документации к [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [электронной документации](https://go.microsoft.com/fwlink/?linkid=121312) по .</span><span class="sxs-lookup"><span data-stu-id="e2646-126">For more information, see the topic for the corresponding data source type in [Add Data from External Data Sources &#40;SSRS&#41;](report-data/add-data-from-external-data-sources-ssrs.md) and [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) in the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2646-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="e2646-127">See Also</span></span>  
 <span data-ttu-id="e2646-128">[Построитель отчетов справки по диалоговым окнам, панелям и мастерам](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="e2646-128">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="e2646-129">[Диалоговое окно "Свойства источника данных", общие &#40;построитель отчетов&#41;](../../2014/reporting-services/data-source-properties-dialog-box-general-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="e2646-129">[Data Source Properties Dialog Box, General &#40;Report Builder&#41;](../../2014/reporting-services/data-source-properties-dialog-box-general-report-builder.md) </span></span>  
 <span data-ttu-id="e2646-130">[Добавление и проверка подключения к данным или источника данных &#40;построитель отчетов и служб SSRS&#41;](report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e2646-130">[Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;](report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e2646-131">Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e2646-131">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-data/report-datasets-ssrs.md)  
  
  
