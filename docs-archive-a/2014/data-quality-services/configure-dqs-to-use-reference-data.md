---
title: Настройка служб DQS для использования эталонных данных | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.admin.config.rds.f1
- sql12.dqs.administration.rdsconfiguration.f1
- sql12.dqs.administration.configuration.createDirectRDS.f1
ms.assetid: fae745e7-57a7-4cbc-8979-56ea8e392e4e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 670e984c2afabb70dece75d94701d7a3a03c95bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728733"
---
# <a name="configure-dqs-to-use-reference-data"></a><span data-ttu-id="6cc6f-102">Настройка служб DQS для использования справочных данных</span><span class="sxs-lookup"><span data-stu-id="6cc6f-102">Configure DQS to Use Reference Data</span></span>
  <span data-ttu-id="6cc6f-103">В этом разделе описывается настройка служб [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) на использование ссылочных данных для очистки данных.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-103">This topic describes how to configure [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) to use reference data for cleansing your data.</span></span> <span data-ttu-id="6cc6f-104">Можно либо использовать эталонные данные из Azure Marketplace, либо напрямую обращаться к сторонним поставщикам ссылочных данных.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-104">You could either use reference data from Azure Marketplace or from direct online third-party reference data providers.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="6cc6f-105">Перед началом</span><span class="sxs-lookup"><span data-stu-id="6cc6f-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="6cc6f-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="6cc6f-106">Prerequisites</span></span>  
 <span data-ttu-id="6cc6f-107">Чтобы использовать ссылочные данные из Marketplace, необходим действительный ключ учетной записи Marketplace.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-107">To use reference data from Marketplace, you must have a valid Marketplace account key.</span></span> <span data-ttu-id="6cc6f-108">Подробные сведения о создании ключа учетной записи Marketplace см. в разделе [Создание учетной записи](https://go.microsoft.com/fwlink/?LinkId=212936) ( https://go.microsoft.com/fwlink/?LinkId=212936) .</span><span class="sxs-lookup"><span data-stu-id="6cc6f-108">For detailed information about creating a Marketplace account key, see [Create Your Account](https://go.microsoft.com/fwlink/?LinkId=212936) (https://go.microsoft.com/fwlink/?LinkId=212936).</span></span> <span data-ttu-id="6cc6f-109">Ключ учетной записи Marketplace также можно создать с помощью [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , выбрав команду **Настройка** в разделе **Администрирование** главной страницы [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , а затем нажав кнопку **Создать идентификатор учетной записи DataMarket** на вкладке **Ссылочные данные** .</span><span class="sxs-lookup"><span data-stu-id="6cc6f-109">You can also create a Marketplace account key from within [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] by clicking **Configuration** under **Administration** in the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, and then clicking **Create a DataMarket Account ID** under the **Reference Data** tab.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6cc6f-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="6cc6f-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6cc6f-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="6cc6f-111">Permissions</span></span>  
 <span data-ttu-id="6cc6f-112">Для настройки параметров службы ссылочных данных в DQS необходимо иметь роль dqs_administrator в базе данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-112">You must have the dqs_administrator role on the DQS_MAIN database to configure reference data service settings in DQS.</span></span>  
  
##  <a name="configure-dqs-to-use-reference-data-from-marketplace"></a><a name="Marketplace"></a> <span data-ttu-id="6cc6f-113">Настройка служб DQS на использование ссылочных данных из Marketplace</span><span class="sxs-lookup"><span data-stu-id="6cc6f-113">Configure DQS to Use Reference Data from Marketplace</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="6cc6f-114">[Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="6cc6f-114">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="6cc6f-115">На главном экране [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] в разделе **Администрирование**выберите команду **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-115">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, under **Administration**, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="6cc6f-116">На вкладке **Ссылочные данные** в области **Параметры сети** введите соответствующие значения в поля **Прокси-сервер** и **Порт** , если в вашей организации для подключения к Интернету используется прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-116">In the **Reference Data** tab, under the **Network Settings** area, type appropriate values in the **Proxy Server** and **Port** boxes if you or your organization uses proxy server to connect to the Internet.</span></span>  
  
4.  <span data-ttu-id="6cc6f-117">Укажите ключ учетной записи Marketplace в поле **Идентификатор учетной записи DataMarket** и щелкните значок **Проверить идентификатор учетной записи DataMarket** , чтобы проверить действительность ключа учетной записи.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-117">Specify the Marketplace account key in the **DataMarket Account ID** box, and click the **Validate DataMarket Account ID** icon to validate the account key.</span></span> <span data-ttu-id="6cc6f-118">Отображается сообщение, указывающее, действителен ли заданный ключ учетной записи Marketplace.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-118">A message appears to display whether the specified Marketplace account key is valid.</span></span>  
  
 <span data-ttu-id="6cc6f-119">Теперь можно использовать в DQS службы ссылочных данных из Marketplace, на которые подписан указанный ключ учетной записи Marketplace.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-119">You are now ready to use the reference data services from Marketplace in DQS that are subscribed for the specified Marketplace account key.</span></span>  
  
##  <a name="configure-dqs-to-use-reference-data-from-direct-online-third-party-reference-data-providers"></a><a name="ThirdParty"></a> <span data-ttu-id="6cc6f-120">Настройка служб DQS на использование ссылочных данных от сторонних поставщиков ссылочных данных в сети</span><span class="sxs-lookup"><span data-stu-id="6cc6f-120">Configure DQS to Use Reference Data from Direct Online Third-Party Reference Data Providers</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="6cc6f-121">[Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="6cc6f-121">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="6cc6f-122">На главном экране [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] в разделе **Администрирование**выберите команду **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-122">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, under **Administration**, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="6cc6f-123">На вкладке **Ссылочные данные** в области **Параметры сети** введите соответствующие значения в поля **Прокси-сервер** и **Порт** , если в вашей организации для подключения к Интернету используется прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-123">In the **Reference Data** tab, under the **Network Settings** area, type appropriate values in the **Proxy Server** and **Port** boxes if you or your organization uses proxy server to connect to the Internet.</span></span>  
  
4.  <span data-ttu-id="6cc6f-124">В области **Настройки службы ссылочных данных стороннего поставщика при непосредственном подключении по сети** щелкните значок **Добавить новый поставщик служб ссылочных данных** .</span><span class="sxs-lookup"><span data-stu-id="6cc6f-124">In the **Direct Online 3rd Party Reference Data Service Settings** area, click the **Add new reference data service provider** icon.</span></span>  
  
5.  <span data-ttu-id="6cc6f-125">В области **Создать новый сторонний поставщик службы ссылочных данных с непосредственным подключением по сети** укажите следующие данные.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-125">In the **Create New Direct Online 3rd Party Reference Data Service Provider** dialog box, specify the following details:</span></span>  
  
    1.  <span data-ttu-id="6cc6f-126">В поле **Имя** введите имя нового поставщика служб ссылочных данных с прямой ссылкой для подключения.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-126">In the **Name** box, type a name of the new direct reference data service provider.</span></span>  
  
    2.  <span data-ttu-id="6cc6f-127">(Необязательно.) В поле **Описание** введите описание нового поставщика служб ссылочных данных с прямой ссылкой для подключения.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-127">(Optional) In the **Description** box, type a description of the new direct reference data service provider.</span></span>  
  
    3.  <span data-ttu-id="6cc6f-128">В поле **Категория** введите категорию данных, предоставляемых новым поставщиком служб ссылочных данных с прямой ссылкой для подключения.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-128">In the **Category** box, type the category of the data provided by the new direct reference data service provider.</span></span>  
  
    4.  <span data-ttu-id="6cc6f-129">В поле «Схема» укажите схему, определяющую строку полей (имен столбцов), которые будут получаться от поставщика служб ссылочных данных с прямой ссылкой для подключения.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-129">In the Schema box, specify the schema that defines the string of fields (column names) to be used from the direct reference data service provider.</span></span> <span data-ttu-id="6cc6f-130">Имя поля не должно содержать пробелов, а поля должны разделяться запятыми.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-130">A field name should not contain a space, and the fields should be separated by commas.</span></span> <span data-ttu-id="6cc6f-131">Например: `FirstName, LastName, City, State`.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-131">For example: `FirstName, LastName, City, State`.</span></span>  
  
    5.  <span data-ttu-id="6cc6f-132">В поле **URI** введите URI нового поставщика служб ссылочных данных с прямой ссылкой для подключения.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-132">In the **URI** box, type the URI of the direct reference data service provider.</span></span> <span data-ttu-id="6cc6f-133">В службах DQS разрешены только безопасные идентификаторы URI (адрес начинается с "https://").</span><span class="sxs-lookup"><span data-stu-id="6cc6f-133">Only secure URIs (address starting with "https://") are allowed in DQS.</span></span>  
  
    6.  <span data-ttu-id="6cc6f-134">В поле **Максимальный размер пакета** введите максимальное число записей в пакете, отправляемом поставщику служб ссылочных данных для очистки.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-134">In the **Max Batch Size** box, type the maximum number of records per batch that will be sent to the reference data service provider for cleansing.</span></span> <span data-ttu-id="6cc6f-135">Для действия по очистке можно указать до 100 записей в пакете включительно.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-135">A maximum of 100 records per batch can be specified for the cleansing activity.</span></span>  
  
    7.  <span data-ttu-id="6cc6f-136">В поле **Идентификатор учетной записи** введите идентификатор учетной записи подписчика для поставщика служб ссылочных данных.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-136">In the **Account ID** box, type the account ID of the subscriber with the reference data service provider.</span></span>  
  
6.  <span data-ttu-id="6cc6f-137">Нажмите кнопку **ОК** , чтобы сохранить данные и закрыть диалоговое окно **Создать новый сторонний поставщик служб ссылочных данных с непосредственным подключением по сети** .</span><span class="sxs-lookup"><span data-stu-id="6cc6f-137">Click **OK** to save the data, and close the **Create New Direct Online 3rd Party Reference Data Service Provider** dialog box.</span></span> <span data-ttu-id="6cc6f-138">Новый добавленный сторонний поставщик служб ссылочных данных с непосредственным подключением по сети будет доступен в поле **Сетка поставщиков служб ссылочных данных с прямой ссылкой для подключения** в службах DQS.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-138">The newly added direct online third party reference data provider becomes available in the **Direct Reference Data Service Providers Grid** in DQS.</span></span>  
  
 <span data-ttu-id="6cc6f-139">Теперь службы ссылочных данных из настроенного стороннего поставщика служб ссылочных данных с непосредственным подключением по сети можно использовать в DQS.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-139">You are now ready to use the reference data services from the newly configured direct online third-party reference data service provider in DQS.</span></span>  
  
##  <a name="follow-up-after-configuring-dqs-to-use-reference-data"></a><a name="FollowUp"></a><span data-ttu-id="6cc6f-140">Дальнейшие действия. После настройки служб DQS для использования ссылочных данных</span><span class="sxs-lookup"><span data-stu-id="6cc6f-140">Follow Up: After Configuring DQS to use Reference Data</span></span>  
 <span data-ttu-id="6cc6f-141">Теперь необходимо сопоставить требуемые домены базы знаний со ссылочными данными, доступными в только что настроенных поставщиках данных.</span><span class="sxs-lookup"><span data-stu-id="6cc6f-141">You must now map the required knowledge base domains to the reference data available from the data providers you just configured.</span></span> <span data-ttu-id="6cc6f-142">Дополнительные сведения см. в разделе [Подключение домена или составного домена к ссылочным данным](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span><span class="sxs-lookup"><span data-stu-id="6cc6f-142">To do so, see [Attach a Domain or Composite Domain to Reference Data](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span></span>  
  
  
