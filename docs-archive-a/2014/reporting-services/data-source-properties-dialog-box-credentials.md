---
title: Диалоговое окно "Свойства источника данных" — "учетные данные" | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.datasourceproperties.credentials.f1
- "10100"
ms.assetid: 14c3eeb6-d37b-4fda-967b-43afcdb48119
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 491da16e6cd38db54c4d27bd8497ca7fdfaae5b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664765"
---
# <a name="data-source-properties-dialog-box-credentials"></a><span data-ttu-id="62ab0-102">Диалоговое окно «Свойства источника данных» — «Учетные данные»</span><span class="sxs-lookup"><span data-stu-id="62ab0-102">Data Source Properties Dialog Box, Credentials</span></span>
  <span data-ttu-id="62ab0-103">Вкладка **Общие** в диалоговом окне **Свойства источника данных** позволяет просмотреть и изменить учетные данные, используемые для подключения отчета к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="62ab0-103">Select **Credentials** on the **Data Source Properties** dialog box to display and modify credentials to connect to a data source in the report.</span></span> <span data-ttu-id="62ab0-104">Предоставленные учетные данные используются для доступа к источнику данных и кэширования копии данных для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="62ab0-104">The credentials that you provide are used to access the data source and to cache a copy of the data for previewing reports.</span></span> <span data-ttu-id="62ab0-105">Дополнительные сведения о кэшировании данных для предварительного просмотра см. в разделе [Предварительный просмотр отчетов](reports/previewing-reports.md).</span><span class="sxs-lookup"><span data-stu-id="62ab0-105">For more information about how preview data is cached, see [Previewing Reports](reports/previewing-reports.md).</span></span> <span data-ttu-id="62ab0-106">Дополнительные сведения об учетных данных см. в разделе [Указание учетных данных и сведений о соединении для источников данных отчета](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="62ab0-106">For more information about credentials, see [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="62ab0-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="62ab0-107">Options</span></span>  
 <span data-ttu-id="62ab0-108">**Использовать проверку подлинности Windows (встроенная безопасность)**</span><span class="sxs-lookup"><span data-stu-id="62ab0-108">**Use Windows Authentication (integrated security)**</span></span>  
 <span data-ttu-id="62ab0-109">Выберите этот параметр, чтобы использовать проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="62ab0-109">Select this option to use Windows Authentication.</span></span>  
  
 <span data-ttu-id="62ab0-110">**Использовать имя пользователя и пароль**</span><span class="sxs-lookup"><span data-stu-id="62ab0-110">**Use this user name and password**</span></span>  
 <span data-ttu-id="62ab0-111">Выберите этот параметр, чтобы использовать определенное имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="62ab0-111">Select this option to provide a specific user name and password.</span></span> <span data-ttu-id="62ab0-112">Для общих источников данных при публикации проекта сервера отчетов на целевом сервере имя пользователя и пароль сохраняются как сохраненные учетные данные для базы данных.</span><span class="sxs-lookup"><span data-stu-id="62ab0-112">For shared data sources: when you publish the report server project to the target server, the user name and password are saved as the stored credentials for the database.</span></span> <span data-ttu-id="62ab0-113">Если необходимо использовать имя пользователя и пароль как учетные данные Windows, можно изменить свойства опубликованного общего источника данных на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="62ab0-113">If you want to use the user name and password as Windows credentials, you can edit the properties for the published shared data source on the target server.</span></span> <span data-ttu-id="62ab0-114">Дополнительные сведения см. в разделе [Создание, удаление или изменение общего источника данных (диспетчер отчетов)](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="62ab0-114">For more information, see [Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md).</span></span>  
  
 <span data-ttu-id="62ab0-115">**User name**</span><span class="sxs-lookup"><span data-stu-id="62ab0-115">**User name**</span></span>  
 <span data-ttu-id="62ab0-116">Введите имя пользователя для получения доступа к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="62ab0-116">Type a user name to log in to the data source.</span></span>  
  
 <span data-ttu-id="62ab0-117">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="62ab0-117">**Password**</span></span>  
 <span data-ttu-id="62ab0-118">Введите пароль для получения доступа к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="62ab0-118">Type a password to log in to the data source.</span></span>  
  
 <span data-ttu-id="62ab0-119">**Запрос учетных данных**</span><span class="sxs-lookup"><span data-stu-id="62ab0-119">**Prompt for credentials**</span></span>  
 <span data-ttu-id="62ab0-120">Выберите этот параметр, чтобы учетные данные запрашивались при запуске отчета.</span><span class="sxs-lookup"><span data-stu-id="62ab0-120">Select this option to prompt for credentials when the report is run.</span></span>  
  
 <span data-ttu-id="62ab0-121">**Введите строку приглашения**</span><span class="sxs-lookup"><span data-stu-id="62ab0-121">**Enter prompt string**</span></span>  
 <span data-ttu-id="62ab0-122">Введите предложение пользователю ввести учетные данные входа для источника данных.</span><span class="sxs-lookup"><span data-stu-id="62ab0-122">Type a sentence to instruct the user to provide login credentials for the data source.</span></span>  
  
 <span data-ttu-id="62ab0-123">**Нет учетных данных**</span><span class="sxs-lookup"><span data-stu-id="62ab0-123">**No credentials**</span></span>  
 <span data-ttu-id="62ab0-124">Выберите этот параметр, чтобы учетные данные не запрашивались при доступе к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="62ab0-124">Select this option to provide no credentials for the data source.</span></span> <span data-ttu-id="62ab0-125">Этот параметр работает, только если источник данных не принимает учетные данные или если учетные данные передаются каким-то другим способом.</span><span class="sxs-lookup"><span data-stu-id="62ab0-125">This option only works if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62ab0-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="62ab0-126">See Also</span></span>  
 <span data-ttu-id="62ab0-127">[Диалоговое окно «Свойства источника данных» — «Общие»](../../2014/reporting-services/data-source-properties-dialog-box-general.md) </span><span class="sxs-lookup"><span data-stu-id="62ab0-127">[Data Source Properties Dialog Box, General](../../2014/reporting-services/data-source-properties-dialog-box-general.md) </span></span>  
 <span data-ttu-id="62ab0-128">[Задание учетных данных и сведениях о соединении для источников данных отчета](report-data/specify-credential-and-connection-information-for-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="62ab0-128">[Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md) </span></span>  
 [<span data-ttu-id="62ab0-129">Подключения данных, Источники данных и Строки подключения в службе Reporting Services</span><span class="sxs-lookup"><span data-stu-id="62ab0-129">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  
