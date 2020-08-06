---
title: Диспетчер подключений подписки Azure | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpsubscrconn.f1
- sql11.dts.designer.afpsubscrconn.f1
ms.assetid: e1225327-c308-4c50-8f44-c411f52ef378
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bff1286525983b32c2191f1f8864a0f2bef0e6b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664442"
---
# <a name="azure-subscription-connection-manager"></a><span data-ttu-id="7b8b1-102">Диспетчер подключений подписки Azure</span><span class="sxs-lookup"><span data-stu-id="7b8b1-102">Azure Subscription Connection Manager</span></span>
  <span data-ttu-id="7b8b1-103">Диспетчер подключений Azure HDInsight позволяет пакету служб SSIS подключаться к подписке Azure с помощью указываемых вами значений свойств: идентификатора подписки Azure и сертификата управления.</span><span class="sxs-lookup"><span data-stu-id="7b8b1-103">The Azure HDInsight connection manager enables an SSIS package to connect to an Azure subscription by using the values you specify for the properties: Azure Subscription ID and Management Certificate.</span></span>

1.  <span data-ttu-id="7b8b1-104">В диалоговом окне **Добавление диспетчера соединений со службами SSIS** выберите **Подписка Azure**и щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7b8b1-104">In the **Add SSIS Connection Manager** dialog box shown above, you select **Azure Subscription**, and click **Add**.</span></span>  <span data-ttu-id="7b8b1-105">Отобразится следующее диалоговое окно **Azure Subscription Connection Manager Editor** (Редактор диспетчера подключений подписки Azure).</span><span class="sxs-lookup"><span data-stu-id="7b8b1-105">You should see the following **Azure Subscription Connection Manager Editor** dialog box.</span></span>

     <span data-ttu-id="7b8b1-106">![SSIS-AzureSubscriptionManager](../media/ssis-azuresubscriptionmanager.png "SSIS-AzureSubscriptionManager")</span><span class="sxs-lookup"><span data-stu-id="7b8b1-106">![SSIS-AzureSubscriptionManager](../media/ssis-azuresubscriptionmanager.png "SSIS-AzureSubscriptionManager")</span></span>

2.  <span data-ttu-id="7b8b1-107">Введите уникальный идентификатор подписки Azure, который идентифицирует подписку Azure, в поле **Идентификатор подписки Azure**.</span><span class="sxs-lookup"><span data-stu-id="7b8b1-107">Enter your Azure subscription ID, which uniquely identifies an Azure subscription, for the **Azure subscription ID**.</span></span>  <span data-ttu-id="7b8b1-108">Значение можно найти на [портале управления Azure](https://manage.windowsazure.com) на странице **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="7b8b1-108">The value can be found on the [Azure Management Portal](https://manage.windowsazure.com) under **Settings** page:</span></span>

     <span data-ttu-id="7b8b1-109">![SSIS-AzureSettings-SubscriptionID](../media/ssis-azuresettings-subscriptionid.png "SSIS-AzureSettings-SubscriptionID")</span><span class="sxs-lookup"><span data-stu-id="7b8b1-109">![SSIS-AzureSettings-SubscriptionID](../media/ssis-azuresettings-subscriptionid.png "SSIS-AzureSettings-SubscriptionID")</span></span>

3.  <span data-ttu-id="7b8b1-110">В раскрывающихся списках выберите значения **Расположение хранилища сертификатов управления** и **Имя хранилища сертификатов управления** .</span><span class="sxs-lookup"><span data-stu-id="7b8b1-110">Choose **Management certificate store location** and **Management certificate store name** from the drop-down lists.</span></span>

4.  <span data-ttu-id="7b8b1-111">Введите значение **Отпечаток сертификата управления** или щелкните **Обзор…** и выберите сертификат из выбранного хранилища.</span><span class="sxs-lookup"><span data-stu-id="7b8b1-111">Enter **Management certificate thumbprint** or click the **Browse...** to choose a certificate from the selected store.</span></span> <span data-ttu-id="7b8b1-112">Сертификат должен быть передан как сертификат управления для подписки.</span><span class="sxs-lookup"><span data-stu-id="7b8b1-112">The certificate must be uploaded as a management certificate for the subscription.</span></span> <span data-ttu-id="7b8b1-113">Чтобы сделать это, нажмите кнопку **Отправить** на следующей странице портала Azure (см. эту [запись MSDN](https://msdn.microsoft.com/library/azure/gg551722.aspx) для получения дополнительных сведений).</span><span class="sxs-lookup"><span data-stu-id="7b8b1-113">To do so, click **Upload** on the following page of the Azure Portal (see this [MSDN post](https://msdn.microsoft.com/library/azure/gg551722.aspx) for more detail).</span></span>

     <span data-ttu-id="7b8b1-114">![SSIS-AzureSettings-ManagementCertificate](../media/ssis-azuresettings-managementcertificate.png "SSIS-AzureSettings-ManagementCertificate")</span><span class="sxs-lookup"><span data-stu-id="7b8b1-114">![SSIS-AzureSettings-ManagementCertificate](../media/ssis-azuresettings-managementcertificate.png "SSIS-AzureSettings-ManagementCertificate")</span></span>

5.  <span data-ttu-id="7b8b1-115">Нажмите кнопку **проверить подключение** , чтобы проверить подключение.</span><span class="sxs-lookup"><span data-stu-id="7b8b1-115">Click **Test Connection** to test the connection.</span></span>

6.  <span data-ttu-id="7b8b1-116">Чтобы закрыть диалоговое окно, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="7b8b1-116">Click **OK** to close the dialog box.</span></span>


